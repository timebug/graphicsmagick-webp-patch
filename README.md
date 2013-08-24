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
wget 'https://webp.googlecode.com/files/libwebp-0.3.1.tar.gz'
tar -xzvf libwebp-0.3.1.tar.gz
cd libwebp-0.3.1
 ./configure
 make
 make install
```

Then, apply a `WebP` patch for `GM`

```
cp graphicsmagick-webp-patch/patch/gm-1.3.18-webp.patch /opt/GraphicsMagick-1.3.18/

cd /opt/GraphicsMagick-1.3.18/
patch -p1 < gm-1.3.18-webp.patch
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
