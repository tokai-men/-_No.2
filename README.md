# -_No.2
from numpy.lib import roots
import random
import numpy as np
import tkinter as tk
card=np.array([["B","I","N","G","O"],[0,0,0,0,0],[0,0,0,0,0],[0,0,"●",0,0],[0,0,0,0,0],[0,0,0,0,0]])
result=[]
for i in range(5):
  for j in range(5):
    if i==2 and j==2:
      continue
    if j==0:
      roll=random.randint(1,15)
    elif j==1:
      roll=random.randint(16,30)
    elif j==2:
      roll=random.randint(31,45)
    elif j==3:
      roll=random.randint(46,60)
    elif j==4:
      roll=random.randint(61,75)
    if roll not in result:
      card[i+1][j]=roll
      result.append(roll)

print(card)
root=tk.Tk()
root.title("BINGO CARD")
root.geometry("600x400")
for n,i in enumerate(card):
  for n2,j in enumerate(i):
    if j=="B" or j=="I" or j=="N" or j=="G" or j=="O":
      label=tk.Label(root,text=j,height=3,width=9,bg="cyan")
    else:
      label=tk.Button(root,text=j,height=3,width=9,bg="lightgreen")
    label.place(x=n2*100,y=n*80)
root.mainloop()