# Perceptron
entradas = [
    [0, 0],
    [0, 1],
    [1, 0],
    [1, 1]
]

saidas = [0, 0, 1, 1]

pesos = [0.0, 0.0, 0.0]

taxa = 0.1

def ativacao(soma):
    return 1 if soma >= 0 else 0

for ciclo in range(2):
    print(f"\n--- Ciclo {ciclo + 1} ---")

    for i in range(len(entradas)):
        x1, x2 = entradas[i]
        desejado = saidas[i]

        soma = x1 * pesos[0] + x2 * pesos[1] + 1 * pesos[2]

        saida = ativacao(soma)

        erro = desejado - saida

        # Atualização dos pesos
        pesos[0] += taxa * erro * x1
        pesos[1] += taxa * erro * x2
        pesos[2] += taxa * erro * 1

        print(f"Entradas: {entradas[i]}, Desejado: {desejado}, Saiu: {saida}, Erro: {erro}")
        print(f"Pesos atualizados: {pesos}")

print("\nPesos finais:", pesos)
