import random





def jogar():
    mensagem_abertura()
    palavra_secreta = fruta_randomica()
    lista_letras = espaco_letras(palavra_secreta)

    enforcou = False
    acertou = False
    tentativas = 7

    letras_set = {}
    letras_erradas = []


    print("Voce tem {} tentativas.".format(tentativas))
    while (not enforcou and not acertou):
        chute = pede_chute()


        if chute not in palavra_secreta:
            tentativas -= 1
            desenha_forca(tentativas)
            letras_erradas.append(chute)
            s = set(letras_erradas)



        else:
            verifica_palavra(chute,palavra_secreta,lista_letras)

        print("letras erradas ate agora:{}".format(s))
        print(lista_letras)
        print("Voce tem {} tentativas restantes".format(tentativas))

        if (tentativas == 0):
            desenho_perdedor(palavra_secreta)
            enforcou = True

        elif "_" not in lista_letras:
            desenho_ganhador()
            acertou = True

    print("o jogo acabou")


def desenha_forca(tentativas):
    print("  _______     ")
    print(" |/      |    ")

    if(tentativas == 6):
        print(" |      (_)   ")
        print(" |            ")
        print(" |            ")
        print(" |            ")

    if(tentativas == 5):
        print(" |      (_)   ")
        print(" |      \     ")
        print(" |            ")
        print(" |            ")

    if(tentativas == 4):
        print(" |      (_)   ")
        print(" |      \|    ")
        print(" |            ")
        print(" |            ")

    if(tentativas == 3):
        print(" |      (_)   ")
        print(" |      \|/   ")
        print(" |            ")
        print(" |            ")

    if(tentativas == 2):
        print(" |      (_)   ")
        print(" |      \|/   ")
        print(" |       |    ")
        print(" |            ")

    if(tentativas == 1):
        print(" |      (_)   ")
        print(" |      \|/   ")
        print(" |       |    ")
        print(" |      /     ")

    if (tentativas == 0):
        print(" |      (_)   ")
        print(" |      \|/   ")
        print(" |       |    ")
        print(" |      / \   ")

    print(" |            ")
    print("_|___         ")
    print()






def desenho_perdedor(palavra_secreta):
    print("Puxa, você foi enforcado!")
    print("A palavra era {}".format(palavra_secreta))
    print("    _______________         ")
    print("   /               \       ")
    print("  /                 \      ")
    print("//                   \/\  ")
    print("\|   XXXX     XXXX   | /   ")
    print(" |   XXXX     XXXX   |/     ")
    print(" |   XXX       XXX   |      ")
    print(" |                   |      ")
    print(" \__      XXX      __/     ")
    print("   |\     XXX     /|       ")
    print("   | |           | |        ")
    print("   | I I I I I I I |        ")
    print("   |  I I I I I I  |        ")
    print("   \_             _/       ")
    print("     \_         _/         ")
    print("       \_______/           ")

def desenho_ganhador():
    print("Parabéns, você ganhou!")
    print("       ___________      ")
    print("      '._==_==_=_.'     ")
    print("      .-\\:      /-.    ")
    print("     | (|:.     |) |    ")
    print("      '-|:.     |-'     ")
    print("        \\::.    /      ")
    print("         '::. .'        ")
    print("           ) (          ")
    print("         _.' '._        ")
    print("        '-------'       ")


def mensagem_abertura():
    print("*********************************")
    print("***Bem vindo ao jogo da Forca!***")
    print("*********************************")


def fruta_randomica():
    lista_frutas = []
    arquivo = open("frutas.txt", "r")
    for linha in arquivo:
        linha = linha.strip()
        lista_frutas.append(linha)
    arquivo.close()

    numero = random.randrange(0, len(lista_frutas))
    palavra_secreta = lista_frutas[numero].upper()
    return (palavra_secreta)


def espaco_letras(a):
    return ['_' for letra in a]

def pede_chute():
    chute = input("Qual a letra?")
    chute = chute.upper().strip()
    return chute

def verifica_palavra(chute, palavra_secreta, lista_letras):
    index = 0
    for letra in palavra_secreta:
        if (chute == letra):
            lista_letras[index] = letra
        index = index + 1

if (__name__ == "__main__"):
    jogar()
