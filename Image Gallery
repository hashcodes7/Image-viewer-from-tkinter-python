from tkinter import *
import os
from PIL import ImageTk,Image
root = Tk()
back=ImageTk.PhotoImage(Image.open('backward.png').resize((30,30)))
forw=ImageTk.PhotoImage(Image.open('forward.png').resize((30,30)))
included_extensions = ['jpg','jpeg', 'bmp', 'png', 'gif']
imagelist = [fn for fn in os.listdir('.')
              if any(fn.endswith(ext) for ext in included_extensions)]
current=0
my_img = ImageTk.PhotoImage(Image.open(imagelist[current]).resize((500,300)))
mylabel = Label(image=my_img)
mylabel.grid(row=1, columnspan=10)
current = 0
statelabel = Label(text=current)
statelabel.grid(row=0, columnspan=10)
def forwardfun():
    global my_img
    global current
    btnbackward = Button(root, state=NORMAL, image=back, width=20, height=20, command=backwardfun).grid(row=2, column=4)
    current = current + 1
    statelabel = Label(text=current)
    statelabel.grid(row=0, columnspan=10)
    my_img = ImageTk.PhotoImage(Image.open(imagelist[current]).resize((500, 300)))
    mylabel = Label(image=my_img)
    mylabel.grid(row=1, columnspan=10)
    if current==len(imagelist)-1:
        btnforward = Button(root, image=forw,state=DISABLED, width=20, height=20, command=forwardfun).grid(row=2, column=5)

def backwardfun():
    global my_img
    global current
    current = current - 1
    btnforward = Button(root, image=forw, state=NORMAL, width=20, height=20, command=forwardfun).grid(row=2, column=5)
    btnbackward = Button(root, image=back, width=20, height=20, command=backwardfun).grid(row=2, column=4)

    statelabel = Label(text=current)
    statelabel.grid(row=0, columnspan=10)
    my_img = ImageTk.PhotoImage(Image.open(imagelist[current]).resize((500, 300)))
    mylabel = Label(image=my_img)
    mylabel.grid(row=1, columnspan=10)
    if current==0:
        btnbackward=Button(root,image=back,state=DISABLED,width=20,height=20,command=backwardfun).grid(row=2,column=4)

btnforward=Button(root,image=forw,width=20,height=20,command=forwardfun).grid(row=2,column=5)
btnbackward=Button(root,image=back,state=DISABLED,width=20,height=20,command=backwardfun).grid(row=2,column=4)

root.mainloop()
