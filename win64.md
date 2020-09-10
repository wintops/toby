
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




v8_base_without_compiler.lib;IPHLPAPI.LIB ;PSAPI.LIB;WINMM.LIB;dbghelp.lib;shlwapi.lib;SHELL32.LIB;USER32.LIB;USERENV.LIB;WS2_32.LIB;V8_LIBPLATFORM.LIB;ICUI18N.LIB;ZLIB.LIB;CARES.LIB;LIBUV.LIB;V8_LIBBASE.LIB;ICUUCX.LIB;ICUDATA.LIB;V8_SNAPSHOT.LIB;v8_zlib.lib;v8_init.lib;v8_initializers.lib;v8_compiler.lib;v8_libsampler.lib;
