# Speech-Recognition: .Wav File to Text
Speech Recognition: .Wav File to Text <br>
<br>
Two considerations:<br>
(1) Speech recognition does not work on low volume<br>
(2) It is not sophisticated enough to distinguish users (you would have to use an Artificial Neural Network for that)<br>

To start:<br>
In your IDE:<br>
(1) Open your terminal and type: install speechrecognition<br>
(2) Install SpeechRecognition as an interpreter<br>
<br>
CODE:


    import speech_recognition as sr
    
    # .wav file must be in the same folder as your script
    from os import path
    # call your .Wav file 
    AUDIO_FILE = path.join(path.dirname(path.realpath(__file__)), "YourFileName.wav")

    r = sr.Recognizer()
    with sr.AudioFile(AUDIO_FILE) as source:
        audio = r.listen(source)

        try:
            text = r.recognize_google(audio)
            print(text)
