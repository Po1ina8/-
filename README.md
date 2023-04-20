# -# Инициализация карты
field = [1,2,3,
        4,5,6,
        7,8,9]
# победа в линиях
victor = [[0,1,2],
          [3,4,5],
          [6,7,8],
          [0,3,6],
          [1,4,7],
          [2,5,8],
          [0,4,8],
          [2,4,6]]
# Вывод карты на экран
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

# Сделаем ход
def step_field(step,symbol):
    inp = field.index(step)
    field[inp] = symbol
# Получить текущий результат игры
def get_result():
    win = ""

    for i in victories:
        if field[i[0]] == "X" and field[i[1]] == "X" and field[i[2]] == "X":
            win = "X"
        if field[i[0]] == "0" and field[i[1]] == "0" and field[i[2]] == "0":
            win = "0"

    return win

# Программа
game_over = False
player1 = True
while game_over == False:
    # 1) Показываем карту
    print_field()

    # 2) Спросить у игрока, куда делать ход
    if player1 == True:
        symbol = "X"
        step = int(input("Игрок 1, ваш ход: "))
    else:
        symbol = "0"
        step = int(input("Игрок 2, ваш ход: "))

    step_field(step,symbol) # делаем ход в ячейку
    win = get_result() # победитель
    if win != "":
        game_over = True
    else:
        game_over = False

    player1 = not(player1)
# игра окончена, победитель
print_field()
print("Победил ", win)
        

