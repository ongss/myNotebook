# Java

java เป็นภาษาที่มีจุดเด่นเกี่ยวกับการทำ android apps 

[TOC]


# syntax

## variable type

## data structure

## functions



# OOP

Object Oriented Programming หรือ OOP คือหลักการที่มองทุกอย่างที่อยู่ภายในโปรแกรมเป็น object ซึ่งแต่ละ object จะเก็บตัวแปร หรือ ฟังก์ชั่นอยู่ในตัวมัน โดยเราสามารถเรียกใช้ดูค่าของตัวแปร หรือ เรียกใช้งานฟังก์ชั่นที่อยู่ใน object ได้

```
// ดูค่าตัวแปร name ใน object person
System.out.println(person.name); // John Smith

// เรียกใช้ฟังก์ชั่น sayHi ของ person
person.sayHi(); // Hello, my name is John Smith
```

## class
โดยปกติแล้วในภาษา java เราจะไม่สามารถสร้าง object ขึ้นมาเฉยๆได้ แต่เราจะสร้างมันผ่าน class นั้นเอง class ทำหน้าที่เหมือนโรงงานสำหรับผลิต object โดยเราสามารถกำหนดคุณสมบัติของ object หรือ ฟังก์ชั่นที่ object ต้องมี ได้จาก class นั้นเอง

> Note : การตั้งชื่อ class ควรขึ้นต้นด้วยตัวพิมพ์ใหญ่เสมอ
```
public class Human {
	String name = "John Smith";
	public void sayHi(){
		System.out.println("Hello, my name is "+this.name);
	}
}

Human person = new Human();
```

>Note :  Integer String Scanner ก็เป็น class เหมือนกันนะ แต่มันถูก build in มาพร้อมกับ java แล้ว 
### constructor
แล้วถ้าเราต้องการสร้าง object จาก class Human ที่มีชื่อแตกต่างกันหละ!! เราสามารถทำมันได้โดยการใส่ constructor ลงไปใน class นั้นเอง constructor คือฟังก์ชั่นที่ใช้กำหนดค่าของตัวแปรในแต่ละ object ที่สร้างจาก class โดยที่ฟังก์ชั่นที่มีชื่อเดียวกับ class จะเป็น constructor 

```
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
person1.sayHi() // Hello, my name is John Smith

Human person2 = new Human("Ong eiei");
person2.sayHi() // Hello, my name is Ong eiei 
```

### extends
extends เป็นคำสั่งที่เราใช้เมื่อเราต้องการที่จะสร้าง class ใหม่ที่มีคุณสมบัติใกล้เคียงกับคลาสเดิมหรือดึงคุณสมบัติจาก class เดิมมาใช้ โดยคำสั่ง  extends จะคัดลอกคุณสมบัติของ class ที่ต้องการมา

> Note : คำสั่ง extends ไม่คัดลอก constructor มาให้จึงต้องเขียนใหม่เองทุกครั้ง
> Note : สามารถ extends ได้แค่ class เดียวเท่านั้น


```
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
hero.sayHi() //Hi, my name is eiei. I am Hero
hero.usePower() // eiei use his/her power : Fire balls
hero.HumanSayHi() // Hello, my name is eiei 
``` 

### getter & setter
เป็น pattern การเขียน class รูปแบบหนึ่งที่ใช้สำหรับการรับ หรือ แก้ไขค่าตัวแปรให้มีความเหมาะสมกับการใช้งาน

```
public class Human {
	String name = "John Smith";
	double weight = "50.5";
	public void setWeight(double weight){
		if(weight<0){
			this.weight 0;
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


### instanceof
คือคำสั่งที่ใช้ตรวจสอบว่า object นี้ถูกสร้างมาจาก class นี้รึปล่าวเช่น

```
Hero hero = new Hero("eiei","say hi");
hero instanceof Hero //true
hero instanceof Human //true
```


## prefix
เป็นพวกคำต่างๆที่ใช้เติมหน้า ตัวแปร class หรือ functions เช่น public private static ซึ่งแต่ละคำก็มีคุณสมบัติแตกต่างกันไป

### access modifiers
เป็น prefix ที่ใช้สำหรับการกำหนดสิทธิในการเข้าถึงตัวแปรหรือฟังก์ชั่นที่อยู่ใน class นั้นๆ  ในหมวดนี้มีอยู่ 3 คำคือ <code>public</code> <code>protect</code> <code>private</code> สามารถเติมได้ทั้งหน้า class function และ ตัวแปร


| modifier| class |  package | sub class | world |
|---------|-------|----------|-----------|-------|
| public  |  yes  |    yes   |     yes   |  yes  |
| protect |  yes  |    yes   |     yes   |   no  |
| private | yes   |    no    |     no    |   no  |

> Note : ถ้าไม่ได้เติมคำนำหน้าที่เกี่ยวกับ access modifiers เลยจะถือว่าเป็น public เสมอ
> Note : access modifiers ของ class มักจะเปิดกว้างกว่าตัวแปร หรือ ฟังก์ชั่นข้างใน เพราะถ้าตัวแปร หรือ ฟังก์ชั่นข้างในเป็น public แต่ access modifiers ของ class เป็น protect ก็ไม่ต่างอะไรกับการให้ access modifiers ของตัวแปรใน class เป็น protect อยู่ดี
 


### final
เป็น prefix ที่ใช้เติมหน้าตัวแปรที่ต้องการให้เป็นค่าคงที่ หรือ ด้านหน้าฟังก์ชั่นที่ไม่ต้องการให้ถูก override 

```
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
เป็น prefix ที่ใช้เติมด้านหน้า ตัวแปร เพื่อกำหนดให้เป็นตัวแปรประจำ class ซึ่งก็คือตัวแปรstatic ของ ทุก object ที่ถูกสร้างจาก class นั้น จะมีค่าเท่ากันตลอดเวลา (ถ้าตัวแปร static ของ object นึงถูกเปลี่ยนตัวแปรนั้นใน object อื่นจะเปลี่ยนไปด้วย )
ถ้าใช้ static เติมหน้าฟังก์ชั่น จะเป็นการบอกว่าเราสามารถเรียกใช้ฟังก์ชั่นนั้นจาก class ได้โดยตรง (ปกติต้องเรียกใช้ฟังก์ชั่นผ่าน object)

```
public class Human {
	static String NAME = "John Smith";
	// sayHi() จะไม่สามารถถูก override ได้แล้ว
	static public void sayHi(){
		System.out.println("Hello, my name is "+this.name);
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
Human.sayHi() // Hello, my name is John Smith
 
```

>Note : ฟังก์ชั่นที่เป็น static ต้องมีพารามิเตอร์เป็น static เท่านั้น


### abstract
abstract class เป็น class ที่เป็นนามธรรม ไม่สามารถเอาไปสร้าง object ได้ เอาไว้ใช้เพื่อให้ class อื่น extends เท่านั้น
abstract method เป็นฟังก์ชั่นที่ระบุเอาไว้ว่า**ต้องมี**ฟังก์ชั่นนี้นะ แต่ยังไม่ได้เขียนลงไปว่า ฟังก์ชั่นนี้สามารถทำอะไรได้

```
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


# build in property

## build in class
## build in function

# compiler
