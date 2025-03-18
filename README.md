# custom-html-integrate-with-google-sites

- First create custom html
- create a google sheet
- go to app script
- create a function like :-
  
    function doPost(e) {
    var sheet = SpreadsheetApp.openById("10SmgfJ35S0jMPpl0lI47Z05VkKatDYV65WGDcHVmksw").getActiveSheet();
    var data = e.parameter;
  
    sheet.appendRow([
      new Date(),
      data.name,
      data.email,
      data.address,
      data.phone,
      data.comments || "" // Handle optional comments
    ]);
  
    return ContentService.createTextOutput("Success").setMimeType(ContentService.MimeType.TEXT);
  }

- do new deployment with web app and share with "anyone"
- copy web url from management deployment
- paste in form action and use methid post
