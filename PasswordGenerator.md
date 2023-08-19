import random
import string
import PySimpleGUI as ja
ja.theme('black')
ja.set_options(font='Roman''20')

layout=[
    [ja.Text('Uppercase:'),ja.Push(),ja.Input(size=20,key='-UP-')],
    [ja.Text('Lowercase:'),ja.Push(),ja.Input(size=20,key='-LOW-')],
    [ja.Text('Numbers:'),ja.Push(),ja.Input(size=20,key='-NUM-')],
    [ja.Text('Symbols:'),ja.Push(),ja.Input(size=20,key='-SYM-')],
    [ja.Button('Run'),ja.Button('Cancel')],
    [ja.Text('Password'),ja.Push(),ja.Multiline(size=20,no_scrollbar=True,disabled=True,key='-PASS-')]


]

Window=ja.Window('Password Generator',layout)

while True:
    event, values= Window.read()
    if event == 'Cancel' or event==ja.WIN_CLOSED:
        break

    if event == 'Run':
        try:
            u_upper=int(values['-UP-'])
            upper=random.sample(string.ascii_uppercase,u_upper)
            l_lower=int(values['-LOW-'])
            lower=random.sample(string.ascii_lowercase,l_lower)
            n_umber=int(values['-NUM-'])            
            number=random.sample(string.digits,n_umber)            
            s_ymbol=int(values['-SYM-'])
            symbol=random.sample(string.punctuation,s_ymbol)

            total=upper+lower+number+symbol
            total=random.sample(total,len(total))
            total=''.join(total)
            Window['-PASS-'].update(total)
        except ValueError:
            Window['-PASS-'].update("Enter valid Data")


Window.close()             



# Codesoft_Python
This repository is of the Internship Training from The codsoft. The tasks which get completed are uploaded here In this Repository.
