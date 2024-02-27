# Fix-GTk3-GTK4
Here are some of my methods to fixing GTK3 and GTK4 With VS code.

# GTK4 WITH VS-CODE

If you are using the c/c++ extension in vs code you will be required to include the following directories into your c_cpp_properties.json <strong>INSIDE OF THE INCLUDEPATH TABLE!<strong/>

<strong>FOR GTK4 ONLY! SCROLL DOWN TO SEE GTK3<strong/>

<strong>Directories: <strong/>
<pre>
"${workspaceFolder}/**",
"/usr/include/gtk-4.0/**",
"/usr/include/pango-1.0/**",
"/usr/include/gdk-pixbuf-2.0/**",
"/usr/include/cairo/**",
"/usr/include/graphene-1.0/**",
"/usr/lib64/graphene-1.0/include/**",
"/usr/include/harfbuzz/**",
"/usr/include/glib-2.0/**",
"/usr/lib64/glib-2.0/include/**",
"/usr/include/freetype2/**",
"/usr/include/blkid/**",
"/usr/include/pixman-1/**",
"/usr/include/libmount/**",
"/usr/include/fribidi/**",
"/usr/include/libxml2/**",
"/usr/include/sysprof-6/**",\
"/usr/include/libpng16/**"
</pre>
Place the directories listed above inside of the <strong>INCLUDEPATH TABLE!<strong/>

Here's a full example.

<strong>Full example: <strong/>
<pre>
  {
    "configurations": [
        {
            "name": "Linux",
            "includePath": [
                "${workspaceFolder}/**",
                "/usr/include/gtk-4.0/**",
                "/usr/include/pango-1.0/**",
                "/usr/include/gdk-pixbuf-2.0/**",
                "/usr/include/cairo/**",
                "/usr/include/graphene-1.0/**",
                "/usr/lib64/graphene-1.0/include/**",
                "/usr/include/harfbuzz/**",
                "/usr/include/glib-2.0/**",
                "/usr/lib64/glib-2.0/include/**",
                "/usr/include/freetype2/**",
                "/usr/include/blkid/**",
                "/usr/include/pixman-1/**",
                "/usr/include/libmount/**",
                "/usr/include/fribidi/**",
                "/usr/include/libxml2/**",
                "/usr/include/sysprof-6/**",
                "/usr/include/libpng16/**"
            ],
            "defines": [],
            "compilerPath": "/usr/lib64/ccache/clang",
            "cStandard": "c17",
            "cppStandard": "c++17",
            "intelliSenseMode": "linux-clang-x64"
        }
    ],
    "version": 4
}
</pre>

The code above goes inside of the <strong>c_cpp_properties.json<strong/>

# GTK3 WITH VS-CODE

<strong>FOR GTK3 ONLY! SCROLL UP TO SEE GTK4<strong/>

<strong>Directories: <strong/>
<pre>
"${workspaceFolder}/**",
"/usr/include/gtk-3.0/**",
"/usr/include/at-spi2-atk/2.0/**",
"/usr/include/at-spi-2.0/**",
"/usr/include/dbus-1.0/**",
"/usr/include/gtk-3.0/**",
"/usr/include/gio-unix-2.0/**",
"/usr/include/cairo/**",
"/usr/include/libdrm/**",
"/usr/include/pango-1.0/**",
"/usr/include/harfbuzz/**",
"/usr/include/pango-1.0/**",
"/usr/include/fribidi/**",
"/usr/include/atk-1.0/**",
"/usr/include/cairo/**",
"/usr/include/pixman-1/**",
"/usr/include/freetype2/**",
"/usr/include/libpng16/**",
"/usr/include/gdk-pixbuf-2.0/**",
"/usr/include/libmount/**",
"/usr/include/blkid/**",
"/usr/include/uuid/**",
"/usr/include/glib-2.0/**",
</pre>
Place the directories listed above inside of the <strong>INCLUDEPATH TABLE!<strong/>

Here's a full example.

<strong>Full example: <strong/>
<pre>
    {
    "configurations": [
        {
            "name": "Linux",
            "includePath": [
                "${workspaceFolder}/**",
                "/usr/include/gtk-3.0/**",
                "/usr/include/at-spi2-atk/2.0/**",
                "/usr/include/at-spi-2.0/**",
                "/usr/include/dbus-1.0/**",
                "/usr/include/gtk-3.0/**",
                "/usr/include/gio-unix-2.0/**",
                "/usr/include/cairo/**",
                "/usr/include/libdrm/**",
                "/usr/include/pango-1.0/**",
                "/usr/include/harfbuzz/**",
                "/usr/include/pango-1.0/**",
                "/usr/include/fribidi/**",
                "/usr/include/atk-1.0/**",
                "/usr/include/cairo/**",
                "/usr/include/pixman-1/**",
                "/usr/include/freetype2/**",
                "/usr/include/libpng16/**",
                "/usr/include/gdk-pixbuf-2.0/**",
                "/usr/include/libmount/**",
                "/usr/include/blkid/**",
                "/usr/include/uuid/**",
                "/usr/include/glib-2.0/**",
            ],
            "defines": [],
            "compilerPath": "/usr/lib64/ccache/clang",
            "cStandard": "c17",
            "cppStandard": "c++17",
            "intelliSenseMode": "linux-clang-x64"
        }
    ],
    "version": 4
}
</pre>

# COMPILING

I recommend using a <strong>Makefile<strong/> to compile GTK easily without any problem's with extension's. It's easier to use GCC or G++ in order to compile the C/C++ file.

Here's how to compile the C/CPP file correctly. <strong>THIS IS ONLY FOR GTK4!<strong/>

<pre>
  gcc FILENAME.c -o main $(pkg-config --libs --cflags gtk4)
</pre>

Here's how to compile the C/CPP file correctly. <strong>THIS IS ONLY FOR GTK3!<strong/>

<pre>
  gcc FILENAME.c -o main $(pkg-config --libs --cflags gtk+-3.0)
</pre>

Here's how to compile the C/CPP file correctly. <strong>THIS IS THE NORMAL WAY TO COMPILE! DOES NOT WORK WITH GTK<strong/>

<pre>
  gcc FILENAME.c -o main
</pre>

How to fix Include problems?

I recommend using the <strong>echo<strong/> command to <strong>echo<strong/> the include path directories so all you would need to do is just copy and paste them into the <strong>c_cpp_properties INSIDE THE INCLUDEPATH TABLE!<strong/>

<strong>Example for GTK4: <strong/>

<pre>
  echo $(pkg-config --libs --cflags gtk4)
</pre>

<strong>Example for GTK3: <strong/>

<pre>
  echo $(pkg-config --libs --cflags gtk+-3.0)
</pre>

Thank you for reading.

# CREDITS

Author: VeryChubbyCats
Note: Thank you for reading this. I thought I could help people figure out how to use GTK with VS Code sense to be honest people are not so great and respectful when helping other user's.
