## 概念

* **程序\(Program\)** 如果一个项的类型为规范说明，则它被称为一个程序
* **辖域** 定义了符号该如何解释
* **声明** 把一个标识符和一个类型相关联，但并不给出标识符的值
* **定义** 给标识符一个合法的项
* **变量** 局部声明或定义的标识符
* **常量** 全局定义的标识符
* **全局变量** 全局声明的标识符
* **栖息类型** 如果在环境和上下文中，存在一个项t使得t的类型是A，则称类型A是栖息的
* **自由** 如果一个变元v的出现不在为v所绑定的作用域中，那么变元v是自由的，否则v就是约束的
* **alpha变换** 约束变元的重命名操作，具有等价关系
* **首类型** 
* **终极类型**
* **规范说明\(Specification\)** 如果一个项的类型为Set，则它被称为一个规范说明
* **规范说明的实现** 如果t是类型A的项，则称t为A的一个实现
* **规约的强正则性** 给定项的任何规约序列都是有限的
* **规约的合流性** 如果使用不同的规约序列，t可以分别转化为t1和t2，则存在t3使得t1和t2均能规约为t3
* **谓词** 返回命题的函数
* **依赖类型** 把谓词应用到表达式上而获得的类型称为依赖类型

## 符号表示

* 环境 $$E$$
* 上下文 $$\Gamma$$
* 空上下文 $$[]$$
* 声明 $$(v:A)$$
* 声明序列 $$[v_1:A_1;v_2:A_2;...;v_n:A_n]$$
* 加入声明 $$\Gamma :: (v:A)$$
* 声明的存在性 $$(v:A) \in \Gamma$$
* 类型判断 $$E,\Gamma \vdash t:A$$
* 替换 2.4.1
* 规约 2.4.3
* 可转换 2.4.4

## 推理规则（省去部分冗余符号）

* 标识符 $$\begin{eqnarray}
    Var \frac{(x:A)}{x:A}
  \end{eqnarray}$$

* 函数作用 $$\begin{eqnarray}
  App \frac{e_1:A \rightarrow B \quad  e_2:A}{e_1 \ e_2: B}
  \end{eqnarray}$$

* 函数作用 $$\begin{eqnarray}
  App^* \frac{e:A_1 \rightarrow  ... \rightarrow A_n \rightarrow B \quad e_i:A_i}{e \ e_1 \ ... \ e_n:B}
  \end{eqnarray}$$
  
- 函数作用-依赖积 $$\begin{eqnarray}
  App \frac{t_1:forall \ v:A,B \quad t_2:A}{t1 \ t2:B\{v/t_2\}}  
  \end{eqnarray}$$

* 抽象 $$\begin{eqnarray}
    Lam \frac{v:A \quad e:B}{fun \ v:A \Rightarrow e: A \rightarrow B}
  \end{eqnarray}$$

- 抽象-依赖积 $$\begin{eqnarray}
    Lam \frac{v:A \quad t:B}{fun \ v:A \Rightarrow t:forall \ v:A,B}
  \end{eqnarray}$$
* 4.2.2

* 局部绑定 Let-in 2.2.3.3
* Prod-Set
* Prod-Prop
* Prod-dep 4.1.1.3
* Prod 3.2.1.3
* 高阶类型 Prod-sup 4.1.1.6

## 规约规则

* delta-规约 用来将标识符的定义展开
* beta-规约 将具有`(fun v:T => e1) e2`形式的项转换为项`e1{v/e2}`
* zeta-规约 将局部绑定转化成不使用局部绑定结构的等价形式
* iota-规约 用来计算递归程序的

## 命题和证明

* **最小命题逻辑** 仅由命题变量和蕴含式构造而成
* **命题** 若P的类型为Prop，则它被称为一个命题
* **证明** 若项t的类型为命题，则它被称为一个证明项



