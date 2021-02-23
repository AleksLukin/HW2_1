# HW2_1 
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace HW_2_1_1
{
    class Program
    {
        static void Main()
        {

        }

         public static bool CheckNumber()
         { 
            int number = int.Parse(Console.ReadLine());
            int d = 0;
            int i = 2;

            while (i < number)
            {
                if (number % i == 0)
                {
                    d++;
                }
                else
                {
                    i++;
                }
                
            }

            if (d == 0)
            {
                return true; 
            }
            else
            {
                return false;
            }

         }         
    }
}
/*Требуется реализовать на C# функцию согласно блок-схеме. 
   Блок-схема описывает алгоритм проверки, простое число или нет.
1. Написать консольное приложение.
2. Алгоритм реализовать отдельно в функции согласно блок-схеме.
3. Написать проверочный код в​ main​ функции.
4. Код выложить на GitHub.*/

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace HW2_1_2
{
    class Program
    {
        static void Main(string[] args) //Вычислите асимптотическую сложность функции из примера
        {
        }
        public​ ​ static​ ​ int​ ​ StrangeSum​(​ int​[] inputArray)
        {
        int​ sum = ​ 0​ ;                                               
            ​ for​(​ int​ i = ​ 0​ ; i < inputArray.Length; i++)            ​ // O(N*N*N)
                {
                for​(​ int​ j = ​ 0​ ; j < inputArray.Length; j++)          ​ // O(N*N)
                    { 
                    ​ for​(​ int​ k = ​ 0​ ; k < inputArray.Length; k++)      ​ // O(N)
                    {
                    int y = 0;

                    if (j != 0) 
                    {
                        y = k/ j;
                    }

                    sum += inputArray[i] + i + k + j + y; //O(1)
                    }
                }

            }
        return sum;                                  //O(1)               

        }//N*N*N 
    }
}

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace HW_2_1_3
{
    class Program
    {
        static void Main(string[] args) //Требуется реализовать рекурсивную версию и версию без рекурсии (через цикл) чисел Фибоначчи.
        {
            Console.WriteLine(FibCyc(10));
            Console.WriteLine(FibReq(10));
        }
        static int FibReq(int n)
        {
            if (n == 1 || n == 0)
            {
                return n;
            }
            return (FibReq(n - 1) + (FibReq(n - 2)));
        }

        static int FibCyc(int n)
        {
            int x = 0;
            int y = 1;
            int temp = 0;

            for (int i = 0; i < n; i++)
            {
                temp = x;
                x = y;
                y += temp;
            }
            return x;
        }
    }
}
