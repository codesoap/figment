`figment` is a shell script which takes two audio files as arguments,
plays a random one repeatedly and let's you guess which one had the
better audio quality each time. After exiting with CTRL-C it will show
you how many times you were right.

This could help you decide how strongly you want to compress your music
library or similar.

You'll need `mpv` to use the script.

# Example
```console
$ ffmpeg -ss 00:45 -t 5 -i 07.Run_With_The_Wolves.flac -c:a libopus -b:a 96k good.opus
$ ffmpeg -ss 00:45 -t 5 -i 07.Run_With_The_Wolves.flac -c:a libopus -b:a 64k bad.opus
$ figment good.opus bad.opus
Was this [g]ood or [b]ad? g
Was this [g]ood or [b]ad? g
Was this [g]ood or [b]ad? b
Was this [g]ood or [b]ad? b
Was this [g]ood or [b]ad? b
Was this [g]ood or [b]ad? b
Was this [g]ood or [b]ad? g
^C
You were correct 3 out of 7 times (43%).
```
