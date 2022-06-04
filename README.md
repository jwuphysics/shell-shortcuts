# Shell Shortcuts
Shell shortcuts that I probably should have memorized.

These should work for `bash` and `fish`


## Find small image files
```
find . -name "*.jpg" -type f -size -64c
```
Note that `-size -64c` means size less than 64 bytes. You could do `-size +1k` to find files above 1 kb.

## Multiple downloads from file

Assume that `url_list.txt` is formatted like:
```
image1.jpg https://some.path/to/image1.jpg
image2.jpg https://some.path/to/image2.jpg
```

Then download 8 files at a time with `wget` using.
```
xargs < ./url_list.txt -P 8 -L 1 wget -q --no-clobber -O
```
