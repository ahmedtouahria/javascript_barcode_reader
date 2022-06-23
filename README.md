**Simple Barcode Scanner ** with `javascript` and `html`
how to read barcodes using a USB barcode scanner device in JavaScript.
**its easy !**
```javascript
var barcode ="";
var interval;
```
and create simple body 
```html
        <h1>Simple Barcode Scanner</h1>
        <strong>Last scanned barcode: </strong>
        <div id="last-barcode"></div>
```
thene create a simple function to read barcode 
```javascript
   document.addEventListener('keydown', function(evt) {
   if (interval) clearInterval(interval);
  if (evt.code == 'Enter') {
    if (barcode)
     handleBarcode(barcode);
     barcode = '';
      return;
                }
    if (evt.key != 'Shift') barcode += evt.key;
      interval = setInterval(() => barcode = '', 20);
            });
```
and display in body 
```javascript
function handleBarcode(scanned_barcode) {
document.querySelector('#last-barcode').innerHTML = scanned_barcode;
            }
```
