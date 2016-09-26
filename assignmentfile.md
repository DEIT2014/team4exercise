1. dart语言特性中的循环语句定义和操作方法

2. dart字符串的定义和操作方法

3. dart函数定义和使用方法

4. dart中数组定义和使用方法

5. dart中列表定义和使用方法
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
6. dart中 Map定义和使用方法
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
7. querySelector（）函数的详细API解释

8. 详细解释dart如何操作html的文档

9. dart web app 应用程序组织结构的解释部分

10. dart可用的各种工具的解释部分

11. 指引你到其他社区社区寻求dart相关问题帮助的解释部分
官方网站：www.dartlang.org
其他学习资源：dart语言入门（附视频） http://dart.hanguokai.com/
Dart语言中文社区（可与他人交流学习）http://www.cndartlang.com/ 

12. 从web storm软件菜单找出webstrom 中dart开发的帮助文档
https://confluence.jetbrains.com/display/WI/Getting+started+with+Dart
