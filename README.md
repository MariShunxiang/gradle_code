《Android Gradle 权威指南》 代码练习，方便以后查阅。

### 2.1 字符串

1. 单引号没有运算能力, 它里面所有表达式都是字符串常量
2. 双引号可以对字符串里的表达式做运算
3. 链接字符串,嵌套字符串; ${}
 > ${!+1}, ${name},只有一个变量的时候可以省略花括号, $name

### 2.3 方法

1. 括号是可以省略的
2. return可以不写
3. 代码块是可以作为参数传递的
 > 如果方法的最后一个参数是闭包,可以放到方法外面(方法可以省略)

### 2.5 闭包

1. 当必要有一个参数时, 默认就是`it`; 当有多个参数时, `it`就不能表示了, 我们需要把参数一一列出
2. Groovy的强大之处在于它支持闭包方法的委托. Groovy的闭包有 `thisObject`,`owner`,`delegate` 三个属性; 当你在闭包内调用方法时, 由它们来确定使用哪个对象来处理.默认情况下`delegate`和`owner`是相等的,但是`delegate`是可以被修改的,这个是功能非常强大的,Gradle中的闭包的很多功能都是通过修改`delegate`
实现的.

### 5.2

`buildscript{}`块是一个在项目构建之前，为项目进行前期准备和初始化配置依赖的地方，配置好所需要的依赖，就可以应用插件了：
```groovy
buildscript {
    repositories {
        jcenter()
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:1.5.0'
    }
}
```