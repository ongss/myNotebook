# Discrete 

# Proposition
ประพจน์ที่เป็นประโยคบอกเล่า ที่บอกค่าความจริง True หรือ False เท่านั้น

# Logic 
คือหลักการคำนวนค่าความจริงของประพจน์(proposition) หรือประพจน์ที่มารวมตัวกัน(compound proposition)

## Logical operators
* Negetion (Not) : นิเสธ (¬)
* Conjunction (AND) : และ (˄)
* Disjunction (OR) : หรือ (˅)
* Implication (IF..THEN) : ถ้าแล้ว (→) 
* Biconditional (IF && ONlY IF) : ก็ต่อเมื่อ (↔) 
* Exclusive OR (XOR) : นิเสธของก็ต่อเมื่อ 

unary operator -> one operand : not
binary operator -> two operand 
 
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
* tautolgy(สัจนิรันดร์) คือ compound proposition ที่มีค่าความจริงเป็นจริงเสมอทุกกรณี always True
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
x = variable, goes to school = predicate
หมายความว่าต้องแทนค่า x ด้วย John หรือ Mary ก่อนถึงจะบอกค่าความจริงได้ 

## Quatifier
* Universal quantifier คือ ∀xP(x) [read : for all x P(x)] ≡ P(x1)∧P(x2)∧…∧P(xn) หมายความว่า P(x) นั้นจะต้องเป็นจริงทุกกรณีใน universal of discourse(x1,x2,...xn) ∀xP(x) ถึงจะเป็นจริง
* Existential quantifier คือ ∃xP(x) [read : for some x P(x)] ≡ P(x1)∨P(x2)∨…∨P(xn) หมายความว่า P(x) นั้นจะต้องเป็นจริงอย่างน้อย 1 กรณีใน universal of discourse ∃xP(x) ถึงจะเป็นจริง
### Negations of quatifier
¬∀xP(x) ≡ ∃x ¬P(x)

¬∃xP(x) ≡ ∀x ¬P(x)


 
