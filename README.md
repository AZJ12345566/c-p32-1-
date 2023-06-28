# c-p32-1-
C语学习笔记 p32 指针详解(1)
#include<>stdio.h>
void test(int arr[])
{
    printf("%d\n",sizeof(arr)/sizeof(arr[]));
}//这里实际传过来的也是一个指针，在32位系统为4，所以输出为1
int main()
{
    int arr[10]={0;}
    test(arr);
    return 0;
}

int main()
{
    char ch='w';
    char* pc=&ch;
    return 0;
}
//源自
int main()
{
    char arr[]="abcdef";
    char* pc=arr;
    printf("%s\n",arr);
    printf("%s\n",pc);
    return 0;
}//这里的两个输出值都是abcdef，因为把arr的地址传给了pc，但pc传的是首元素地址这里时打印%s

int main()
{
    const char* p="abcdef";//这里的“abcdef”是一个常量字符串
    *p='W';//这里是编不过去的，常量字符串不能被修改，一般最好在常量字符串前面加const修饰
    printf("%c\n",*p)//这里的*p存的就是首字符a
    printf("%s\n",p);//这里打印的就是“abcdef”
    return 0;
}

//www.stackoverflow.com
//segmentfault.com//技术问答网站，类似国外的stackoverflow

int main()
{
    char arr1[]="abcdef";
    char arr2[]="abcdef";
    const char* p1="abcdef";
    const char* p2="abcdef";//这里最好加上const，是代码更加健壮
    if(arr1==arr2)
    {
        printf("hehe\n");
    }
    else
    {
        printf("haha\n");
    }//这里输出haha，因为这里时两个不同的常量数组，存储的首元素也是不同的地址，所以arr1！=arr2a
    return 0;
}



//指针数组其实是数组
int main()
{
    int arr[20]={0};//整形数组
    char ch[5]={0};//字符数组
    int* parr[4];//存放整形指针的数组-指针数组
    char* pch[5];//存放字符指针的数组-指针数组
    return 0;
}

int mian()
{
    int arr1[]={1,2,3,4,5};
    int arr2[]={2,3,4,5,6};
    int arr3[]={3,4,5,6,7};
    int* parr[]={arr1,arr2,arr3};

    int i=0;
    for(i=0;i<3;i++)
    {
        int j=0;
        for(j=0;j<5;j++)
        {
            printf("%d",*(parr[i]+j));
        }
        printf("\n");
    }
    return 0;
}
