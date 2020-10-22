# tip
- [히스토리가 없으면 창닫기](https://stackoverflow.com/questions/3588315/how-to-check-if-the-user-can-go-back-in-browser-history-or-not/16580022#16580022)
  ```
  function goBackOrClose() {  

    window.history.back();
    window.close(); 

    //or if you are not interested in closing the window, do something else here
    //e.g. 
    theBrowserCantGoBack();

  }
  ```
