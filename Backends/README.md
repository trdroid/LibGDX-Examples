# LibGDX Backends

LibGDX provides cross-platform support for the applications by interfacing with *backends* specific to each platform. 

A call to one of the platform-independent methods of LibGDX gets routed to the corresponding platform's backend.

*Examples*

A few of the platform-independent calls to LibGDX includes requests to 

* place an image at a specific location on the screen
* play an audio file at a specified volume
* save to a file or read from a file

LibGDX provdes the following backends

|Platform   | Backend  |
|---|---|---|---|---|
|  Android |  Android SDK |
|  iOS | RoboVM  |
|  Web Browser | WebGL  |
|  Desktop | Lightweight Java Game Library (LWJGL)  |



