# Files Module

The files module can be accessed using 

* The *Gdx.getFiles()* method (or)
* The *Gdx.files* variable

### Getting Handles

**Internal Files**

Internal files are files relative to 

* *assets* folder on Android and WebGL platforms
* *root* folder on Desktops

The file handle for an internal file can be obtained using the method

* *Gdx.files.internal()* 

**External Files**

External files are relative to

* SD card on Android
* Unavailable on WebGL platform
* User's home directory on Desktops

The file handle for an internal file can be obtained using the method

* *Gdx.files.external()* 

