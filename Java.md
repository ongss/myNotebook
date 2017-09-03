# Java

java เป็นภาษาที่มีจุดเด่นเกี่ยวกับการทำ android apps 

[TOC]


# syntax

## variable type
ในภาษา java มีตัวแปรชนิดหลักๆดังนี้ 
* ประเภทตัวอักษร <code>String</code> : ตัวอักษรหลายตัว, <code>char</code> : ตัวอักษรตัวเดียว
* ประเภทตัวเลข <code>int</code> : จำนวนเต็มขนาด 4 byte, <code>short</code> : จำนวนเต็มขนาด 2 byte, <code>byte</code> : จำนวนเต็มขนาด 4 byte, <code>long</code> : จำนวนเต็มขนาด 8 byte, <code>float</code> : จำนวนจริงขนาด 4 byte, <code>double</code> : จำนวนจริงขนาด 8 byte
* ประเภทอื่นๆ <code>boolean</code> : เก็บค่าความจริง true,false

>Note : การใช้ float ในการคำนวนอาจจะได้ค่าที่ผิดพลาดดังนั้นควรใช้ double แทน

>Note : 1 byte = 8 bit ซึ่ง 1 bit เก็บเลขฐานสองได้ 1 หลัก ดังนั้น short ที่มี 2 byte จึงเก็บค่าได้ 2^(2x8) =  65536 แบบ จึงสามารถเก็บค่าในช่วง [-32768,32767]

>Note : ' ' คือ char สามารถเก็บอักขระได้ตัวเดียว , " " คือ Stirng สามารถเก็บอักขระได้กี่ตัวก็ได้

ตัวอย่างการใช้งาน
```java
int a = 15; //จำนวนเต็มส่วนใหญ่นิยมใช้ int
long b = 123981718937100999L; //ต้องมี L ด้วยนะ
// byte short ก็ประกาศแบบเดียวกับ int
float c = 3.l4; //ไม่ควรใช้อันนี้เพราะอาจจะเกิดการผิดพลาดเวลาคำนวน
double d = 9.999; //จำนวนจริงส่วนใหญ่นิยมใช้ double

char e = 'a'; 
String f = "Hello"; //ตัวอักษรที่เป็น string จะต้องอยู่ใน " " เท่านั้น ถ้าอยู่ใน ' ' จะเกิด error
int g = 'c'-'a'; // char สามารถบอกระยะห่างของตัวอักษรได้ด้วยนะ g = 2
int h = 'a'+'a'; // h = 194

boolean h = true;

```

การเปลี่ยนชนิดของตัวแปร
```java
//เปลียนเป็น String
String a = Integer.toString(2);
String b = Double.toString(2.3);
String c = Boolean.toString(true);

a = "" + 3; // a = "3"  
b = "" + true;// b = "true"
c = "python" + 2 + "java"; // c = python2java -> เปลี่ยน 2 เป็น string แล้วค่อยต่อ string
d = 3 - 1 + "eiei"; // d = 2eiei
e = "eiei" + 3 + 1; // e = eiei31
f = "eiei" + 3 - 1; // error !!!
 

//เปลียนตัวแปร  char <--> int <--> double (วิธีนี้ใช้กับ String ไม่ได้)
int x = (int) 2.3;
double y = (double) 2;
char w = (char) 97; //w = 'a';
int z = (int) 'a'; //z = 97;

//เปลี่ยน String เป็นตัวเลข
int i = Integer.parseInt("12");
double j = Double.parseDouble("12.2");
boolean k = Boolean.parseBoolean("true");

```

## operator
```java
// operator เกี่ยวกับการคำนวนเลขใช้ + - * / % Math.pow(base,exponent)
// and --> && , or --> || , นิเสธ(~) --> !
//	mod %
// 5%3 = 2      -5%3 = -2	    5%-3 = 2    -5%-3 = -2  ได้ค่าติดลบ ขึ้นกับตัวหน้าติดลบมั๊ย 
** หลักการ mod ขึ้นอยู่กับภาษาที่ใช้ python ได้ค่าไม่เหมือน java


//if-else
if( 2 + 3 == 5 || !(Math.pow(2,3) == 8)){
	System.out.println("Hello");
} 
else{
	System.out.println("World");
}


//loop
int n = 10;
while(n>0){
	System.out.printf(n);
	n-=1;
} // 10,9,8,7,6,5,4,3,2,1

for(int i=10;i>0;i--){
	System.out.printf(i);
} // 10,9,8,7,6,5,4,3,2,1
```

>Note : == คือ เท่ากับ

>Note : while() จะทำงานไปเรื่อยๆถ้าค่าใน () ยังเป็นจริง

>Note : for(start;stop;step)

## main
main เป็นฟังก์ชั่นที่ใช้เขียนโค้ดในโปรแกรม โดยที่โปรแกรมจะเรื่มทำงานที่ในฟังก์ชั่น main ในภาษา java ฟังก์ชั่น main ต้องประกาศอยู่ใน class 
```java
public class HelloWorld{ // public class filename -> HelloWorld.java
	public static void main(String[] args){
		//program start here!! 
	}
}
```
โดยพารามิเตอร์ของ main จะเป็นเป็น array ของ String ที่เรียกว่า agrs โดย agrs จะได้มาจากการสั่งรัน java file จาก cmd
```cmd
C:\User\Name\Desktop>java HelloWorld myname myage
```
คำสั่งนี้เป็นการรันไฟล์ HelloWorld.class โดยมี args = ["myname","myage"] 

## input & output
```java

import java.util.Scanner;

public class HelloWorld{
	public static viod main(String[] agrs){
		
		//การรับ input แบบต่างๆ
		Scanner sc = new Scanner(System.in);
		int a = sc.nextInt(); //รับ input ตัวถัดไปโดยต้องเป็น int เท่านั้น
		double b = sc.nextDouble(); //รับ input ตัวถัดไปโดยต้องเป็น double เท่านั้น
		String c = sc.next(); //รับ input ตัวถัดไปโดยต้องเป็น String
		String d = sc.nextLine(); //รับ input โดยต้องเป็น String ไปจนจบบรรทัด
		//สมมุติรับ input มาเป็น 124 55.2 Hello my name is ong --> a = 124,b = 55.2,c = "Hello",d = "my name is ong"
		
		//การแสดง output แบบต่างๆ
		System.out.print("Hello"); //print Hello
		System.out.println("Hello"); //print Hello แล้วก็ขึ้นบรรทัดใหม่
	}
}
```
## String
```java
String S = "  Hello World  ";
int n = S.length(); // n = 15
String t = S.trim(); // t = "Hello World" เหมือน strip ใน python  
t = S.toUpperCase(); // t = "  HELLO WORLD  "
t = S.toLowerCase(); // t = "  hello world  "
n = S.indexOf("-"); // n = 7 เหมือน find ใน python ถ้าไม่เจอ return -1 
n = S.indexOf("o",7); // n = 9 เริ่มหา o ตั้งแต่ช่องที่ 7

boolean b = S.contains("or"); // b = true
b = S.equals("Hello World"); // b = false 

if(S.compareTo(t) == 0) // S == t
if(S.compareTo(t) < 0) // S < t
if(S.compareTo(t) > 0) // S > t

for(char c: s.toCharArray()) // วนfor char ทีละตัว

t = S.substring(2,3); // S[2]
t = S.substring(2,8); // S[2:8]
t = S.substring(2); // S[2:]
t = S.substring(0,8); // S[:8]
t = S.substring(s.length()-1); // S[-1]
char c = S.charAt(6); // c = o
```
## data structure
เป็นรูปแบบการเก็บข้อมูลจำนวนมากๆ ให้สามารถเรียกใช้ข้อมูลหรือแก้ไขข้อมูลได้ง่าย

### array
เป็นรูปแบบการเก็บข้อมูลที่มีรูปแบบเป็นช่องมาต่อๆกัน วิธีการเรียกข้อมูลออกมาจะต้องใช้เลขช่องของ array เช่น <code>a[3]</code> (array a ช่องที่ 3) โดยการสร้าง array จะต้องประกาศขนาดและชนิดของตัวแปรเอาไว้ตั้งแต่แรก
```java
import java.util.Arrays; //เวลาใช้ Arrays.mathod
// การประกาศ array 
int[] n = new int[10]; //ประกาศ array n เป็นชนิด int ขนาด 10 ช่อง ตั้งแต่ช่องที่ 0 ถึง 9
// ลองใส่ค่าลงไปใน array
for(int i=0;i<n.length;i++){ // .length เป็นฟังก์ชั่นที่ใช้อ่านความยาวของ array
	n[i] = i; //ใส่ค่าเข้าไปใน array n
}// array n จะมีค่า [0,1,2,3,4,5,6,7,8,9]
//หรือประกาศแบบนี้ก็ได้
int[] n = new int[] {0,1,2,3,4,5,6,7,8,9};
//หรือไม่ก้แบบนี้
int[] n = {0,1,2,3,4,5,6,7,8,9};
//สามารถเปลี่ยน int เป็นตัวแปรชนิดอื่นก็ได้ เช่น
String[] days = new String[] {"mon","tue","wed","thu","fri","sat","sun"};

// การเรียกข้อมูลใน array
System.out.println(n[3]); // 3
System.out.println(Arrays.toString(n)); //[0,1,2,3,4,5,6,7,8,9]
for(int e : n) // for each number in array >>in python -> for e in n:

// array หลายมืติ หรือก็คือ array มาซ้อนกันหลายๆชั้นเช่น
int[][] x = {{1,2,3},{4,5,6},{7,8,9}};
for(int i=0;i<x.length();i++)
   for(int j=0;j<x[i].length();j++)
	// x[i][j];
for(int[] row:x)    //for row in x:
   for(int e:row)   //   for e in row;
       //e;
System.out.println(x[0][0]); // 1 
System.out.println(x[0][1]); // 2
System.out.println(Arrays.deepToString(x)); // [[1,2,3],[4,5,6],[7,8,9]] 

```
>Note : เวลาการข้าถึงข้อมูลใน array ใช้ O(1) เช่น a[1] แต่ใช้เวลาในการแทรกข้อมูล O(n) ถ้าจะแทรกช่องที่ m จะต้องขยับข้อมูลช่องที่ m ถึง n ไปหนึ่งช่อง

### ArrayList
เป็น sub class ของ List ที่มีรูปแบบการเก็บข้อมูลที่คล้าย array แต่สามารถขยายขนาดได้
```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

public class HelloWorld{
	public static void main(String[] agrs){
		ArrayList<Integer> a = new ArrayList<>(); //ประกาศ arraylist ชื่อ a เก็บข้อมูลประเภท Integer
		LinkedList<Integer> a = new LinkedList<>(); 
		// List<Integer> a = new ArrayList<>(); สามารถเขียนงี้ได้ 
		// List<Integer> a = new LinkedList<>(); สามารถเขียนงี้ได้
		a.add(2); //ใส่ข้อมูล 2 ต่อท้าย arraylist
		a.add(0,1); //ใส่ข้อมูล 1 แทรกที่ arraylist ช่องที่ 0 
		a.set(1,3); //set ข้อมูลช่องที่ 1 ให้เป็นค่า 3 a[1]=3;
		a.get(1); //เรียกดูข้อมูลช่องที่ 1 a[1];
		a.set(1,a.get(1)+100); //เพิ่มค่าช่อง 1 ไป 100 a[1]+=100;
		a.remove(1); //ลบข้อมูลตำแหน่งที่ 1 ของ a
		a.contains(1); //ใน aมีค่าที่เป็น 1 มั้ย return เป็น true false
		
		
	}
}
```
>Note : สังเกตว่าตอนประกาศ ArrayList ประกาศเป็น Integer ไม่ใช่ int เพราะใน <> ต้องใส่ class เท่านั้น

>Note : เราสามารถประกาศ <code>List<Integer> a = new ArrayList<>();</code> ได้ เพราะ ArrayList ก็ถือเป็น List คล้ายๆกับ <code>double x = 3;</code> 3 ที่เป็นจำนวนเต็มก็ถือว่าเป็นจำนวนเต็มเช่นกัน

### List
เป็นการเก็บข้อมูลที่ไม่จำเป็นต้องรู้จำนวนข้อมูลที่แน่นอนเพราะภายใน 1 ช่องของ list จะประกอบไปด้วยสองส่วนคือ ข้อมูลในช่องนั้น และ pointer ที่ชี้ไปที่ list ช่องถัดไป และยังจำเป็นต้องมี pointer ที่ชี้ไปที่ช่องแรกของ list ด้วย นอกจากนี้ List ยังถือเป็น super class ของ ArrayList

>Note : เนื่องจาก List เป็น super class ของ ArrayList ดังนั้น syntax การรับข้อมูลเข้าของ ArrayList จึงเหมือนกับ List 

>Note : List สร้างได้แบบ ArrayList, LinkedList

```java
import java.util.List;

public class HelloWorld{
	public static void main(){
		List<Integer> myList = new List<>();
		a.add(2); //ใส่ข้อมูล 2 ต่อท้าย list
		a.add(0,1); //ใส่ข้อมูล 1 แทรกที่ list ช่องที่ 0
		a.set(1,3); //set ข้อมูลช่องที่ 1 ให้เป็นค่า 3
		a.get(1); //เรียกดูข้อมูลช่องที่ 1
		a.remove(1); //ลบข้อมูลตำแหน่งที่ 1 ของ a
		a.contains(1); //ใน a มีค่าที่เป็น 1 มั้ย return เป็น true false
		a.size() //ดูความยาวของ list
		
		List<Integer> b = Arrays.asList(1,2,3,4); //ประกาศ list ตั้งแต่ 1 ถึง 4
		a.addAll(b); //เอา list b มาต่อหลัง list a
		a.addAll(0,b); //เอา list b มาแทรกตำแหน่งที่ 0 
		
		//เรีนกดูข้อมูลทั้งหมดใน list
		System.out.println(a);
		for(Integer x : a){
			System.out.print(x+" ");
		}
	}
}
```
>Note : เวลาในการเข้าถึงข้อมูลใน List ใช้ O(n) เนื่องจากต้องไล่วิ่ิงไปทีละช่องๆจนกว่าจะถึงข้อมูลที่ต้องการ แต่สามารถแทรกช่องใหม่ได้เร็ว O(1)เนื่องจากแค่เปลี่ยน pointer เท่านั้น

#### join & split
```java
import java.util.List;
import java.util.Arrays;

public class HelloWorld{
	public static void main(){
		String s = "a-bb-ccc-dddd";
		String[] array =  s.split("-"); //สร้าง array string ["a","bb","ccc","dddd"]
		List<String> list = Arrays.aslist(array); //แปลง array เป็น list 
		String newS = String.join(",",list); //"a,bb,ccc,dddd"
		String newS = String.join(",",array); //อย่างงี้ก็ได้เหมือนกัน
		
		for(String s:list){
			//use s;
		}
		
 	}
}
```

### Set
เป็นรูปแบบการเก็บข้อมูลแบบเดียวกับ set ทางคณิตศาสตร์ซึ่งจะไม่มีสมาชิกที่ซ้ำกันเลย
>Note : Set สร้างได้แบบ TreeSet, HashSet
```java
import java.util.HashSet;
import java.util.Set;

public class HelloWorld{
	public static void main(String[] args){
		Set<Integer> s = new HashSet<>(); //ประกาศ set ใหม่ขึ้นมา
		s.add(1); //เพิ่ม 1 เข้าไปใน set s
		s.remove(1); //เอา 1 ออกจาก set s
		s.contains(4) //เช็คว่าข้างใน set s มี 4 มั้ย
		
		//เรียกดูข้อมูลทั้งหมดใน set 
		for(int x : s){
			System.out.println(x);
		}
	}
}
```
>Note : ข้อมูลใน set ไม่จำเป็นต้องเรียงตามลำดับการ input

### Map
คือการเก็บข้อมูลที่เป็นคู่ระหว่าง key กับ value โดยเราสามารถเข้าถึงข้อมูล มั้value ได้โดยที่ key ทุกอันต้องไม่ซ้ำกัน
```java
import java.util.Map;
import java.util.Map.Entry;

public class HelloWorld{
	public static void main(String[] agrs){
		Map<String,String> day = new HashMap<>(); //ประกาศ map ที่ <key = String,value = String>
		day.put("Mon","Monday"); //ใส่ค่าลงไปใน map โดย key="Mon" , value="Monday" 
		day.get("Mon"); //เรียกดูข้อมูล Monday
		System.out.print(day) //{Mon=Monday,}
		day.containsKey("Mon"); //เช็คว่าใน map มี key ชื่อ Mon มั้ย
		day.containsValue("Monday"); //เข็คว่าใน map มี value ชื่อ Monday มั้ย
	
		//ดู key ทั้งหมดของ day
		for(String x:day.keySet()){
			System.out.println(x);
		}
		//ดู values ทั้งหมดของ day
		for(String x:day.values()){
			System.out.print(x);
		}
		
		//เรียกดูทั้ง key และ values
		for(Entry<String,String> x : day.entrySet()){
			System.out.println(x); //key=values
		}
	}
}
```
>Note : ข้อมูลใน map ไม่จำเป็นต้องเรียงตามลำดับการ input

## functions
เป็นเหมือนโปรแกรมขนาดย่อยๆที่เราเขียนขึ้นมาเพื่อทำงานบางอย่าง โดยจะประกาศ type ของตัวแปรที่ function นั้นจะส่งออกมา ไว้ที่หน้าชื่อของ function และวงเล็บด้านหลังฟังก์ชั่นเป็นที่สำหรับการส่ง input ( parameter )เข้าไปทำงานที่ function 
```java
public class HelloWorld{
	public int a = 5; //global variable
	public static void main(String[] args){
		int b = 2; //local variable -> use only in main
	}
	static void m(){
		Symtem.out.println(a); // print a in global
	}
	static void n(){
		int a = 10;
		Symtem.out.println(a); // print a in local
	}
}
```
### function overload
เป็นเทคนิคการเขียนฟังก์ชั่น ที่จะเขียนฟังก์ชั่นที่มีชื่อซ้ำกันแต่จะมีชนืดหรือจำนวนของ parameter ต่างกัน 
```java
public class HelloWorld{
	public static void main(String[] args){
		System.out.println(prod(5,3)); //15
		System.out.println(prod(5,3,2)); //30
		System.out.println(prod(5,1.5)); //7.5
		
		for(String x:args){
			System.out.println(x);
		}
		
		/* cmd
		HelloWorld.java -> complier -> HelloWorld.class 
		>> javac HelloWorld.java 
		>> java HelloWorld kt eiei 555
		args = [kt,eiei,555]
		args.length = 3
		*/
		
	}
	
	//overloading
	static int prod(int a,int b,int c){ //prod(int,int,int)
		return a*b*c; 
	}
	static int prod(int a,int b){ //prod(int,int)
		return a*b; 
	}
	static double prod(int a,double b){ //prod(int,double)
		return a*b; 
	}
	
	//varargs
	static int prod(int a,int.. args){
		int ans = a;
		for(int x: args){
			ans*= x;
		}
		return ans;
	}
	
}
```

### lambda map filter
เป็น functional programing ชนิดหนึง หรือก็คือค่าที่อยู่ด้านในฟังก์ชั่นจะไม่สามารถเปลี่ยนได้แต่จะ return ค่ามาให้ฟังก์ชั่นอื่นทำงานต่อ
```java
import java.util.Arrays;
import java.util.ArrayList;
import java.util.List;
import java.util.stream.Collectors;
public class HelloWorld{
	public static void main(String[] args){
		List<Integer> a,b;
		a = Arrays.asList(1,2,3,4,5);
		b = new ArrayList<>();
		
		for(int x:a){
		  b.add(x*2);
		}
		System.out.println(b);
		
		b = a.stream()
		     .map( e -> e*2 ); //e->e*2 is lambda
		     .collect(Collectors.toList());
		System.out.println(b);  // [2,4,6,8,10]
		// b = [e*2 for e in a];
		
		/*---------------------------------------------*/
		for(int x:a){
		  if(x%2==0) b.add(x);
		}
		System.out.println(b);
		
		b = a.stream()
		     .filter( e -> e%2==0 ); // e -> e%2==0 is lambda
		     .collect(Collectors.toList());
		System.out.println(b); // [2,4]
		// b = [e for e in a if e%2==0];
		
		/*---------------------------------------------*/
		for(int x:a){
		  if(x%2==0) b.add(x*2);
		}
		System.out.println(b);
		
		b = a.stream()
		     .filter( e -> e%2==0 );
		     .map(e->e*2)
		     .collect(Collectors.toList());
		System.out.println(b); // [4,8]
		// b = [e*2 for e in a if e%2==0];
		
		
	}
}
```
### file
ใช้เพื่อการเขียนหรืออ่านไฟล์ที่อยู่ในเครื่อง
```java
import java.io.File;
import java.io.IOException;
import java.io.PrintStream;
import java.util.Scanner;
public class HelloWorld{
	public static void main(String[] args) throws IOException{ //Exception : ข้อผิดพลาดในโปรแกรม
								   //IOException : ปัญหาเกี่ยวกับ input/output ->อ่านไฟล์ไม่ได้ บลาๆ
								   //โปรแกรมพัง จะจบเลย
		//read file
		Scanner infile = new Scanner(new File("filePath"));
		//write file
		PrintStream outfile = new PrintStream(new file("filePath"));
		while(infile.hasNextLine()){
			String line = infile.nextLine();
			outfile.println(line);
		}
	}
	infile.close();
	outfile.close();
}
```

# OOP

Object Oriented Programming หรือ OOP คือหลักการที่มองทุกอย่างที่อยู่ภายในโปรแกรมเป็น object ซึ่งแต่ละ object จะเก็บตัวแปร หรือ ฟังก์ชั่นอยู่ในตัวมัน โดยเราสามารถเรียกใช้ดูค่าของตัวแปร หรือ เรียกใช้งานฟังก์ชั่นที่อยู่ใน object ได้

```java
// ดูค่าตัวแปร name ใน object person
System.out.println(person.name); // John Smith

// เรียกใช้ฟังก์ชั่น sayHi ของ person
person.sayHi(); // Hello, my name is John Smith
```

## class
โดยปกติแล้วในภาษา java เราจะไม่สามารถสร้าง object ขึ้นมาเฉยๆได้ แต่เราจะสร้างมันผ่าน class นั้นเอง class ทำหน้าที่เหมือนโรงงานสำหรับผลิต object โดยเราสามารถกำหนดคุณสมบัติของ object หรือ ฟังก์ชั่นที่ object ต้องมี ได้จาก class นั้นเอง

```java
public class Human {
	String name = "John Smith";
	public void sayHi(){
		System.out.println("Hello, my name is "+this.name);
	}
}

// สร้างตัวแปร person ที่เป็นชนิด Human แล้วสร้าง new Human ใส่ลงไปใน person
Human person = new Human();
```

>Note : การตั้งชื่อ class ควรขึ้นต้นด้วยตัวพิมพ์ใหญ่เสมอ

>Note : Integer String Scanner ก็เป็น class เหมือนกันนะ แต่มันถูก build in มาพร้อมกับ java แล้ว

>Note : ตัวแปร object เช่น person จะเป็น pointer ที่ชี้ไปยังที่ข้อมูล่างๆใน object นั้นเก็บไว้อยู่

### constructor
แล้วถ้าเราต้องการสร้าง object จาก class Human ที่มีชื่อแตกต่างกันหละ!! เราสามารถทำมันได้โดยการใส่ constructor ลงไปใน class นั้นเอง constructor คือฟังก์ชั่นที่ใช้กำหนดค่าของตัวแปรในแต่ละ object ที่สร้างจาก class โดยที่ฟังก์ชั่นที่มีชื่อเดียวกับ class จะเป็น constructor 

```java
public class Human {
	String name;
	// ถ้าไม่ใส่อะไรในวงเล็บจะเข้าเคสนี้ Human ที่สร้างขึ้นมาชื่อ John Smith 
	Human(){
		// this คือการอ้างอิงถึงตัวเอง(Human)
		this.name = "John Smith";
	}
	Human(String name){
		this.name = name;
	}
	public void sayHi(){
		System.out.println("Hello, my name is "+this.name);
	}
}

Human person1 = new Human();
person1.sayHi(); // Hello, my name is John Smith

Human person2 = new Human("Ong eiei");
person2.sayHi(); // Hello, my name is Ong eiei 
```

### extends
extends เป็นคำสั่งที่เราใช้เมื่อเราต้องการที่จะสร้าง class ใหม่ที่มีคุณสมบัติใกล้เคียงกับคลาสเดิมหรือดึงคุณสมบัติจาก class เดิมมาใช้ โดยคำสั่ง  extends จะคัดลอกคุณสมบัติของ class ที่ต้องการมา

> Note : คำสั่ง extends ไม่คัดลอก constructor มาให้จึงต้องเขียนใหม่เองทุกครั้ง

> Note : สามารถ extends ได้แค่ class เดียวเท่านั้น


```java
// คัดลอกคุณสมบัติของ Human มาใส่ใน Hero
public class Hero extends Human {
	String power;
	Hero(String name,String power){
		// super คือการอ้างอิงถึง class แม่ของ class นี้ ในที่นี้คือ Human
		// super() คือ constructor ของ class แม่ของ class นี้
		super(name); 
		this.power = power;
	}
	// override คือการเขียนฟังช่ันเดิมทับ sayHi ของ Human
	@Override
	public void sayHi(){
		System.out.println("Hi, my name is "+this.name+". I am Hero");
	}
	public usePower(){
		System.out.println(this.name " use his/her power : "+ this.power);
	}
	public humanSayHi(){
		super.sayHi() // super คือการอ้างอิงถึง class แม่ของ class นี้ ในที่นี้คือ Human
	}
}

Hero hero = new Hero("eiei","Fire balls");
hero.sayHi(); //Hi, my name is eiei. I am Hero
hero.usePower(); // eiei use his/her power : Fire balls
hero.HumanSayHi(); // Hello, my name is eiei


//หรือสามารถทำแบบนี้ได้ด้วย สร้าง sub class มาใส่ตัวแปรที่เป็น super class
Human a = new Hero("super main","Power fuill");
a.sayHi() //Hi, my name is eiei. I am Hero
a.humanSayHi() // ไม่สามารถทำงานได้เพราะ class Human ไม่มีฟังก์ชั่น ้ humanSayHi() หรือก็คือการ สร้าง sub class มาใส่ตัวแปรที่เป็น super class เป็นการ limit การทำงานของ object น้ันเอาไว้
Hero b = (Hero) a; // สามารถเปลี่ยน object a เป็น class Hero โดยสมบูรณ์
Hero b.humanSayHi() //Hello, my name is eiei



```

> Note : Hero extends Human มาเพราะงั้น Hero เป็น subclass ของ Human

### getter & setter
เป็น pattern การเขียน class รูปแบบหนึ่งที่ใช้สำหรับการรับ หรือ แก้ไขค่าตัวแปรให้มีความเหมาะสมกับการใช้งาน

```java
public class Human {
	String name = "John Smith";
	private double weight = "50.5"; // ใช้ private เพราะ เมื่อเราสร้าง getter & setter ขึ้นมาแล้วเราจึงไม่ต้องการให้มีการเข้าถึงตัวแปรได้โดยตรง
	// weight ไม่สามรถน้อยกว่า 0 ได้นะ
	public void setWeight(double weight){
		if(weight<0){
			this.weight = 0;
		}
		else{
			this.weight = weight;
		}
	}
	public double getWeight(){
		return this.weight;
	}
}

```
### equals
เป็น pattern การเปรียบเทียบ class สองอันว่าเหมือนหรือต่างกัน
```java
public class Human {
	String name = "John Smith";
	public boolean equal(Human other){
		if(this.name == other.name){
			return true;
		}
		return false
	}
}

Human person1 = new Human();
Human person2 = new Human();
person1 == person2 // False เพราะว่า person1 กับ person2 เป็นคนละ object กัน ดังนั้นเราจึงค้องสร้างฟังก์ชั่น equal
person1.equals(person2) // True

```



### instanceof
คือคำสั่งที่ใช้ตรวจสอบว่า object นี้ถูกสร้างมาจาก class นี้รึปล่าวเช่น

```java
Hero hero = new Hero("eiei","say hi");
hero instanceof Hero //true
hero instanceof Human //true
```


## prefix
เป็นพวกคำต่างๆที่ใช้เติมหน้า ตัวแปร class หรือ functions เช่น public private static ซึ่งแต่ละคำก็มีคุณสมบัติแตกต่างกันไป

### access modifiers
เป็น prefix ที่ใช้สำหรับการกำหนดสิทธิในการเข้าถึงตัวแปรหรือฟังก์ชั่นที่อยู่ใน class หรือตัว class เอง ในหมวดนี้มีที่นิยมใช้อยู่ 3 คำคือ <code>public</code> <code>protect</code> <code>private</code> สามารถเติมได้ทั้งหน้า class function และ ตัวแปร


| modifier| class |  package | sub class | world |
|---------|-------|----------|-----------|-------|
| public  |  yes  |    yes   |     yes   |  yes  |
| protect |  yes  |    yes   |     yes   |   no  |
| private | yes   |    no    |     no    |   no  |

> Note : ถ้าไม่ได้เติมคำนำหน้าที่เกี่ยวกับ access modifiers เลยจะถือว่าเป็น public เสมอ

> Note : access modifiers ของ class มักจะเปิดกว้างกว่าตัวแปร หรือ ฟังก์ชั่นข้างใน เพราะถ้าตัวแปร หรือ ฟังก์ชั่นข้างในเป็น public แต่ access modifiers ของ class เป็น protect ก็ไม่ต่างอะไรกับการให้ access modifiers ของตัวแปรใน class เป็น protect อยู่ดี
 


### final
เป็น prefix ที่ใช้เติมหน้าตัวแปรที่ต้องการให้เป็นค่าคงที่ ,ด้านหน้าฟังก์ชั่นที่ไม่ต้องการให้ถูก override หรือถ้าเอา final ไว้หน้า class จะทำให้ class นั้นไม่สามารถถูก extend   

```java
public class Human {
	final String NAME = "John Smith";
	// sayHi() จะไม่สามารถถูก override ได้แล้ว
	final public void sayHi(){
		System.out.println("Hello, my name is "+this.name);
	}
}
```
> Note : ชื่อตัวแปรที่อยู่หลัง final เป็น conts ควรประกาศเป็นตัวพิมพ์ใหญ่ทั้งหมด

### static
เป็น prefix ที่ใช้เติมด้านหน้า ตัวแปร เพื่อกำหนดให้เป็นตัวแปรประจำ class ซึ่งก็คือตัวแปร static ของ ทุก object ที่ถูกสร้างจาก class นั้น จะมีค่าเท่ากันตลอดเวลา (ถ้าตัวแปร static ของ object นึงถูกเปลี่ยนตัวแปรนั้นใน object อื่นจะเปลี่ยนไปด้วย )
ถ้าใช้ static เติมหน้าฟังก์ชั่น จะเป็นการบอกว่าเราสามารถเรียกใช้ฟังก์ชั่นนั้นจาก class ได้โดยตรง (ปกติต้องเรียกใช้ฟังก์ชั่นผ่าน object)

```java
public class Human {
	static String NAME = "John Smith";
	// sayHi() จะไม่สามารถถูก override ได้แล้ว
	static public void sayHi(){
		System.out.println("Hello, my name is "+this.name);
	}
}

public class Hero extends Human {
	static void sayHi(){
		System.out.println("hero");
	}
}

// ตัวแปร static
Human person1 = new Human();
Human person2 = new Human();
System.out.println(person1.name); // John Smith
System.out.println(person2.name); // John Smith
person2.name = "eiei";
System.out.println(person1.name); // eiei
System.out.println(person2.name); // eiei

// ฟังก์ชั่น static
Human.sayHi(); // Hello, my name is John Smith

Human hero = new Hero();
hero.sayhi() // Hello, my name is John Smith
// เพราะว่า static จำทำตาม type ที่ประกาศไว้ซึ่งเป็น Human
 
```

>Note : ฟังก์ชั่นที่เป็น static ต้องมีพารามิเตอร์เป็น static เท่านั้น


### abstract
abstract class เป็น class ที่เป็นนามธรรม ไม่สามารถเอาไปสร้าง object ได้ เอาไว้ใช้เพื่อให้ class อื่น extends เท่านั้น
abstract method เป็นฟังก์ชั่นที่ระบุเอาไว้ว่า**ต้องมี**ฟังก์ชั่นนี้นะ แต่ยังไม่ได้เขียนลงไปว่า ฟังก์ชั่นนี้สามารถทำอะไรได้

```java
	abstract class Human{
		abstract void doSomethings();
	}

	class Hero extends Human{
		@Override 
		void doSomethings(){
			System.out.println("Hero use power!!!");
		}
	}
```

## interface
เป็นเหมือนกรอบการทำงานคราวๆ เพื่อบอกว่าถ้าเป็น class ที่อยู่ใน interface นี้จะต้องมีรายละเอียดดังนี้ จะมีตัวแปรค่านี้ๆ ฟังก์ชั่นอะไรบ้าง(แต่ไม่ต้องเขียนว่าฟังชั่นทำอะไร) บลาๆๆ โดยที่ตัวแปรทุกตัวที่อยู่ใน interface จะเป็น <code>final</code> ทั้งหมด และ ฟังก์ชั่นทั้งหมดเป็น <code>abtract</code> และแน่นอนว่า เราไม่สามารถใช้ interface สร้าง object ได้โดยตรง

### implements
คือคำสั่งที่เรียกใช้ interface เข้าไปอยู่ใน class ที่ต้องการ ซึ่งเราสามารถ <code>implement</code>  หลาย Interface เข้าไปอยู่ใน class เดียวได้ ซึ่งต่างกับ <code>extends</code>

## generic
เป็นเหมือนการกำหนดชนิดของตัวแปรที่จะใส่เข้าไปใน class หรือ function เช่น
```java
// ArrayList ถือเป็น generics 
ArrayList<Integer> = new ArrayList<>(); //Interger ที่อยู่ระหว่าง < > เป็นการกำหนดชนิดของตัวแปรใน class ArrayList ว่าจะเก็บเป็น int
```
### generic class
ใช้เพื่อกำหนดชนิดของตัวแปรที่จะใส่เป็น parameter ของ constuctor
```java
// <T> ไว้สำหรับเก็บ type ของตัวแปรเพื่อเอาไปใช้งานต่อในคลาส
public class GenericStarct<T> { 
	private ArrayList<T> list = new ArrayList<>(); //สร้าง ArrayList ด้วย type T
	public int getSize(){
		return list.size();
	}
	public T pop(){ // return ค่าออกมาเป็น type T
		T ans = list.get(getSize() - 1);
		list.remove(getSize() -1 );
		return ans;
	}
	public void push(T a){ //รับค่าตัวแปรที่เป็น type T เป็น parameter
		list.add(a);
	}
	
	//ถ้าต้องการใช้ genericStack เก็บตัวแปรชนิด String
	GernericStack<String> stack1 = new GenericStack<>(); //แทนค่า T ด้วย String
	stack1.push("name");
	stack1.push("age");
	
	//ถ้าต้องการใข้ genericStack เก็บตัวแปรชนิด Integer 
	GernericStack<Integer> stack2 = new GenericStack<>(); //แทนค่า T ด้วย Integer
	stack2.push(1);
	stack2.push(2)
}
```
### generic methods
คล้ายกับ generic class ใช้เพื่อกำหนดชนิดของตัวแปรที่จะใส่เป็น parameter ของฟังก์ช่ัน

```java
public class HelloWorld{
	public static void main(String[] agrs){
		Integer[] a = {1,2,3};
		Stirng[] b = {"Hello","World"};
		
		HelloWorld.<Integer>print(a); // เรียกใช้ฟังก์ชั่น print โดยกำหนดชนิดของ parameter เป็น Integer[]
		HelloWorld.<String>print(b); // เรียกใช้ฟังก์ชั่น print โดยกำหนดชนิดของ parameter เป็น String[]
	}
	// generic method ใช้เพื่อกำหนดชนิดตัวแปรที่จะใส่เข้าไปเป็น parameter
	public static <E> void print(E[] list){
		for(int i=0;i<list.length;i++){
			System.out.print(list[i]+" ");
		}
		System.out.println();
	}
	
	
}
```
### bounded
เป็นการใช้ generic เพื่อกำหนดว่าต้องเป็นตัวแปรที่ใส่เข้ามาใน function หรือ constuctor ต้องถูก extends มาจาก class ที่กำหนดไว้เท่านั้น
```java
public class BoundedType{
	public static void main(String[] agrs){
		String a = "5555"; 
		String b = "Hero";
		
		System.out.print(BoundedType.equalLength(a,b)) // a และ b ต้องเป็น class ที่ extends String มาเท่านั้น
	}
	
	//ใช้เพื่อกำหนด parameter ว่าต้อง เป็น class ที่ extends มาจาก String เท่านั้น
	public static <E extends String> boolean equalLength(E obj1, E obj2){
		return obj1.length() == obj2.length();
	}
}
```


# compiler
การคอมไฟล์ภาษา java จำเป็นจะต้องอาศัย jdk ซึ่งเป็นตัวที่ทำให้คอมเราสามารถอ่านภาษา java ได้รู้เรื่องซึ่งเราสามารถตรวจอบได้จาก cmd ถ้าในคอมมี jdk จะขึ้นตามนี้
```cmd
C:\User\Name\Desktop>java -version
java version "1.8.0_131"
Java(TM) SE Runtime Environment (build 1.8.0_131-b11)
Java HotSpot(TM) 64-Bit Server VM (build 25.131-b11, mixed mode)
```

## .class
ปกติแล้วเราจะ compile ไฟล์ java ภายใน text editor ของเรา แต่ถ้าเราอยาก compile มันจาก cmd หละ หากเราลองเข้าไปในไฟล์งานของเรา จะเห็นว่าไฟล์ที่เราเขียนขึ้นมามีนามกุลเป็น .java ซึ่งปกติแล้ว window ไม่สามารถอ่านไฟล์ .java ได้ ดังนั้นเราจึงจำเป็นต้องแปลงไฟล์ .java ให้เป็น .class ที่ window สามารถอ่านได้ก่อน โดยวิธีการแปลงไฟล์นั้นต้องใช้ javac.exe ซึ่งเก็บอยู่ใน jdk1.x.x_xxx/bin โดยต้องเก็บ path นี้เอาไว้ในตัวแปร PATH ที่เป็น environment variable ของ window แล้วรันคำสั่ง javac ใน cmd 

```cmd
C:\User\Name\Desktop>javac HelloWorld.java
```
แล้วจะมีไฟล์ HelloWorld.class โผล่ขึ้นมาที่ Desktop หลังจากน้ันใช้คำสั่ง java เพื่อรันไฟล์
```cmd
C:\User\Name\Desktop>java HelloWorld
```
>Note : ไฟล์ HelloWorld.class สามารถละ .class ทิ้งไปได้ จึงเขียนแค่ java HelloWorld


## .jar
แล้วถ้าเราอยากคลิกเพื่อรันไฟล์ java ผ่านทาง desktop หละ ไฟล์ที่สามารถคลิกแล้วรันได้ผ่านทาง desktop นั้นคือ ไฟล์นามสกุล .jar ซึ่งเราสามารถสร้่างได้จากไฟล์ .class และ jar.exe ที่เก็บไว้ที่ jdk1.x.x_xxx/bin เช่นเดียวกับ javac.exe
```cmd
C:\User\Name\Desktop>jar cvfe MyProgram.jar HelloWorld *.class
```
>Note : c หมายถึง create file, v หมายถึงให้แสดงผลทาง cmd ว่าคำสั่งนี้ทำงานนะ,f หมายถึงเราจะกำหนด file name เอง, e หมายถึงเราจะบอก main class ให้

>Note : การกรอก args ก็เป็นไปตามลำดับของ option(cvfe คือ option) เช่น เราเขียน f ก่อน e จึงต้องกรอก file name ก่อน main class

>Note : <code>*.class</code> เป็น args ของคำสั่ง jar ที่บอกว่าจะสร้างไฟล์ .jar จาก class ไหนบ้าง โดยปกติจะเลือก .class ทั้งหมดที่อยู่ในโฟลเดอร์น้ัน ( <code>*.class</code> ) เพราะงั้นในโฟลเดอร์ที่ทำควรมีแต่ไฟล์ .class ที่เกี่ยวข้องทำนั้นนะ

รู้ป่าววว ความจริงแล้ว .jar เป็นไฟล์ zip เราจึงสามารถแตกไฟล์ได้เหมือนไฟล์ zip ปกติเลย  ข้างใน .jar จะประกอบด้วยไฟล์ .class และ โฟลเดอร์นึงที่ชื่อว่า META-INF
ของที่อยู่ข้างใน META-INF คือไฟล์ MANIFEST.MF ในไฟล์จะมีหน้าตาเป็นแบบนี้
```cmd
Manifest-Version: 1.0
Created-By: 1.8.0_131 (Oracle Corporation)
Main-Class: HelloWorld
```
มันเป็นไฟล์ข้อมูลของ .jar นั้นเอง ซึ่งเราสามารถเปลี่ยน main class ของไฟล์ .jar ได้จากตรงนี้ด้วย

>Note : สรุปแล้ว ลำดับการแปลงไฟล์เป็นตามนี้จ้า  .java --> .class --> .jar
