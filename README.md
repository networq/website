Networq website
===============

This repository contains the content for www.networq.io

It is managed using Couscous. Check [couscous.io](https://couscous.io) to learn how to use it.

## Local preview:

    $ couscous preview

You can now point your browser to http://localhost:8000 to preview the site. It gets updated automatically everytime you change a file.

## Build

    $ couscous generate

This generates the static HTML version of this site in `.couscous/generated`

## Deploy

    $ couscous deploy

This builds the static website, commits it to the `gh-pages` branch, and pushes it to github.

You should be able to see the latest updats on https://networq.github.io/website/

## Proxy

In order to use a custom domain-name with SSL, there's a proxy that forwards requests from https://www.networq.io to https://networq.github.io/website/

