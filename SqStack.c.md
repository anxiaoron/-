```c
#include"SqStack.h"

void InitStack(SqStack* S)
{
	S->base = (SElemType*)malloc(sizeof(SElemType) * STACK_INIT_SIZE);
	S->top = S->base;
	S->stacksize = STACK_INIT_SIZE;

}

void DestroyStack(SqStack* S)
{
	free(S->base);
	S->top = S->base;
	S->stacksize = 0;
}

void ClearStack(SqStack* S)
{
	S->top = S->base;
	S->stacksize = 0;
}

bool StackEmpty(SqStack* S)
{
	return S->top == S->base;
}

int StackLength(SqStack S)
{
	return S.top - S.base;
}

SElemType GetTop(SqStack S)
{
	assert(!StackEmpty(&S));

	SElemType e;
	e = *(S.top - 1);

	return e;
}

void Push(SqStack* S, SElemType e)
{
	if (StackLength(*S) == S->stacksize)//栈满，需要追加空间
	{
		S->base = (SElemType*)realloc(S->base, sizeof(SElemType) * (STACKINCREMENT + S->stacksize));
		if (!S->base) exit(OVERFLOW);

		S->top = S->base + S->stacksize;
		S->stacksize += STACKINCREMENT;
	}
	*(S->top++) = e;
	
}

void Pop(SqStack* S, SElemType* e)
{
	assert(!StackEmpty(S));//栈不能为空

	--S->top;
	*e = *(S->top);

}

```

