# <a name="main"></a> 众象科技JavaScript代码规范
## <a name="hy-ruleList"></a>规范目录

* [Rule 1. 字符串`“”`的双引号是首选，字符用单引号`''`](#T-rule1)
* [Rule 2. 缩进使用四个空格](#T-rule2)
* [Rule 3. 尽量避免使用太长的字符串（最多长度80个字符）](#T-rule3)
* [Rule 4. 在声明变量的时候总是用 `let|const`, 不允许使用var](#T-rule4)
* [Rule 5. 所有的变量和函数都必须先定义再使用](#T-rule5)
* [Rule 6. 永远记住使用";"，禁止依靠自动分号插入（ASI)](#T-rule6)
* [Rule 7. 命名约定-通常使用camelCase和...](#T-rule7)
* [Rule 8.使用新的空行来划分一组逻辑上相关联的代码片段](#T-rule8)
* [Rule 9. 聪明的写注释，最理想地是编写自注释的代码](#T-rule9)
* [Rule 10. 不要声明多行字符串](#T-rule10)
* [Rule 11. 始终将花括号与要打开的花括号的代码放在同一行](#T-rule11)
* [Rule 12. 使用空格来区分逻辑上相关的代码部分](#T-rule12)
* [Rule 13. 使用换行符对与逻辑相关的代码片段进行分组](#T-rule13)
* [Rule 14. `eval` is Evil](#T-rule14)
* [Rule 15. 始终使用非阻塞I / O函数](#T-rule15)
* [Rule 16. 命名约定-通常使用camelCase和...](#T-rule16)
* [Rule 17. 使用`Array` 和 `Object`的字面量形式，而不是是它们的构造形式](#T-rule17)
* [Rule 18. 数组和对象初始化表达式](#T-rule18)
* [Rule 19. 注意不直观的布尔表达式](#T-rule19)
* [Rule 20. 如果可能，所有函数参数都应在同一行上列出，否则以高可读性方式分离它们](#T-rule20)
* [Rule 21. 你不应当使用 `for-in`, 对arrays 或者 objects 进行循环](#T-rule21)
* [Rule 22. 不建议使用 `with`](#T-rule22)
* [Rule 23. 你应当使用嵌套函数](#T-rule23)
* [Rule 24. 切勿修改内置对象的原型（如“对象”或“数组”）](#T-rule24)
* [Rule 25. `&&`和`||`二进制布尔运算符是短循环的，只有在必要时才会计算到最后一项](#T-rule25)
* [Rule 26. 如果不需要，请勿修改函数中的输入参数](#T-rule26)
* [Rule 27. 更改输入参数的函数应具有建议输入的名称](#T-rule27)
* [Rule 28. 除非完全确定要使用`==`运算符，否则使用`===`代替`==`](#T-rule28)
* [Rule 29. 不同模块导入的默认命名遵循变量命名规范](#T-rule29)
* [Rule 30. ES模块文件必须使用import语句来导入其他ES模块文件。 请勿require另一个ES模块。](#T-rule30)
* [Rule 31. 不同模块导入的默认命名遵循变量命名规范](#T-rule31)
* [Rule 32. ES模块中不能循环依赖](#T-rule32)
* [Rule 33. 不要通过length遍历列表](#T-rule33)


## <a name="hy-languageRules"></a>语言规范

### <a name="T-rule1"></a>Rule 1. 字符串`“”`的双引号是首选，字符用单引号`''`

![原理](/images/help_16.png) 原理:  

为了公司统一代码风格。

### <a name="T-rule2"></a>Rule 2. 缩进使用四个空格

![原理](/images/help_16.png) 原理:  

缩进单位为四个空格。 禁止使用制表符，因为（截至21世纪撰写本文时）仍然没有制表符位置的标准。 虽然使用空格比制表符产生更大的文件大小，但是这点变化对于在本地网络上传输并不起到明细变化。

### <a name="T-rule3"></a>Rule 3. 尽量避免使用太长的字符串（最多长度80个字符）

 ![原理](/images/help_16.png) 原理:  

当一条语句不能放在一行中时，上下文几乎变得不可读，可能没有必要破坏它。 将中断放在运算符之后，最好放在逗号之后。

### <a name="T-rule4"></a>Rule 4. 在声明变量的时候总是用 `let|const`, 不允许使用var

![原理](/images/help_16.png) 原理:  

如果您未能指定`let | const`，该变量将被放置在全局上下文中，从而有可能破坏现有值。 另外，如果没有声明，就很难说出变量在哪个作用域中生存。 所以总是用`let | const`声明。

![注意](/images/warning.png)**注意**：let => 用于声明块级的局部变量，const => 声明块级域的只读局部变量。



### <a name="T-rule5"></a>Rule 5. 所有的变量和函数都必须先定义再使用

![原理](/images/help_16.png) 原理:  
虽然JS不是强制先定义再使用，但是这样做的可让阅读代码和理解变得更简单，并且能够更容易发现因为隐式提升为全局变量。隐式的全局变量应该尽量避免，并且应该尽量少的使用全局变量。



### <a name="T-rule6"></a>Rule 6. 永远记住使用";"，禁止依靠自动分号插入（ASI)

![原理](/images/help_16.png) 原理:  

大多数情况下，分号并非必不可少，不过for的分号是必须的。如果缺少分号，JS为自动为代码补上分号，这样可能无意间改变代码逻辑。如果仅仅只是为了“代码的美观”，省去一些键盘输入，这样有点得不偿失，所以建议在所有的地方加上分号，避免ASI无意间改变代码逻辑。

*  依赖隐式插入分号会导致难以调试的细微问题。
*  JavaScript要求语句以分号结尾，除非你认为可以安全地推断其存在位置。
*  如果下一个标记是中缀或括号运算符，则Javascript永远不会结束语句。

![注意](/images/warning.png)**注意**：函数表达式的最后必须使用分号，而函数的申明形式却不使用分号

```javascript
let foo = function() {
    return true;
}; // Semicolon here

function foo() {
    return true;
} // No semicolon here
```

***

### <a name="T-rule7"></a>Rule 7. 命名约定-通常使用camelCase和...

![原理](/images/help_16.png) 原理:  
通常，请使用`functionNamesLikeThis`，`variableNamesLikeThis`，`ClassNamesLikeThis`，`EnumNamesLikeThis`，`methodNamesLikeThis`，`CONSTANT_VALUES_LIKE_THIS`，`foo.namespaceNamesLikeThis.bar`和`fileNamesLikeThis.js`。

* 请勿在名称中使用$ *（美元符号）*或\ *（反斜杠）*。
* 请勿使用_ *（下划线）*作为名称的第一个或最后一个字符。它有时旨在表示隐私，但实际上并不提供隐私。如果隐私很重要，请使用提供[私人成员]（http://javascript.crockford.com/private.html）的表格。
* 大多数变量和函数应以小写字母开头。
* 必须与[`new`前缀]（http://yuiblog.com/blog/2006/11/13/javascript-we-hardly-new-ya/）一起使用的构造函数应以大写字母开头。如果省略了必需的新代码，JavaScript既不会发出编译时警告，也不会发出运行时警告。如果不使用“ new”，可能会发生不好的事情，因此大写约定是我们唯一的辩护。
* 全局变量应大写。 （JavaScript没有宏或常量，因此使用所有大写字母来表示JavaScript没有的功能没有多大意义。）

### <a name="T-rule8"></a>Rule 8.使用新的空行来划分一组逻辑上相关联的代码片段

使用新的空行来划分一组逻辑上相关联的代码片段。例如：

```
doSomethingTo(x);
doSomethingElseTo(x);
andThen(x);

nowDoSomethingWith(y);

andNowWith(z);
```

### <a name="T-rule9"></a>Rule 9. 聪明的写注释，最理想地是编写自注释的代码

![原理](/images/help_16.png) 原理:  

留下一些信息，以便以后需要了解您所做工作的人员（可能是您自己）阅读。 注释应写得清晰，清晰，就像注释的代码一样。 偶尔的幽默可能会受到赞赏。 挫败感和怨恨不会。

重要的是要保持评论最新。 错误的注释会使程序更难以阅读和理解。

使评论有意义。 专注于不立即可见的内容。 不要在诸如此类的东西上浪费读者的时间：

```javascript
i = 0; // Set i to zero.
```

### <a name="T-rule10"></a>Rule 10. 不要声明多行字符串

![原理](/images/help_16.png) 原理:  

![badExample][badExample] Here:

```javascript
const myString = "A rather long string of English text, an error message \
                actually that just keeps going and going -- an error \
                message to make the Energizer bunny blush (right through \
                those Schwarzenegger shades)! Where was I? Oh yes, \
                you\'ve got an error and all the extraneous whitespace is \
                just gravy. Have a nice day.";
```

在编译时不能安全地剥离每行开头的空白。 斜杠后的空格将导致棘手的错误，尽管大多数脚本引擎支持此错误，但它不是ECMAScript的一部分。

![goodExample][goodExample] 请使用字符串串联：

```javascript
const myString = "A rather long string of English text, an error message " +
    "actually that just keeps going and going -- an error " +
    "message to make the Energizer bunny blush (right through " +
    "those Schwarzenegger shades)! Where was I? Oh yes, " +
    "you\'ve got an error and all the extraneous whitespace is " +
    "just gravy. Have a nice day.";
```

### <a name="T-rule11"></a>Rule 11. 始终将花括号与要打开的花括号的代码放在同一行

![原理](/images/help_16.png) 原理:  

函数名称与其参数列表的（（* *（左括号）*）之间不应有空格。`）*（右括号）*与`{* *（ 左花括号）*，开始执行语句主体。 身体本身缩进了四个空格。 “}”（右花括号）*与包含函数声明开头的行对齐。

```javascript
function outer(c, d) {
    let e = c * d;

    function inner(a, b) {
        return (e * a) + b;
    }

    return inner(0, 1);
}
```

如果函数文字是匿名的，则单词“ function”和`（（* *（左括号）*）之间不应有空格。

```javascript
div.onclick = function(e) {
    return false;
};

that = {
    method: function() {
        return this.datum;
    },
    datum: 0
};
```

***

### <a name="T-rule12"></a>Rule 12. 使用空格来区分逻辑上相关的代码部分

![原理](/images/help_16.png) 原理:  

空行通过设置逻辑上相关的代码段来提高可读性。
在以下情况下应使用空格：

* 关键字（“ function”除外）后跟“（” *（左括号）*，应用空格分隔。`while (true) {`
* 在函数值（或匿名函数的关键字`function`）与其`（（* *（左括号）*）`之间不能使用空格。
* 除`.` *（句点）*和`（`*（左括号）*和`[`*（左括号）*外的所有二进制运算符应与它们的操作数之间用空格分隔。
* 一元运算符及其操作数之间不能有空格分开，除非运算符是诸如“ typeof”之类的单词。
* for语句的控制部分中的每个`;`*（分号）*后面应加一个空格。
* 空格应跟随每个`，`*（逗号）*。

### <a name="T-rule13"></a>Rule 13. 使用换行符对与逻辑相关的代码片段进行分组

![原理](/images/help_16.png) 原理:  

这样可以提高代码的可读性并跟踪方案的流程。

### <a name="T-rule14"></a>Rule 14. `eval` is Evil

![原理](/images/help_16.png) 原理:  

eval函数是JavaScript中最常被滥用的功能。 避开它。

1.不正确地使用eval会使您的代码遭受注入攻击
2.调试可能会更具挑战性（没有行号等）
2.评估的代码执行速度较慢（没有机会编译/缓存评估的代码）

### <a name="T-rule15"></a>Rule 15. 始终使用非阻塞I / O函数

![原理](/images/help_16.png) 原理:  

Node.js是单线程运行时环境，使用阻塞的I / O函数会影响整个应用程序并使它无响应。

![badExample][badExample] Bad example

```javascript
let fs = require("fs");
let fileContent = fs.readFileSync("filename.ext", "utf8");

doSomeAction(fileContent);
```

![goodExample][goodExample] Good example

```javascript
let Promise = require("bluebird");
let fs = Promise.promisifyAll(require("fs"));

fs.readFileAsync("filename.ext", "utf8").then(doSomeAction);
```

***

### <a name="T-rule16"></a>Rule 16. 始终使用async/await或者Promises编写异步代码

![原理](/images/help_16.png) 原理:  

当链接多个异步操作时，回调往往变得越来越嵌套。 这会混淆代码，并使操作流程难以遵循。

承诺极大地提高了此类代码的可读性，并使它看起来像是同步代码，因此操作流程易于遵循。 它还将压痕减少到几乎单个水平。

![badExample][badExample] Bad example

```javascript
doSomeAsyncOperation(param, function(err, result) {
    if (err) {
        return handleError(err);
    }
    return anotherAsync(result, function(err, something) {
        if (err) {
            return handleSpecificError(err);
        }
        var nextArg = syncOp(something);
        return anotherCallbackedOperation(nextArg, function(err, whatever) {
            if (err) {
                return handleError(err);
            }
            return youCanSeeWhereItIsGoing(whatever, function(err, yeah) {
                if (err) {
                    return handleError(err);
                }
                return toBeautifulChristmasTree(yeah, function(err, bummer) {
                    if (err) {
                        return handleError(err);
                    }
                    return soHardToReadAndThisHasOnlyLinearFlow(bummer);
                });
            });
        });
    });
});
```

![goodExample][goodExample] Good example

```javascript
doSomeAsyncOperation(param)
    .then(anotherAsync)
    .then(function(something) {
        return anotherPromisifiedOperation(syncOp(something));
    })
    .then(nowYouCanSee)
    .then(thatThisIsMuchEasierToRead)
    .then(andFollow)
    .then(especiallyWhenYouDefineAllStepsAsSeparateFunctions)
    .then(thereIsNoChristmasTreeAtTheEnd)
    .catch(specificError, alsoErrorsAreEasierToHandle)
    .catch(asYouCanHandleThemAlsoInGenericWay);
```

```javascript
const alsoAsyncFunction = async () => {
    try {  
        const operResult = await doSomeAsyncOperation(param);
        const antherResult = await anotherPromisifiedOperation(syncOp(operResult));
        const youCanSeeResult = await nowYouCanSee(antherResult)
        await andFollow(youCanSeeResult)
        await especiallyWhenYouDefineAllStepsAsSeparateFunctions()
        await thereIsNoChristmasTreeAtTheEnd()
    } catch (err) {
        alsoErrorsAreEasierToHandle(err);
    }
}
```

***

### <a name="T-rule17"></a>Rule 17. 使用`Array` 和 `Object`的字面量形式，而不是是它们的构造形式

![原理](/images/help_16.png) 原理:  

![warning][warning] 数组构造函数由于其参数而容易出错。

因为，如果有人更改代码以传递1个参数而不是2个参数，则数组可能没有预期的长度：

```javascript
// Length is 3.
let a1 = new Array(x1, x2, x3);

// Length is 2.
let a2 = new Array(x1, x2);

// If x1 is a number and it is a natural number the length will be x1.
// If x1 is a number but not a natural number this will throw an exception.
// Otherwise the array will have one element with x1 as its value.
let a3 = new Array(x1);

// Length is 0.
let a4 = new Array();
```

为了避免出现这种奇怪的情况，请始终使用可读性更高的数组文字：

```javascript
let a = [x1, x2, x3];
let a2 = [x1, x2];
let a3 = [x1];
let a4 = [];
```

![remark][remark] 对象构造函数没有相同的问题，但是为了提高可读性和一致性，应使用对象文字形式。 所以下面的代码：

```javascript
let o = new Object();

let o2 = new Object();
o2.a = 0;
o2.b = 1;
o2.c = 2;
o2["strange key"] = 3;
```

应当写为：

```javascript
let o = {};

let o2 = {
    a: 0,
    b: 1,
    c: 2,
    "strange key": 3
};
```

![remark][remark] 当成员名称为连续整数时，请使用数组。 成员名称是任意字符串或名称时，请使用对象。

### <a name="T-rule18"></a>Rule 18. 数组和对象初始化表达式

多行数组和对象初始化表达式缩进两个空格，括号的处理就像块一样单独成行。

```
//对象初始化表达式
var inset = {
  top: 10,
  right: 20,
  bottom: 15,
  left: 12
};

//数组初始化表达式
this.rows_ = [
  '"Slartibartfast" <fjordmaster@magrathea.com>',
  '"Zaphod Beeblebrox" <theprez@universe.gov>',
  '"Ford Prefect" <ford@theguide.com>',
  '"Arthur Dent" <has.no.tea@gmail.com>',
  '"Marvin the Paranoid Android" <marv@googlemail.com>',
  'the.mice@magrathea.com'
];

//在方法调用中使用
goog.dom.createDom(goog.dom.TagName.DIV, {
  id: 'foo',
  className: 'some-css-class',
  style: 'display:none'
}, 'Hello, world!');
```

长标识符或值在对齐的初始化列表中存在问题，所以初始化值不必对齐。例如：

```
CORRECT_Object.prototype = {
  a: 0,
  b: 1,
  lengthyName: 2
};
```

不要像这样：

```
WRONG_Object.prototype = {
  a          : 0,
  b          : 1,
  lengthyName: 2
};
```

### <a name="T-rule19"></a>Rule 19. 注意不直观的布尔表达式

![原理](/images/help_16.png) 原理:  

以下是布尔表达式中的false

* `null`
* `undefined`
* `""` -- 空字符串
* `0` -- 数字0

![warning][warning]： 但是要小心，因为这些都是true：

* `"0"` -- 字符串”0”
* `[]` -- 空数组
* `{}` -- 空对象

下面这样写不好：

```
while (x != null) {
```

你可以写成这种更短的代码（只要你不期望x为0、空字符串或者false）：

```
while (x) {
```

如果你想检查字符串是否为null或空，你可以这样写：

```
if (y != null && y != '') {
```

但是以下这样会更简练更好：

```
if (y) {
```

注意：还有很多不直观的关于布尔表达式的例子，这里是一些：

- Boolean(‘0’) == true ‘0’ != true
- 0 != null 0 == [] 0 == false
- Boolean(null) == false null != true null != false
- Boolean(undefined) == false undefined != true undefined != false
- Boolean([]) == true [] != true [] == false
- Boolean({}) == true {} != true {} != false

### <a name="T-rule20"></a>Rule 20. 如果可能，所有函数参数都应在同一行上列出，否则以高可读性方式分离它们

![原理](/images/help_16.png) 原理:  

如果可能，应该在同一行上列出所有函数参数。如果这样做将超出每行80个字符的限制，参数必须以一种可读性较好的方式进行换行。为了节省空间，在每一行你可以尽可能的接近80个字符，或者把每一个参数单独放在一行以提高可读性。缩进可能是四个空格，或者和括号对齐。下面是最常见的参数换行形式：

为了节省空间，您可以将每个参数放在自己的行上以提高 *可读性*。
Examples:

```javascript
// Four-space, one argument per line. Works with long function names,
// survives renaming, and emphasizes each argument.
// Arguments are indented twice to show separation with function code.
mz.foo.bar.baz.doThatThingThatIsVeryDifficultToExplain = function(
        veryDescriptiveArgumentNumberOne,
        anotherVeryDescriptiveArgumentNumberTwo,
        tableModelEventHandlerProxyThing,
        descriptorAdapterIteratorControllerThing) {
    // ...
};
// Keep 'em aligned
if ((functionA() === functionB()) ||
    (functionC() && functionD())) {
    // ...
}

if (searchableCollection(allYourStuff).contains(stuffYouWant) &&
    !ambientNotification.isActive() &&
    (client.isAmbientSupported() ||
     client.alwaysTryAmbientAnyways())) {
    // ...
}

let stuff = foo.bar.myExcellentMapFunction(
    someCollectionNameThatVeryLong,
    function(item) {
        // ...
    }
    // ...
);
```

### <a name="T-rule21"></a>Rule 21. 你不应当使用 `for-in`, 对arrays 或者 objects 进行循环

![原理](/images/help_16.png) 原理:  
在函数式编程中不使用此类循环，而应使用诸如map或each（forEach）之类的概念来遍历容器。 还有一些实用程序可以将对象键/值转换为数组，以后可以在该数组上进行迭代。 “ for-in”循环通常不正确地用于循环数组中的元素。 但是，这很容易出错，因为它不会从“ 0”循环到“ length-1”，而是遍历对象及其原型链中的所有当前键。

**注意**：breack 没有办法中止或跳出 `forEach` 循环。如果你需要中止或跳出循环，`forEach()` 方法不是应当使用的工具。若你需要提前终止循环，你可以使用：

- 一个简单的 [for](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/for) 循环

以下是几种失败的情况：

```
function printArray(arr) {
    for (var key in arr) {
        print(arr[key]);
    }
}

printArray([0,1,2,3]);  //这样可以

var a = new Array(10);
printArray(a);  //这样不行

a = document.getElementsByTagName('*');
printArray(a);  //这样不行

a = [0,1,2,3];
a.buhu = 'wine';
printArray(a);  //这样不行

a = new Array;
a[3] = 3;
printArray(a);  //这样不行
```

在数组循环时常用的一般方式：

```
function printArray(arr) {
    var l = arr.length;
    for (var i = 0; i < l; i++) {
        print(arr[i]);
    }
}
```

### <a name="T-rule22"></a>Rule 22. 不建议使用 `with` 

不建议使用。

使用 `with` 会影响程序的语义。因为 `with` 的目标对象可能会含有和局部变量冲突的属性，使你程序的语义发生很大的变化。例如，这是做什么用？

 例如，这是做什么用？ 

```
with (foo) {
    var x = 3;
    return x;
}
```

 答案：什么都有可能。局部变量 `x` 可能会被 `foo` 的一个属性覆盖，它甚至可能有setter方法，在此情况下将其赋值为3可能会执行很多其他代码。不要使用 `with` 。 



***

### <a name="T-rule23"></a>Rule 23. 你应当使用嵌套函数

![原理](/images/help_16.png) 原理:  

嵌套函数非常有用，例如在创建延续和隐藏助手函数的任务中, 随时使用它们。 但是，内部函数应遵循函数表达式语句。 这有助于弄清楚其范围中包括哪些变量。
```javascript

function foo() {
    let innerFoo = function() { //函数表达式
        return true;
    }; 
    return true;
}
```

### <a name="T-rule24"></a>Rule 24. 切勿修改内置对象的原型（如“对象”或“数组”）

![原理](/images/help_16.png) 原理:  

严格禁止修改诸如Object.prototype和Array.prototype之类的内置函数。 修改其他内置函数（如Function.prototype）的危险性较小，但仍会导致难以调试生产中的问题，因此应避免。
***



***

### <a name="T-rule25"></a>Rule 25. `&&`和`||`二进制布尔运算符是短循环的，只有在必要时才会计算到最后一项

![原理](/images/help_16.png) 原理:  

二元布尔操作符是可短路的，只有在必要时才会计算到最后一项。

`||`被称为默认运算符，下面的写法不被提倡：

```javascript
function foo(opt_win) {
    let win;
    if (opt_win) {
        win = opt_win;
    } else {
        win = window;
    }
}
```

你应该写成这样

```javascript
function foo(opt_win) {
    let win = opt_win || window;
}
```

“&&” 也可以用来缩减代码。例如，以下这种写法可以被缩减：

```
if (node) {
  if (node.kids) {
    if (node.kids[index]) {
      foo(node.kids[index]);
    }
  }
}
```

你可以这样写：

```
if (node && node.kids && node.kids[index]) {
  foo(node.kids[index]);
}
```

或者这样写：

```
var kid = node && node.kids && node.kids[index];
  if (kid) {
    foo(kid);
}
```

然而以下这样写就有点过头了：

```
node && node.kids && node.kids[index] && foo(node.kids[index]);
```



### <a name="T-rule26"></a>Rule 26. 如果不需要，请勿修改函数中的输入参数

![原理](/images/help_16.png) 原理:  

这样可以提高代码的可重用性。

***

### <a name="T-rule27"></a>Rule 27. 更改输入参数的函数应具有建议输入的名称

![badExample][badExample] Bad example, do not do this:

```javascript
function calculateSomething(someObject) {
    someObject.calculations = someObject.a + someObject.b;
    return someObject.calculations;
}
```

![goodExample][goodExample] Good example

```javascript
function insertParameterToManagedObject(managedObject, parameter) {
    managedObject.parameters.push(parameter);
}
```



***

### <a name="T-rule28"></a>Rule 28. 除非完全确定要使用`==`运算符，否则使用`===`代替`==`

![原理](/images/help_16.png) 原理:  

您可以在https://dorey.github.io/JavaScript-Equality-Table/中找到`==`运算符的相等表。 如果您确定它是您想要的，则可以使用它。
***

### <a name="T-rule29"></a>Rule 29. 注意不要在+或++后面加上+

![原理](/images/help_16.png) 原理:  

这种模式可能会造成混淆。 在它们之间插入括号以使您的意图清楚：

```javascript
total = subtotal + +myInput.value;
```

is better written as:

```javascript
total = subtotal + (+myInput.value);
```

![warning][warning] 这样，“ + +”不会被误读为“ ++”。

***

***

### <a name="T-rule30"></a>Rule 30. ES模块文件必须使用import语句来导入其他ES模块文件。 请勿require另一个ES模块。

```javascript
import './sideeffects';

import * as goog from '../closure/goog/goog';
import * as parent from '../parent';

import {name} from './sibling';
```
![remark] 注意: .js文件扩展名在导入路径中不用填写。
![badExample][badExample] bad code example:

```javascript
import '../directory/file.js';
```

![goodExample][goodExample] good code example:
```javascript
import '../directory/file';
```

![remark] 注意: 不要多次导入同一文件。 这可能使确定文件的聚合导入变得困难。

![badExample][badExample] bad code example:
```javascript
// Imports have the same path, but since it doesn't align it can be hard to see.
import {short} from './long/path/to/a/file';
import {aLongNameThatBreaksAlignment} from './long/path/to/a/file';
```
![goodExample][goodExample] good code example:
```javascript
import {short, aLongNameThatBreaksAlignment} from './long/path/to/a/file';
```

***
### <a name="T-rule31"></a>Rule 31. 不同模块导入的默认命名遵循变量命名规范
```javascript
import MyClass from '../my-class';
import myFunction from '../my_function';
import SOME_CONSTANT from '../someconstant';
```
***
### <a name="T-rule32"></a>Rule 32. ES模块中不能循环依赖
![原理](/images/help_16.png) 原理:  

即使ECMAScript规范允许这样做，也不要在ES模块之间创建循环。 请注意，使用导入和导出语句也可能创建循环。

![badExample][badExample] bad code example:
```javascript
// a.js
import './b';

// b.js
import './a';

// `export from` can cause circular dependencies too!
export {x} from './c';

// c.js
import './b';

export let x;
```



### <a name="T-rule33"></a>Rule 33. 注意不直观的布尔表达式

![原理](/images/help_16.png) 原理:  

以下是布尔表达式中的false

* `null`
* `undefined`
* `""` -- 空字符串
* `0` -- 数字0

![warning][warning]： 但是要小心，因为这些都是true：

* `"0"` -- 字符串”0”
* `[]` -- 空数组
* `{}` -- 空对象

下面这样写不好：

```
while (x != null) {
```

你可以写成这种更短的代码（只要你不期望x为0、空字符串或者false）：

```
while (x) {
```

如果你想检查字符串是否为null或空，你可以这样写：

```
if (y != null && y != '') {
```

但是以下这样会更简练更好：

```
if (y) {
```

注意：还有很多不直观的关于布尔表达式的例子，这里是一些：

- Boolean(‘0’) == true ‘0’ != true
- 0 != null 0 == [] 0 == false
- Boolean(null) == false null != true null != false
- Boolean(undefined) == false undefined != true undefined != false
- Boolean([]) == true [] != true [] == false
- Boolean({}) == true {} != true {} != false



### <a name="T-rule34"></a>Rule 34. 不要通过length遍历列表

节点列表是通过给节点迭代器加一个过滤器来实现的。这表示获取他的属性，如length的时间复杂度为O(n)，通过length来遍历整个列表需要O(n^2)。

```
var paragraphs = document.getElementsByTagName('p');
for (var i = 0; i < paragraphs.length; i++) {
  doSomething(paragraphs[i]);
}
```

这样写更好：

```
var paragraphs = document.getElementsByTagName('p');
for (var i = 0, paragraph; paragraph = paragraphs[i]; i++) {
  doSomething(paragraph);
}
```

这种方法对所有的集合和数组(只要数组不包含被认为是false值的元素) 都适用。

在上面的例子中，你也可以通过firstChild和nextSibling属性来遍历子节点。

```
var parentNode = document.getElementById('foo');
for (var child = parentNode.firstChild; child; child = child.nextSibling) {
  doSomething(child);
}
```