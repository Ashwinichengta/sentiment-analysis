# sentiment-analysis
import tkinter as tk
from textblob import TextBlob

def on_submit():
    from tkinter import messagebox
    text=text_entry.get()

    blob=TextBlob(text)

    sentiment_polarity=blob.sentiment.polarity

    if sentiment_polarity<0:
        messagebox.showinfo("Info","Negative")
    elif sentiment_polarity>0:
        messagebox.showinfo("Info","Positive")
    else:
        messagebox.showinfo("Info","Neutral")

# Creating main window
window=tk.Tk()
window.title("Supervised Learning program")
window.geometry("300x300")

head=tk.Label(window,text="TextBlob program",font="sans 10 bold",bg="white",fg="black")
head.grid(row=0,column=0,columnspan=2,padx=15,pady=10)

text_name=tk.Label(window,text="Enter Text : ")
text_name.grid(row=1,column=0,padx=10,pady=10)

text_entry=tk.Entry(window)
text_entry.grid(row=1,column=1)

submit_button=tk.Button(window,text="submit",command=on_submit)
submit_button.grid(row=2,columnspan=2,pady=10)

#status_label=tk.Label(window,text="")
#status_label.grid(row=3,column=0,pady=10)

window.mainloop()
