```c
#pragma once
#include<stdio.h>
#include<stdlib.h>
#include<math.h>
#include<stdbool.h>
#include<assert.h>

#define STACK_INIT_SIZE 100//存储空间初始分配量
#define STACKINCREMENT 10//存储空间分配增量
#define SElemType int
//typedef char SElemType;//也是可以的

typedef struct {
	SElemType* base;
	SElemType* top;
	int stacksize;
}SqStack;

void InitStack(SqStack* S);
void DestroyStack(SqStack* S);
void ClearStack(SqStack* S);
bool StackEmpty(SqStack* S);
int StackLength(SqStack S);
SElemType GetTop(SqStack S);//直接把栈顶元素传入参数表中的e（需要传入地址）中
void Push(SqStack* S, SElemType e);
void Pop(SqStack* S, SElemType* e);
```

