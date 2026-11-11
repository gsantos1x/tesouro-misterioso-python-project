import random

print("================================")
print("       TESOURO MISTERIOSO")
print("================================")

nickname = input("Insira seu nickname: ").strip()

if nickname == "":
    nickname = "Jogador"

# Cadastro dos jogadores
jogadores = {
    nickname: {"vitorias": 0, "derrotas": 0}
}

# Quantidade de portas em cada fase
fases = [5, 7, 9, 12, 15]

while True:
    print("\n========== MENU PRINCIPAL ==========")
    print(f"Jogador atual: {nickname}")
    print("1 - Jogar")
    print("2 - Ver placar")
    print("3 - Sair")
    print("4 - Trocar nickname")
    print("5 - Como jogar?")

    opcao = input("\nEscolha uma opção: ")

    if opcao == "1":

        print("\n=== TESOURO MISTERIOSO ===")
        print("Encontre o tesouro nas 5 fases para vencer!")

        vidas = 3
        venceu = False

        # Início das fases
        for fase in range(1, 6):

            quantidade_portas = fases[fase - 1]
            tesouro = random.randint(1, quantidade_portas)

            print(f"\n========== FASE {fase} ==========")
            print(f"Você tem {quantidade_portas} portas disponíveis!")
            print(f"Vidas: {vidas}")

            encontrou_tesouro = False

            while vidas > 0:

                try:
                    porta = int(input(
                        f"\nEscolha uma porta de 1 a {quantidade_portas}: "
                    ))
                except ValueError:
                    print("Digite apenas números!")
                    continue

                if porta < 1 or porta > quantidade_portas:
                    print("Escolha uma porta válida!")
                    continue

                if porta == tesouro:
                    print("\nPARABÉNS! Você encontrou o tesouro!")
                    encontrou_tesouro = True
                    break

                else:
                    print("\nVocê não encontrou o tesouro!")

                    # Sorteio de evento aleatório
                    evento = random.randint(1, 3)

                    if evento == 1:
                        vidas += 1
                        print("Você encontrou uma vida extra!")

                    elif evento == 2:
                        vidas -= 1
                        print("Você caiu em uma armadilha!")

                    else:
                        print("Nada aconteceu desta vez.")

                    # Dica sobre a localização do tesouro
                    if porta < tesouro:
                        print("Dica: o tesouro está em uma porta maior!")
                    else:
                        print("Dica: o tesouro está em uma porta menor!")

                    print("Vidas restantes:", vidas)

            # Se o jogador perdeu todas as vidas, a partida termina
            if vidas == 0:
                break

            if encontrou_tesouro:
                print(f"\nFASE {fase} CONCLUÍDA!")

                if fase == 5:
                    print("\nINCRÍVEL! Você completou todas as fases!")
                    venceu = True

        # Resultado da partida
        if venceu:
            print("VOCÊ VENCEU!")
            jogadores[nickname]["vitorias"] += 1

        else:
            print("\nFIM DE JOGO!")
            jogadores[nickname]["derrotas"] += 1

    elif opcao == "2":

        print("\n========== PLACAR ==========")

        for nome, dados in jogadores.items():
            print(f"\nJogador: {nome}")
            print(f"Vitórias: {dados['vitorias']}")
            print(f"Derrotas: {dados['derrotas']}")

    elif opcao == "3":

        print("\n========== RESULTADO FINAL ==========")

        for nome, dados in jogadores.items():
            print(f"\n{nome} - {dados['vitorias']} vitórias e "
                  f"{dados['derrotas']} derrotas")

        print("\nObrigado por jogar!")
        break

    elif opcao == "4":

        print("\n========== TROCAR NICKNAME ==========")

        novo_nickname = input("Digite seu novo nickname: ").strip()

        if novo_nickname == "":
            print("O nickname não pode ficar vazio!")

        else:
            nickname = novo_nickname

            if nickname not in jogadores:
                jogadores[nickname] = {
                    "vitorias": 0,
                    "derrotas": 0
                }

            print(f"\nNickname alterado para {nickname}!")

    elif opcao == "5":

        print("""
========== COMO JOGAR? ==========

1. O jogo possui 5 fases.

2. Cada fase possui uma quantidade diferente
   de portas:
   - Fase 1: 5 portas
   - Fase 2: 7 portas
   - Fase 3: 9 portas
   - Fase 4: 12 portas
   - Fase 5: 15 portas

3. Você começa com 3 vidas.

4. Ao escolher uma porta errada, um evento
   aleatório pode acontecer:

   - VIDA EXTRA: recebe uma vida adicional.
   - ARMADILHA: perde uma vida.
   - NADA: nenhum efeito.

5. Você avança de fase ao encontrar o tesouro.

6. Para vencer, encontre o tesouro nas 5 fases.

7. Se perder todas as vidas, a partida termina.

8. O placar registra suas vitórias e derrotas.

BOA SORTE NA AVENTURA!
""")

    else:
        print("Opção inválida! Escolha entre 1 e 5.")
