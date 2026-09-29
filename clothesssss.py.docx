import tkinter as tk
import math

root = tk.Tk()
root.title("Windy Day Animation")
canvas = tk.Canvas(root, width=800, height=400, bg="skyblue")
canvas.pack()

# ground
canvas.create_rectangle(0, 300, 800, 400, fill="green")

# clothesline
canvas.create_line(100, 200, 700, 200, width=3, fill="black")

# trees
def draw_tree(x, y):
    trunk = canvas.create_rectangle(x, y, x+20, y+60, fill="brown")
    leaves = canvas.create_oval(x-30, y-40, x+50, y+40, fill="darkgreen")
    return trunk, leaves

trees = [draw_tree(150, 240), draw_tree(350, 240), draw_tree(550, 240)]

# clothes
colors = ["white", "red", "blue", "yellow", "pink"]
clothes = []
x = 150
for c in colors:
    rect = canvas.create_rectangle(x, 180, x+40, 220, fill=c)
    clothes.append(rect)
    x += 100

# animation
angle = 0
def animate():
    global angle
    angle += 0.1
    sway = math.sin(angle) * 10

    for _, leaves in trees:
        canvas.move(leaves, sway, 0)
    for cloth in clothes:
        canvas.move(cloth, sway / 2, 0)

    root.update()
    canvas.after(50, animate)

animate()
root.mainloop()
