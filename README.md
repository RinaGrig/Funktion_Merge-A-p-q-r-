# Funktion_Merge-A-p-q-r-
function in C++ programming language

#include <iostream>
#include <stack>
using namespace std;

//Быстрая сортировка (итеративный вариант алгоритма использую стек в явном виде)
const  int N = 8;
int mas[N] = { 5, 2, 4, 6, 1, 3, 2, 6 };

int p, r;
int left = 0, right = N - 1;
int pivot;
stack <int> stk;
stack.push(left);
stack.push(right);

do
{
    right = stk.top();
    stk.pop;
    left = stk.top();
    stk.pop;

    p = left;
    r = right;
    pivot = (p + r) / 2;

    //Основная сортировка, которая осуществлет предварительное упорядочение  отностельно левых и правых границ и относиительно центрального элемента. 
    //После первого срабатывания цикла в левой части массива будут значения меньшие чем центральное значение, а в правой - больше. 
    do
    {
        while(mas[p] < mas[pivot])
            p++;
        while(mas[r] > mas[pivot])
            r--;
        if(p <= r)

        {
            int t = mas[p];
            mas[p] = mas[r];
            mas[r] = t;
            p++;
            r--;
        }
    } 
    while(p <= r)

        if (left < r)
        {
            stack.push(left);
            stack.push(r);
        }

    if(right < p)
    {
        stack.push(p);
        stack.push(right);
    }
}
    while(!stk.empty());

    for(int p = 0; p < N; p++)
    {
        cout << mas[p] << " ";
    }
