# -# Инициализация карты
maps = [1,2,3,
        4,5,6,
        7,8,9]
# Инициализация победных линий
victories = [[0,1,2],
             [3,4,5],
             [6,7,8],
             [0,3,6],
             [1,4,7],
             [2,5,8],
             [0,4,8],
             [2,4,6]]
# Вывод карты на экран
def print_maps():
    print(maps[0], end = " ")
    print(maps[1], end = " ")
    print(maps[2])

    print(maps[3], end = " ")
    print(maps[4], end = " ")
    print(maps[5])

    print(maps[6], end = " ")
    print(maps[7], end = " ")
    print(maps[8])

# Сделать ход в ячейку
def step_maps(step,symbol):
    ind = maps.index(step)
    maps[ind] = symbol
# Получить текущий результат игры
def get_result():
    win = ""

    for i in victories:
        if maps[i[0]] == "X" and maps[i[1]] == "X" and maps[i[2]] == "X":
            win = "X"
        if maps[i[0]] == "0" and maps[i[1]] == "0" and maps[i[2]] == "0":
            win = "0"

    return win

# Основная программа
game_over = False
player1 = True
while game_over == False:
    # 1) Показываем карту
    print_maps()

    # 2) Спросить у игрока, куда делать ход
    if player1 == True:
        symbol = "X"
        step = int(input("Игрок 1, ход за вами: "))
    else:
        symbol = "0"
        step = int(input("Игрок 2, ход за вами: "))

    step_maps(step,symbol) # делаем ход в указанную ячейку
    win = get_result() # определяем победителя
    if win != "":
        game_over = True
    else:
        game_over = False

    player1 = not(player1)
# игра окончена, объявляем победителя
print_maps()
print("Победил ", win)
        

