
### win x64 in win10 (vc++ 2019)
```
vcbuild.bat dll 
```
```
# run 'Visual C++ 2019 x64 Native Build Tools Command Prompt'
cl toby.cpp /c /MD /EHsc  -I../node/deps/v8/include -I../node/deps/uv/include  -I../node/src
cl example.cpp /c /MD /EHsc
link example.obj toby.obj /LIBPATH:../node/out/Release /LIBPATH:../node/out/Release/lib node.lib v8_libplatform.lib v8_libbase.lib WINMM.LIB dbghelp.lib  shlwapi.lib


# debug
cl toby.cpp /c /MDd /DEBUG /EHsc  -I../node/deps/v8/include -I../node/deps/uv/include  -I../node/src && cl example.cpp /c /MDd /D /EHsc && link example.obj toby.obj /LIBPATH:../node/Debug /LIBPATH:../node/build/Debug/lib node.lib v8_libplatform.lib v8_libbase.lib WINMM.LIB dbghelp.lib  shlwapi.lib

```




 https://github.com/nodejs/node/issues/28845
