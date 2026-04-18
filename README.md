# ZX Spectrum Nerd Font

## History

This is based on a fork of [zx-spectrum-unicode-font](https://github.com/jfsebastian/zx-spectrum-unicode-font) by Jorge Ferrer
García, which is in turn based on the wonderful job made by Darko Stanicic with his original Spectrum True Type Font (released as
"healthware"), still available in a number of places (for example, [World of Spectrum](https://worldofspectrum.net/utilities/)).

Jorge had the idea to improve and complete this font from a personal project he started a few years ago (and the willing to learn).
He realized that some of the glyphs' shape was reversed and had been drawn with intersections which seems to be problematic
sometimes, so he completely redrew each glyph with no intersections, and also added some more unicode characters.

His objective was create a way to let people to complete and improve the work if they find it interesting. In his words: "I'm not
an expert in fonts and obviously not a designer. I hope that the font is simple enough to be able to understand the glyph/font
processes."

As he's an open source enthusiast, he worked with [FontForge](https://fontforge.github.io) both GUI and Python library.

I haven't yet found a need to add any glyphs, but I found this wonderful project when I was looking for a ZX Spectrum font to use
in my terminal for that authentic retro experience, but these days that means it needs to be a [Nerd Font](https://www.nerdfonts.com/)!

## How to Build

### Prerequisites

To build the font, you'll need the following:

- [FontForge](https://fontforge.github.io)
- Python
- [The Nerd Fonts FontPatcher](https://github.com/ryanoasis/nerd-fonts/releases/latest/download/FontPatcher.zip)

You can try to build it on Windows, but given the tools required Linux or MacOS is probably the better / easier option.

### Building the base font

1. Clone the repository:

```sh
git clone https://github.com/wibblemonkey/ZXSpectrumUnicodeNerdFont.git
```

2. Change into the `scripts` directory and execute the `createFont.py` script:

```sh
cd scripts
fontforge --script=createFont.py
```

### Patching to a Nerd Font

1. Download [the latest version of the Nerd Fonts Font Patcher tool](https://github.com/ryanoasis/nerd-fonts/releases/latest/download/FontPatcher.zip) and unzip into to the `scripts` directory.

```sh
wget https://github.com/ryanoasis/nerd-fonts/releases/latest/download/FontPatcher.zip
unzip FontPatcher.zip
```

2. Patch the font using the font-patcher script, _e.g._

```sh
fontforge --script ./font-patcher --careful --complete --has-no-italic --mono --name "ZX Spectrum Unicode NF" --outputdir ../build ../build/ZXSpectrumUnicode.ttf
```

You can see all the options supported by the patcher by executing the following command:

```sh
fontforge --script ./font-patcher --help
```
