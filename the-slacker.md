# The Slacker

![](http://botoes.co/assets/imgs/face-renato.png)
![](https://www.hipaajournal.com/wp-content/uploads/2017/11/slack.jpg)

Replace the notification sound from Slack with a random clip from Renato Alexandre.
This might need a restart from Slack to actually work


```bash
#!/usr/bin/env bash

# We need to find slack
slack="$(osascript -e 'tell application "System Events" to POSIX path of (file of process "Slack" as alias)' 2> /dev/null)"
renato=(
  "http://renato.botoes.co/assets/sounds/000017.mp3?v=1",
  "http://renato.botoes.co/assets/sounds/000016.mp3?v=1",
  "http://renato.botoes.co/assets/sounds/000015.mp3?v=1",
  "http://renato.botoes.co/assets/sounds/000014.mp3?v=1",
  "http://renato.botoes.co/assets/sounds/000013.mp3?v=1",
  "http://renato.botoes.co/assets/sounds/000012.mp3?v=1",
  "http://renato.botoes.co/assets/sounds/000011.mp3?v=1",
  "http://renato.botoes.co/assets/sounds/000010.mp3?v=1",
  "http://renato.botoes.co/assets/sounds/000009.mp3?v=1",
  "http://renato.botoes.co/assets/sounds/000008.mp3?v=1",
  "http://renato.botoes.co/assets/sounds/000007.mp3?v=1",
  "http://renato.botoes.co/assets/sounds/000006.mp3?v=1",
  "http://renato.botoes.co/assets/sounds/000005.mp3?v=1",
  "http://renato.botoes.co/assets/sounds/000004.mp3?v=1",
  "http://renato.botoes.co/assets/sounds/000003.mp3?v=1",
  "http://renato.botoes.co/assets/sounds/000002.mp3?v=1",
  "http://renato.botoes.co/assets/sounds/000001.mp3?v=1"
)
notification_file="${slack}/Contents/Resources/knock_brush.mp3"

size=${#renato[@]}
index=$(($RANDOM % $size))
temp_file=$(mktemp)
curl -Ls "${renato[$index]}" > ${temp_file}
cp ${temp_file} ${notification_file}
```
