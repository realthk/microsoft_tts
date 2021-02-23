# Microsoft Text-to-Speech (TTS)
The original MS TTS cannot change parameters like gender and type dynamically, as it pays no attention to the option parameter.

This component passes over optional 
- gender
- type
- rate
- volume
- pitch
- contour

parameters.

### Install
Clone this repo under ```custom_components```

eg.
```
cd [HA PATH]/custom_components
git clone https://github.com/realthk/microsoft_tts.git
```
and restart Home Assistant


### Sample call:

```
  action:
    - service: tts.microsoft_say
      data:
        entity_id: media_player.mpd
        message: teszt2
        options: 
          gender: Female
          type: NoemiNeural
```

Where ```gender``` is **Male** or **Female**, ```type``` is "Voice name" without the language prefix from [Microsoft's documentation](https://docs.microsoft.com/en-us/azure/cognitive-services/speech-service/language-support#text-to-speech), eg. **TamasNeural**