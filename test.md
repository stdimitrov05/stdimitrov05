using System;

class Program {
  static void Main() {
    Console.Write("Enter the size of the matrix: ");
    int size = int.Parse(Console.ReadLine());
    double[,] matrix = new double[size, size];
    for (int i = 0; i < size; i++) {
      for (int j = 0; j < size; j++) {
        Console.Write($"Enter the element at row {i+1} column {j+1}: ");
        matrix[i, j] = double.Parse(Console.ReadLine());
      }
    }
    double det = Determinant(matrix, size);
    Console.WriteLine($"The determinant of the matrix is {det}.");
  }

  static double Determinant(double[,] matrix, int size) {
    if (size == 1) {
      return matrix[0, 0];
    } else if (size == 2) {
      return matrix[0, 0] * matrix[1, 1] - matrix[0, 1] * matrix[1, 0];
    } else {
      double det = 0;
      for (int j = 0; j < size; j++) {
        double[,] submatrix = new double[size - 1, size - 1];
        for (int i = 1; i < size; i++) {
          for (int k = 0; k < size; k++) {
            if (k != j) {
              submatrix[i - 1, k < j ? k : k - 1] = matrix[i, k];
            }
          }
        }
        int sign = j % 2 == 0 ? 1 : -1;
        det += sign * matrix[0, j] * Determinant(submatrix, size - 1);
      }
      return det;
    }
  }
}
