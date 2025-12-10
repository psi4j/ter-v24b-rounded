# ter-v24b-rounded

Terminus console font (v24b) patched with rounded box-drawing corners for Linux TTY/console.

## Why?

Standard Linux console fonts generally don't include the Unicode "arc" box-drawing characters (`╮ ╭ ╯ ╰`). Applications using rounded corners fall back to `+` characters, which looks ugly.

This font patches the Terminus v24b font to:

1. Draw rounded corners on the box-drawing glyphs
2. Map rounded corner Unicode codepoints (U+256D-2570) to these glyphs

## Installation

### AUR (Arch Linux)

```bash
paru -S ter-v24b-rounded
# or
yay -S ter-v24b-rounded
```

### Manual

```bash
sudo cp ter-v24b-rounded.psf.gz /usr/share/kbd/consolefonts/
echo "FONT=ter-v24b-rounded" | sudo tee /etc/vconsole.conf
sudo systemctl restart systemd-vconsole-setup
```

## Usage

After installation, set in `/etc/vconsole.conf`:

```
FONT=ter-v24b-rounded
```

Reboot or run:

```bash
sudo systemctl restart systemd-vconsole-setup
```

## Compatibility

Works great with:

- tuigreet (greetd greeter)
- yazi (terminal file manager)
- btop
- Any TUI app using box-drawing characters

## License

Based on Terminus Font, licensed under OFL (SIL Open Font License).
