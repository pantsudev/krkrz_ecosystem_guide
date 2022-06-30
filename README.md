A short guide, or rather reference, to the Krkr2/KrkrZ ecosystem for the western reverser.

# Systems

## KRKR2 / KiriKiri2
KRKR2 aka KiriKiri2 is a game engine that executes its own TJS script language, syntax-wise somewhat similar to JavaScript.  
It was created and developed by W.Dee as a rewrite of their original KiriKiri engine.  
KRKR2 has been thoroughly outdated for well over a decade, and no sane person would make new games with it.  
- KRKR2 Source tree: https://github.com/krkrz/krkr2/tree/master/kirikiri2/trunk (Time-frozen/Read-only copy)

## KRKRZ / KiriKiriZ
KRKRZ however is a more modern fork of KRKR2 and is still widely used and supported.  
KRKRZ features a (separate) backwards compatibility layer for Krkr2 called k2compat.  
This document in general will refer and link to KRKRZ versions of plugins etc, where available.
- KRKRZ Source tree: https://github.com/krkrz/krkrz
- KRKRZ Docs: http://krkrz.github.io/documents/

## KAG3
KAG3, short for "Kirikiri Adventure Game", is a VN scene and UI building system written by W.Dee in TJS for Krkr2/KrkrZ.  
KAG3 runs .ks files and is the base system on top of which almost all KiriKiri VNs are built.
- KAG3 Docs: http://kirikirikag.sourceforge.net/contents/index.html
- KAG3 Source for KrkrZ: https://github.com/krkrz/kag3

## KAGEX
KAGEX is an extension of KAG3 by sakano/Naoya Komatsu.  
It mostly adds new graphical processing functions for Layers.  
Some developers use KAGEX, some don't, whereas KAG3 itself is practically ubiquitous.
- KAGEX Docs: https://biscrat.com/krkr/docs/kagex/contents/
- KAGEX Book: https://github.com/sakano/krkr_archives/raw/master/doc/kagex_book/KagexBook.pdf

# Glossary
- TJS: The script language executed by the KiriKiri engines. Similar to JavaScript, but unique.  
File extension is `.tjs`, but the file itself can be either a plaintext script that is compiled on the fly by the engine,  
or it can be a precompiled binary file which contains just the assembled TJS virtual machine instructions.  
Apart from basic string constant replacements, there are no reliable or convenient ways to edit compiled TJS script.  
Disassemblers let you see what the TJS script does, but the disassembly cannot be parsed back into runnable TJS.  
A decompiler can be found within the Furikiri project and run from the command line via the Girigiri interface, but it
only works for simple and short TJS files. In general the success rate for decompilation of TJS files found in the wild is about 20%.
- KAG: The visual novel/adventure game system that takes care of basic UI and UX, layered rendering and game state  
machinery for the game developer's convenience. KAG is written entirely in TJS, and is itself a processor for KS (KAG Script) files.  
KAG Script is a simple tag-based language, and a whole game can be written in KS alone. Often, however, developers will use  
additional systems for ease of rapid development on top of KAG, which relegates the KS scripts to mostly serve the configuration/UI  
base role. One such example is the SCN scene format and parser by M2 Co. Ltd.
- AMV: A custom video file format which features an alpha channel, implemented by the freeware plugin AlphaMovie.dll.
- SCN: TLDW
- PSB: TLDW
- TLG:

# Plugins
A major part of the KiriKiri engines' success is their extremely comprehensive support for plug-in DLLs.  
A massive number of plugins exist for the engine, and are used to implement anything from clipboard support  
to additional renderers, custom audio mixing and interactive cat girls. This is a very lacking list of  
some plugins by their filename, for which I've been able (and cared enough) to identify a source.
- [AlphaMovie.dll](http://kaede-software.com/krlm/plugin/alphamovie.zip): Free but not open source. Implements movie files which have an alpha channel.  
These files have the `.amv` extension. Encoder and playback via http://kaede-software.com/krlm/plugin/alphamovie.zip,  
Decoding/dumping via https://github.com/xmoeproject/AlphaMovieDecoder
- extNagano.dll: Free but not open source. Used to be available at http://ymtkyk.sakura.ne.jp/krkr.STG/plugin/extNagano.html,  
but I haven't found a copy of the archive. It is used to implement numerous layer transition effects.
- extrans.dll
- [getSample.dll](https://github.com/wtnbgo/getSample): Used for reading sample data from WaveSoundBuffer, usually for mouth movement.
- k2compat.dll
- kagexopt.dll
- [KAGParserEx.dll](https://github.com/wtnbgo/KAGParserEx): This is an extended replacement for the original KAGParser.
- krmovie.dll
- [layerExDraw.dll](https://github.com/wtnbgo/layerExDraw): Implements support for drawing onto Layers with GDI+.
- lzfs.dll: Kirikiri LZ4fs Plugin. No source found.
- [menu.dll](https://github.com/krkrz/menu): Implements `Window.menu` to enable Win32 window menu bars.
- PackinOne.dll
- pkutil.dll
- psbfile.dll: TLDW
- psd.dll: Possibly https://github.com/wtnbgo/psdfile
- textrender.dll
- [win32dialog.dll](https://github.com/wtnbgo/win32dialog): For displaying native Win32 dialog boxes.
- [win32ole.dll](https://github.com/wtnbgo/win32ole): Allows calling into Win32 OLE/ActiveX components.
- [windowEx.dll](https://github.com/wtnbgo/windowEx): Extends the TJS Window class with some events and multi-monitor stuff.  
Mostly used to implement window resizing with a fixed 16:9 aspect ratio.
- [wuopus.dll](https://github.com/krkrz/wuopus): Adds support for [Opus](https://opus-codec.org/) audio file playback.
- [wuvorbis.dll](https://github.com/krkrz/wuvorbis): Adds support for [Ogg/Vorbis](https://xiph.org/vorbis/) audio file playback.
