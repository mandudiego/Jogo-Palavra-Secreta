## Jogo da Palavra Secreta em Python!
Neste jogo o usuário insere letras em busca de adivinhar qual a palavra secreta pré-definida pelo sistema!

## Código do jogo:
```python
import os
palavra_secreta = 'SECRETA'
letras_acerto = ''
tentativas = 0

print('--' * 20)
print('Jogo da Palavra Secreta')
print('--' * 20)

while True: # Enquanto verdadeiro
    letra_usuario = input ('Digite uma letra: ').upper() # Recebe uma letra do usuário
    tentativas += 1 # Contador de tentativas
    if len(letra_usuario) > 1: # Se o usuário digitar mais de uma letra
        print ('Digite apenas uma letra!') # [ERRO-01] -> mais de 1 letra
        continue

    if letra_usuario in palavra_secreta: # Se a letra inserida pelo usuário estiver na palavra secreta
        letras_acerto += letra_usuario # Atribui a letra para a variavel 'letras_acerto'

    palavra_formada = ''

    for letra_secreta in palavra_secreta: # Laço: para cada letra secreta na palavra secreta
        if letra_secreta in letras_acerto: # Condição: se a letra secreta estiver na letra acertada
            palavra_formada += letra_secreta # Atribui a letra secreta na palavra formada
        else: # Se não
            palavra_formada += '*' # Atribui um * na palavra formada

    print('Palavra formada:', palavra_formada) # Exibe a palavra formada
    if palavra_formada == palavra_secreta: # Se a palavra formada for igual a secreta
        os.system('cls') # Comando 'cls' para limpar o terminal
        print('VOCÊ GANHOU! PARABÉNS!') 
        print('A palavra secreta era:', palavra_secreta)
        print('Tentativas:', tentativas)
        break
```
