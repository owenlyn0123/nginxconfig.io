---
description: C/C++
---

# Error Code and Message for Development License Initialization

## Symptoms

_For users who use Dynamsoft Barcode Reader SDK\(C/C++\), errors occurred unepected during license initialization phrase. We will give some solutions if you have met following Error Messages:_

**InitLicenseFromServer**

1. No Internet Connection: Initial license under offline scenario.\(Error Message: Failed to request the license content; Error Code: -10044 \)
2. Run out of quota: No available quota for new development.\(Error Message: The device number in the license key runs out; Error Code: -10054 \)
3. License expired: Current License key comes to an end of its expires.\(Error Message: The license has expired; Error Code: -10004 \)
4. Barcode License invalid: Current License doesn't include specific barcode type or Current License contain the specific barcode type, whereas you still got an error.\(Error Message: Failed to read barcode: The xxx License is invalid \)
5. Unproperly choose License DLL version: Using wrong instruction DLL for current OS.\(Error Message: The License DLL is missing; Error Code: -10042 \)

**InitLicenseFromLicenseContent**

1. Wrong License content: Parameters Reverse or Incorrect content.\(Error Message: The license content is invalid; Error Code: -10052\)

##  Solutions

_If it is the first time you run the code, we suggest you use `GetErrorString` method to have a better understanding when an error occurred._ 

**InitLicenseFromServer**

1. Check Internet connection, try to reconnect to the Internet. We also have offline solutions, but you still need to connect to the Internet at least one time for license check.
2. Contact our [Customer Service](https://www.dynamsoft.com/Company/Contact.aspx) for further requirements.
3. Contact our [Customer Service](https://www.dynamsoft.com/Company/Contact.aspx) for further requirements.
4. If your license doesn't include the specific barcode, please contact our [Customer Service](https://www.dynamsoft.com/Company/Contact.aspx). Otherwise, please refer to solution 5.
5. For 8 digits development key, we use License DLL to verify the License. The DLLs can be found in  `[INSTALLATION FOLDER]\Components\C_C++\Redist\`

* For any OS using X86 instruction, copy "DynamsoftLicClientx86.dll" from `[INSTALLATION FOLDER]\Components\C_C++\Redist\x86\` to the same folder as the EXE file.
* For any OS using X64 instruction, copy "DynamsoftLicClientx64.dll" from `[INSTALLATION FOLDER]\Components\C_C++\Redist\x64\` to the same folder as the EXE file.

**InitLicenseFromLicenseContent**

1. For users who use offline license initialization, please verify the generated content, and recheck the order of the parameters.

`InitLicenseFromLicenseContent(const char*`_`pLicenseKey, const char*`_ `pLicenseContent)`

_If this article doesn't help resolve the license issue, please contact_ [_**Dynamsoft support team**_](http://www.dynamsoft.com/Company/Contact.aspx) _for further assistance._



