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
###**4. dart中数组定义和使用方法**
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
###**8. 详细解释dart如何操作html的文档**
###**9. dart web app 应用程序组织结构的解释部分**
###**10. dart可用的各种工具的解释部分**
###**11. 指引你到其他社区社区寻求dart相关问题帮助的解释部分**
官方网站：www.dartlang.org
其他学习资源：dart语言入门（附视频） http://dart.hanguokai.com/
Dart语言中文社区（可与他人交流学习）http://www.cndartlang.com/ 
###**12. 从web storm软件菜单找出webstrom 中dart开发的帮助文档**
https://confluence.jetbrains.com/display/WI/Getting+started+with+Dart


