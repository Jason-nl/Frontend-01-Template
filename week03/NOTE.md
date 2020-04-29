# 每周总结可以写在这里

----

##### JavaScript中特殊的对象

- Function Object

  - [[call]] 视为函数Function
  - [[Construct]] 可以被new 操作符调用，根据new的规则返回对象。

- Array Object

  - [[DefineOwnProperty]]

    - Property == length

      设置对象的length属性，根据length的变化对对象进行操作

      newLength > length 用空扩充数组

      newLength < length 截取数组

- String Object

  string的length是不可写不可配的。

- Arguments Object

  [[callee]] 视为函数参数对对象，伪数组 caller

- Object

  [[Get]] property被访问时调用 get

  [[Set]] property被赋值时调用 set

  [[GetPrototypeOf]] 对应getPrototypeOf方法 获取对象原型

  [[SetPrototypeOf]] 对应setPrototypeOf方法 设置对象原型

  [[GetOwnProperty]] getOwnPropertyDescriptor 获取对象私有属性的描述列表

  [[HasProperty]] hasOwnProperty 私有属性判断

  [[IsExtensible]] isExtensible对象是否可扩展

  [[PreventExtensions]] preventExtension控制对象是否可以添加属性

  [[DefineOwnProperty]] defineProperty 定义对象属性

  [[Delete]] delete 操作符

  [[OwnPropertyKeys]] Object.keys() Object.entries() Object.values()

  [[Call]] 能够调用call

- Module Namespece

  [[Module]] 视为一个引入的模块

  [[Exports]] 视为一个导出的模块

##### Left Handside & Right Handside

 Left Handside (赋值操作的目标) Reference 引用

 Right Handside (赋值操作的来源)

##### Left Handside

运算符

表达式树结构 => 表达式优先级

- Member

  ```
  a.b
  a[b]
  foo`string` // styles-compontents
  super.b
  super[b]
  new.target // 判断函数是否是new调用
  new Foo()
  ```

- New

  new Foo

- Call

  ```
  foo()
  super()
  foo()[b]
  foo().b
  foo()`string`
  ```

##### Right Handside

- Update

  ```
  a++
  a--
  --a
  ++a
  ```

- Unary

  ```
  delete a.b
  void 0; // 生成undefined
  typeof a
  +a
  -a
  ~a
  !a // !!a 转换为boolean值
  await a
  ```

- Exponental

  **

- Multiplicative

  \* / %

- Additive

  - - 

- Shift

  << >> >>>

- Relationship

  < > <= >= instanceof in

- Equality

  ```
  ==
  !=
  ===
  !==
  ```

- Bitwise 位运算

  & ^ |

- Logical

  && ||

  短路逻辑

  ```
  a && b  a为true时，b才会执行
  a || b  a或b为true，a或b才会执行
  ```

- Conditional

  ? :

##### 类型转换

- 基础类型

  - Undefined
  - Boolean
  - String
  - Number
  - Null
  - Symbol
  - BigInt
  - Object

- 装箱拆箱

  装箱：基础类型 => 包装类型 `Boolean String Boolean ...`

  拆箱：包装类型(Object) => 基础类型, 会优先调用`valueOf toString toPrimitive`进行转换

- 类型的判断

  - typeof
  - Obejct.prototype.toString.call
  - instanceof

- 隐式转换发生的场景

  - Left Handside Right Handside

    左右取值，转换为原始值，如果转换后的值存在string, 则进行toString后拼接。否则按toNumber处理

  - ==

    优先按照number处理

  - if

    优先按照boolean处理

  - 数学运算符

    优先转换非number为number



#### Statement

`简单语句`

- Expression Statement 表达式语句 `a = 1 + 2;`
- Empty Statement 空语句 `;`
- Debugger Statement debugger 运行时不产生作用 `debugger;`

- ThrowStatement 抛异常语句 `throw a;`

- Continue Statement 继续下一次的循环 `continue;`
- Break Statement 跳出循环语句或者Switch语句 `break;`

- Return Statement 返回值语句 `return; return expression;`

`组合语句`

- Block Statement `{}`
- Iteration Statement 
  - while()
  - do...while()
  - for(;;)
  - for...in...
  - for...or...

`声明`

- FunctionDeclaration

- GeneratorDeclaration

- AsyncFunctionDeclaration

- AsyncGeneratorDeclaration

- VariableStatement

- ClassDeclaration

- LexicalDeclaration

  

#### JS对象机制

`Object`

- 任何一个对象都是`唯一的`，这与它本身的状态无关
- 我们用`状态`来描述对象
- 状态的改变即`行为`
- 三大特性：封装（复用、依赖）、继承（单继承）、多态（父类作方法形参｜返回值）



`基于类的面向对象`

- 基类
- interface
- mixin



`Object in Javascript`

- Property

  - Key
    - Symbol
    - String
  - Value
    - Data Property
      - [[value]]
      - writable
      - emumerable
      - configurable
    - Accessor Property
      - get
      - set
      - emumerable
      - configurable

- [[Prototype]]

  原型链

##### Object API

- 基础API

  `{} . [] Object.defineProperty`

- 原型API

  `Object.create Object.setPrototypeOf Object.getPrototypeOf`

- 基于类的面向对象API(模拟)

  `new class extends`

- 基于原型的面向对象API

  `new function prototype`

