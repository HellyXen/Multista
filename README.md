Görseldeki "Multiple Stacks" uygulamasını C# ile yazılmış bir kod olarak istiyorsanız, aşağıda temel bir C# kodu paylaşıyorum. Bu kod, iki stack (yığın) içeren basit bir programdır ve kullanıcının seçimlerine göre stack'lere eleman ekleme, çıkarma ve görüntüleme işlemleri yapmasını sağlar.

C# ile Multiple Stacks Uygulaması

using System;
using System.Collections.Generic;

class MultipleStacks
{
    static Stack<int> stackA = new Stack<int>();
    static Stack<int> stackB = new Stack<int>();

    static void Main()
    {
        while (true)
        {
            Console.WriteLine("\n********MENU********");
            Console.WriteLine("1. PUSH IN STACK A");
            Console.WriteLine("2. PUSH IN STACK B");
            Console.WriteLine("3. POP FROM STACK A");
            Console.WriteLine("4. POP FROM STACK B");
            Console.WriteLine("5. DISPLAY STACK A");
            Console.WriteLine("6. DISPLAY STACK B");
            Console.WriteLine("7. EXIT");
            Console.Write("Enter your choice: ");

            int choice = Convert.ToInt32(Console.ReadLine());

            switch (choice)
            {
                case 1:
                    PushStack(stackA, "A");
                    break;
                case 2:
                    PushStack(stackB, "B");
                    break;
                case 3:
                    PopStack(stackA, "A");
                    break;
                case 4:
                    PopStack(stackB, "B");
                    break;
                case 5:
                    DisplayStack(stackA, "A");
                    break;
                case 6:
                    DisplayStack(stackB, "B");
                    break;
                case 7:
                    Console.WriteLine("Exiting...");
                    return;
                default:
                    Console.WriteLine("Invalid choice! Please enter a valid option.");
                    break;
            }
        }
    }

    static void PushStack(Stack<int> stack, string stackName)
    {
        Console.Write($"Enter value to push on Stack {stackName}: ");
        int value = Convert.ToInt32(Console.ReadLine());
        stack.Push(value);
        Console.WriteLine($"Value {value} pushed to Stack {stackName}.");
    }

    static void PopStack(Stack<int> stack, string stackName)
    {
        if (stack.Count > 0)
        {
            int value = stack.Pop();
            Console.WriteLine($"Popped value from Stack {stackName}: {value}");
        }
        else
        {
            Console.WriteLine($"Underflow! Stack {stackName} is empty.");
        }
    }

    static void DisplayStack(Stack<int> stack, string stackName)
    {
        Console.Write($"Contents of Stack {stackName}: ");
        if (stack.Count > 0)
        {
            foreach (var item in stack)
            {
                Console.Write(item + " ");
            }
            Console.WriteLine();
        }
        else
        {
            Console.WriteLine("Stack is empty.");
        }
    }
}

Kod Açıklaması:

Stack<int> stackA ve stackB: İki farklı yığın (stack) tanımladık.

PushStack(): Kullanıcının bir yığına eleman eklemesini sağlar.

PopStack(): Yığından eleman çıkarmasını sağlar.

DisplayStack(): Yığının içeriğini görüntüler.

Ana döngü (while true): Kullanıcının seçimlerini alır ve ilgili işlemleri yapar.


Bu kod, görseldeki çıkışa benzer bir çalışma sunacaktır. Eğer belirli bir geliştirme ya da değişiklik isterseniz, bildirin!

