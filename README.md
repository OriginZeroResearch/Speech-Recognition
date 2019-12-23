# Speech-Recognition
Speech Recognition - Audio File to Text
This script can be used to translate .Wav files to text.

Two considerations:
(1) Speech recognition does not work on low volume
(2) It is not sophisticated enough to distinguish users - you would have to use an ANN for that.

To start:
you must make sure that you have Speech Recognition installed
Open your terminal and type install speechrecognition
In your IDE, install Speech Recognition as an interpreter

CODE:


import speech_recognition as sr

from os import path
AUDIO_FILE = path.join(path.dirname(path.realpath(__file__)), "TestFile.wav")

r = sr.Recognizer()
with sr.AudioFile(AUDIO_FILE) as source:
    audio = r.listen(source)

    try:
        text = r.recognize_google(audio)
        print(text)

    except:
        print('Sorry...run again')
