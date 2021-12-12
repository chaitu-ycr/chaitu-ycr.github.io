- 👋 Hi, I’m @chaitanya-ycr -aka software and system tester 😛
- 🌱 I’m using Python 🐍 for Automation. I would love 💞️ to collaborate on Python 🐍 automation projects and Automotive 🚗 related projects

### Want to connect 🤝 me on [linkedIn click here](https://www.linkedin.com/in/chaitanya-ycr/) 👈<br>

## Python Q & A
### 1. swapping two numbers 👇
```python
a, b = 11, 22
print(f'values before swapping a={a}, b={b}')
a, b = b, a
print(f'values after swapping a={a}, b={b}')
```
### 2. create simple gui using 'PySimpleGUI' library
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
chaitanya-ycr/chaitanya-ycr is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
