# -# создаём карту
field = [1,2,3,
        4,5,6,
        7,8,9]
# победа в линиях
lines = [[0,1,2],
         [3,4,5],
         [6,7,8],
         [0,3,6],
         [1,4,7],
         [2,5,8],
         [0,4,8],
         [2,4,6]]
# поле на экране
def print_field():
    print(field[0], end = " ")
    print(field[1], end = " ")
    print(field[2])

    print(field[3], end = " ")
    print(field[4], end = " ")
    print(field[5])

    print(field[6], end = " ")
    print(field[7], end = " ")
    print(field[8])

# делаем ход
def step_field(map,sym):
    inp = field.index(map)
    field[inp] = sym
# результат игры
def get_result():
    win = ""
for i in viclin:
        if lines[i[0]] == "X" and lines[i[1]] == "X" and lines[i[2]] == "X":
            win = "X"
        if lines[i[0]] == "0" and lines[i[1]] == "0" and lines[i[2]] == "0":
            win = "0"

    return win

# программа

game_over = False
player1 = True

while game_over == False:
    
    # 1) Показываем карту
    
    print_lines()

    # 2) делаем ход
    
    if player1 == True:
        sym = "X"
        mapr = int(input("игрок 1, ваш ход: "))
    else:
        sym = "0"
        mapr = int(input("игрок 2, ваш ход: "))

    step_lines(mapr,sym) # делаем ход
    
    win = get_result() # победитель
    
    if win != "":
        game_over = True
    else:
        game_over = False

    player1 = not(player1)
    
# игра окончена, победитель

print_lines()
print("Победил ", win)
    
