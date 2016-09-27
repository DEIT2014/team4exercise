###**1. dart语言特性中的循环语句定义和操作方法**
####**for loops**
```dart
var message = new StringBuffer("Dart is fun");
for (var i = 0; i < 5; i++)        {message.write('!');}
```
在for循环中还可以定义函数来对当前索引值进行操作
```dart
  main() {  
      var callbacks = [];  
      for (var i = 0; i < 2; i++) 
      {callbacks.add(() => print(i));}  
      callbacks.forEach((c) => c());} 
```
####**While and do-while**
  while 循环在循环前判断条件
```while (!isDone()) {doSomething();}```
  do-while 循环在循环后判断条件
```
do {printLine();} 
      while (!atEndOfPage());
```
####**Break and continue**
  break 用来停止循环
```
while (true) {
      if (shutDownRequested()) break;
      processIncomingRequests();}
```
  continue 用来继续循环
```
for (int i = 0; i < candidates.length; i++) {
      var candidate = candidates[i];
      if (candidate.yearsExperience < 5) {continue;}
      candidate.interview();}
```
####**Switch and case** 
  switch使用==来判断对象是否相等，每个非空的条款以break语句结束
```
var command = 'OPEN';
  switch (command) {
  case 'CLOSED':
    executeClosed();
    break;
  case 'PENDING':
    executePending();
    break;
  case 'APPROVED':
    executeApproved();
    break;
  case 'DENIED':
    executeDenied();
    break;
  case 'OPEN':
    executeOpen();
    break;
  default:
    executeUnknown();}
```
####**Assert**
  如果这个语句的条件是不成立的，那么这个程序就此中断。
```
  // Make sure the variable has a non-null value.
  assert(text != null);

  // Make sure the value is less than 100.
  assert(number < 100);

  // Make sure this is an https URL.
  assert(urlString.startsWith('https'));
```
###**2. dart字符串的定义和操作方法**
**定义字符串**：可用String（指定字符串类型）或var（没有指定变量类型）声明字符串变量，用单引号或双引号括起来的表示字符串
```
var s1 = 'Single quotes work well for string literals.';
var s2 = "Double quotes work just as well.";
```  
  
在字符串中可以使用表达式，${expression}，该表达式的值将会作为字符串的一部分。如果表达式只是一个变量，可以不加大括号，即：$var
```
var s ='string interpolation';  
      print('Dart has $s, which is very handy.');  
      print('That deserves all caps. ${s.toUpperCase()} is very handy!');  
``` 
  连接两个字符串：可以用相邻的字符串或“+”
```
  var s1 = 'String ' 'concatenation'" works even over line breaks.";
      assert(s1 == 'String concatenation works even over line breaks.');
      var s2 = 'The + operator '+ 'works, as well.';
      assert(s2 == 'The + operator works, as well.');
``` 
  
  比较字符串相等可以使用==号

  字符串是不可变对象，也就是说它的值一旦创建就不会再变。要使用可变字符串，可以使用StringBuffer对象，类似于java中的 StringBuffer类，它的值是  可变的，使用该对象的toString方法可以生成字符串。
```
      var sb = new StringBuffer();  
      sb.add("Use a StringBuffer");  
      sb.addAll(["for ", "efficient ", "string ", "creation "]);  
      sb.add("if you are ").add("building lots of strings.");  
      var fullString = sb.toString();  
      print(fullString);   
      sb.clear();  
```
###**3. dart函数定义和使用方法**
dart是一个真正的面向对象的语言，所以即使是函数也有对象、类型和功能。这意味着函数可以被分配给变量或作为参数传递给其他函数。你也可以调用一个类的实例，好像它是一个函数。详情见可调用的类。
、、、
bool isNoble(int atomicNumber) {
  return _nobleGases[atomicNumber] != null;
}
虽然有效的dart为公共的函数库推荐了类型注释，但如果省略了类型，函数仍然有效isNoble(atomicNumber) {
  return _nobleGases[atomicNumber] != null;
}
对于只包含一个表达式的函数，您可以使用速记语法：
bool isNoble(int atomicNumber) => _nobleGases[atomicNumber] != null;
The => expr syntax 是r { return expr; }.的缩写

###**4. dart中数组定义和使用方法**
在Dart中数组也叫列表list.

定义一个数组：

var list = [1,2,3];  
  操作数组：

var list = [1,2,3];  
print(list.length); // the # of elements: 3  
print(list[1]);     // the second item: 2  
  给数组添加元素：

var list = [1,2,3];  
list.add(4);  
  从数组中删除一定范围内的元素：

var list = [1,2,3,4];  
list.removeRange(2, 1); // remove the third element  
  创建固定长度的数组：

var list = new List(3); //fixed-size list (full of null values)  
 注意：固定长度的数组不能调用add,removeRange等方法改变其大小。

可以使用for, for...in, 或forEach()几种方式遍历数组，

使用for:
var list = [1,2,3];  
for (var x = 0; x < list.length; x++) {  
  print('$x: ${list[x]}');  
}  
  for...in:

var list = [1,2,3];  
for (final x in list) {  
  print(x);  
}  
  forEach():

var list = [1,2,3]  
void printElement(element) => print(element);  
list.forEach(printElement);  
  可更简洁的方式：
var list = [1,2,3];  
list.forEach((element) => print(element));  
  list的父类是Collection,它提供了一系列操作集合的方法。

###**5. dart中列表定义和使用方法**
Dart 语言中内置了常用的 List ，List 是 Collection 的子类型，另外 Queue 和 Set 也是 Collection 的子类型 。
一个简单的list：
```dart
var list = [1, 2, 3];
```
list使用从零开始的索引，其中0是第一个元素，列表长度减一是的最后一个元素的索引。
```dart
var list = [1, 2, 3];
assert(list.length == 3);
assert(list[1] == 2);

list[1] = 1;
assert(list[1] == 1);
```
创建一个列表为编译时常量，在list前添加const：
```dart
var constantList = const [1, 2, 3];
// constantList[1] = 1; // Uncommenting this causes an error.
```
###**6. dart中 Map定义和使用方法**
地图是包含指针和值得一个对象。
一个简单的地图：
```dart
var gifts = {
// Keys      Values
  'first' : 'partridge',
  'second': 'turtledoves',
  'fifth' : 'golden rings'
};
var nobleGases = {
// Keys  Values
  2 :   'helium',
  10:   'neon',
  18:   'argon',
};
```
您可以使用地图构造函数创建相同的对象：
```dart
var gifts = new Map();
gifts['first'] = 'partridge';
gifts['second'] = 'turtledoves';
gifts['fifth'] = 'golden rings';
var nobleGases = new Map();
nobleGases[2] = 'helium';
nobleGases[10] = 'neon';
nobleGases[18] = 'argon';
```
向现有的地图添加新的指针值：
```dart
var gifts = {'first': 'partridge'};
gifts['fourth'] = 'calling birds'; // Add a key-value pair
```
在地图中检索一个值：
```dart
var gifts = {'first': 'partridge'};
assert(gifts['first'] == 'partridge');
```
如果寻找一个不在地图上的指针，会得到空的返回值：
```dart
var gifts = {'first': 'partridge'};
assert(gifts['fifth'] == null);
```
使用.length来获取地图中指针对的数量：
```dart
var gifts = {'first': 'partridge'};
gifts['fourth'] = 'calling birds';
assert(gifts.length == 2);
```
创建一个地图为编译时常量，在地图上添加const：
```dart
final constantMap = const {
  2: 'helium',
  10: 'neon',
  18: 'argon',
};
// constantMap[2] = 'Helium'; // Uncommenting this causes an error.
```
###**7. querySelector（）函数的详细API解释**
**概述:**  返回第一个

**语法:**
```
element = document.querySelector(selectors);
```
其中
* element 是一个 element 对象（DOM 元素）。
* selectors 是一个字符串，包含一个或是多个 CSS 选择器 ，多个则以逗号分隔。

**例子**
这个例子中，会返回当前文档中第一个类名为 "myclass" 的元素：
```
var el = document.querySelector(".myclass");
```
**例子：一个强大的选择方式**
这个例子中，你将感受到selectors的强大。例子将返回<div class="user-panel main">标签中的<input name="login"/>标签。
```
<div class="user-panel main">
    <input name="login"/> //这个标签将被返回
</div>

<script>
    var el = document.querySelector("div.user-panel.main input[name=login]");
</script>
``` 
**注意**
*如果没有找到匹配元素，则返回 null，否则找到多个匹配元素，则返回第一个匹配到的元素。

*如果选择器是一个 ID，并且这个 ID 在文档中错误地使用了多次，那么返回第一个匹配该 ID 的元素。

*如果指定的选择器不合法，则抛出 SYNTAX_ERR 异常。

*querySelector()在 Selectors API 中引入。

*传递给 querySelector 的字符串参数必须符合 CSS 语法。

*CSS 伪类不会返回任何元素，见 Selectors API 中的相关规定。

*如果要匹配的ID或选择器不符合 CSS 语法（比如不恰当地使用了冒号或者空格），你必须用反斜杠将这些字符转义。由于 JavaScript 中，反斜杠是转义字符，所以当你输入一个文本串时，你必须将它转义两次（一次是为 JavaScript 字符串转义，另一次是为 querySelector 转义）：
```
<div id="foo\bar"></div>
<div id="foo:bar"></div>

<script>
  console.log('#foo\bar')               // "#fooar"
  document.querySelector('#foo\bar')    // 不匹配任何元素

  console.log('#foo\\bar')              // "#foo\bar"
  console.log('#foo\\\\bar')            // "#foo\\bar"
  document.querySelector('#foo\\\\bar') // 匹配第一个div

  document.querySelector('#foo:bar')    // 不匹配任何元素
  document.querySelector('#foo\\:bar')  // 匹配第二个div
</script>
```
###**8. 详细解释dart如何操作html的文档**
http://www.dartlang.cc/docs/tutorials/connect-dart-html/
###**9. dart web app 应用程序组织结构的解释部分**
https://webdev.dartlang.org/codelabs/ng2/1-skeleton#--what-did-you-get
###**10. dart可用的各种工具的解释部分**
*DartPad
 DartPad是一个很好学习Dart语法，实验dart语言特征和核心库的方式
 体验Dart语言，无需在电脑上安装Dart开发环境，可以使用Google提供的Dart云编译服务——DartPad。DartPad是一个自由、开放的源码服务，帮助开发人员学习Dart语言，进入DartPad的源代码会被发送到谷歌云计算平台上运行，服务器会将源代码进行编译并处理成JavaScript返回给浏览器，编译产生的错误和警告也会返回
 *IDES
 许多常用的IDE插件存在插件。如果你还没有一个喜欢的IDE，试试WebStorm，是dart语言支持下的。IDES 的全称是 Internet Demonstration and Evaluation System (互联网演示和评估系统)。IDES 是 SAP R/3 系统的一个演示版本，IDES 系统模拟了一个范例公司，该公司是一个在一些国家拥有分公司的国际集团。IDES 系统还包含了各种业务场景所需的应用数据。IDES 通过简单易懂的业务场景来演示 SAP R/3 系统的功能，这些业务流程都是为了反应现实生活中的业务需求而设置的。不过 IDES 的重点并不在于强调功能本身，而是在于业务流程以及业务流程之间的整合。
 *SDKs
软件开发工具包
 *Command-line tools命令行工具
 Pub package manager 包管理器
 管理dart包，便于用户安装、使用和分享库，命令行工具和其他。有些dart的技术如flutter可能不支持所有的pub命令。支持DART的软件开发包大体上支持pub，但是你也可以用命令行。(pub)
 Static analyzer静态分析
 评估报告代码中的错误或警告，dart的IDE插件运用dart的分析引擎，也可以通过命令行运行分析器(dartanalyzer)
 Static Analyzer是一个非常好的工具, 它可以帮助我们发现编译器警告不会提示的问题。
 Static Analysis 优点：
 1、使用操作容易。
 2、能够在编码阶段，开发自行进行代码检查。早期发现代码隐患。
 3、直接分析源代码来发现程序中的错误，而不需要实际运行。
 4、自动检测objective-C程序中的BUG，发现内存泄露和其它问题。
 5、内存问题发现越早，解决的代价就越小。
 
 Code formatter程序代码格式制作器
 支持dart的IDEs允许格式化代码，或者可以通过命令行来运行。 (dartfmt)
 
 Tools for the Web
 *Dartium
 用Dartium意味着在你准备在浏览器上测试前不用去Javascript上编译。
 不要用Dartium作为你的首要浏览器，也不要把Dartium散步给用户。
 *Webstorm
 *Command-line tools
 对于网站开发的命令行工具有：dart2js；dart2js；pub serve
###**11. 指引你到其他社区社区寻求dart相关问题帮助的解释部分**
官方网站：www.dartlang.org
其他学习资源：dart语言入门（附视频） http://dart.hanguokai.com/
Dart语言中文社区（可与他人交流学习）http://www.cndartlang.com/ 
###**12. 从web storm软件菜单找出webstrom 中dart开发的帮助文档**
https://confluence.jetbrains.com/display/WI/Getting+started+with+Dart


