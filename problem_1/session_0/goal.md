```c
#include <stdio.h>
#include <stdlib.h>

#define N 5

typedef struct {
  char name[16];
  int table[N][N];
  int size;
} Matrix;

Matrix new_matrix(int size) {
  return (Matrix){.name = "", .table = {0}, .size = size};
}

void matrix_traverse(Matrix matrix, int row, int col) {
  if (!(row || col)) printf("Matriz %s\n", matrix.name);
  if (row >= matrix.size) {
    printf("\n");
    return;
  }
  if (col >= matrix.size) {
    printf("\n");
    matrix_traverse(matrix, row + 1, 0);
    return;
  }

  printf("%d ", matrix.table[row][col]);

  matrix_traverse(matrix, row, col + 1);
}

void matrix_mult(Matrix *a, Matrix *b, Matrix *c, int row, int col, int k) {
  if (row >= c->size) return;
  if (col >= c->size) {
    matrix_mult(a, b, c, row + 1, 0, 0);
    return;
  }
  if (k == 0) c->table[row][col] = 0;

  c->table[row][col] += a->table[row][k] * b->table[k][col];

  if (k + 1 < a->size) {
    matrix_mult(a, b, c, row, col, k + 1);
  } else {
    matrix_mult(a, b, c, row, col + 1, 0);
  }
}

void matrix_transpose(Matrix *a, Matrix *c, int row, int col) {
  if (row >= N) return;
  if (col >= N) {
    matrix_transpose(a, c, row + 1, 0);
    return;
  }
  c->table[row][col] = a->table[col][row];

  matrix_transpose(a, c, row, col + 1);
}

void matrix_sum(Matrix *a, Matrix *b, Matrix *c, int row, int col) {
  if (row >= c->size) return;
  if (col >= c->size) {
    matrix_sum(a, b, c, row + 1, 0);
    return;
  }

  c->table[row][col] = a->table[row][col] + b->table[row][col];

  matrix_sum(a, b, c, row, col + 1);
}

void matrix_sub(Matrix *a, Matrix *b, Matrix *c, int row, int col) {
  if (row >= c->size) return;
  if (col >= c->size) {
    matrix_sub(a, b, c, row + 1, 0);
    return;
  }

  c->table[row][col] = a->table[row][col] - b->table[row][col];

  matrix_sub(a, b, c, row, col + 1);
}

void matrix_scalar(Matrix *a, float num, Matrix *b, int row, int col) {
  if (row >= b->size) return;
  if (col >= b->size) {
    matrix_scalar(a, num, b, row + 1, 0);
    return;
  }
  b->table[row][col] = a->table[row][col] * num;

  matrix_scalar(a, num, b, row, col + 1);
}

int main() {
  Matrix a = new_matrix(N);
  Matrix b = new_matrix(N);
  Matrix c = new_matrix(N);
  a.name[0] = 'A';
  b.name[0] = 'B';
  c.name[0] = 'C';
  for (int i = 0; i < N*N; ++i) {
    a.table[i / N][i % N] = i % N;
    b.table[i % N][i / N] = i % N;
  }

  matrix_traverse(a, 0, 0);
  matrix_traverse(b, 0, 0);

  matrix_mult(&a, &b, &c, 0, 0, 0);
  matrix_traverse(c, 0, 0);

  matrix_transpose(&a, &c, 0, 0);
  matrix_traverse(c, 0, 0);

  matrix_sum(&a, &b, &c, 0, 0);
  matrix_traverse(c, 0, 0);

  matrix_scalar(&a, 3.2, &c, 0, 0);
  matrix_traverse(c, 0, 0);

  matrix_sub(&a, &b, &c, 0, 0);
  return 0;
}
```