# C 函数与程序控制

下面我们来介绍一下 C 语言中一个非常重要的概念 - **函数 ( function ) **。首先就要先给函数下一个定义，函数就是完成特定任务的独立代码单元，这也就是说，一个函数肯定是要为了完成某种功能的，比如一个函数它能够执行加法运算，比如一个函数能交换两个数的值，还有一些函数可能只是为了打印某些东西等等。

当然也有函数定义出来什么都没有做，这就相当于是一个空函数，C 语言默认是允许空函数出现的，当然我们不推荐只定义一个空函数而什么都不做。

函数也可以把很多大的任务拆分成一个个小的任务，通过设计每个小的任务来完成一个大的功能。一个设计优良的函数能够把程序中不需要了解的细节隐藏起来，从而使整个程序结构更加清晰，降低程序的修改难度。

 C 语言程序由许多小的函数组成，一个程序会被保存在多个源文件中，每个文件可以单独编译，并可以与库中已编译过的函数一起加载。

下面我们通过一个例子来讨论一下函数是如何创建并使用的。

## 函数创建以及使用

函数的创建和使用会分为三个步骤：

* 函数原型 ( function type )：这个是创建函数定义，也叫函数清单，能够表明一个文件中有哪些函数。
* 函数调用 ( function call )：调用函数的位置，函数被定义出来肯定是要使用它的，在哪里使用的这个函数就被称为函数调用。
* 函数定义 ( function definition )：这个就是函数的具体要干的什么事儿，也就是函数的具体逻辑是什么。

这么一看，函数和变量简直一模一样了，函数需要原型、调用和定义，而变量也需要这些，只不过变量还可以把原型和定义一起表示。

```C
#include <stdio.h>

int num; // 变量原型 

int sum(int,int); // 函数原型 

int main(void){

	num = 12; // 变量定义 
	int num2 = 11; // 函数原型 + 函数定义 
	
	int all = sum(num,num2); // 变量使用 ，函数使用 
	printf("all = %d",all);
	
	return 0;
} 

// 函数定义 
int sum(int a,int b){
	
	return a + b;
	
}
```

上面这段代码很好的列举了变量的定义以及函数的定义。

我们首先定义了一个 num 变量，这个就是变量的原型，然后在 main 函数中使用这个变量，就是变量的定义和使用，当然变量也可以直接使用原型 + 定义的方式（ 上面的 num2 ），sum 函数演示了函数的原型、定义和使用。这里注意一点，main 函数比较特殊，它是所有方法的入口，而且 main 函数无需定义原型就能直接使用。

上面这段代码被一起保存在一个文件中，当然你也可以把它们保存在不同的文件中，只不过把它们放在同一个文件中我们在演示的时候比较方便，还有一点就是**能够一起进行编译**，这两个函数也可以定义在不同的文件中，分别进行编译，这样的好处是使程序更加易于维护，代码读起来更加顺畅，事实上项目中也是采用的分别编译的方式。当然你也可以把所有的功能都写在 main 函数中，只不过这样不易于维护，也不符合项目开发标准。














