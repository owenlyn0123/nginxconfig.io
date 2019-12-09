---
description: 'Windows, C/C+, TroubleShooting, License'
---

# Error Message About Your License

_For users who use_ [_Dynamsoft Barcode Reader SDK_](https://www.dynamsoft.com/Products/Dynamic-Barcode-Reader.aspx)_\(C/C++\), errors may occurred unepected during license initialization phrase. In this article, we will give some solutions if you have met following Sympton_

## Sympton

_Value: 12345\*. XXX barcode license invalid, please contact support@dynamsoft.com to get a valid trial license._

## Solutions

If you are using trail version, it indicates your license has expired. You could contact our [Customer Service](https://www.dynamsoft.com/Company/Contact.aspx) for help.

If you are using full version, please check the error code in order to troubleshoot the issue. Below is the code snippet shows how to get the error code& error message:

```cpp
int iRet = -1;

CBarcodeReader reader;

iRet = reader.InitLicenseFromServer("", "licenseKey1;licenseKey2");

if (iRet != DBR_OK)
{
    printf("Error code: %d. Error message: %s\n", iRet, CBarcodeReader::GetErrorString(iRet));
    return -1;
}
```

## Error Code Lists

Error Code:  -10044

Error Message: Failed to request the license content

Solution: Double check your network condition, ensure you can connect to the Internet.



Error Code: -10054

Error Message: The device number in the license key runs out

Solution: Contact [Customer Service](https://www.dynamsoft.com/Company/Contact.aspx) for help



Error Code: -10004

Error Message: The license has expired

Solution: Contact [Customer Service](https://www.dynamsoft.com/Company/Contact.aspx) for help



Error Code: -10042

Error Message: The license DLL is missing

Solution:  For 8 digits development key, we use License DLL to verify the License. The DLLs can be found in  `[INSTALLATION FOLDER]\Components\C_C++\Redist\`

* For any OS using X86 instruction, copy "DynamsoftLicClientx86.dll" from `[INSTALLATION FOLDER]\Components\C_C++\Redist\x86\` to the same folder as the EXE file.
* For any OS using X64 instruction, copy "DynamsoftLicClientx64.dll" from `[INSTALLATION FOLDER]\Components\C_C++\Redist\x64\` to the same folder as the EXE file.



Error Code: -10052

Error Message: The license content is invalid

Solution: For users who use  `InitLicenseFromLicenseContent()` API to register the license , please verify the generated content, and recheck the order of the parameters.

 If this article doesn't help resolve the license issue, please contact [Customer Service](https://www.dynamsoft.com/Company/Contact.aspx) for further assistance.

