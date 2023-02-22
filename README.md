//Задайте двумерный массив. Напишите программу, которая упорядочит по убыванию элементы каждой строки двумерного массива.
//Например, задан массив:
//1 4 7 2
//5 9 2 3
//8 4 2 4
//В итоге получается вот такой массив:
//7 4 2 1
//9 5 3 2
//8 4 4 2

Console.WriteLine("Введите количество строк: ");

int m = Convert.ToInt32(Console.ReadLine());

Console.WriteLine("Введите количество столбцов: ");

int n = Convert.ToInt32(Console.ReadLine());

int[,] a = new int[m,n];

for (int i = 0; i < m;i++)

{

    for (int j =0; j<n; j++)
    
    {
    
        a[i,j] = new Random().Next(0,100);
        
        Console.Write(string.Format("{0} ", a[i, j]));
        
    }
    
    Console.Write(Environment.NewLine + Environment.NewLine);
    
}

for (int i = 0; i < m;i++)

{

    for (int j =0; j<n; j++)
    
    {
    
        for (int k = j; k<n; k++){
        
        if (a[i,j]<a[i,k])
        
        {
        
            int p = a[i,j];
            
            a[i,j] = a[i,k];
            
            a[i,k] = p;
            
        }
        
    }
    
    }
    
}

Console.WriteLine("Отсортированная матрица: ");

Console.Write(Environment.NewLine + Environment.NewLine);

for (int i = 0; i < m;i++)

{

    for (int j =0; j<n; j++)
    
    {
        Console.Write(string.Format("{0} ", a[i, j]));
    }
    
    Console.Write(Environment.NewLine + Environment.NewLine);
    
}
