#!/usr/bin/env bash
# Use ~media's copy of `beet` to import music.
# See ~media/.config/beets/config.yaml for import settings

# pretend we are ~media
export HOME="/home/media"

# activate the virtualenv so we have access to `beet`
source "$HOME/.virtualenvs/beets/bin/activate"

# then import the musics
echo "Beet: Importing $@"
beet import -q "$@"
