- 👋 Hi, I’m @chaitanya -aka software and system Engineer 😛
- 🌱 I’m using Python 🐍 for Automation. I would love 💞️ to collaborate on Python 🐍 automation projects and Automotive 🚗 related projects

### [click here](https://www.linkedin.com/in/chaitu-ycr/) 👈 to connect 🤝 with me on LinkedIn <br>

### My Active GitHub opensource Projects:
- [py_canoe](https://github.com/chaitu-ycr/py_canoe)

## Python Q & A
### 1. create simple gui using 'PySimpleGUI' library 👇
```python
import PySimpleGUI as sg
layout = [  [sg.Text('Some text on Row 1')],
            [sg.Text('Enter something on Row 2'), sg.InputText()],
            [sg.Button('Ok'), sg.Button('Cancel')] ]
            
window = sg.Window('Window Title', layout)

while True:
    event, values = window.read()
    if event == sg.WIN_CLOSED or event == 'Cancel': # if user closes window or clicks cancel
        break
    print('You entered ', values[0])

window.close()
```

<!---
chaitu-ycr/chaitu-ycr is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
### [click here](https://www.linkedin.com/in/chaitu-ycr/) 👈 to connect 🤝 with me on LinkedIn <br>
