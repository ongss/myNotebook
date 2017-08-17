# Discrete

# Logic 
คือหลักการคำนวนค่าความจริงของประพจน์(proposition) หรือประพจน์ที่มารวมตัวกัน(compound proposition)

## operators
* Negetion (Not) : นิเสธ (¬)
* Conjunction (AND) : และ (˄)
* Disjunction (OR) : หรือ (˅)
* Implication (IF..THEN) : ถ้าแล้ว (→) 
* Biconditional (IF && ONlY IF) : ก็ต่อเมื่อ (↔)
* Exclusive OR (XOR) : นิเสธของก็ต่อเมื่อ 

>Note : ลำดับความสัญของ operator คัญเรียงตามลำดับจากบนลงล่างคือให้ทำ ¬ , ˄ , ˅ , → , ↔ ตามลำดับ เช่น p ˄ ¬q ˅ r → p ↔ s จะเขียนได้เป็น (((p ˄ (¬q)) ˅ r ) → p) ↔ s

## Contrapositive & Converse & Inverse
เป็นการนิยามความสัมพันธ์ที่เกี่ยวกับ operator implication(ถ้าแล้ว) เพิ่มเติมโดยมีความสัมพันธ์ดังนี้
* contrapositive ของ p → q คือ ¬q → ¬p 
* converse ของ p → q คือ q → p
* invert ของ p → q คือ  ¬p → ¬q 

## Consistency
คือกลุ่มของ compound proposition ที่ไม่ขัดแย้งกัน หรือก็คือมีค่าความจริงอย่างน้อยหนึ่งชุดที่ทำให้ทุกๆ compound proposition ในกลุ่มเป็นจริง เช่น
1) p → ¬q
2) q → r
3) ¬r → ¬p 
กลุ่มของ compound proposition นี้เป็น consistency เพราะเมื่อ p ≡ T , q ≡ F, r ≡ T ทั้ง3ประพจน์มีค่าความมจริงเป็นจริง

## Tautology & Contradiction & Contingency
* tautolgy คือ compound proposition ที่มีค่าความจริงเป็นจริงเสมอทุกกรณี
* contradiction คือ compound proposition ที่มีค่าความจริงเป็นเท็จเสมอทุกกรณี
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

##
