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
(they all share a build file to ease maintenance),
if this is the case, open an issue.

## installing

You will first need to build and install graphite-harfbuzz:

```sh
kiss b graphite-harfbuzz
kiss i graphite-harfbuzz
```

Swap to graphite-harfbuzz using kiss-alternative

```sh
kiss a | grep graphite-harfbuzz | kiss a -
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

