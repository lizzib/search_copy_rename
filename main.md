# search_copy_rename
#####Import####
import pyinstaller
import tkinter
from tkinter import *
import shutil
import os,sys
    
tk = Tk()
var = StringVar()
serial = StringVar()
entry = StringVar()
label = Label( tk, textvariable=var, relief=RAISED )

var.set("Enter the serial number:",)#What you want the prompt to be
label.pack() #add to window
e = Entry(tk, textvariable = entry) #text field
e.pack() #add to window
b = Button(tk,text='Ok', command = tk.destroy) #ok button to terminate
b.pack() #add to window

tk.geometry("500x500")#The size of the box
tk.wm_title("") #set title of window
tk.mainloop() #call function

serial = entry.get() #sets serial to the serial number inputted
print(serial)

filePath = "C:\\Users\\lizzi\\Desktop\\" + serial + ".xlsx"
folderPath =  
print(filePath)
print(folderPath)
shutil.copy(filePath, folderPath)

filename = serial + ".xlsx"
for filename in os.listdir(folderPath):
       infilename = os.path.join(folderPath,filename)
       if not os.path.isfile(infilename): continue
       oldbase = os.path.splitext(filename)
       newname = infilename.replace('.xlsx', '.exe')
       output = os.rename(infilename, newname)
