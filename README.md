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

  ## Add this in the HTML page where you embed the form
  ```
<p>
  <iframe frameborder="0" id="line-graph" scrolling="no" src="URL-OF-THE-FORM" width="100%"></iframe>
</p>
<script src="/bt_files/2021/form/iframeResizer.min.js"></script>
<script>
  iFrameResize({ log: true }, '#line-graph')
</script>