- š Hi, Iām @chaitanya -aka software and system tester š
- š± Iām using Python š for Automation. I would love šļø to collaborate on Python š automation projects and Automotive š related projects

### Want to connect š¤ me on [linkedIn click here](https://www.linkedin.com/in/chaitu-ycr/) š<br>

## Python Q & A
### 1. swapping two numbers š
```python
a, b = 11, 22
print(f'values before swapping a={a}, b={b}')
a, b = b, a
print(f'values after swapping a={a}, b={b}')
```
### 2. create simple gui using 'PySimpleGUI' library š
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
chaitanya-ycr/chaitanya-ycr is a āØ special āØ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
### Want to connect š¤ me on [linkedIn click here](https://www.linkedin.com/in/chaitu-ycr/) š<br>
