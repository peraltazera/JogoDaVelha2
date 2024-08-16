def imprimir_tabuleiro(tabuleiro):
    print("\n")
    for linha in tabuleiro:
        print("|".join(linha))
        print("-" * 5)
    print("\n")


def verificar_vencedor(tabuleiro):
    # Verificar linhas
    for linha in tabuleiro:
        if linha[0] == linha[1] == linha[2] != " ":
            return linha[0]

    # Verificar colunas
    for col in range(3):
        if tabuleiro[0][col] == tabuleiro[1][col] == tabuleiro[2][col] != " ":
            return tabuleiro[0][col]

    # Verificar diagonais
    if tabuleiro[0][0] == tabuleiro[1][1] == tabuleiro[2][2] != " ":
        return tabuleiro[0][0]
    if tabuleiro[0][2] == tabuleiro[1][1] == tabuleiro[2][0] != " ":
        return tabuleiro[0][2]

    return None


def tabuleiro_cheio(tabuleiro):
    for linha in tabuleiro:
        if " " in linha:
            return False
    return True


def obter_linhas_disponiveis(tabuleiro):
    linhas_disponiveis = [i for i in range(3) if " " in tabuleiro[i]]
    return linhas_disponiveis


def obter_colunas_disponiveis(tabuleiro, linha):
    colunas_disponiveis = [i for i in range(3) if tabuleiro[linha][i] == " "]
    return colunas_disponiveis


def jogar():
    tabuleiro = [[" " for _ in range(3)] for _ in range(3)]
    jogador_atual = "X"

    while True:
        imprimir_tabuleiro(tabuleiro)
        print(f"Jogador {jogador_atual}, é a sua vez.")

        linhas_disponiveis = obter_linhas_disponiveis(tabuleiro)
        while True:
            try:
                linha = int(
                    input(
                        f"Escolha uma linha das disponíveis {linhas_disponiveis}: "
                    ))
                if linha not in linhas_disponiveis:
                    print("Linha indisponível. Escolha outra.")
                    continue
                break
            except ValueError:
                print("Entrada inválida! Insira um número válido.")

        colunas_disponiveis = obter_colunas_disponiveis(tabuleiro, linha)
        while True:
            try:
                coluna = int(
                    input(
                        f"Escolha uma coluna das disponíveis {colunas_disponiveis}: "
                    ))
                if coluna not in colunas_disponiveis:
                    print("Coluna indisponível. Escolha outra.")
                    continue
                break
            except ValueError:
                print("Entrada inválida! Insira um número válido.")

        tabuleiro[linha][coluna] = jogador_atual

        vencedor = verificar_vencedor(tabuleiro)
        if vencedor:
            imprimir_tabuleiro(tabuleiro)
            print(f"Parabéns! O jogador {vencedor} venceu!")
            break

        if tabuleiro_cheio(tabuleiro):
            imprimir_tabuleiro(tabuleiro)
            print("O jogo empatou!")
            break

        jogador_atual = "O" if jogador_atual == "X" else "X"


if __name__ == "__main__":
    jogar()
