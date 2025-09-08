# Validate data

How to validate that data has not been corrupted or tampered with, after a system compromission or ransomware decryption.

* Validation environment should be segmented both from Internet and from regular/recovery network
* Data restoration and validation - "dirty" backup/data
  * format check. easier if data is categorized. (regular expression, binary data, html/xml/js code, ccn luhn check...)
  * AV scan
  * services functional tests
  * manual check
  * per business decision compared to other options (start from fresh, known good backup)

Your insurance, IR retainer or partners may be able to recommend third-party to help but usually those services will be very costly and can't provide a full warranty of integrity.

## Resources

* [Dangerzone](https://dangerzone.rocks/about/) - open pdf, office or images, inspired from Qubes TrustedPDF
