# Zuev-Ilya-Software-Development
«Разработка программного обеспечения» олимпиада «Цифровая весна»


///Я добавил метод Main, чтобы программа могла запускаться. Также добавил проверку на отрицательное число, или если пользователь введёт символ, а не цифру.
namespace Library
{
    class Program
    {
        static void Main(string[] args)
        {
            LibraryHelper.One();
            LibraryHelper.Two();

            Console.WriteLine("Нажмите любую клавишу для выхода...");
            Console.ReadKey();
        }
    }
    public class LibraryHelper
    {
        public static void One()
        {
            int n;
            while (true)
            {
                Console.Write("Введите число N: ");
                if (!int.TryParse(Console.ReadLine(), out n) || n <= 0)
                {
                    Console.WriteLine("Вы ввели некорректное число. Попробуйте еще раз.");
                }
                else
                {
                    break;
                }
            }

            string result = string.Join(", ", Enumerable.Range(1, n));
            Console.WriteLine(result);
        }

        public static void Two()
        {
            int n;
            while (true)
            {
                Console.Write("Введите нечетное число N: ");
                if (!int.TryParse(Console.ReadLine(), out n) || n <= 0 || n % 2 == 0)
                {
                    Console.WriteLine("Вы ввели некорректное число. Попробуйте еще раз.");
                }
                else
                {
                    break;
                }
            }

            for (int row = 1; row <= n; row++)
            {
                for (int col = 1; col <= n; col++)
                {
                    if (row == n / 2 + 1 && col == n / 2 + 1) Console.Write(" ");
                    else Console.Write("#");
                }
                Console.WriteLine();
            }
        }
    }
}
