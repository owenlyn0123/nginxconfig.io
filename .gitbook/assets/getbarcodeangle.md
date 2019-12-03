# How to get the angle of the barcodes

Dynamsoft Barcode Reader SDK is able to detect barcodes at all angles. The SDK is also able to return the angles of the barcodes decoded. The result is stored in the struct `LocalizationResult`. The following code snippet shows how to get the rotation/skew angles of the barcodes decoded by the SDK.

{% codetabs name="C", type="c" -%}
void *hBarcode = NULL;
int iIndex = 0;
TextResultArray* pResult = NULL;
hBarcode = DBR_CreateInstance();
DBR_InitLicense(hBarcode,"put your license here");
DBR_DecodeFile(hBarcode, "put your file path here", "");
DBR_GetAllTextResults(hBarcode, &pResult);
for (iIndex = 0; iIndex < pResult->resultsCount; iIndex++)
{
printf("Result %d\n", iIndex + 1);
printf("Barcode angle:$d \n", pResult->results[iIndex]->localizationResult->angle);
}
DBR_FreeTextResults(&pResult);
DBR_DestroyInstance(hBarcode);

{%- language name="C++", type="cpp" -%}

TextResultArray* paryResult = NULL;
CBarcodeReader reader;
reader.InitLicense("put your license key here");
reader.DecodeFile("put your image file full path here", "");
reader.GetAllTextResults(&paryResult);
printf("%d total barcodes found. \r\n", paryResult->resultsCount);
for (int iIndex = 0; iIndex < paryResult->resultsCount; iIndex++)
{
printf("Result %d\r\n", iIndex + 1);
printf("Barcode Angle:%d \n", paryResult->results[iIndex]->localizationResult->angle);
}
CBarcodeReader::FreeTextResults(&paryResult);
{%- language name="C#", type="csharp" -%}
BarcodeReader dbr = new BarcodeReader();
PublicRuntimeSettings runtimeSettings = dbr.GetRuntimeSettings();
dbr.ProductKeys = "Put your license key here";
TextResult[] aryResult = dbr.DecodeFile("Put your file path here", "");
for (var i = 0; i < aryResult.Length; i++)
{
Console.WriteLine("Barcode: {0}", (i + 1));
Console.WriteLine("Barcode Angle: {0}", aryResult[i].LocalizationResult.Angle);
}
{%- language name="Java", type="java" -%}
BarcodeReader dbr = new BarcodeReader("put your license here");
TextResult[] results = dbr.decodeFile("put your file path here", "");
String output = "";
for(int i =0; i<result.length;i++){
output += "Barcode Angle: ";
output += result[i].localizationResult.angle + "\n\n";                  
}
System.out.println(output);
{%- endcodetabs %}

## Angles for different barcodes

The following illustrations will show how the angle is calculated for different barcode types. 

1. OneD barcode

 <img src="../Images/1D_Angle.png" width="750" height="154"/>

2. QR 

 <img src="../Images/QR_Angle.png" width="550" height="154"/>

3. Data Matrix

 <img src="../Images/DM_Angle.png" width="550" height="154"/>

4. Aztec

 <img src="../Images/Aztec_Angle.png" width="600" height="170"/>

5. Maxicode

 <img src="../Images/Maxicode_Angle.png" width="750" height="193"/>