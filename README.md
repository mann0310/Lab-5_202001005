<h3> # Lab-5_202001005
  
**Static Analysis of Python File using various tools:**

**1.passpdf.py (mypy tool)**

Code File:
<!-- <p align="center"> -->
  <a href="https://qxresearch.github.io/qxresearch-event-1">
    <img src="https://github.com/xiaowuc2/xiaowuc2/blob/master/source/qxr/cir.png" alt="Logo" width="240" height="240">
  </a>

<!-- <h3 align="center">qxresearch-event-1</h3> -->

  <p align="center">
    10 Python Application | 10 lines of code + Video Explanation 🧭
    <br />
    <br>
    <br />
  </p>
</p>


Error :


C:\Users\student\Downloads\qxresearch-event-1-master\qxresearch-event-1-master>
C:\Users\student\Downloads\qxresearch-event-1-master\qxresearch-event-1-master>mypy passpdf.py
passpdf.py:1: error: Cannot find implementation or library stub for module named "PyPDF2"  [import]
passpdf.py:1: note: See https://mypy.readthedocs.io/en/stable/running_mypy.html#missing-imports
Found 1 error in 1 file (checked 1 source file)


**2.jarvis.py (flake8 tool)**

Code File:
```python

import pyttsx3  #pip install pyttsx3
import datetime  #module
import speech_recognition as sr
import wikipedia
import smtplib
import webbrowser as wb
import os  #inbuilt
import pyautogui
import psutil  #pip install psutil
import pyjokes  # pip install pyjokes
import requests, json  #inbuilt

engine = pyttsx3.init()
engine.setProperty('rate', 190)
voices = engine.getProperty('voices')
engine.setProperty('voice', voices[1].id)
engine.setProperty('volume', 1)


#change voice
def voice_change(v):
    x = int(v)
    engine.setProperty('voice', voices[x].id)
    speak("done sir")


#speak function
def speak(audio):
    engine.say(audio)
    engine.runAndWait()


#time function
def time():
    Time = datetime.datetime.now().strftime("%H:%M:%S")
    speak("The current time is")
    speak(Time)    
```

Error:

```python
C:\Users\student\Downloads\qxresearch-event-1-master\qxresearch-event-1-master>flake8 jarvis.py
jarvis.py:1:17: E262 inline comment should start with '# '
jarvis.py:2:18: E262 inline comment should start with '# '
jarvis.py:7:12: E262 inline comment should start with '# '
jarvis.py:9:16: E262 inline comment should start with '# '
jarvis.py:11:1: F401 'json' imported but unused
jarvis.py:11:16: E401 multiple imports on one line
jarvis.py:11:24: E262 inline comment should start with '# '
jarvis.py:20:1: E265 block comment should start with '# '
jarvis.py:27:1: E265 block comment should start with '# '
jarvis.py:33:1: E265 block comment should start with '# '
jarvis.py:40:1: E265 block comment should start with '# '
jarvis.py:77:1: E265 block comment should start with '# '
jarvis.py:107:1: E265 block comment should start with '# '
jarvis.py:118:9: E265 block comment should start with '# '
jarvis.py:119:9: E265 block comment should start with '# '
jarvis.py:129:1: E265 block comment should start with '# '
jarvis.py:139:1: E265 block comment should start with '# '
jarvis.py:147:1: E265 block comment should start with '# '
jarvis.py:158:1: E265 block comment should start with '# '
jarvis.py:165:1: E265 block comment should start with '# '
jarvis.py:167:29: E261 at least two spaces before inline comment
jarvis.py:167:30: E262 inline comment should start with '# '
jarvis.py:194:80: E501 line too long (107 > 79 characters)
jarvis.py:204:9: E265 block comment should start with '# '
jarvis.py:209:1: E265 block comment should start with '# '
jarvis.py:214:1: E265 block comment should start with '# '
jarvis.py:230:1: E265 block comment should start with '# '
jarvis.py:247:1: E265 block comment should start with '# '
jarvis.py:262:80: E501 line too long (89 > 79 characters)
jarvis.py:266:1: E265 block comment should start with '# '
jarvis.py:275:1: E265 block comment should start with '# '
jarvis.py:284:1: E265 block comment should start with '# '
jarvis.py:295:1: E265 block comment should start with '# '
jarvis.py:301:1: E265 block comment should start with '# '
jarvis.py:306:1: E265 block comment should start with '# '
jarvis.py:311:1: E265 block comment should start with '# '
jarvis.py:315:1: E265 block comment should start with '# '
jarvis.py:319:1: E265 block comment should start with '# '
jarvis.py:334:80: E501 line too long (94 > 79 characters)
jarvis.py:352:1: E265 block comment should start with '# '
jarvis.py:366:1: E265 block comment should start with '# '

```
jarvis.py(mypy tool)

Code:
(same as above)

Error:
```python
C:\Users\student\Downloads\qxresearch-event-1-master\qxresearch-event-1-master>mypy jarvis.py
jarvis.py:1: error: Cannot find implementation or library stub for module named "pyttsx3"  [import]
jarvis.py:1: note: See https://mypy.readthedocs.io/en/stable/running_mypy.html#missing-imports
jarvis.py:3: error: Cannot find implementation or library stub for module named "speech_recognition"  [import]
jarvis.py:4: error: Cannot find implementation or library stub for module named "wikipedia"  [import]
jarvis.py:8: error: Library stubs not installed for "pyautogui"  [import]
jarvis.py:8: note: Hint: "python3 -m pip install types-PyAutoGUI"
jarvis.py:8: note: (or run "mypy --install-types" to install all missing stub packages)
jarvis.py:9: error: Library stubs not installed for "psutil"  [import]
jarvis.py:9: note: Hint: "python3 -m pip install types-psutil"
jarvis.py:10: error: Cannot find implementation or library stub for module named "pyjokes"  [import]
jarvis.py:11: error: Library stubs not installed for "requests"  [import]
jarvis.py:11: note: Hint: "python3 -m pip install types-requests"
Found 7 errors in 1 file (checked 1 source file)

```
<h2>Comparision : </h2>

  mypy and flake8 both are false at somewhere.
  flake8 tool also gives error of Comment thts is wrong error.
  mypy tool do not give all the correct erorrs.




3.app.my(pylint tool)

Code:
```python
import time
# from datetime import datetime as dt

# Enter the site name which you want to block
sites_to_block = [
    "www.facebook.com",
    "facebook.com",
    "www.youtube.com",
    "youtube.com",
    "www.gmail.com",
    "gmail.com",
]

# different hosts for different os
    Linux_host = "/etc/hosts"
Window_host = r"C:\Windows\System32\drivers\etc\hosts"
default_hoster = Linux_host # if you are on windows then change it to Window_host
redirect = "127.0.0.1"


    def block_websites(start_hour, end_hour):
    while True:
        if (
```        
Error:

```python
C:\Users\student\Downloads\qxresearch-event-1-master\qxresearch-event-1-master>pylint app.py
************* Module app
app.py:21:4: E0001: Parsing failed: 'unexpected indent (<unknown>, line 21)' (syntax-error)

C:\Users\student\Downloads\qxresearch-event-1-master\qxresearch-event-1-master>pylint app.py
************* Module app
app.py:15:4: E0001: Parsing failed: 'unexpected indent (<unknown>, line 15)' (syntax-error)
```  
  
