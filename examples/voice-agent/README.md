# Voice Agent
This is an example of use of the command functionality of whisper.cpp to allow control of the multimedia of your computer using your voice.
This program should only works on Linux and Windows for now. It was tested on Windows 10 and Ubuntu 22.04.
## Run
To run the program, execute the following commands:
```bash
# Run with default arguments and small model on Linux
./build/bin/voice-agent -m ./models/ggml-base.en.bin -cmd ./examples/voice-agent/commands.txt -ac 768 -t 3 -c 1

# Run with default arguments and small model on Windows
.\build\bin\Release\voice-agent.exe -m ./models/ggml-base.en.bin -cmd ./examples/voice-agent/commands.txt -ac 768 -t 3 -c 1
```

To control the multimedia, you then just need to say one of the following words: play, next, previous, more, less, mute, exit. Each word has a different function:
- **play**: Pause or Play the current media
- **next**: Put the next track
- **previous**: Put the previous track
- **more**: Increase the volume
- **less**: Decrease the volume
- **mute**: Mute the sound
- **exit**: Quit the program

If too many commands are activated by mistake or if it is too hard to activate them, I recommend adjusting the threshold with the parameter `-cth`. The default value is 0.8.

## Editing words
The words used can be modified by editing the [commands.txt](/examples/voice-agent/commands.txt) file in examples/voice-agent. The order of the words are important, the first one will always be used to pause, the second one to put the next music...

I has some difficulties with using multiple words. I recommand using one word for each command and words that are pronounced differently to reduce the possible errors.

## Building
To build this example, it requires having SDL2 library installed.
```bash
#On Linux
sudo apt-get install libsdl2-dev
```
To install the library on windows, it requires a few extra steps. 
I recommend following the following post: https://github.com/ggerganov/whisper.cpp/issues/2053#issuecomment-2116536324.

