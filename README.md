# Lego keyboard layout

This keyboard layout has the useful traits of US International without its
inconvenient dead keys.

The standard Estonian layout is not suitable for coding because common
characters such as `{ } [ ] < >` require AltGr and many characters are in
uncomfortable positions. US International makes it possible to write Estonian
characters such as `õ ä ö ü`, but uses dead keys for common punctuation.
Lego combines the US layout used for coding with Estonian letters on AltGr.

## Windows

The Windows MSKLC source is [`lego1.klc`](lego1.klc). Installable releases are
available from <https://github.com/leg0/lego-keyboard/releases>.

## Linux/XKB (Sway)

The XKB symbols definition is [`xkb/symbols/lego`](xkb/symbols/lego). It uses
Right Alt as AltGr and reproduces the normal, Shift, AltGr, and Shift+AltGr
levels from the Windows layout.

Install it for the current user:

```sh
mkdir -p ~/.config/xkb/symbols
cp xkb/symbols/lego ~/.config/xkb/symbols/lego
```

Test it immediately in Sway:

```sh
swaymsg 'input type:keyboard xkb_variant ""; input type:keyboard xkb_layout lego'
```

To enable it persistently, add this to the Sway configuration:

```text
input type:keyboard {
    xkb_layout lego
    xkb_variant ""
}
```

Then reload Sway with `swaymsg reload`.
