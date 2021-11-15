# kiss-tex

A repo for building texlive.

This repo contains the dependencies to build texlive, as well as add on packages.

The structure of the repo is directly stolen from Archlinux, as their sources are used
for the latex packages (texlive-latexextra, etc)

## kiss path

You will need to enable both the `extra` repo and the `texlive` repo
in order for LaTeX to build.

## repo structure

`extra` - contains needed libraries and utilities to build LaTeX; it's not strictly nessecary

`texlive` - contains LaTeX itself

**NOTE:** - texlive-* packages may not be fully functional
as they all share a build file to ease maintenance, so scripts may be missing.
If this is the case, open an issue.

## installing

First, add the kiss hook for this repo to `KISS_HOOK`:

```sh
echo KISS_HOOK="/path/to/kiss-tex/kiss-tex-hook:$KISS_HOOK" >> $HOME/.profile
```

You will then need to update freetype-harfbuzz:

```sh
kiss u # make sure freetype-harfbuzz is from kiss-tex!
kiss b freetype-harfbuzz
kiss i freetype-harfbuzz
```
Now proceed onto building texlive-bin.

```sh
kiss b texlive-bin
```

After that is finished installing, you can then move on to installing
extra packges like so:

```sh
kiss b texlive-latexextra texlive-music ...
```

