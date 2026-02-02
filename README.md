# fibonacci
impresora de numeros fibonacci

def fibonacci_list(n):
    if n <= 0:
        return []
    seq = [0]
    if n == 1:
        return seq
    seq.append(1)  # ahora seq = [0, 1]
    while len(seq) < n:
        seq.append(seq[-1] + seq[-2])
    return seq

def main():
    entrada = input("Ingrese la cantidad de números Fibonacci a imprimir: ").strip()
    try:
        n = int(entrada)
    except ValueError:
        print("Entrada inválida: por favor ingrese un número entero.")
        return

    if n <= 0:
        print("Valor inválido: debe ingresar un entero positivo mayor que 0.")
        return

    seq = fibonacci_list(n)
    # Imprimir en una sola línea, separados por espacios
    print(" ".join(str(x) for x in seq))

if __name__ == "__main__":
    main()
