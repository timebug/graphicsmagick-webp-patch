# A WebP patch for GraphicsMagick

```
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%                                                                             %
%                                                                             %
%                                                                             %
%                         W   W  EEEEE  BBBB   PPPP                           %
%                         W   W  E      B   B  P   P                          %
%                         W W W  EEE    BBBB   PPPP                           %
%                         WW WW  E      B   B  P                              %
%                         W   W  EEEEE  BBBB   P                              %
%                                                                             %
%                                                                             %
%                     Read/Write Google WEBP Image Format.                    %
%                                                                             %
%                                                                             %
%                              Software Design                                %
%                                John Cristy                                  %
%                                 March 2011                                  %
%                                  TIMEBUG                                    %
%                                January 2013                                 %
%                                                                             %
%                                                                             %
%                                                                             %
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%
```

# Installation

First, you need Build & Install [libwebp](https://code.google.com/p/webp/downloads/list)

```
wget 'https://webp.googlecode.com/files/libwebp-0.2.1.tar.gz'
tar -xzvf libwebp-0.2.1.tar.gz
cd libwebp-0.2.1
 ./configure
 make
 make install
```

Then, apply a `WebP` patch for `GM`

```
cp graphicsmagick-webp-patch/src/coders/webp.c /opt/GraphicsMagick-1.3.17/coders/
cp graphicsmagick-webp-patch/src/patch/GraphicsMagick-1.3.17-WebP-autotools.patch /opt/GraphicsMagick-1.3.17/

cd /opt/GraphicsMagick-1.3.17/
patch -p1 < GraphicsMagick-1.3.17-WebP-autotools.patch
```

Now, you can Build & Install `GM` just like before

```
./configure --enable-shared
make
make install
```

```
WEBP  --with-webp=yes  yes
```

# Example

```
gm convert foo.jpg bar.webp
gm identify bar.webp
```

# Licence

```
Copyright (C) 2003, 2007 GraphicsMagick Group
Copyright (C) 2002 ImageMagick Studio
Copyright 1991-1999 E. I. du Pont de Nemours and Company

This program is covered by multiple licenses, which are described in
Copyright.txt. You should have received a copy of Copyright.txt with this
package; otherwise see http://www.graphicsmagick.org/www/Copyright.html.
```

# Links

* https://developers.google.com/speed/webp/
* http://www.graphicsmagick.org/