#PreviewHelper
Hook for the content menu preview entry

#Usage
- Load the script, if not already done
``` javascript
    if (typeof(codiad.PreviewHelper) == 'undefined') {
        $.getScript(this.path+"previewHelper.js");
    }
```
- Listen for amplify publication
  - Return `false` if you handeld the preview
``` javascript
    amplify.subscribe("helper.onPreview", function(path){
        //Your code
    });
```