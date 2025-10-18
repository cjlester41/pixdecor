# pixdecor


A highly configurable decorator plugin for wayfire, pixdecor features antialiased rounded corners with shadows and optional animated effects.

## Installing

Set `--prefix` to the same as the wayfire installation.

```
$ meson setup build --prefix=/usr
$ ninja -C build
# ninja -C build install
```

Restart wayfire.

## Running

Disable other decorator plugins and enable pixdecor plugin in core section of `wayfire.ini`.
