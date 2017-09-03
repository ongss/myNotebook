# Discrete 

# Logic 
คือหลักการคำนวนค่าความจริงของประพจน์(proposition) หรือประพจน์ที่มารวมตัวกัน(compound proposition) ค่าความจริง True หรือ False เท่านั้น

## Logical operators
* Negetion (Not) : นิเสธ (¬)
* Conjunction (AND) : และ (˄)
* Disjunction (OR) : หรือ (˅)
* Implication (IF..THEN) : ถ้าแล้ว (→) 
* Biconditional (IF && ONlY IF) : ก็ต่อเมื่อ (↔) 
* Exclusive OR (XOR) : นิเสธของก็ต่อเมื่อ 

- unary operator -> one operand : not
- binary operator -> two operand 
 
>Note : ลำดับความสำคัญของ operator เรียงตามลำดับจากบนลงล่างคือให้ทำ ¬ , ˄ , ˅ , → , ↔  ตามลำดับ เช่น p ˄ ¬q ˅ r → p ↔ s จะเขียนได้เป็น (((p ˄ (¬q)) ˅ r ) → p) ↔  s

## Contrapositive & Converse & Inverse
เป็นการนิยามความสัมพันธ์ที่เกี่ยวกับ operator implication(ถ้าแล้ว) เพิ่มเติมโดยมีความสัมพันธ์ดังนี้
* contrapositive ของ p → q คือ ¬q → ¬p 
* converse ของ p → q คือ q → p
* inverse ของ p → q คือ  ¬p → ¬q 

## Consistency
คือกลุ่มของ compound proposition ที่ไม่ขัดแย้งกัน หรือก็คือมีค่าความจริงอย่างน้อยหนึ่งชุดที่ทำให้ทุกๆ compound proposition ในกลุ่มเป็นจริง เช่น
1) p → ¬q
2) q → r
3) ¬r → ¬p 

กลุ่มของ compound proposition นี้เป็น consistency เพราะเมื่อ p ≡ T , q ≡ F, r ≡ T ทั้ง 3 compound proposition มีค่าความจริงเป็นจริง

## Tautology & Contradiction & Contingency
* tautology(สัจนิรันดร์) คือ compound proposition ที่มีค่าความจริงเป็นจริงเสมอทุกกรณี always True
* contradiction คือ compound proposition ที่มีค่าความจริงเป็นเท็จเสมอทุกกรณี always False
* contigency คือ compound proposition ที่แล้วนอกเหนือจาก tautology และ contradiction

## Showing Logically Equivalent propositions
คือการแสดงว่า compound proposition สองอันสมมูลกัน
* แสดงตารางค่าความจริง(ถึก)
* แปลง compound proposition ให้มีหน้าตาเหมือนกัน

## Logical Equivalences
### Distributive Laws
p ∨ ( q ∧ r ) ≡ ( p ∨ q ) ∧ ( p ∨ r )

p ∧ ( q ∨ r ) ≡ ( p ∧ q ) ∨ ( p ∧ r )
### De Morgan's Laws
¬ ( p ∧ q ) ≡ ¬ p ∨ ¬ q

¬ ( p ∨ q ) ≡ ¬ p ∧ ¬ q

## Predicate Logic
คือประพจน์ที่ต้องแทนค่าที่อยู่ในขอบเขตของมันลงไปถึงจะบอกค่าความจริงได้ เช่น P(x) | x gose to school, where x can be John or Mary 
x = variable, goes to school = predicate หมายความว่าต้องแทนค่า x ด้วย John หรือ Mary ก่อนถึงจะบอกค่าความจริงได้ 

## Quatifier
* Universal quantifier คือ ∀xP(x) [read : for all x P(x)] ≡ P(x1)∧P(x2)∧…∧P(xn) 
หมายความว่า P(x) นั้นจะต้องเป็นจริงทุกกรณีใน universal of discourse(x1,x2,...xn) ∀xP(x) ถึงจะเป็นจริง

* Existential quantifier คือ ∃xP(x) [read : for some x P(x)] ≡ P(x1)∨P(x2)∨…∨P(xn)
หมายความว่า P(x) นั้นจะต้องเป็นจริงอย่างน้อย 1 กรณีใน universal of discourse ∃xP(x) ถึงจะเป็นจริง

### Negations of quatifier
¬∀xP(x) ≡ ∃x ¬P(x)

¬∃xP(x) ≡ ∀x ¬P(x)

## Rules of inference
เป็นกฏที่ใช้เพื่อการอ้างเหตุผลเพื่อใช้แสดงว่า กลุ่มของ proposition สมเหตุสมผลหรือไม่

### Rules 
* Addition                               p | p ∨ q 
* Simplification                     p ∧ q | p
* Conjunction                        p , q | p ∧ q
* Modus ponen                    p , p → q | q 
* Modus tollens                 ¬q , p → q | ¬p
* Hypthetical syllogism       p → q ,q → r | r
* Disjuction syllogism          p ∨ q , ¬p | q
* Resolution                p ∨ q , ¬q ∨ r | q ∨ r

### Rules for Quantified
* Universal instantiation                     ∀xP(x) | P(c)
* Universal generalization            P(c) for all c | ∀xP(x)
* Existential instantiation                   ∃xP(x) | P(c) for some c
* Existential generalization         P(c) for some c |  ∃xP(x)

 
### valid Argument
กลุ่มของ proposition จะสมเหตุสมผลก็ต่อเมื่อ (p1 ∧ p2 ∧ p3 ∧ .. ∧ pN ) → q ≡ T เมื่อ p เป็นสมมุติฐาน และ q เป็นข้อสรุป

# Sets & Functions

## Sets 
เป็นการเก็บข้อมูลเอาไว้ในเครื่อง { } ข้อมูลแต่ละตัวที่อยู่ในเซ็ตเราจะเรียกมันว่าสมาชิก โดยสมาชิกแต่ละตัวในเซ็ตจะต้องไม่ซ้ำกันเลย

ตัวอย่าง set
* {1,2,3,4,5}
* O = {x | x%2=1 ∧  x less than 100}

### type of sets
* Empty set     :
* subset        :
* proper subset :
* power set     : P(S)

>> Note : เช็ตว่างเป็น subset ของเช็ตทุกเซ็ต

>> Note : power set ของเช็ต x จะมีสมาชิค 2^n เมื่อ n เป็นจำนวนสมาชิกของ set x

### operations
* Union : A U B เอาเซ็ต A กับ B มารวมกัน
* inetersection : เซ็ตของส่วนที่ A กับ B เหมือนกัน
* Differrence : เซ็ตที่เหมือนกับเซ็ต A เมื่อเอาสมาชิกทุกตัวของ B ออก
* Complement : เซ็ตของทุกอย่างใน universe ที่ไม่ใช่ A
* Symetric difference : เซ็ตของส่วนที่ A กับ B ต่างกัน

### set identities

#### Distributive Laws
A  ( B  C ) = ( A  B )  ( A  C )
A  ( B  C ) = ( A  B )  ( A  C )

#### DeMorgan's Laws
(A  B) = A B
(A  B) = A B

### ordered n-tuple
รูปแบบการเก็บข้อมูลที่เรียงกันกันตามลำดับการใส่ข้อมูล เช่น (1,2,3,4) เมื่อใส่ 1-4 เรียงตามลำดับ


### Catesian Products
เป็นเช็ตของความสัมพันธ์ของสองเซ็ตขึ้นไปที่จะเอาสมาชิกทุกตัวของแต่ละเช็ตมาเซ็ตละหนึ่งตัวแล้วจัดกลุ่มกันเป็น odered n-tuple ทุกแบบที่เป็นไปได้กล่าวคือ

เช่น Catesian Prodoucts ของ AxBxC เมื่อ  A = {0,1} ,  B = {2,3} , C = {a,b,c}
AxBxC = {(0,2,a),(0,2,b),(0,2,c),(0,3,a),(0,3,b),(0,3,c),(1,2,a),(1,2,b),(1,2,c),(1,3,a),(1,3,b),(1,3,c)}






 
