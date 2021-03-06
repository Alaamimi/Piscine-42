## :information_source: Table Content :

| C01 | Problems |
|--- |--- |
| ex00 | ft_strcpy |
| ex01 | ft_strncpy |
| ex02 | ft_str_is_alpha |
| ex03 | ft_str_is_numeric |
| ex04 | ft_str_is_lowercase |
| ex05 | ft_is_uppercase |
| ex06 | ft_str_is_printable |
| ex07 | ft_strupcase |
| ex08 | ft_strlowcase |
| ex09 | ft_strcapitalize |
| ex10 | ft_str_strlcpy |
| ex11 | ft_putstr_non_printable |
| ex12 | ft_print_memoery |

## MOAR !

</p>
<p align="center">  
<img src="https://tahirjan.com/media/posts/9/responsive/c-string-manipulation-md.jpg" width="1200">
</p>

---

## Exercise 00 : ft_strcpy :

1. :dart: Task :
```c
� Reproduce the behavior of the function strcpy (man strcpy).
� Here�s how it should be prototyped :
char *ft_strcpy(char *dest, char *src);
```

2. :dart: Function :
```c
char	*ft_strcpy(char *dest, char *src)
{

	while(*src != '\0')
	{
		*dest++ = *src++;
	}
	*dest = '\0';
	return(dest);
}
```

3. :wrench: :beetle: Test && Debug :
```c
int	main(void)
{
	char src[] = "testing\n";
	char dest[] = "qq   qqqq\n";
		write(1, "-----\n", 6);
		write(1, "Destination string is : ", 24);
	ft_putstr(dest);
		write(1, "-----\n", 6);
	ft_strcpy(dest, src);
		write(1, "The result is : ", 16);
	ft_putstr(dest);
		write(1, "-----\n", 6);
	char src1[] = "";
	char dest1[] = "42";
		write(1, "Destination string is : ", 24);
	ft_putstr(dest1);
		write(1, "\n", 1);
		write(1, "-----\n", 6);
	ft_strcpy(dest1, src1);
		write(1, "The result is : ", 16);
	ft_putstr(dest1);
		write(1, "\n", 1);
		write(1, "-----\n", 6);
	return (EXIT_SUCCESS);
}
```

4. :8ball: Expected output :
```c
-----
Destination string is : qq   qqqq
-----
The result is : testing
-----
Destination string is : 42
-----
The result is : 
-----
```
---

## Exercise 01 : ft_strncpy :

1. :dart: Task :
```c
� Reproduce the behavior of the function strncpy (man strncpy).
� Here�s how it should be prototyped :
char *ft_strncpy(char *dest, char *src, unsigned int n);
```

2. :dart: Function :
```c
char	*ft_strncpy(char *dest, char *src, unsigned int n)
{
	while (*src != '\0' && n--)
		*dest++ = *src++;
	*dest = '\0';
	return (dest);
}
```
3. :wrench: :beetle: Test && Debug :
```c
int	main(void)
{
	char	dest[] = "";
	char	src[]= "Text1.txt\n";
	unsigned int	n;

	n = 10;
	write(1, "-----\n", 6);
	ft_putstr(src);
	write(1, "\n", 1);
	write(1, "-----\n", 6);
	ft_strncpy(dest, src, n);
	ft_putstr(dest);
	write(1, "\n", 1);
	write(1, "-----\n", 6);
	return (EXIT_SUCCESS);
}
```

4. :8ball: Expected output :
```c
-----
Text1.txt

-----
Text1.txt

-----
```

---

## Exercise 02 : ft_str_is_alpha :

1. :dart: Task :
```c
� Create a function that returns 1 if the string given as a parameter contains only
alphabetical characters, and 0 if it contains any other character.
� Here�s how it should be prototyped :
int ft_str_is_alpha(char *str);
� It should return 1 if str is empty
```

2. :dart: Function :
```c
int	ft_str_is_alpha(char *str)
{
	while (*str != '\0')
	{
		if (!((*str >= 'A' && *str <= 'Z') || (*str >= 'a' && *str <= 'z')))
			return (0);
		*str++;
	}
	return (1);
}
```

3. :wrench: :beetle: Test && Debug :
```c
int	main(void)
{
	/*TEST 1 :*/
	char	str[] = "";
		write(1, "-----\n", 6);
	ft_putstr(str);
		write(1, "\n", 1);
	ft_str_is_alpha(str);
		write(1, "-----\n", 6);
		write(1, "Return : ", 9);
	ft_putnbr(ft_str_is_alpha(str));
		write(1, "\n", 1);
		write(1, "-----\n", 6);
	/*TEST 2 :*/
	char str1[] = "123";
	ft_putstr(str1);
		write(1, "\n", 1);
	ft_str_is_alpha(str1);
		write(1, "-----\n", 6);
		write(1, "Return : ",9);
	ft_putnbr(ft_str_is_alpha(str1));
		write(1, "\n", 1);
		write(1, "-----\n", 6);
	/*TEST 3 :*/
	char	str2[] = "abcDEF";
	ft_putstr(str2);
		write(1, "\n", 1);
		write(1, "-----\n", 6);
	ft_str_is_alpha(str2);
	write(1, "Return :", 9);
	ft_putnbr(ft_str_is_alpha(str2));
		write(1, "\n", 1);
		write(1, "-----\n", 6);
	return (EXIT_SUCCESS);
}
```

---

4. :8ball: Expected output :
```c

-----

-----
Return : 1
-----
123
-----
Return : 0
-----
abcDEF
-----
Return :1
-----
```

## Exercise 03 : ft_str_is_numeric :

1. :dart: Task :
```c
� Create a function that returns 1 if the string given as a parameter contains only
digits, and 0 if it contains any other character.
� Here�s how it should be prototyped :
int ft_str_is_numeric(char *str);
� It should return 1 if str is empty.
```

2. :dart: Function :
```c
int ft_str_is_numeric(char *str)
{
	while (*str != '\0')
	{
		if (!(*str >= '0' && *str <= '9'))
			return (0);
		*str++;
	}
	return (1);
}
```

3. :wrench: :beetle: Test && Debug :
```c
int	main(void)
{
	/*TEST 1 : */
	char	str[] = "";
		write(1, "-----\n", 6);
	ft_putstr(str);
		write(1, "\n", 1);
		write(1, "-----\n", 6);
	ft_str_is_numeric(str);
	ft_putnbr(ft_str_is_numeric(str));
		write(1, "\n", 1);
		write(1, "-----\n", 6);
	/*TEST 2 : */
	char	str1[] = "0bcd11";
	ft_putstr(str1);
		write(1, "\n", 1);
		write(1, "-----\n", 6);
	ft_str_is_numeric(str1);
	ft_putnbr(ft_str_is_numeric(str1));
		write(1, "\n", 1);
		write(1, "-----\n", 6);
	/*TEST 3 :*/
	char	str2[] = "1234";
	ft_putstr(str2);
		write(1, "\n", 1);
		write(1, "-----\n", 6);
	ft_str_is_numeric(str2);
	ft_putnbr(ft_str_is_numeric(str2));
		write(1, "\n", 1);
		write(1, "-----\n", 6);
	return (EXIT_SUCCESS);
}
```

4. :8ball: Expected output :
```c
-----

-----
1
-----
0bcd11
-----
0
-----
1234
-----
1
-----
```

---

## Exercise 04 : ft_str_is_lowercase :

1. :dart: Task :
```c
� Create a function that returns 1 if the string given as a parameter contains only
lowercase alphabetical characters, and 0 if it contains any other character.
� Here�s how it should be prototyped :
int ft_str_is_lowercase(char *str);
� It should return 1 if str is empty.
```
2. :dart: Function :
```c
int	ft_str_is_lowercase(char *str)
{
	while (*str != '\0')
	{
		if (!(*str >= 'a' && *str <= 'z'))
			return (0);
		*str++;
	}
	return (1);
}
```

3. :wrench: :beetle: Test && Debug :
```c
int	main(void)
{
	/*TEST 1 : */
	char	str[] = "abcd";
		write(1, "-----\n" , 6);
	ft_putstr(str);
		write(1, "\n", 1);
	ft_str_is_lowercase(str);
		write(1, "Return : ", 9);
	ft_putnbr(ft_str_is_lowercase(str));
		write(1, "\n", 1);
		write(1, "-----\n", 6);
	/*TEST 2 : */
	char	str1[] = "aaaAAAaaa";
	ft_putstr(str1);
		write(1, "\n", 1);
		write(1, "-----\n", 6);
	ft_str_is_lowercase(str1);
	write(1, "Return : ", 9);
	ft_putnbr(ft_str_is_lowercase(str1));
		write(1, "\n", 1);
		write(1, "-----\n", 6);
	/*TEST 3 : */
	char	str2[] = "";
	ft_putstr(str2);
		write(1, "\n", 1);
		write(1, "-----\n",6);
	ft_str_is_lowercase(str2);
	ft_putnbr(ft_str_is_lowercase(str2));
		write(1, "\n", 1);
		write(1, "-----\n", 6);
	return (EXIT_SUCCESS);
}
```

4. :8ball: Expected output :
```c
-----
abcd
-----
Return : 1
-----
aaaAAAaaa
-----
Return : 0
-----

-----
Return : 1
-----
```

---

## Exercise 05 : ft_str_is_uppercase :

1. :dart: Task :
```c
� Create a function that returns 1 if the string given as a parameter contains only
uppercase alphabetical characters, and 0 if it contains any other character.
� Here�s how it should be prototyped :
int ft_str_is_uppercase(char *str);
� It should return 1 if str is empty.
```

2. :dart: Function :
```c
int	ft_str_is_uppercase(char *str)
{
	while (*str != '\0')
	{
		if (!(*str >= 'A' && *str <= 'Z'))
			return (0);
		str++;
	}
	return (1);
}
```

3. :wrench: :beetle: Test && Debug :
```c
int	main(void)
{
	/*TEST 1 : */
	char	str[] = "ABCD";
		write(1, "-----\n" , 6);
	ft_putstr(str);
		write(1, "\n", 1);
		write(1, "-----\n", 6);
	ft_str_is_uppercase(str);
		write(1, "Return : ", 9);
	ft_putnbr(ft_str_is_uppercase(str));
		write(1, "\n", 1);
		write(1, "-----\n", 6);
	/*TEST 2 : */
	char	str1[] = "AAAaaaAAA";
	ft_putstr(str1);
		write(1, "\n", 1);
		write(1, "-----\n", 6);
	ft_str_is_uppercase(str1);
	write(1, "Return : ", 9);
	ft_putnbr(ft_str_is_uppercase(str1));
		write(1, "\n", 1);
		write(1, "-----\n", 6);
	/*TEST 3 : */
	char	str2[] = "";
	ft_putstr(str2);
		write(1, "\n", 1);
		write(1, "-----\n",6);
	ft_str_is_uppercase(str2);
	ft_putnbr(ft_str_is_uppercase(str2));
		write(1, "\n", 1);
		write(1, "-----\n", 6);
	return (EXIT_SUCCESS);
}
```

4. :8ball: Expected output :
```c
-----
ABCD
-----
Return : 1
-----
AAAaaaAAA
-----
Return : 0
-----

-----
Return : 1
-----
```

---

## Exercise 06 : ft_str_is_printable :

1. :dart: Task :
```c
� Create a function that returns 1 if the string given as a parameter contains only
printable characters, and 0 if it contains any other character.
� Here�s how it should be prototyped :
int ft_str_is_printable(char *str);
� It should return 1 if str is empty.
```

2. :dart: Function :
```c
```

3. :wrench: :beetle: Test && Debug :
```c
```

4. :8ball: Expected output :
```c
```

## Exercise 07 : ft_strupcase :

1. :dart: Task :
```c
� Create a function that transforms every letter to uppercase.
� Here�s how it should be prototyped :
char *ft_strupcase(char *str);
� It should return str.
```

2. :dart: Function :
```c
```

3. :wrench: :beetle: Test && Debug :
```c
```

4. :8ball: Expected output :
```c
```

---

---

## Exercise 08 : ft_strlowcase :

1. :dart: Task :
```c
� Create a function that transforms every letter to lowercase.
� Here�s how it should be prototyped :
char *ft_strlowcase(char *str);
� It should return str.
```

2. :dart: Function :
```c
```

3. :wrench: :beetle: Test && Debug :
```c
```

4. :8ball: Expected output :
```c
```
---

## Exercise 09 : ft_strcapitalize :

1. :dart: Task :
```c
� Create a function that capitalizes the first letter of each word and transforms all
other letters to lowercase.
� A word is a string of alphanumeric characters.
� Here�s how it should be prototyped :
char *ft_strcapitalize(char *str);
� It should return str.
```

2. :dart: Function :
```c
```

3. :wrench: :beetle: Test && Debug :
```c
```

4. :8ball: Expected output :
```c
```
---

## Exercise 10 : ft_strlcpy :

1. :dart: Task :
```c
� Reproduce the behavior of the function strlcpy (man strlcpy).
� Here�s how it should be prototyped :
unsigned int ft_strlcpy(char *dest, char *src, unsigned int size);
```

2. :dart: Function :
```c
```

3. :wrench: :beetle: Test && Debug :
```c
```

4. :8ball: Expected output :
```c
```

## Exercise 11 : ft_putstr_non_printable :

1. :dart: Task :
```c
� Create a function that displays a string of characters onscreen. If this string contains characters that aren�t printable, they�ll have to be displayed in the shape of
hexadecimals (lowercase), preceeded by a "backslash".
� For example :
Coucou\ntu vas bien ?
� The function should display :
Coucou\0atu vas bien ?
� Here�s how it should be prototyped :
void ft_putstr_non_printable(char *str);
```

2. :dart: Function :
```c
```

3. :wrench: :beetle: Test && Debug :
```c
```

4. :8ball: Expected output :
```c
```

## Exercise 12 : ft_print_memory :

1. :dart: Task :
```c
� Create a function that displays the memory area onscreen.
� The display of this memory area should be split into three "columns" separated by
a space :
? The hexadecimal address of the first line�s first character followed by a �:�.
? The content in hexadecimal with a space each 2 characters and should be
padded with spaces if needed (see the example below).
? The content in printable characters.
� If a character is non-printable, it�ll be replaced by a dot.
� Each line should handle sixteen characters.
� If size equals to 0, nothing should be displayed.
```
2. :dart: Function :
```c
```

3. :wrench: :beetle: Test && Debug :
```c
```

4. :8ball: Expected output :
```c
```

---



