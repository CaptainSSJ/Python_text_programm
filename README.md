import random

color = ('black','red')
ruletka = {k: color[k%2] for k in range(1,11)}
ruletka1 = {k: color[k%2-1] for k in range(11,19)}
ruletka3 = {k: color[k%2] for k in range(19,29)}
ruletka4 = {k: color[k%2-1] for k in range(29,37)}

rul = {**ruletka,**ruletka1,**ruletka3,**ruletka4}

def randomNumber():
    number = int(input())
    return number, rul[number]

def lose_or_win():
    rnd = random.randint(1,37)
    a,b = randomNumber()
    if a == rnd:
        return f'Вы поставили на {a,b} {int(input())}р'
    else:
        return f'Вы поставили на {a,b} {int(input())}р \
            \nК сожалению Вы проиграли, так как на рулетке выпало {rnd, rul[rnd]}'
    
print(lose_or_win())
