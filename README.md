# horizontal-bar-chart
## Add this code in the google sheet apps script 

```
  if (e.parameter.method == "horizontal") { 
    var sheet = SpreadsheetApp.getActiveSpreadsheet().getSheetByName("horizontal-bar-chart");
    var data = sheet.getDataRange().getValues();
    Logger.log(JSON.stringify(data));
    return ContentService
      .createTextOutput(e.parameter.callback + "(" + JSON.stringify(data) + ")")
      .setMimeType(ContentService.MimeType.JAVASCRIPT);
  }
```