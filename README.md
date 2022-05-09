# jogoforca
#python

secreto = 'perfume'
digitadas = []
chances = 3
while True:
    letra = input('Digite uma letra: ')

    if chances <= 0:
        print('Você perdeu!!!')
        break

    if len(letra) > 1:
        print('Ahh isso não vale, digite apenas uma letra')
        continue
    digitadas.append(letra)

    if letra in secreto:
        print(f'Acertou!, tem essa {letra} na palavra.')
    else:
        print(f'Errrrrou, não tem a letra {letra}')
        digitadas.pop()
    secreto_temporario = ''
    for letra_secreta in secreto:
        if letra_secreta in digitadas:
            secreto_temporario += letra_secreta
        else:
            secreto_temporario += '*'

    if secreto_temporario == secreto:
        print(f'Que legar, você acertou!! A palavra era {secreto_temporario}')
        break
    else:
        print(f'A palabra secreta esta assim:{secreto_temporario}')

    if letra not in secreto:
        chances -= 1
        print(f'Você ainda tem {chances} chances.')
        print()
