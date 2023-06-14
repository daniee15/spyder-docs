import math

def fun(x):
    return math.cos(x) ** 3 - math.sin(x)

def encontrar_raiz(a, b, erro1=0.00001, erro2=0.00001):
    esp = 25
    h = 0

    if fun(a) * fun(b) > 0:
        print('Não há garantia de raiz no intervalo fornecido.')
        return None

    print(f'{" " * esp}ITERAÇÃO      X                  f(x)                      b-a ')

    while True:
        d = (a + b) / 2
        c = fun(d)
        intervalo = abs(b - a)

        if abs(c) <= erro1 or intervalo <= erro2:
            print('Encontrada a raiz:')
            print(d)
            return d

        if c * fun(a) < 0:
            b = d
        else:
            a = d

        h += 1
        print(f'{" " * esp} {h:<6}    {d:<19} {c:<25} {intervalo:<16}')

# Exemplo de uso:
a = 0
b = math.pi / 2
encontrar_raiz(a, b)
