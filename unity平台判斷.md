# unity平台判斷

\#【OCOE筆記】 unity平台判斷(整理中)

Example:

```
#if UNITY_EDITOR 
Debug.Log("unity editor test");  
#endif  

#if UNITY_ANDROID  
Debug.Log("這裡是安卓平台");  
#endif  

#if UNITY_STANDALONE_WIN  
Debug.Log("我是從Windows執行的");  
#endif  
```

| 名稱                       | 描寫敘述                                                                                                                         |
| ------------------------ | ---------------------------------------------------------------------------------------------------------------------------- |
| UNITY\_EDITOR            | Define for calling Unity Editor scripts from your game code.                                                                 |
| UNITY\_STANDALONE\_OSX   | Platform define for compiling/executing code specifically for Mac OS (This includes Universal, PPC and Intel architectures). |
| UNITY\_DASHBOARD\_WIDGET | Platform define when creating code for Mac OS dashboard widgets.                                                             |
| UNITY\_STANDALONE\_WIN   | Use this when you want to compile/execute code for Windows stand alone applications.                                         |
| UNITY\_STANDALONE\_LINUX | Use this when you want to compile/execute code for Linux stand alone applications.                                           |
| UNITY\_STANDALONE        | Use this to compile/execute code for any standalone platform (Mac, Windows or Linux).                                        |
| UNITY\_WEBPLAYER         | Platform define for web player content (this includes Windows and Mac Web player executables).                               |
| UNITY\_WII               | Platform define for compiling/executing code for the Wii console.                                                            |
| UNITY\_IPHONE            | Platform define for compiling/executing code for the iPhone platform.                                                        |
| UNITY\_ANDROID           | Platform define for the Android platform.                                                                                    |
| UNITY\_PS3               | Platform define for running PlayStation 3 code.                                                                              |
| UNITY\_XBOX360           | Platform define for executing Xbox 360 code.                                                                                 |
| UNITY\_NACL              | Platform define when compiling code for Google native client (this will be set additionally to UNITY\_WEBPLAYER).            |
| UNITY\_FLASH             | Platform define when compiling code for Adobe Flash.                                                                         |
