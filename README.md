using System;

public class DivisionApp
{
    public static void Main(string[] args)
    {
        try
        {
            Console.Write("Введите первое число: ");
            string input1 = Console.ReadLine();

            Console.Write("Введите второе число: ");
            string input2 = Console.ReadLine();

            double num1 = double.Parse(input1);
            double num2 = double.Parse(input2);

            if (num2 == 0)
            {
                throw new DivideByZeroException("Деление на ноль запрещено!");
            }

            double result = num1 / num2;

            Console.WriteLine($"Результат деления: {result}");
        }
        catch (FormatException)
        {
          
            Console.WriteLine("Ошибка: Введенные значения не являются корректными числами.");
        }
        catch (DivideByZeroException ex)
        {
            Console.WriteLine($"Ошибка: {ex.Message}");
        }
        catch (Exception ex)
        {
            Console.WriteLine($"Произошла непредвиденная ошибка: {ex.Message}");
        }
        finally
        {
           
        }

        Console.WriteLine("Нажмите любую клавишу для выхода");
        Console.ReadKey();
    }
}
