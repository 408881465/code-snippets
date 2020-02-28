- [using-javascript-mqtt-client-websockets](http://www.steves-internet-guide.com/using-javascript-mqtt-client-websockets/)
- [submitting html form without reload the page](https://www.codexpedia.com/javascript/submitting-html-form-without-reload-the-page/)
- [簡單理解 JavaScript Async 和 Await](https://www.oxxostudio.tw/articles/201908/js-async-await.html)
- [sort-array-of-objects-by-string-property-value](https://stackoverflow.com/questions/979256/sorting-an-array-of-objects-by-property-values)
- [Declaring JavaScript global variable within function](https://www.javatpoint.com/javascript-global-variable)

#### Scripts
- [how-can-i-export-a-directory-structure-in-windows](https://superuser.com/questions/258287/how-can-i-export-a-directory-structure-in-windows)
``` shell
tree /A /f ["directory path"] > tree.txt
``` 
- [open-powershell-window-here-context-menu-add-windows-10](https://www.tenforums.com/tutorials/60175-open-powershell-window-here-context-menu-add-windows-10-a.html)

### Javascript ES6 sort a array
```JavaScript
var homes = [
    {
        "h_id": "3",
        "city": "Dallas",
        "state": "TX",
        "zip": "75201",
        "price": "162500"
    }, {
        "h_id": "4",
        "city": "Bevery Hills",
        "state": "CA",
        "zip": "90210",
        "price": "319250"
    }, {
        "h_id": "5",
        "city": "New York",
        "state": "NY",
        "zip": "00010",
        "price": "962500"
    }
];
//根据数组数值降序排列数组
homes.sort((a, b) => parseFloat(b.price) - parseFloat(a.price));
```
