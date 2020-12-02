using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ConsoleApp6
{
    class Program
    {
        static void Main(string[] args)
        {
            Random rand = new Random();
            Console.WriteLine("Введите размерность матрицы MxM :");
            int M = Convert.ToInt32(Console.ReadLine());
            int[,] matrix = new int[M, M];
            int sum = 0;
            for (int j = 0; j < M; j++)
            {
                for (int m = 0; m < M; m++)
                {
                    matrix[j, m] = rand.Next(-10, 10);
                    Console.Write(matrix[j, m] + " ");

                }
                Console.WriteLine();
                if (j % 2 == 0)
                {
                    for (int i = 0; i < M; i++)
                    {
                        sum += matrix[j, i];
                    }
                }
                int max = matrix[0, 0];
                for (int i = 1; i < matrix.GetLength(0); i++)
                {
                    if (matrix[i, j] > max)
                        max = matrix[i, j];
                }
            }
            Console.Write(" Сумма четных строк матрицы = {0}", sum);
            Console.ReadKey();
        }
    }
}
