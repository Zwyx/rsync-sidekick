# rsync-sidekick

`rsync` is a fantastic tool. Yet, by itself, it's a pain to use for repeated backing up of media files (videos, music,
photos, etc.) _that are reorganized frequently_.

`rsync-sidekick` is a simple tool that is designed to be run **before** `rsync` is run. This propagates following
changes from _source directory_ to _destination directory_ (or any combination of below):

1. Changes to file modified timestamp
2. Rename of a file
3. Moving a file from one directory to another

Using `rsync-sidekick` before `rsrync` makes the backup process significantly faster than using only `rsync` (sometimes
even 100x faster if the only changes at source directory are above 3)

`rsync` options such as `--detect-renamed`, `--detect-renamed-lax`, `--detect-moved` and `--fuzzy` don't work reliably
and sometimes are dangerous! `rsync-sidekick` is reliable alternative to all these options and much more. 