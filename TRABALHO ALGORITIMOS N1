#include <stdio.h>

// Função para calcular o MDC (Máximo Divisor Comum) usando o algoritmo de Euclides
int mdc(int a, int b) {
    if (b == 0)
        return a;
    return mdc(b, a % b);
}

// Função para simplificar uma fração
void simplificar(int *numerador, int *denominador) {
    int divisor = mdc(*numerador, *denominador);
    *numerador /= divisor;
    *denominador /= divisor;
}

// Função para somar frações
void somar(int numerador1, int denominador1, int numerador2, int denominador2, int *nr, int *dr) {
    *nr = numerador1 * denominador2 + numerador2 * denominador1;
    *dr = denominador1 * denominador2;
    simplificar(nr, dr);
}

// Função para subtrair frações
void subtrair(int numerador1, int denominador1, int numerador2, int denominador2, int *nr, int *dr) {
    *nr = numerador1 * denominador2 - numerador2 * denominador1;
    *dr = denominador1 * denominador2;
    simplificar(nr, dr);
}

// Função para multiplicar frações
void multiplicar(int numerador1, int denominador1, int numerador2, int denominador2, int *nr, int *dr) {
    *nr = numerador1 * numerador2;
    *dr = denominador1 * denominador2;
    simplificar(nr, dr);
}

// Função para dividir frações
void dividir(int numerador1, int denominador1, int numerador2, int denominador2, int *nr, int *dr) {
    *nr = numerador1 * denominador2;
    *dr = denominador1 * numerador2;
    simplificar(nr, dr);
}

int main() {
    int numerador1, denominador1, numerador2, denominador2;
    int nr, dr;
    char operacao;

    // Entrada das frações e da operação
    printf("Digite a primeira fração (numerador denominador): ");
    scanf("%d %d", &numerador1, &denominador1);
    printf("Digite a operação (+ - * /): ");
    scanf(" %c", &operacao);
    printf("Digite a segunda fração (numerador denominador): ");
    scanf("%d %d", &numerador2, &denominador2);

    // Realização da operação
    switch (operacao) {
        case '+':
            nr = numerador1 * denominador2 + numerador2 * denominador1;
            dr = denominador1 * denominador2;
            break;
        case '-':
            nr = numerador1 * denominador2 - numerador2 * denominador1;
            dr = denominador1 * denominador2;
            break;
        case '*':
            nr = numerador1 * numerador2;
            dr = denominador1 * denominador2;
            break;
        case '/':
            nr = numerador1 * denominador2;
            dr = denominador1 * numerador2;
            break;
        default:
            printf("Operação inválida!\n");
            return 1;
    }

    // Simplificação do resultado
    int divisor = mdc(nr, dr);
    nr /= divisor;
    dr /= divisor;

    // Exibição do resultado
    printf("Resultado: %d/%d\n", nr, dr);

    return 0;
}
