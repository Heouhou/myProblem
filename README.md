autoauto- [1. Java](#1-java)auto    - [1.1. 【Java笔记】Java8中数组(引用类型)、String、List、Set之间的相互转换问题](#11-java笔记java8中数组引用类型stringlistset之间的相互转换问题)auto- [2. Mysql](#2-mysql)auto    - [2.1. **SUM 函数的用法**](#21-sum-函数的用法)auto    - [2.2. **SQL日期格式化**](#22-sql日期格式化)autoauto

# 1. Java

## 1.1. 【Java笔记】Java8中数组(引用类型)、String、List、Set之间的相互转换问题

* 问题场景 : 有一些String 需要去重,想到用利用Set 去重的原理来进行去重,期间用到了String 和Set 之间的转换
* 网站链接: [数组、String、List、Set之间的相互转换问题](https://blog.csdn.net/SnailMann/article/details/80614006)
* 部分代码: 
   >  String转换为Set
	
	``` java
	public static void stringToSet(){
		String str = "12345";
		String[] strs= str.split("");
		
		//方式一
		List<String> list1 = Arrays.asList(strs);
		Set<String> set1 = new HashSet<>(list1);

		//方式二
		Set<String> set2 = new HashSet<>();
		Collections.addAll(set2, strs);
	}
	```
	方式一有三个步骤：
	1 .String转换为String[]数组 或包装类型数组（如Character[]）
	2 .将数组转换为List,可以使用Arrays或Collections工具类
	3 . 将list转换为Set
	方式二有两个步骤  
	1 . String转换为String[]数组 或包装类型数组（如Character[]）
	2 . 使用Collections工具类将数组转换为Set


    > Set转换为String

   ```java
   public static void setToString(){
	Set<String> set = new HashSet<>();
	String.join("", set);
   }
   ```
    
    
*  //TODO MDL链接 [数组、String、List、Set之间的相互转换问题](introduce.md)





# 2. Mysql
## 2.1. **SUM 函数的用法**
```sql
select sum(money) from user group by id;
```

## 2.2. **SQL日期格式化**
```sql
oracle：

WHERE a.gmt_modified >= to_date('2017-03-04','yyyy-MM-dd')

MySQL：

A.MODIFY_TIME >= DATE_FORMAT('2017-03-31','%Y-%m-%d') 
WHERE DATE_FORMAT(modify_time, '%Y-%m-%d') = DATE_FORMAT(DATE_SUB(NOW(), INTERVAL 2 DAY),'%Y-%m-%d')
```







