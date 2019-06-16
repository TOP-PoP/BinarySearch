# BinarySearch
Position BinarySearch( List L, ElementType X ){              //  my code
    int middle,right,left;
    left = 1;
    right = L->Last;
    middle = left + right/2;
    if(X > L->Data[right] || X < L->Data[left]){
        return NotFound;
    }else{
        while(left <= right  /*X != L->Data[middle]*/){
            if(X > L->Data[middle]){
                left = middle + 1;
            }else if(X < L->Data[middle]){
                right = middle - 1;
            }else if(X == L->Data[middle]){
                return middle;
            }else return NotFound;
            middle = (right + left)/2;
        }
        return NotFound;
    }
}

/*  initial code
#include <stdio.h>
#include <stdlib.h>

#define MAXSIZE 10
#define NotFound 0
typedef int ElementType;

typedef int Position;
typedef struct LNode *List;
struct LNode {
    ElementType Data[MAXSIZE];
    Position Last; /* 保存线性表中最后一个元素的位置 */
};

List ReadInput(); /* 裁判实现，细节不表。元素从下标1开始存储 */
Position BinarySearch( List L, ElementType X );

int main()
{
    List L;
    ElementType X;
    Position P;

    L = ReadInput();
    scanf("%d", &X);
    P = BinarySearch( L, X );
    printf("%d\n", P);

    return 0;
}
*/
