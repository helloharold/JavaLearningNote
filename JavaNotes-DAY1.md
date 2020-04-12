# 《Java核心技术》
## Day 1  
1. JDK、JRE、JVM
JDK：Java Development Kit，Java开发工具包，安装JDK后此电脑即安装了JRE  
JRE: Java Runtime Enviroment，Java运行时环境，主要作用就是提供虚拟机  
JVM：Java Virtual Machine，Java虚拟机
2. Java版本
Java 2是版本1.2时推出，1.2、1.3、1.4都称为Java 2  
Java 5是版本1.5  
3. J2SE、J2EE、J2ME以及Java SE、Java EE、Java ME  
J2SE(Java 2 Standard Edition): Java 2标准版，实质就是Java编程语言基本开发运行环境，基本上对应JDK  
J2EE(Java 2 Enterprise Edition): Java 2企业版，构建企业应用的平台，实质上是Java的服务器端应用开发运行环境；J2EE通过一系列的技术规范对J2EE应用服务器进行标准化  
J2ME(Java 2 Micro Edition): Java 2微型版，是进行手机、pad、机顶盒等移动设备、嵌入设备开发的Java解决方案  
在版本1.5推出后，J2SE、J2EE、J2ME就变成了Java SE、Java EE、Java ME  
4. 环境变量设置  
PATH(操作系统环境变量):如果JDK的安装目录是C:\\jdk1_6，则需要在操作系统PATH中增加C:\\jdk1_6\\bin；增加后可以直接在命令行中执行C:\\jdk1_6\\bin目录下的java.exe、javac.exe、jar.exe
JAVA_HOME:之所以设置，原因是有些基于Java开发的应用程序或系统中使用Shell脚本或bat批处理来执行程序，设置JAVA_HOME后，可以避免在Shell或bat中使用具体的目录路径，从而使Shell或bat能够方便地在不同系统间复制而无需修改
5. 使用JDK命令行进行程序开发步骤:
    1. 编写源代码。可采用任意文本编辑器其进行编写，保存为.java文件即可
    2. 编译程序。javac <选项> <源文件列表>；javac -help可查看帮助
    3. 运行程序。java <选项> 类的名字 <参数列表>；java -help查看帮助；
6. 示例一：  
    ```java
    public class Hi{
        public static void main(String[] args){
            System.out.println("Hi,friend!");
        }
    }
    ```
注：  
   * 开发java类时建议始终定义明确的package  
   * 在编译大量的源文件时，可以使用列表文件，将要编译的源代码罗列起来，使用javac @列表文件名进行编译
   * 可以通过执行jar命令进行类文件打包
1. 在进行正式开发的工程，最好采用规划好的专门的目录
2. JAVA对大小写敏感！！！是一种常用的命名习惯。在一个规范的项目中，通常会制定类似的开发规范以保证项目代码风格的一致性，方便团队协作，有助于提高代码的*可读性及可维护性*
3. 类和接口是JAVA程序编写的基本单元，java所有的代码都在类和接口中
4.  使用Java命令执行类时，虚拟机会执行这个类的main方法，main方法不是必须的，如果想使用java命令执行，必须定义main方法，具体格式：   
    ```java
    public static void main(String[] args){}
    ```   
5.  java使用“;”、“}”作为结束标志，{}不需要增加分号，调用方法时，括号不能省  
6.  注释方式：  
    //：单行注释   
    /* */：多行注释  
    /** */：多行注释，用于自动产生Javadoc文档   
7.  基本类型,不对应于class，变量不是Object，4种整数型、2种浮点型、1种char型、1种boolean型：
    | Type   | Storage Requirement | range                                       |
    | :----- | :------------------ | :------------------------------------------ |
    | int    | 4 bytes             | -2147483648 to 2147493647                   |
    | short  | 2 bytes             | -32768 to 32767                             |
    | long   | 8 bytes             | -9223372036854775808 to 9223372036854775807 |
    | byte   | 1bytes              | -128 to 127                                 |
    | float  | 4 bytes             | +-3.40282347E+38F                           |
    | double | 8 bytes             | +-1.79769313486231570E+308                  |
8.  应根据实际情况选择合适的数据类型
9.  在使用变量最近处进行变量声明，这样可以方便地看到变量定义
10. 使用final关键字定义常量时，声明的变量全部使用大写字母，可以增加程序可读性
11. 使用static final进行类产量定义，定义时需定义在main方法外，其他方法可以直接调用，使用public声明后，其他类方法也能直接调用
12. strictfp关键字可强制将浮点运算整个过程使用64位，从而确保在任何处理器上产生相同的结果；不适用stricfp关键字的默认情况下工作正常的程序若改为strictfp时可能会发生溢出：  
```java  
public static strictfp void main(String[] args)  
```
19. 使用&&时尽可能将最可能为false的放在前面，使用||时尽可能将true的放在前面；采用长路&及|时会强制进行全过程运算  
20. 在进行运算时，数值类型会自动转换，基本规则是短的自动转换为长的
21. 枚举：
```java
enum Size{SMALL, MEDIUM, LARGE, EXTRA_LARGE};  
Size s = Size.MEDIUM;
```
22.  String创建后不可再改变，可使用str.substring(0,3)进行截取；多次对字符串进行处理后会在内存中产生多个字符串，增加对资源的占用，采用StringBuffer的方式只会在内存中产生一个字符串：
```java
StringBuffer sb = new StringBuffer();     
sb.append("The");   //内存只有一个字符串  
sb.append("name");  //内存亦仅只有一个字符串  
```
23. 字符串比较：需使用String的equals方法进行比较，采用==仅比较两个String是否在内存中处于相同的位置  
24. 可查看API文档进行应用  
25. Scanner：
```java
import java.util.Scanner;
public class Input{
    public static void main(String[] args){
        Scanner in = new Scanner(System.in);
        String str = in.nextLine();
        int i = in.nextInt();
        double d = in,nextDouble();
    }
}
```  
26. 格式化打印：  
```java
    System.out.printf("%8.2f",x);
```  
常用参数：  
| Character | Type             | Example  |
| :-------- | :--------------- | :------- |
| d         | 十进制整型       | 159      |
| x         | 十六进制整型     | 9f       |
| o         | 八进制整型       | 237      |
| f         | 浮点型           | 5.9      |
| e         | 科学表示法浮点型 | 1.59e+01 |
| s         | 字符串           | Hello    |
| c         | 字符             | H        |
| b         | 布尔型           | true     |
| n         | 分割线           | -        |   
27. 文件输入输出，如果路径中存在\，则需要\\，"C:\\mydir\\myfile.txt"：  
 ```java
    Scanner in = new Scanner(new File("myfile.txt"));  
```
28. for循环与while循环在开始一轮循环时首先判断循环条件，若不满足则不进入循环体，do循环在循环结束位置进行条件检测   
29. switch语句注意不要漏掉break；使用break和continue时要保持清晰的思路，建议只在非常必要的情况下使用break和continue
```java
label;
{
    ...
    if (condition) break label; //退出块
    ...
}
// 跳到此处
```
30. for each循环：
```java
    for (variable : collection) statement
```
31. 二维数组for each,假设有数组a[][]:  
```java
    for (double[] row :a){
        for (double value : row){
            do something with value；
        }
    }
```

