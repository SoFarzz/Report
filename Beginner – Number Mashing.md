# **Beginner – Number Mashing**
Solved by whymir.

## **Question**
Mash your keyboard numpad in a specific order and a flag might just pop out!

## **Flag**
`DUCTF{w0w_y0u_just_br0ke_math!!}`

## **Provided File**
Link Here \[<https://github.com/DownUnderCTF/Challenges_2024_Public/blob/main/beginner/number-mashing/src/number-mashing\>]

## **Solution**
Run the file at first to see what programs it is. Then open the ghidra to do more analysis on it.
[image ghidra https://ibb.co/fxJMqLd]
There is logic where can be concluded as, 
```
Val 1 and Val 2 != 0 and Val 2 != 1.
HoldingValue == Val 1 / Val 2. 
Vulnerability occurs here where it does not check input which mean can be negative. Val 2 = -1. 
For Val 1 always return Val 1 after divide is when it reaches maximum number in int range which 
-2,147,483,647 to 2,147,483,647. 
If we put 2,147,483,648 it will always return 2,147,483,648. 
Why? It wraps the overflow value.
```
[image challenge https://ibb.co/x32Qqdz ]