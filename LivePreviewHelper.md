#LivePreviewHelper
Implement a live preview in your plugin

#Usage
- Load the script, if not already done
  - Initialise the code with the path of the directory which contains the source file
``` javascript
    if (typeof(codiad.LivePreviewHelper) == 'undefined') {
        $.getScript(this.path+"LivePreviewHelper.js",function(){
            codiad.LivePreviewHelper.init(_this.path);
        });
    }
```
- Listen for amplify publications
  - Use on `onLivePreviewInit` to register your extensions
  - Use on `onStartLivePreview` and `onChangeLivePreview` to render your preview
    - Return `false` if you handeld the preview
``` javascript
    amplify.subscribe('helper.onStartLivePreview', function(path){
        //Your code
    });
    amplify.subscribe('helper.onChangeLivePreview', function(event){
        //Your code
    });
    amplify.subscribe('helper.onLivePreviewInit', function(event){
        codiad.LivePreviewHelper.registerExtension([YOUR EXTENSIONS]);
    });
```
- Update the preview in the iframe
``` javascript
    codiad.LivePreviewHelper.updateContent(content);
```