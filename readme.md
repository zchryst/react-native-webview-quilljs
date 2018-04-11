# React Native Webview Quilljs
## Quill.js editor and viewer components with no native code for React Native apps built using [Expo](https://expo.io/).

[![npm](https://img.shields.io/npm/v/react-native-webview-quilljs.svg)](https://www.npmjs.com/package/react-native-webview-quilljs)
[![npm](https://img.shields.io/npm/dm/react-native-webview-quilljs.svg)](https://www.npmjs.com/package/react-native-webview-quilljs)
[![npm](https://img.shields.io/npm/dt/react-native-webview-quilljs.svg)](https://www.npmjs.com/package/react-native-webview-quilljs)
[![npm](https://img.shields.io/npm/l/react-native-webview-quilljs.svg)](https://github.com/react-native-component/react-native-webview-quilljs/blob/master/LICENSE)


![Image](https://thumbs.gfycat.com/CelebratedSilentDromedary-size_restricted.gif)

## Try it in Expo
![QR Code](https://github.com/reggie3/react-native-webview-quilljs/blob/master/expo-qr-code.png)


[Link to Expo Project Page](https://expo.io/@reggie3/react-native-webview-quilljs)

## New Beta Version With Full Offline Support Now Available
The new beta does not require downloading any files during program launch to make it work.  All Editor and Viewer JavaScript files are bundled with the package.  
install it by using:
~~~
npm install --save react-native-webview-quilljs@beta
~~~
or 
~~~
yarn add react-native-webview-quilljs@beta
~~~

The code for the beta is in the inline-javascript-3 branch.
NOTE: Barring any unforeseen circumstances, I will be merging the beta and publishing it by 7 April, 2018.

## Installation
~~~
npm install --save react-native-webview-quilljs
~~~
or 
~~~
yarn add react-native-webview-quilljs
~~~

and then
~~~
import {WebViewQuillEditor, WebViewQuillViewer} from 'react-native-webview-quilljs'
~~~

## Usage
This package can be used to create both an editor and a viewer

Creating a Quill.js editor with the standard toolbar:
~~~~
 <WebViewQuillEditor
    ref={component => (this.webViewQuillEditor = component)}
    getDeltaCallback={this.getDeltaCallback}
    contentToDisplay={contentToDisplay}
    onLoad={this.onLoadCallback}
  />
~~~~

This component accepts the following props:


| Name                   | Required      | Description |
| ---------------------- | ------------- | ----------- |
| ref            |    yes        | A reference to the editor componment to be used to retrieve its contents using     this.webViewQuillEditor.getDelta();
| getDeltaCallback  |    no        | Function called in response to a call to this.webViewQuillEditor.getDelta().  It will receive a Delta object containing the contents of editor |
| contentToDisplay     |    no        | A Delta object that will be displayed by the editor when it mounts|
| onLoad | no| A function called when the Editor finishes loading |
| onDeltaChangeCallback | no | Function called when the contents of Quill editor have changed.  The function receives a delta containing the new contents, the old contents, and source as described in the Quill.js API [documentation](https://quilljs.com/docs/api/events.html) |
| backgroundColor| no | String that equates to a valid CSS color value that the background of the editor will be set to|
|getEditorCallback| no | A function that will receive the Quill.js editor as an arguement |


Creating a Delta viewer that can display content created with Quill.js:
~~~
<WebViewQuillViewer
    ref={component => (this.webViewQuillViewer = component)}
    contentToDisplay={this.state.messageDelta}
    onLoad={this.onLoadCallback}
  />
~~~

This component accepts the following props:

| Name                   | Required      | Description |
| ---------------------- | ------------- | ----------- |
| ref            |    yes        | A reference to the editor componment to be used to update its contents using     this.webViewQuillViewer.sendContentToViewer(delta);
| contentToDisplay     |    no        | A Delta object that will be displayed by the viewer when it mounts|
|onLoad | no| A function called when the Editor finishes loading |
| backgroundColor| no | String that equates to a valid CSS color value that the background of the viewer will be set to|
|getViewerCallback| no | A function that will receive the Quill.js viewer as an arguement |

## Changelog
### 0.6.5
* Added initial testing framework
### 0.6.0
* Removed requirement to download JavaScript files from GitHub in order for the package to work.  JavaScript files are now inline with the HTML which enables the package to work without an Internet connection.
* Added getViewerCallback and getEditorCallback
### 0.4.4
* Changed HTTP path for files to be downloaded in preparation for potential inline JS bundling or Expo Packager bundling of files.
### 0.4.0
* Added "backgroundColor" props for both the WebViewQuillViewer and WebViewQuillEditor
### 0.3.20
* Added copy and paste of HTML
### 0.3.10
* Revert file access features from 0.3.0.
### 0.3.0
* Library no longer relies on accessing WebView files from the Internet.  All files needed by both the Editor and Viewer are included with the packages.
* Fonts display correctly on iOS devices
### 0.2.5
* Added onDeltaChangeCallback property to Editor

## LICENSE

MIT
