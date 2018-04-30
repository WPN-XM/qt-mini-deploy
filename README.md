### Qt Minimal Deployment Kits for Windows (deprecated)

These are dynamic Mingw builds, build without ICU (Unicode) dependencies.
If your application doesn't depend on Unicode features, you might simply drop these dependencies.

- v5.1.1, build without ICU (Unicode) dependencies. 
  - You don't have to ship the following files anymore: 
  - icudt51.dll (22Mb), icuin51.dll (3.5Mb), icuuc51.dll (2Mb). This saves 27.5 MB.
- v5.2.2
- v5.4.0

http://doc.qt.io/qt-5/windows-deployment.html

**Configure**

```
configure.bat -release -opensource -confirm-license -platform win32-g++ -prefix $QtDir
              -qt-zlib -qt-pcre -qt-libpng -qt-libjpeg -qt-freetype -opengl desktop
              -qt-sql-sqlite -no-openssl -no-icu -no-iconv -no-angle -no-rtti -no-dbus 
              -make libs -nomake tools -nomake examples -nomake tests -opengl desktop
              -strip -plugin-sql-sqlite

mingw32-make --quiet --jobs=N
```

**Build Script for static version of Qt for Windows.**

Qt Wiki: http://qt-project.org/wiki/How-to-build-a-static-Qt-for-Windows-MinGW

If you want to build Qt static, then you might use this Powershell build script.

https://gist.github.com/jakoch/ebab7ff300e76257a1bd
