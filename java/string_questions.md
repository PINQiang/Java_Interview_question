# 字符串基础问题

**题目一**
```
public class Test{
    public static void main(String[] args){
        String s1 = "abc";
        String s2 = s1;
        String s3 = new String("abc");
        String s4 = new String("abc");
        String s5 = "abc";

        System.out.println(s1==s5);
        System.out.println(s1==s2);
        System.out.println(s1.equals(s2));
        System.out.println(s3==s4);
        System.out.println(s1.equals(s4));
        System.out.println(s3.equals(s4));
    }
}```


输出是 true true true false true true

**题目二**

    String s = "a" + "b" + "c" + "d" + "e"

创建了几个对象? 1个 赋值号右边都是常量,编译时直接储存它们的字面值, 在编译时直接把结果取出来面成了 "abcde"

**题目三**

```
# 创建了几个String Object?二者之间有什么区别？

    String s = new String("xyz");```

两个或一个,
”xyz”对应一个对象,
这个对象放在字符串常量缓冲区,
常量”xyz”不管出现多少遍,
都是缓冲区中的那一个.
New String每写一遍,
就创建一个新的对象,
它一句那个常量”xyz”对象的内容来创建出一个新String对象.
如果以前就用过’xyz’,
这句代表就不会创建”xyz”自己了,
直接从缓冲区拿.

**题目四**

    String s1 = new String("777");
    String s2 = "aaa777";
    String s3 = "aaa" + "777";
    String s4 = "aaa" + s1;

s2 == S3 : true
s2 == S4 : false
s2 == S4.intern() : true


**题目五**

    String str = "ABCDEFGH";
    String str1 = str.substring(3,5);
    System.oout.println(str1);

输出是 DE substring 是前包括后不包括

**题目六**

    执行后，原始的String对象中的内容到底变了没有？

        String s = "Hello";
        s = s + " world!";

没有.
因为String被设计成不可变(immutable)类,
所以它的所有对象都是不可变对象.

在这段代码中,
s原先指向一个String对象,
内容是 "Hello",然后我们对s进行了+操作,
这时，s不指向原来那个对象了,
而指向了另一个 String对象,
内容为"Hello world!",
原来那个对象还存在于内存之中,
只是s这个引用变量不再指向它了.
