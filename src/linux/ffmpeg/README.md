# FFMPEG

## Convert video to high quality gif:

```
ffmpeg -i input.mkv -vf "fps=30,scale=-1:-1:flags=lanczos,split[s0][s1];[s0]palettegen[p];[s1][p]paletteuse" -loop -1 output.gif
```

Where
- `fps` is Frames per second
- `scale` is dimentions of output, can be like `scale=320:-1` or `scale=320:480`
- `split` filter will allow everything to be done in one command and avoids having to create a temporary PNG file of the palette.
- `palettegen` and `paletteuse` filters will generate and use a custom palette generated from your input.
- Control looping with -loop output option but the values are confusing. A value of 0 is infinite looping, -1 is no looping, and 1 will loop once meaning it will play twice. So a value of 10 will cause the GIF to play 11 times