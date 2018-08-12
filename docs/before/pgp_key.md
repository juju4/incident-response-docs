PGP/GPG key management

## Usage

For confidential email, PGP/GPG is the standard way to communicate in a protected manner.
It is the standard for CERT/CSIRT community.

## Ownership

Who has private key and passphrase?
It will depend on your organization. In some case, it would be the whole team, in others, just part of it.

## Creation

If possible, use an offline system and or a livecd like Tails.
Ensure that ~/.gnupg/gpg.conf is configured appropriately and RNG-tools or similar is installed to have enough entropy.

Create master key for certifying and authenticate, subkeys for signing and encryption.

Template file gen-key-script
```
%echo Generating a basic OpenPGP key
Key-Type: RSA
Key-Length: 4096
Key-Usage: cert,auth
Subkey-Type: RSA
Subkey-Length: 4096
Subkey-Usage: sign
Name-Real: My Company Security Team
Name-Email: security@mycompany.com
Expire-Date: 3y
Passphrase: Example-Passphrase-To-Be-Changed
%pubring /path/to/security.pub
%commit
%echo done
```

Create master key and signing subkey
```
$ gpg --batch --gen-key /path/to/gen-key-script
```

Add encryption subkey
```
$ gpg --edit-key security@mycompany.com
gpg> addkey
Your selection? 6 [RSA]
What keysize do you want? (3072) 4096
Key is valid for? (0) 2y
Is this correct? (y/N) y
Really create? (y/N) y
gpg> save
```
or
```
$ gpg --quick-addkey "<FINGERPRINT>" rsa4096 encr 2y
```

Check
```
$ gpg --import /path/to/security.pub
$ gpg --list-keys
$ gpg --list-secret-keys
```

Export master key and subkeys
```
$ gpg -a --export-secret-key security@mycompany.com > gpg-secret-masterkey.asc
$ gpg -a --export-secret-subkeys security@mycompany.com > gpg-secret-subkeys.asc
$ gpg --delete-secret-key 0x000MASTERKEY
$ gpg --import gpg-secret-subkeys.gpg
$ gpg -a --export security@mycompany.com > gpg-public-subkeys.asc
$ gpg --keyserver pgp.mit.edu --send-key [your subkey ID]
$ gpg --keyserver hkps.pool.sks-keyservers.net --send-key [your subkey ID]
```
Note that delete-secret-key step is selective on recent gnupg. In that case, you may not need to import secret-subkeys.

Secret master key should be archived.
Subkeys and passphrase should be stored in appropriate vault of team password manager.

Note: for individual, it's recommend to use a hardware token like yubikey or smartcard. For team, not manageable.

## Rotation

```
$ gpg --default-key old_key --sign-key new_key
$ gpg --default-key new_key --sign-key old_key
$ gpg --keyserver pgp.mit.edu --send-key old_key new_key
```

## Revokation

It's advised to pre-generated in advance the revocation certificate for key compromise case.
If it's part of normal key rotation (superseded), generate it with reference to new key.

```
$ gpg -a --gen-revoke key > key-revocation-file
$ gpg --import key-revocation-file
$ gpg --send-key key
```


## Archive

Master private key and revocation file should be archived both in electronic format (cd/dvd/tape) and paper format (armor) in an appropriate safebox and backup location, all offline.

## References

* [Unattended key generation, GnuPG Documentation](https://www.gnupg.org/documentation/manuals/gnupg/Unattended-GPG-key-generation.html)
* [Creating a new GPG key, Debian project](http://keyring.debian.org/creating-key.html)
* [Subkeys, Debian project](https://wiki.debian.org/subkeys)
* [Operational PGP, grugq](https://gist.github.com/grugq/03167bed45e774551155)
* [OpenPGP Best Practices, Riseup](https://help.riseup.net/en/security/message-security/openpgp/best-practices)
* [PGP and SSH keys on a Yubikey NEO, Jan 2015](https://www.esev.com/blog/post/2015-01-pgp-ssh-key-on-yubikey-neo/)
* [GnuPG, Caff and Docker, Mar 2015](http://www.barkingiguana.com/2015/03/02/gnupg-caff-and-docker-for-great-justice/)
* [Protecting your private master key in GnuPG 2.1 and later, 2015](https://rudd-o.com/linux-and-free-software/protecting-your-private-master-key-in-gnupg-2-1-and-later)
* [GPG: Strong Keys, Rotation, and Keybase, Nov 2016](https://sungo.wtf/2016/11/23/gpg-strong-keys-rotation-and-keybase.html)
* [I'm giving up on PGP, Dec 2016](https://blog.filippo.io/giving-up-on-long-term-pgp/)
* [Giving Up on PGP, Dec 2016](https://www.schneier.com/blog/archives/2016/12/giving_up_on_pg.html)
* [Configuring YubiKey for GPG and U2F, Apr 2017](https://research.kudelskisecurity.com/2017/04/28/configuring-yubikey-for-gpg-and-u2f/)
* [Configuring an offline GnuPG master key and subkeys on YubiKey, Sep 2017](https://www.andreagrandi.it/2017/09/30/configuring-offline-gnupg-masterkey-subkeys-on-yubikey/)
* [OpenPGP - The almost perfect key pair, Oct 2017](https://blog.eleven-labs.com/en/openpgp-almost-perfect-key-pair-part-1/)

gpg.conf
```
personal-cipher-preferences AES256 TWOFISH AES192
personal-digest-preferences SHA512 SHA384 SHA256
cipher-algo AES256
digest-algo SHA512
cert-digest-algo SHA512
default-preference-list SHA512 SHA384 SHA256 SHA224 AES256 AES192 AES CAST5 ZLIB BZIP2 ZIP TWOFISH
compress-algo ZLIB
disable-cipher-algo 3DES
charset utf8
utf8-strings
fixed-list-mode
keyid-format 0xlong
with-fingerprint
verify-options show-uid-validity
list-options show-uid-validity
fixed-list-mode
no-emit-version
no-comments
export-options export-minimal
s2k-cipher-algo AES256
s2k-digest-algo SHA512
s2k-mode 3
s2k-count 65011712
```
