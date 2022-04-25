from curses import BUTTON1_CLICKED
from pathlib import Path

from tkinter import Tk, Canvas, Entry, Text, Button, PhotoImage


OUTPUT_PATH = Path(__file__).parent
ASSETS_PATH = OUTPUT_PATH / Path("./assets")


def relative_to_assets(path: str) -> Path:
    return ASSETS_PATH / Path(path)


def push_element():
    if button_1 == BUTTON1_CLICKED:
        list.append(123)

    for x in range(len(list)):
        print(list[x]),


BUTTON1_CLICKED = 0
list = []
window = Tk()
x = 0
window.geometry("1200x600")
window.configure(bg="#FF9900")

canvas = Canvas(
    window,
    bg="#FF9900",
    height=600,
    width=1200,
    bd=0,
    highlightthickness=0,
    relief="ridge"
)

canvas.place(x=0, y=0)
canvas.create_text(
    241.0,
    30.0,
    anchor="nw",
    text="PYKLA",
    fill="#000000",
    font=("Inter ExtraBold", 36 * -1)
)

entry_image_1 = PhotoImage(
    file=relative_to_assets("entry_1.png"))
entry_bg_1 = canvas.create_image(
    562.0,
    160.0,
    image=entry_image_1
)
entry_1 = Entry(
    bd=0,
    bg="#000000",
    highlightthickness=0
)
entry_1.place(
    x=502.0,
    y=140.0,
    width=120.0,
    height=38.0
)

button_image_1 = PhotoImage(
    file=relative_to_assets("button_1.png"))
button_1 = Button(
    image=button_image_1,
    borderwidth=0,
    highlightthickness=0,
    command=push_element,
    relief="flat"
)
button_1.place(
    x=506.0,
    y=247.0,
    width=101.0,
    height=36.0
)

window.resizable(False, False)
window.mainloop()
