The purpose of this repository is to demonstrate my understanding of binary addition and its theoretical and practical applications. To achieve this, I will explain one of the simplest methods for adding two binary numbers: the half adder. A half adder is a circuit designed to compute the first digit of binary addition. This circuit serves as the foundation for more complex circuits, such as the full adder and the 4-bit adder.

As a brief recap, binary numbers consist only of 0s and 1s, unlike decimal numbers, which use digits from 0 to 9. Because binary has fewer digits, numbers grow in size more quickly compared to decimal. For example, the decimal sequence 0, 1, 2, 3, 4, 5 corresponds to 0, 1, 10, 11, 100, 101 in binary.
![halfadderdiagram (1)](https://github.com/user-attachments/assets/cc678aa9-826d-44bf-bc0a-81150e22a55a)
(Justice, 2020, p. 76)

In the diagram, the half adder (HA) takes two inputs, A and B, representing the two binary digits to be added. The sum is output through S, while Cout represents the carry digit, which is passed to the next place value. The half adder consists of two logic gates: an XOR gate and an AND gate. The XOR gate computes the sum, while the AND gate determines the carry value.
![halfaddergates](https://github.com/user-attachments/assets/70be830b-f2a4-4a70-a6d2-0ce27a2ad067)
According to Justice (2020, p. 77),
since a half adder is built using logic gates and has a limited number of inputs, we can represent all possible outputs using the truth table below. This allows us to verify various results. For example, adding 0 + 0 results in a sum of 0, while 1 + 1 produces a sum of 0 with a carry of 1.
![image](https://github.com/user-attachments/assets/cb0f48e9-8d4f-4db7-92e5-ca14da4fd7b8)
(Justice, 2020, p. 77)

With all of this information in mind, we can now recreate a half adder using integrated circuits. The integrated circuits I'll be using are simply multiple logic gates packed onto one chip. I'll use the circuit diagram below to construct a simple half adder circuit.
![image](https://github.com/user-attachments/assets/a6f7eb6c-21d1-43e5-b51a-be5069780679)
(Justice, 2020, p. 90)

![image](https://github.com/user-attachments/assets/88519da9-4b85-477f-9100-3bb2949b400c)

In the image above, the half adder is adding two binary zeros together. This explains why both the S and Cout LEDs are off—since 0 + 0 results in a sum of 0 and a carry of 0. To change the bits being added, we simply need to toggle either the first or last switch. Below, I flip switch B on, meaning the half adder is now adding 0 and 1 together.

![image](https://github.com/user-attachments/assets/cda51271-37ff-42e6-bb7a-e8524d02ef81)

This combination illuminates the S LED because 0 + 1 equals 1. Both of these examples make sense, but something interesting happens when we flip both inputs on.

![image](https://github.com/user-attachments/assets/350a11e0-877f-4353-8d64-086b6150aa00)

Since a single LED can't represent the binary number 2, we must turn the Sum LED off and carry the extra value to the next place in the addition. This is similar to how, in decimal, adding any number to 9 results in at least two digits (e.g., 9 + 1 = 10, 9 + 6 = 15). The key difference is that binary only has two possible states (0 and 1), whereas decimal uses ten (0 through 9).

However, a half adder is just one small part of the equation. To add numbers larger than 1 bit, a full adder is needed. A full adder consists of two half adders connected by an OR gate. This setup allows the circuit to take three inputs instead of two, with the additional input (Cin) representing the carry value from the previous adder.
![image](https://github.com/user-attachments/assets/0fb8b80c-54ae-413e-b4c7-d99d822439bc)
![image](https://github.com/user-attachments/assets/6c09c0fb-8fb4-42e4-bbf8-f352146d2f74)
(Justice, 2020, p. 78-79)

Half and full adders chained together allow computers to calculate not only binary numbers, but decimal numbers by extension. A four-bit adder, for example, can handle numbers from 0-15. 0000 in binary represents 0 in decimal, and 1111 in binary represents 15. The cap increases exponentially with every new full adder. This means that an 8-bit adder would be able to handle numbers from 0-255 (0 - 11111111 in binary)! This technology is how the first solid-state transistor calculator, the IBM 608, was created in 1955.
![image](https://github.com/user-attachments/assets/1c419b34-f1b4-43b4-bd72-921d937d8c6c)
While this may look a set of kitchen appliances, this calculator is capable of dealing with up to 18-digit decimal numbers in fractions of a second. All thanks to boards that don't function much differently than the one we created. Of course calculators have become much smaller since then, but early calculators go to show how far we've come in computing power.
References

Cruz, F. (2001, January). The IBM 608 Calculator. Columbia University. Retrieved September 23, 2024, from https://www.columbia.edu/cu/computinghistory/608.html
Justice, M. (2020). How Computers Really Work: A Hands-On Guide to the Inner Workings of the Machine. No Starch Press.
