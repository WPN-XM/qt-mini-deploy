### Qt Minimal Deployment Kits for Windows

- v5.1.1, build without ICU (Unicode) dependencies. 
  - You don't have to ship the following files anymore: 
  - icudt51.dll (22Mb), icuin51.dll (3.5Mb), icuuc51.dll (2Mb). This saves 27.5 MB.
- v5.2.2, build without ICU

**Build Script**

https://gist.github.com/jakoch/ebab7ff300e76257a1bd

**Configure**

```
configure -opensource -confirm-license -platform win32-g++ -make libs
		  -qt-libjpeg -q t-libpng -no-openssl -no-icu -qt-zlib -qt-pcre -no-iconv
		  -nomake examples -nomake tests -no-angle -opengl desktop -no-rtti -no-dbus
		  -strip -plugin-sql-sqlite
```
