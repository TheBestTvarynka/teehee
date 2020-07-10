# Teehee - a modal terminal hex editor

Inspired by Vim, Kakoune and Hiew.

## Motivation

Reverse engineers, software engineers and other IT people often need to work with binary files. Hex editors display are often the go-to tool for dealing with binary file formats when a more specialized tool isn't available. Many of the existing hex editors lack support for modal editing, which Vim/Kakoune/Emacs users will miss. Hiew supports it to an extent, but it's non-free software, and its keybinds are unintuitive. Teehee is designed to provide a native-feeling experience to Kakoune and Vim users, while also providing additional hex editing capabilities like coloured marks for regions of data and encryption/compression scripts.

## Screenshot (more coming later)

![image](https://user-images.githubusercontent.com/6651822/87162527-bab99f00-c2ce-11ea-9aa5-02f81dddc0de.png)

Teehee supports multiple selections.

## Design

![image](https://user-images.githubusercontent.com/6651822/87162730-010efe00-c2cf-11ea-8a0e-f90fbd209cec.png)

## Implement keybinds:
* `hjkl` for movement (press shift to extend selection instead)
```
    ^
< h j l >
    k
    v
```
* `g`[`hjkl`] for jumping (`G`[`hjkl`] to extend selection instead)
    * `h`: to line start
    * `l`: to line end
    * `k`: to file start
    * `j`: to file end
* `;` to collapse selections to cursors
* `<a-;>` (alt and ;) to swap cursor and selection end
* `<a-s>` (alt and s) to split selection to multiple selections of size...
    * `b`: 1 Byte
    * `w`: 2 bytes (Word)
    * `d`: 4 bytes (Dword)
    * `q`: 8 bytes (Qword)
    * `o`: 16 bytes (Oword)
* `d` to delete selected data from buffer
