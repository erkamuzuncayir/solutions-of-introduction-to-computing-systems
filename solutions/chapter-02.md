# Chapter 2

1. Given n bits, how many distinct combinations of the n bits exist?
	1. 2^n
2. There are 26 characters in the alphabet we use for writing English. What is the least number of bits needed to give each character a unique bit pattern? How many bits would we need to distinguish between upperand lowercase versions of all 26 characters?
	1. 26 * 2 = 52 character. So we need 6 bit to represent all of those characters which can represent up to 64 characters.
3.
	1. Assume that there are about 400 students in your class. If every student is to be assigned a unique bit pattern, what is the minimum number of bits required to do this?
		1. 9 bits required. It can represent up to 512 characters.
	2. How many more students can be admitted to the class without requiring additional bits for each student’s unique bit pattern?
		1. Just I say, 512-400 = 112. Up to 112 people we don't need any new bit.
4. Given n bits, how many unsigned integers can be represented with the n bits? What is the range of these integers?
	1. 2^n. But range will be 0 to (2^n)-1 because the representing of 0.
5. Using five bits to represent each number, write the representations of 7 and −7 in 1’s complement, signed magnitude, and 2’s complement integers.
	1. Signed magnitude = 7 = 00111 / -7 = 10111
	2. 1's Complement = 7 = 00111 / -7 = 11000
	3. 2's Complement = 7 = 00111 / -7 = 11001
6. Write the six-bit 2’s complement representation of −32
	1. 100000
7. Create a table showing the decimal values of all four-bit 2’s complement numbers.
	1. 0000 = 0 / 1000 = -8
	2. 0001 = 1 / 1001 = -7
	3. 0010 = 2 / 1010 = -6
	4. 0011 = 3 / 1011 = -5
	5. 0100 = 4 / 1100 = -4
	6. 0101 = 5 / 1101 = -3
	7. 0110 = 6 / 1110 = -2
	8. 0111 = 7 / 1111 = -1
8.
	1. What is the largest positive number one can represent in an eight-bit 2’s complement code? Write your result in binary and decimal.
		1. 0111 1111 = 127
	2. What is the greatest magnitude negative number one can represent in an eight-bit 2’s complement code? Write your result in binary and decimal.
		1. 1000 0000 = -128
	3. What is the largest positive number one can represent in n-bit 2’s complement code?
		1. 2^(n-1) - 1
	4. What is the greatest magnitude negative number one can represent in n-bit 2’s complement code?
		1. -2^(n-1)
9. How many bits are needed to represent Avogadro’s number (6.02 ⋅ 1023) in 2’s complement binary representation?
	1. log(2(6.02 * 10^23))= 2^79.08 ~= 2^80 = 1 bit for sign so 2^81.
10. Convert the following 2’s complement binary numbers to decimal.
	1. 1010 = -6
	2. 01011010 = 90
	3. 11111110 = -2
	4. 0011100111010011 = 14803
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
12. If the last digit of a 2’s complement binary number is 0, then the number is even. If the last two digits of a 2’s complement binary number are 00 (e.g., the binary number 01100), what does that tell you about the number?
	1. It means it is power of 4.
13. Without changing their values, convert the following 2’s complement binary numbers into eight-bit 2’s complement numbers.
	1. 1010
		1. 0000 0101
	2. 011001
		1. 0001 1001
	3. 1111111000
		1. 1111 1000
	4. 01
		1. 0000 0001
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
15. It was demonstrated in Example 2.5 that shifting a binary number one bit to the left is equivalent to multiplying the number by 2. What operation is performed when a binary number is shifted one bit to the right?
	1. Dividing the number by 2
16. Write the results of the following additions as both eight-bit binary and decimal numbers. For each part, use standard binary addition as described in Section 2.5.1.
	1. Add the 1’s complement representation of 7 to the 1’s complement representation of −7.
		1. 0000 0111 + 1111 1000 = 1111 1111 = 0
	2. Add the signed magnitude representation of 7 to the signed magnitude representation of −7.
		1. 0000 0111 + 1000 0111 = 1000 1110
	3. Add the 2’s complement representation of 7 to the 2’s complement representation of −7.
		1. 0000 0111 + 1111 1001 = 1 0000 0000 = 0 in 8 bit
17. Add the following 2’s complement binary numbers. Also express the answer in decimal.
	1. 01 + 1011 = 0001 + 1011 = 1100 = -4
	2. 11 + 01010101 = 1111 1111 + 0101 0101 = (01) 0101 0100 = 84
	3. 0101 + 110 = 0101 + 1110 = (01) 0011 = 3
	4. 01+10 = 11 = -1
18. Add the following unsigned binary numbers. Also, express the answer in decimal.
	1. 01 + 1011 = 1100 = 12
	2. 11 + 01010101 = 0101 1000
	3. 0101 + 110 = 1011 = 11
	4. 01+10 = 11 = 3
19. Express the negative value −27 as a 2’s complement integer, using eight bits. Repeat, using 16 bits. Repeat, using 32 bits. What does this illustrate with respect to the properties of sign-extension as they pertain to 2’s complement representation?
	1. 1110 0101 = 1111 1111 1110 0101 = 1111 1111 1111 1111 1111 1111 1110 0101
	2. 1's doesn't change anything.
20. The following binary numbers are four-bit 2’s complement binary numbers. Which of the following operations generate overflow? Justify your answer by translating the operands and results into decimal.
	1. 1100 + 0011
		1. 1111. No
	2. 1100 + 0100
		1. 0000. No
	3. 0111 + 0001
		1. Yes because result should be 0 1000 which is 8 but without 5th byte result will be 1000 which is -8.
	4. 1000 − 0001
		1. No.
	5. 0111 + 1001
		1.  No.
21. Describe what conditions indicate overflow has occurred when two 2’s complement numbers are added.
	1. Overflow occurs in 2's complement addition when:
		1. Two positive numbers are added, and the result is negative.
		2. Two negative numbers are added, and the result is positive.
22. Create two 16-bit 2’s complement integers such that their sum causes an overflow?
	1. 0111 1111 1111 1111 + 0000 0000 0000 0001
23. Describe what conditions indicate overflow has occurred when two unsigned numbers are added.
	1. If the two unsigned number added and leftmost digit of the sum will be 1 this means an overflow occured. Because unsigned numbers are positive and leftmost digit is 0.
24. Create two 16-bit unsigned integers such that their sum causes an overflow.
	1. 0111 1111 1111 1111 + 0000 0000 0000 0001
25. Why does the sum of a negative 2’s complement number and a positive 2’s complement number never generate an overflow?
	1. When adding a negative and a positive 2's complement number, overflow is not possible because the result will always be within the range of representable values for the given bit width.
26. You wish to express −64 as a 2’s complement number.
	1. How many bits do you need (the minimum number)?
		1. 7
	2. With this number of bits, what is the largest positive number you can represent? (Please give answer in both decimal and binary.)
		1. 011 1111 = 63
	3. With this number of bits, what is the largest unsigned number you can represent? (Please give answer in both decimal and binary.)
		1. 111 1111 = 127
27. The LC-3, a 16-bit machine, adds the two 2’s complement numbers 0101010101010101 and 0011100111001111, producing 1000111100100100. Is there a problem here? If yes, what is the problem? If no, why not?
	1. Yes, it created overflow. He sum two positive numbers but sum is negative.