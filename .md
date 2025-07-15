#include <stdio.h>
#include <stdlib.h>
#include <string.h>

typedef struct {
    int matricula;
    char nome[100];
    float notas[3];
} Aluno;

typedef struct {
    char nome[100];
    int idade;
    char endereco[200];
} Cadastro;

void exercicio1() {
    printf("char: %lu bytes\n", sizeof(char));
    printf("int: %lu bytes\n", sizeof(int));
    printf("float: %lu bytes\n", sizeof(float));
    printf("double: %lu bytes\n", sizeof(double));
}

void exercicio2() {
    printf("Tamanho da estrutura Aluno: %lu bytes\n", sizeof(Aluno));
}

void exercicio3() {
    int N;
    scanf("%d", &N);
    Cadastro* cad = malloc(N * sizeof(Cadastro));
    for (int i = 0; i < N; i++) {
        scanf(" %[^"]", cad[i].nome);
        scanf("%d", &cad[i].idade);
        scanf(" %[^"]", cad[i].endereco);
    }
    free(cad);
}

void exercicio4() {
    int n;
    scanf("%d", &n);
    int* v = malloc(n * sizeof(int));
    for (int i = 0; i < n; i++) scanf("%d", &v[i]);
    for (int i = 0; i < n; i++) printf("%d ", v[i]);
    printf("\n");
    free(v);
}

void exercicio5() {
    int n;
    do scanf("%d", &n); while (n <= 0);
    int* v = malloc(n * sizeof(int));
    for (int i = 0; i < n; i++) do scanf("%d", &v[i]); while (v[i] < 2);
    for (int i = 0; i < n; i++) printf("%d ", v[i]);
    printf("\n");
    free(v);
}

void exercicio6() {
    int r, c, x, found = 0;
    scanf("%d %d", &r, &c);
    int** m = malloc(r * sizeof(int*));
    for (int i = 0; i < r; i++) {
        m[i] = malloc(c * sizeof(int));
        for (int j = 0; j < c; j++) scanf("%d", &m[i][j]);
    }
    scanf("%d", &x);
    for (int i = 0; i < r && !found; i++)
        for (int j = 0; j < c; j++)
            if (m[i][j] == x) found = 1;
    printf("%d\n", found);
    for (int i = 0; i < r; i++) free(m[i]);
    free(m);
}

void exercicio7() {
    int n;
    scanf("%d", &n);
    int* v = malloc(n * sizeof(int));
    for (int i = 0; i < n; i++) v[i] = i;
    for (int i = 0; i < n; i++) printf("%d ", v[i]);
    printf("\n");
    free(v);
}

void exercicio8() {
    int n;
    scanf("%d", &n);
    if (n <= 0) printf("NULL\n");
    else {
        int* v = malloc(n * sizeof(int));
        printf("Alocado\n");
        free(v);
    }
}

void exercicio9() {
    char s[100];
    scanf(" %[^"]", s);
    int len = strlen(s);
    char* inv = malloc(len + 1);
    for (int i = 0; i < len; i++) inv[i] = s[len - i - 1];
    inv[len] = '\0';
    printf("%s\n", inv);
    free(inv);
}

void exercicio10() {
    int n, val;
    scanf("%d %d", &n, &val);
    if (n <= 0) printf("NULL\n");
    else {
        int* v = malloc(n * sizeof(int));
        for (int i = 0; i < n; i++) v[i] = val;
        for (int i = 0; i < n; i++) printf("%d ", v[i]);
        printf("\n");
        free(v);
    }
}

void exercicio11() {
    int N;
    scanf("%d", &N);
    int** m = malloc(N * sizeof(int*));
    for (int i = 0; i < N; i++) {
        m[i] = malloc(N * sizeof(int));
        for (int j = 0; j < N; j++) m[i][j] = (i == j);
    }
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) printf("%d ", m[i][j]);
        printf("\n");
        free(m[i]);
    }
    free(m);
}

void exercicio12() {
    int N;
    scanf("%d", &N);
    int** m = malloc(N * sizeof(int*));
    for (int i = 0; i < N; i++) {
        m[i] = malloc(N * sizeof(int));
        for (int j = 0; j < N; j++) m[i][j] = (i + j == N - 1);
    }
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) printf("%d ", m[i][j]);
        printf("\n");
        free(m[i]);
    }
    free(m);
}

void exercicio13() {
    int N;
    scanf("%d", &N);
    int** m = malloc(N * sizeof(int*));
    for (int i = 0; i < N; i++) {
        m[i] = malloc(N * sizeof(int));
        for (int j = 0; j < N; j++) m[i][j] = (i == j ? 0 : (j > i ? 1 : -1));
    }
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) printf("%d ", m[i][j]);
        printf("\n");
        free(m[i]);
    }
    free(m);
}

void exercicio14() {
    int N;
    scanf("%d", &N);
    int *A = malloc(N * sizeof(int)), *B = malloc(N * sizeof(int)), *C = malloc(N * sizeof(int));
    for (int i = 0; i < N; i++) scanf("%d", &A[i]);
    for (int i = 0; i < N; i++) scanf("%d", &B[i]);
    for (int i = 0; i < N; i++) C[i] = A[i] + B[i];
    for (int i = 0; i < N; i++) printf("%d ", C[i]);
    printf("\n");
    free(A); free(B); free(C);
}

void exercicio15() {
    int N;
    scanf("%d", &N);
    int *A = malloc(N * sizeof(int)), *B = malloc(N * sizeof(int)), *C = malloc(N * sizeof(int));
    for (int i = 0; i < N; i++) scanf("%d", &A[i]);
    for (int i = 0; i < N; i++) scanf("%d", &B[i]);
    for (int i = 0; i < N; i++) C[i] = A[i] * B[i];
    for (int i = 0; i < N; i++) printf("%d ", C[i]);
    printf("\n");
    free(A); free(B); free(C);
}

void exercicio16() {
    int N;
    scanf("%d", &N);
    int **A = malloc(N * sizeof(int*)), *B = malloc(N * sizeof(int)), *C = malloc(N * sizeof(int));
    for (int i = 0; i < N; i++) {
        A[i] = malloc(N * sizeof(int));
        for (int j = 0; j < N; j++) scanf("%d", &A[i][j]);
    }
    for (int i = 0; i < N; i++) scanf("%d", &B[i]);
    for (int i = 0; i < N; i++) {
        C[i] = 0;
        for (int j = 0; j < N; j++) C[i] += A[i][j] * B[j];
    }
    for (int i = 0; i < N; i++) printf("%d ", C[i]);
    printf("\n");
    for (int i = 0; i < N; i++) free(A[i]);
    free(A); free(B); free(C);
}

void exercicio17() {
    int N;
    scanf("%d", &N);
    int **A = malloc(N * sizeof(int*)), *B = malloc(N * sizeof(int));
    for (int i = 0; i < N; i++) {
        A[i] = malloc(N * sizeof(int));
        for (int j = 0; j < N; j++) scanf("%d", &A[i][j]);
    }
    for (int j = 0; j < N; j++) {
        B[j] = 0;
        for (int i = 0; i < N; i++) B[j] += A[i][j];
    }
    for (int i = 0; i < N; i++) printf("%d ", B[i]);
    printf("\n");
    for (int i = 0; i < N; i++) free(A[i]);
    free(A); free(B);
}

void exercicio18() {
    int l1, c1, l2, c2;
    scanf("%d %d", &l1, &c1);
    int **A = malloc(l1 * sizeof(int*));
    for (int i = 0; i < l1; i++) {
        A[i] = malloc(c1 * sizeof(int));
        for (int j = 0; j < c1; j++) scanf("%d", &A[i][j]);
    }
    scanf("%d %d", &l2, &c2);
    if (c1 != l2) return;
    int **B = malloc(l2 * sizeof(int*));
    for (int i = 0; i < l2; i++) {
        B[i] = malloc(c2 * sizeof(int));
        for (int j = 0; j < c2; j++) scanf("%d", &B[i][j]);
    }
    int **C = malloc(l1 * sizeof(int*));
    for (int i = 0; i < l1; i++) {
        C[i] = malloc(c2 * sizeof(int));
        for (int j = 0; j < c2; j++) {
            C[i][j] = 0;
            for (int k = 0; k < c1; k++) C[i][j] += A[i][k] * B[k][j];
        }
    }
    for (int i = 0; i < l1; i++) {
        for (int j = 0; j < c2; j++) printf("%d ", C[i][j]);
        printf("\n");
        free(A[i]); free(C[i]);
    }
    for (int i = 0; i < l2; i++) free(B[i]);
    free(A); free(B); free(C);
}

int main() {
    int op;
    do {
        scanf("%d", &op);
        switch(op) {
            case 1: exercicio1(); break;
            case 2: exercicio2(); break;
            case 3: exercicio3(); break;
            case 4: exercicio4(); break;
            case 5: exercicio5(); break;
            case 6: exercicio6(); break;
            case 7: exercicio7(); break;
            case 8: exercicio8(); break;
            case 9: exercicio9(); break;
            case 10: exercicio10(); break;
            case 11: exercicio11(); break;
            case 12: exercicio12(); break;
            case 13: exercicio13(); break;
            case 14: exercicio14(); break;
            case 15: exercicio15(); break;
            case 16: exercicio16(); break;
            case 17: exercicio17(); break;
            case 18: exercicio18(); break;
        }
    } while(op != 0);
    return 0;
}
