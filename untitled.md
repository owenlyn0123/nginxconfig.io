# How to get the Confidence of a processed barcode

{% tabs %}
{% tab title="C" %}
```c
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
printf("Barcode Confidence : %d \r", pResult->results[iIndex]->results[0]->confidence);
DBR_FreeTextResults(&pResult);
DBR_DestroyInstance(hBarcode);
```
{% endtab %}

{% tab title="C++" %}
```cpp
TextResultArray* paryResult = NULL;
CBarcodeReader reader;
reader.InitLicense("put your license key here");
reader.DecodeFile("put your image file full path here", "");
reader.GetAllTextResults(&paryResult);
printf("%d total barcodes found. \r\n", paryResult->resultsCount);
for (int iIndex = 0; iIndex < paryResult->resultsCount; iIndex++)
{
printf("Result %d\r\n", iIndex + 1);
printf("Barcode Confidence : %d \r", paryResult->results[iIndex]->results[0]->confidence);
CBarcodeReader::FreeTextResults(&paryResult);
```
{% endtab %}
{% endtabs %}



