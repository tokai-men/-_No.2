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
label=tk.Label(roots,text=card)
label.grid()

root.mainloop()