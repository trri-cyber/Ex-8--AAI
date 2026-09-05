
<H3>NAME :  RISHAB P DOSHI  </H3>
<H3>REGISTER NO. 212224240134</H3>
<H3>EX. NO.8</H3>
<H3>DATE : 05/09/2026</H3>
<H1 ALIGN =CENTER>Implementation of Speech Recognition</H1>
<H3>Aim:</H3> 
 To implement the conversion of live speech to text.<BR>
<h3>Algorithm:</h3>
Step 1: Import the speech_recognition library<Br>
Step 2: Initialize the Recognizer<Br>
Step 3: Create an instance of the Recognizer class, which will be used for recognizing speech.<Br>
Step 4: Set the duration for audio capture<Br>
Step 5: Define a variable to specify the duration (in seconds) for which the program will capture audio from the microphone.<Br>
Step 6: Display a message in the console to prompt the user to speak.<Br>
Step 7: Capture audio from the default microphone<Br>
Step 9: Use the default microphone as the audio source.<Br>
Step 10: Record audio for the specified duration using the Recognizer instance.<Br>
Step 11: Perform speech recognition with exceptional handling:<Br>
•	Attempt to recognize speech from the captured audio using the Google Speech Recognition service.<Br>
•	If successful, print the recognized text.<Br>
•	Handle specific exceptions: If the recognition result is unknown or if there is an issue with the request to the Google Speech Recognition service, print corresponding error messages.<Br>
•	A generic exception block captures any other unexpected errors.<Br>
<H3>Program:</H3>

```python
!pip install speechrecognition
!apt-get install -y portaudio19-dev
!pip install PyAudio

import speech_recognition as sr

# Create a Recognizer object
r = sr.Recognizer()

# Replace 'your_audio_file.wav' with the name of your uploaded audio file
# You can also specify the full path if it's in a subfolder, e.g., 'my_folder/my_audio.wav'
audio_file_path = 'split.wav'

try:
    with sr.AudioFile(audio_file_path) as source:
        print(f"Processing audio from {audio_file_path}...")
        audio_data = r.record(source)  # Read the entire audio file
        
    text = r.recognize_google(audio_data)
    print("You said:", text)

except FileNotFoundError:
    print(f"Error: Audio file '{audio_file_path}' not found. Make sure you've uploaded it correctly.")
except sr.UnknownValueError:
    print("Sorry, could not understand the audio.")
except sr.RequestError as e:
    print(f"Error with the request to Google Speech Recognition service: {e}")
except Exception as e:
    print(f"An unexpected error occurred: {e}")

```

<H3> Output:</H3>

<img width="1370" height="88" alt="image" src="https://github.com/user-attachments/assets/605b6922-04a5-4595-a609-9c9376880fcc" />

<H3> Result:</H3>

Thus, The implementation of speech recognition is executed successfully.
