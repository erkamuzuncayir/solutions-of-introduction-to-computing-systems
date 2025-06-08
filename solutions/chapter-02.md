# Chapter 02

1. Given n bits, how many distinct combinations of the n bits exist?
	1. 2^n
---
2. There are 26 characters in the alphabet we use for writing English. What is the least number of bits needed to give each character a unique bit pattern? How many bits would we need to distinguish between upperand lowercase versions of all 26 characters?
	1. 26 * 2 = 52 character. So we need 6 bit to represent all of those characters which can represent up to 64 characters.
---
3. Solution:
	1. Assume that there are about 400 students in your class. If every student is to be assigned a unique bit pattern, what is the minimum number of bits required to do this?
		1. 9 bits required. It can represent up to 512 characters.
	2. How many more students can be admitted to the class without requiring additional bits for each student’s unique bit pattern?
		1. Just I say, 512-400 = 112. Up to 112 people we don't need any new bit.
---
4. Given n bits, how many unsigned integers can be represented with the n bits? What is the range of these integers?
	1. 2^n. But range will be 0 to (2^n)-1 because the representing of 0.
---
5. Using five bits to represent each number, write the representations of 7 and −7 in 1’s complement, signed magnitude, and 2’s complement integers.
	1. Signed magnitude = 7 = 00111 / -7 = 10111
	2. 1's Complement = 7 = 00111 / -7 = 11000
	3. 2's Complement = 7 = 00111 / -7 = 11001
---
6. Write the six-bit 2’s complement representation of −32
	1. 100000
---
7. Create a table showing the decimal values of all four-bit 2’s complement numbers.
	1. 0000 = 0 / 1000 = -8
	2. 0001 = 1 / 1001 = -7
	3. 0010 = 2 / 1010 = -6
	4. 0011 = 3 / 1011 = -5
	5. 0100 = 4 / 1100 = -4
	6. 0101 = 5 / 1101 = -3
	7. 0110 = 6 / 1110 = -2
	8. 0111 = 7 / 1111 = -1
---
8. Solution:
	1. What is the largest positive number one can represent in an eight-bit 2’s complement code? Write your result in binary and decimal.
		1. 0111 1111 = 127
	2. What is the greatest magnitude negative number one can represent in an eight-bit 2’s complement code? Write your result in binary and decimal.
		1. 1000 0000 = -128
	3. What is the largest positive number one can represent in n-bit 2’s complement code?
		1. 2^(n-1) - 1
	4. What is the greatest magnitude negative number one can represent in n-bit 2’s complement code?
		1. -2^(n-1)
---
9. How many bits are needed to represent Avogadro’s number (6.02 ⋅ 1023) in 2’s complement binary representation?
	1. log(2(6.02 * 10^23))= 2^79.08 ~= 2^80 = 1 bit for sign so 2^81.
---
10. Convert the following 2’s complement binary numbers to decimal.
	1. 1010 = -6
	2. 01011010 = 90
	3. 11111110 = -2
	4. 0011100111010011 = 14803
---
11. Convert these decimal numbers to eight-bit 2’s complement binary numbers.
	1. 102
		1. 01100110
	2. 64
		1. 0100 0000
	3. 33
		1. 0010 0001
	4. −128
		1. 1000 0000
	5. 127
		1. 0111 1111
---
12. If the last digit of a 2’s complement binary number is 0, then the number is even. If the last two digits of a 2’s complement binary number are 00 (e.g., the binary number 01100), what does that tell you about the number?
	1. It means it is power of 4.
---
13. Without changing their values, convert the following 2’s complement binary numbers into eight-bit 2’s complement numbers.
	1. 1010
		1. 0000 0101
	2. 011001
		1. 0001 1001
	3. 1111111000
		1. 1111 1000
	4. 01
		1. 0000 0001
---
14. Add the following bit patterns. Leave your results in binary form.
	1. 1011 + 0001
		1. 1100
	2. 0000 + 1010
		1. 1010
	3. 1100 + 0011
		1. 1111
	4. 0101 + 0110
		1. 1011
	5. 1111 + 0001
		1. 1 0000
---
15. It was demonstrated in Example 2.5 that shifting a binary number one bit to the left is equivalent to multiplying the number by 2. What operation is performed when a binary number is shifted one bit to the right?
	1. Dividing the number by 2
---
16. Write the results of the following additions as both eight-bit binary and decimal numbers. For each part, use standard binary addition as described in Section 2.5.1.
	1. Add the 1’s complement representation of 7 to the 1’s complement representation of −7.
		1. 0000 0111 + 1111 1000 = 1111 1111 = 0
	2. Add the signed magnitude representation of 7 to the signed magnitude representation of −7.
		1. 0000 0111 + 1000 0111 = 1000 1110
	3. Add the 2’s complement representation of 7 to the 2’s complement representation of −7.
		1. 0000 0111 + 1111 1001 = 1 0000 0000 = 0 in 8 bit
---
17. Add the following 2’s complement binary numbers. Also express the answer in decimal.
	1. 01 + 1011 = 0001 + 1011 = 1100 = -4
	2. 11 + 01010101 = 1111 1111 + 0101 0101 = (01) 0101 0100 = 84
	3. 0101 + 110 = 0101 + 1110 = (01) 0011 = 3
	4. 01+10 = 11 = -1
---
18. Add the following unsigned binary numbers. Also, express the answer in decimal.
	1. 01 + 1011 = 1100 = 12
	2. 11 + 01010101 = 0101 1000
	3. 0101 + 110 = 1011 = 11
	4. 01+10 = 11 = 3
---
19. Express the negative value −27 as a 2’s complement integer, using eight bits. Repeat, using 16 bits. Repeat, using 32 bits. What does this illustrate with respect to the properties of sign-extension as they pertain to 2’s complement representation?
	1. 1110 0101 = 1111 1111 1110 0101 = 1111 1111 1111 1111 1111 1111 1110 0101
	2. 1's doesn't change anything.
---
20. The following binary numbers are four-bit 2’s complement binary numbers. Which of the following operations generate overflow? Justify your answer by translating the operands and results into decimal.
	1. 1100 + 0011
		1. 1111. No
	2. 1100 + 0100
		1. 0000. No
	3. 0111 + 0001
		1. Yes because result should be 0 1000 which is 8 but without 5th byte result will be 1000 which is -8.
	4. 1000 − 0001
		1. Yes because 1000 is '-8', 0001 is '1', the result should be -8 - 1 = -9. To subtract '1' we should represent it as negative '1111' and add to '1000' (-8). 1000 + 1111 = 1 0111 (-9). But without first (5's) bit the answer is positive 7 (0111). So, overflow occurred.
	5. 0111 + 1001
		1.  No.
---
21. Describe what conditions indicate overflow has occurred when two 2’s complement numbers are added.
	1. Overflow occurs in 2's complement addition when:
		1. Two positive numbers are added, and the result is negative.
		2. Two negative numbers are added, and the result is positive.
---
22. Create two 16-bit 2’s complement integers such that their sum causes an overflow?
	1. 0111 1111 1111 1111 + 0000 0000 0000 0001
---
23. Describe what conditions indicate overflow has occurred when two unsigned numbers are added.
	1. If the two unsigned number added and leftmost digit of the sum will be 1 this means an overflow occured. Because unsigned numbers are positive and leftmost digit is 0.
---
24. Create two 16-bit unsigned integers such that their sum causes an overflow.
	1. 1111 1111 1111 1111 + 0000 0000 0000 0001
---
25. Why does the sum of a negative 2’s complement number and a positive 2’s complement number never generate an overflow?
	1. When adding a negative and a positive 2's complement number, overflow is not possible because the result will always be within the range of representable values for the given bit width.
---
26. You wish to express −64 as a 2’s complement number.
	1. How many bits do you need (the minimum number)?
		1. 7
	2. With this number of bits, what is the largest positive number you can represent? (Please give answer in both decimal and binary.)
		1. 011 1111 = 63
	3. With this number of bits, what is the largest unsigned number you can represent? (Please give answer in both decimal and binary.)
		1. 111 1111 = 127
---
27. The LC-3, a 16-bit machine, adds the two 2’s complement numbers 0101010101010101 and 0011100111001111, producing 1000111100100100. Is there a problem here? If yes, what is the problem? If no, why not?
	1. Yes, it created overflow. He sum two positive numbers but sum is negative.
---
28. If both operands will be 1, then AND operation equal to  1.
---
29. Solution:
	1. 0
	2. 0
	3. 0
	4. 1
---
30. Solution:
	1. 01010111
	2. 100
	3. 10000000
	4. 00010100
	5. 0000
	6. 0000
---
31. If any operands or, both of them are 1, then result will be 1.
---
32. Solution:
	1. 0
	2. 0
	3. 0
	4. 1
---
33. Solution:
	1. 11010111
	2. 111
	3. 11110100
	4. 10111111
	5. 1101
	6. 1101
---
34. Solution:
	1. 0111
	2. 0101
	3. 1101
	4. 0110
---
35. Masks used for masking unchanged value will be remain same.
---
36. Solution:
	1. OR 01000000
	2. AND 10111101
	3. OR 11111111
	4. AND 00000000
	5. Solution:
		1. Mask with m = 0000 0100
		2. Bitwise AND with m (0000 0100)
		3. Shift until the MSB by 5 (<< 5)
		4. Result
			1. (m AND BUSYNESS) << 5
---
37. (((n >> 3) AND (m >> 3) AND NOT(s >> 3)) OR (NOT(n >> 3) AND NOT(m >> 3) AND s >> 3) << 3
---
38. (((n >> 3) AND (m >> 3) AND NOT(s >> 3))) OR (((n >> 3) AND NOT(s >> 3) AND NOT(m >> 3) OR ((m >> 3) AND NOT(s >> 3) AND NOT(n >> 3))))
---
39. Solution:
	1. 0 1000 0000 11100000000000000000000
	2. 1 1000 0100 10111010111000000000000
	3. 0 1000 0000 10010010000111111011011
	4. 0 1000 0101 00000000000000000000000
---
40. Solution:
	1. (+)2^1 = 2
	2. (-)(2^4)*10001 = 17
	3. (+)2^7 = -128 = unknown
	4. (-)2^1 * 1.001 = -3.125
---
41. Solution:
	1. (2^7)-1
	2. (2^7)-2
---
42. Programmer might have treat to result as a character instead of number.
---
43. Solution:
	1. Hello!
	2. hELLO!
	3. Computers!
	4. LC-2
---
44. Solution:
	1. We can add 0x30 to any ASCII representation for a digit. Because it range from 0011 0000 to 0011 1001 in binary and 0x30 hexadecimal notation of 0011 0000 in binary.
---
45. Solution:
	1.  D1AF
	2.  1F
	3.  1
	4.  EDB2
---
46. Solution:
	1. 1000
	2. 1000 0000 0001
	3. 1111 0111 0011 0001
	4. 1111 0001 1110 0010 1101
	5. 1011 1100 1010 1101
---
47. Solution:
	1. 0001 0000 = -16
	2. 0111 1111 1111 = 2047
	3. 0001 0110 = 22
	4. 1000 0000 0000 0000 = -32768
---
48. Solution:
	1. x100
	2. x6F
	3. x75B CD15
	4. xD4
---
49. Solution:
	1. x2939
	2. x6E36
	3. x47F4
	4. xF1A8
	5. On *c* and *d* overflow occurs.
---
50. Solution:
	1. x5468
	2. xBBFD
	3. xFFFF
	4. x32A3
---
51. Solution:
	1. x645
	2. x4428E800
	3. x48656c6c6f
---
52. Solution:
	1. 
		1. 1129270608
		2. 1129270608
		3. 1129270608
		4. 207.302
		5. COMP
	1. 
		1. 1431586130
		2. 1431586130
		3. 1431586130
		4. 1.4587137e13
		5. UTER
---
53. Solution:
	1. a.
		1. 1
		2. 1
		3. 0
	2. b.
		1. 1
		2. 1
		3. 1
---
54. Solution:
	1. a. 
		1. 1
		2. 0
		3. 0
		4. 1
		5. 1
		6. 0
		7. 0
	2. b.
		1. 1
		2. 1
		3. 1
		4. 1
		5. 1
		6. 1
		7. 0
---
55. Solution:
	1. 2^6-1
	2. 2^(2n)-1
	3. 310
	4. 222
	5. 011011.11
	6. 0 1000 0011 10111100000000000000000
	7. 4^4^m
---
56. -52
