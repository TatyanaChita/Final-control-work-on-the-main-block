// Задача: Написать программу, которая из имеющегося массива строк формирует новый массив из строк, 
// длина которых меньше, либо равна 3 символам. Первоначальный массив можно ввести с клавиатуры, либо 
// задать на старте выполнения алгоритма. При решении не рекомендуется пользоваться коллекциями, лучше 
// обойтись исключительно массивами.
// Примеры:
// ["Hello", "2", "world", ":-)"] → ["2", ":-)"]
// ["1234", "1567", "-2", "computer science"] → ["-2"]
// ["Russia", "Denmark", "Kazan"] → []

// функция подсчета элементов массива, отвечающих каким то требваниям
int CountSpecialElements(string[] array)
{
    int count = 0;
    foreach (string elem in array)
    {
        if (elem.Length <= 3) //(элемент,отвечающий каким то требваниям)
        {
            count++;
        }
    }
    return count;
}

string[] CreateNewArray(string[] array, int len)
{
    string[] new_array = new string[len];
    int i = 0;
    foreach (string elem in array)
    {
        if (elem.Length <= 3) 
        {
            new_array[i] = elem;
            i++;
        }
    }
    return new_array;
}


string[] array = {"Russia", "Denmark", "Kazan"};

int count = CountSpecialElements(array);
string[] new_array = CreateNewArray(array, count);

// вывод массива строкой
Console.WriteLine("['" + string.Join("', '", new_array) + "']");
