import tkinter as tk
import tkinter.messagebox as tm 


#проверка победителя
def winner():
    if area[0][0]["text"] == "X" and area[0][1]["text"] == "X" and area[0][2]["text"] == "X":
        return "X"
    if area[1][0]["text"] == "X" and area[1][1]["text"] == "X" and area[1][2]["text"] == "X":
        return "X"
    if area[2][0]["text"] == "X" and area[2][1]["text"] == "X" and area[2][2]["text"] == "X":
        return "X"
    if area[0][0]["text"] == "X" and area[1][0]["text"] == "X" and area[2][0]["text"] == "X":
        return "X"
    if area[0][1]["text"] == "X" and area[1][1]["text"] == "X" and area[2][1]["text"] == "X":
        return "X"
    if area[0][2]["text"] == "X" and area[1][2]["text"] == "X" and area[2][2]["text"] == "X":
        return "X"
    if area[0][0]["text"] == "X" and area[1][1]["text"] == "X" and area[2][2]["text"] == "X":
        return "X"
    if area[0][2]["text"] == "X" and area[1][1]["text"] == "X" and area[2][0]["text"] == "X":
        return "X"
    if area[0][0]["text"] == "0" and area[0][1]["text"] == "0" and area[0][2]["text"] == "0":
        return "0"
    if area[1][0]["text"] == "0" and area[1][1]["text"] == "0" and area[1][2]["text"] == "0":
        return "0"
    if area[2][0]["text"] == "0" and area[2][1]["text"] == "0" and area[2][2]["text"] == "0":
        return "0"
    if area[0][0]["text"] == "0" and area[1][0]["text"] == "0" and area[2][0]["text"] == "0":
        return "0"
    if area[0][1]["text"] == "0" and area[1][1]["text"] == "0" and area[2][1]["text"] == "0":
        return "0"
    if area[0][2]["text"] == "0" and area[1][2]["text"] == "0" and area[2][2]["text"] == "0":
        return "0"
    if area[0][0]["text"] == "0" and area[1][1]["text"] == "0" and area[2][2]["text"] == "0":
        return "0"
    if area[0][2]["text"] == "0" and area[1][1]["text"] == "0" and area[2][0]["text"] == "0":
        return "0"
    return ""

#новая игра
def new_game(): 
    global area, turn, end
    turn = 1
    end = False
    for x in range(3): 
        for y in range(3): 
            area[x][y]["text"] = "" 
            area[x][y]['bg'] = 'white'

#сама логика игры
def push(button): 
    global turn, end
    if turn % 2 == 0:
        turn_char = "0" 
        color = 'red'
    else: 
        turn_char = "X" 
        color = 'blue'
    if button["text"] == "": 
        button["text"] = turn_char 
        button['bg'] = color
        turn += 1 
    if winner() == "X": 
        tm.showinfo("Победитель", "Победили Х")
        end = True
    if winner() == "0": 
        tm.showinfo("Победитель", "Победили 0")
        end = True
    if winner() == "" and turn == 10: 
        tm.showinfo("Ничья", "Победила дружба")
        end = True
    if end:
        if tm.askokcancel('Новая игра', 'Начать новую игру?'):
            new_game()
        else:
            window.destroy()
    


window = tk.Tk() 
window.title("Крестики-нолики") 
window.geometry("300x300") 
window.resizable(False, False)  

area = [] 
turn = 1 
end = False

#создание поля
for x in range(3): 
    area.append([])
    for y in range(3):
        button = tk.Button(window, text = "", width = 13, height = 6) 
        area[x].append(button) 
        area[x][y].place(x = x * 100, y = y * 100)
        area[x][y]["command"] = lambda selected_button = button: push(selected_button) 







window.mainloop() 
