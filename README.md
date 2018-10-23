# Prank-amos
List of pranks that you can do to your office mates 😁

## The Hasslehof

Print as many copies as necessary to cover every inch of the coworkers desk space.
Don't forget to change their wallpaper:

![](https://i.ebayimg.com/images/g/diAAAOSw3xJVeLlb/s-l1600.jpg)

If you don't have that much time, you always have the mandatory crontab opening the browser in any of the following videos:

* [David Hasselhoff - True Survivor (from Kung Fury)][1]
* [David Hasselhoff - Hooked on a feeling][2]
* [David Hasselhodd - Jump in my car][3]

[1]: https://www.youtube.com/watch?v=ZTidn2dBYbY
[2]: https://www.youtube.com/watch?v=PJQVlVHsFF8
[3]: https://www.youtube.com/watch?v=dm7jEA3frY4

```bash
crontab -e
```

```bash
0  11  *  *  * bash ~/.list_videos.sh
```

```bash
#!/usr/bin/env bash

# this is the ~/.list_videos.sh file

VIDEOS=("https://www.youtube.com/watch?v=ZTidn2dBYbY" "https://www.youtube.com/watch?v=PJQVlVHsFF8" "https://www.youtube.com/watch?v=dm7jEA3frY4")

size=${#VIDEOS[@]}
index=$(($RANDOM % $size))

open "${VIDEOS[$index]}"
```
