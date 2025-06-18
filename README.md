# ex00 - ft_putchar.c

**Explicación:**

Esta función `ft_putchar` imprime un solo carácter en la salida estándar. Usa `write`, la función de sistema de bajo nivel que permite enviar datos directamente a un descriptor de archivo, en este caso `1` que representa la salida estándar.

```c
#include <unistd.h>
    
void    ft_putchar(char c)
{   
        write(1, &c, 1);
} 
```

**Paso a Paso**
```c
#include <unistd.h>
```
- Incluye la librería `unistd.h`, que proporciona acceso a la función `write`.

```c
void    ft_putchar(char c)
```
- Declara una función `ft_putchar` que recibe un carácter `c`.

```c
write(1, &c, 1);
```

- Usa `write` para imprimir un solo carácter.
    - `1`: descriptor de archivo para stdout.
    - `&c`: dirección de memoria del carácter.
    - `1`: número de bytes a escribir (1 carácter).

# ex01 - ft_print_alphabet.c

**Explicación:**

La función `ft_print_alphabet` imprime las letras del alfabeto desde la 'a' hasta la 'z' usando un bucle `while`. Cada letra se escribe individualmente con `write`.

```c
#include <unistd.h>

void	ft_print_alphabet(void)
{
	char	a;

	a = 'a';
	while (a <= 'z')
	{
		write(1, &a, 1);
		a++;
	}
}
```

**Paso a Paso**
```c
#include <unistd.h>
```
- Incluye la librería `unistd.h`, necesaria para usar la función write.
```c
void ft_print_alphabet(void)
```
- Declara la función `ft_print_alphabet`, que no recibe argumentos ni devuelve valor.
```c
char a;
a = 'a';
```
- Declara una variable `a` e inicializa con el carácter `'a'`.
```c
while (a <= 'z')
```
- Inicia un bucle que se ejecuta mientras `a` sea menor o igual a `'z'`.
```c
write(1, &a, 1);
```
- Imprime el carácter actual almacenado en `a`.

    - `1`: representa la salida estándar.

    - `&a`: dirección de memoria del carácter a imprimir.

    - `1`: cantidad de bytes a escribir (un carácter).
```c
a++;
```
- Incrementa `a` al siguiente carácter en el alfabeto.

# ex02 - ft_print_reverse_alphabet.c

**Explicación:**

La función `ft_print_reverse_alphabet` imprime las letras del alfabeto desde la 'z' hasta la 'a' en orden decreciente, utilizando un bucle `while` y `write` para mostrar cada carácter.

```c
#include <unistd.h>

void	ft_print_reverse_alphabet(void)
{
	char	c;

	c = 'z';
	while (c >= 'a')
	{
		write(1, &c, 1);
		c--;
	}
}
```

**Paso a Paso**
```c
#include <unistd.h>
```
- Incluye la librería que permite usar la función `write`.
```c
void ft_print_reverse_alphabet(void)
```
- Declara la función sin argumentos ni retorno.
```c
char c;
c = 'z';
```
- Declara la variable `c` e inicia desde la letra `'z'`.
```c
while (c >= 'a')
```
- Bucle que continúa mientras `c` sea mayor o igual a `'a'`.
```c
write(1, &c, 1);
```
- Imprime el carácter actual en la salida estándar.

    - `1`: stdout.

    - `&c`: dirección del carácter.

    - `1`: un byte.
```c
c--;
```
- Decrementa `c` al carácter anterior del alfabeto.

# ex03 - ft_print_numbers.c

**Explicación:**

La función `ft_print_numbers` muestra los dígitos del 0 al 9. Se recorre con un bucle `while` desde el carácter '0' hasta '9', y se imprime cada uno con `write`.

```c
#include <unistd.h>

void	ft_print_numbers(void)
{
	char	n;

	n = '0';
	while (n <= '9')
	{
		write(1, &n, 1);
		n++;
	}
}
```

**Paso a Paso**
```c
#include <unistd.h>
```
- Incluye la librería con `write`.
```c
void ft_print_numbers(void)
```
- Declara la función que imprime los números del 0 al 9.
```c
char n;
n = '0';
```
- Declara e inicia la variable `n` en el carácter `'0'`.
```c
while (n <= '9')
```
- Bucle que recorre del 0 al 9.
```c
write(1, &n, 1);
```
- Imprime el carácter actual.
```c
n++;
```
- Incrementa `n` al siguiente dígito.

# ex04 - ft_is_negative.c

**Explicación:**

`ft_is_negative` comprueba si el número recibido es negativo. Si es menor que 0, muestra 'N'. En caso contrario (positivo o 0), muestra 'P'.

```c
#include <unistd.h>

void	ft_is_negative(int n)
{
	if (n < 0)
		write(1, "N", 1);
	else
		write(1, "P", 1);
}
```

**Paso a Paso**
```c
#include <unistd.h>
```
- Necesaria para `write`.
```c
void ft_is_negative(int n)
```
- Declara una función que recibe un entero `n`.
```c
if (n < 0)
```
- Si el número es menor que cero…
```c
write(1, "N", 1);
```
- Imprime `'N'` en pantalla.
```c
else
```
- Si no es negativo (positivo o cero)…
```c
write(1, "P", 1);
```
- Imprime `'P'`.

# ex05 - ft_print_comb.c

**Explicación:**

La función `ft_print_comb` imprime todas las combinaciones posibles de tres dígitos diferentes en orden creciente. Utiliza tres bucles anidados y evita repetir combinaciones o invertir el orden. Después de cada combinación, si no es la última, imprime una coma y un espacio.

```c
#include <unistd.h>

void	ft_print_comb(void)
{
	char	a;
	char	b;
	char	c;

	a = '0';
	while (a <= '7')
	{
		b = a + 1;
		while (b <= '8')
		{
			c = b + 1;
			while (c <= '9')
			{
				write(1, &a, 1);
				write(1, &b, 1);
				write(1, &c, 1);
				if (!(a == '7' && b == '8' && c == '9'))
					write(1, ", ", 2);
				c++;
			}
			b++;
		}
		a++;
	}
}
```

**Paso a Paso**
```c
#include <unistd.h>
```
- Incluye la librería para usar la función `write`.
```c
void ft_print_comb(void)
```
- Declara la función sin parámetros ni retorno.
```c
char a;
char b;
char c;
```
- Declara tres variables `a`, `b` y `c` para representar los dígitos.
```c
a = '0';
```
- Inicializa `a` en el carácter `'0'`.
```c
while (a <= '7')
```
- Bucle externo: `a` va desde `'0'` hasta `'7'` (porque `b` y `c` deben ser mayores).
```c
b = a + 1;
```
- Inicializa `b` en el siguiente carácter a `a`.
```c
while (b <= '8')
```
- Bucle intermedio: `b` va hasta `'8'`.
```c
c = b + 1;
```
- Inicializa `c` en el siguiente carácter a `b`.
```c
while (c <= '9')
```
- Bucle interno: `c` va hasta `'9'`.
```c
write(1, &a, 1);
write(1, &b, 1);
write(1, &c, 1);
```
- Imprime los caracteres `a`, `b` y `c` uno a uno.
```c
if (!(a == '7' && b == '8' && c == '9'))
```
- Si la combinación no es la última (`789`), imprime:
```c
write(1, ", ", 2);
```
- La coma y espacio para separar las combinaciones.
```c
c++;
```
- Incrementa `c`.
```c
b++;
```
- Incrementa `b` después de terminar con `c`.
```c
a++;
```
- Incrementa `a` después de terminar con `b`.

# ex06 - ft_print_comb2.c

**Explicación:**

`ft_print_comb2` imprime todas las combinaciones posibles de dos números distintos entre 00 y 99, sin repetir ni invertir. Utiliza dos bucles anidados para generar los pares `(a, b)` donde `a < b`. Se formatea cada número como dos dígitos con ceros a la izquierda, y se imprime con `write`.

```c
#include <unistd.h>

void	ft_print_comb2(void)
{
	char	a;
	char	b;
	char	buf[5];

	a = 0;
	while (a <= 98)
	{
		b = a + 1;
		while (b <= 99)
		{
			buf[0] = (a / 10) + '0';
			buf[1] = (a % 10) + '0';
			buf[2] = ' ';
			buf[3] = (b / 10) + '0';
			buf[4] = (b % 10) + '0';
			write(1, buf, 5);
			if (!(a == 98 && b == 99))
				write(1, ", ", 2);
			b++;
		}
		a++;
	}
}
```

**Paso a Paso**
```c
#include <unistd.h>
```
- Incluye la librería para usar `write`.
```c
void ft_print_comb2(void)
```
- Declara la función sin parámetros ni retorno.
```c
char a;
char b;
char buf[5];
```
- Declara las variables `a` y `b` para los números y `buf` como buffer para almacenar la combinación formateada.
```c
a = 0;
```
- Inicializa `a` en 0.
```c
while (a <= 98)
```
- Bucle externo: `a` va desde 0 hasta 98.
```c
b = a + 1;
```
- Inicializa `b` en el siguiente número a `a`.
```c
while (b <= 99)
```
- Bucle interno: `b` va hasta 99.
```c
buf[0] = (a / 10) + '0';
buf[1] = (a % 10) + '0';
```
- Convierte el número `a` en dos caracteres, decenas y unidades, sumando `'0'` para obtener el carácter ASCII.
```c
buf[2] = ' ';
```
- Añade un espacio entre los dos números.
```c
buf[3] = (b / 10) + '0';
buf[4] = (b % 10) + '0';
```
- Convierte el número `b` en dos caracteres, decenas y unidades.
```c
write(1, buf, 5);
```
- Imprime el buffer completo de 5 caracteres.
```c
if (!(a == 98 && b == 99))
```
- Si no es la última combinación, imprime:
```c
write(1, ", ", 2);
```
- La coma y espacio para separar combinaciones.
```c
b++;
```
- Incrementa `b`.
```c
a++;
```
- Incrementa `a` después de terminar con `b`.

# ex07 - ft_putnbr.c

**Explicación:**

La función `ft_putnbr` imprime un número entero, incluyendo negativos y el caso especial del mínimo entero `-2147483648`. Si el número es negativo, primero se imprime un signo `-`. Luego convierte el número en positivo (si no lo era ya) y usa recursión para imprimir cada dígito uno por uno.

```c
#include <unistd.h>

void	ft_putnbr(int nb)
{
	char	d;

	if (nb == -2147483648)
	{
		write(1, "-2147483648", 11);
		return ;
	}
	if (nb < 0)
	{
		write(1, "-", 1);
		nb = -nb;
	}
	if (nb >= 10)
		ft_putnbr(nb / 10);
	d = nb % 10 + '0';
	write(1, &d, 1);
}
```

**Paso a Paso**
```c
#include <unistd.h>
```
- Incluye la librería para usar `write`.
```c
void ft_print_comb3(void)
```
- Declara la función sin parámetros ni retorno.
```c
char a;
char b;
char c;
char buf[6];
```
- Declara las variables `a`, `b`, `c` para los dígitos y `buf` para almacenar la combinación formateada.
```c
a = 0;
```
- Inicializa `a` en 0.
```c
while (a <= 7)
```
- Bucle externo: `a` va desde 0 hasta 7.
```c
b = a + 1;
```
- Inicializa `b` en el siguiente número a `a`.
```c
while (b <= 8)
```
- Bucle intermedio: `b` va hasta 8.
```c
c = b + 1;
```
- Inicializa `c` en el siguiente número a `b`.
```c
while (c <= 9)
```
- Bucle interno: `c` va hasta 9.
```c
buf[0] = a + '0';
buf[1] = ' ';
buf[2] = b + '0';
buf[3] = ' ';
buf[4] = c + '0';
```
- Almacena en `buf` los números `a`, `b` y `c` como caracteres, con espacios intermedios.
```c
write(1, buf, 5);
```
- Imprime los 5 caracteres almacenados en `buf`.
```c
if (!(a == 7 && b == 8 && c == 9))
```
- Si no es la última combinación, imprime:
```c
write(1, ", ", 2);
```
- La coma y espacio para separar combinaciones.
```c
c++;
```
- Incrementa `c`.
```c
b++;
```
- Incrementa `b`.
```c
a++;
```
- Incrementa `a`.

# ex08 - ft_print_combn.c

**Explicación:**

`ft_print_combn` imprime todas las combinaciones posibles de `n` dígitos distintos en orden creciente. Se usa un array `tab` para representar cada combinación. Se incrementan los dígitos de derecha a izquierda cuando es necesario, y se imprime cada combinación con `ft_putchar`. Se asegura de no imprimir una coma después de la última combinación.

```c
#include <unistd.h>

void	ft_putchar(char c)
{
	write(1, &c, 1);
}

void	print_comb(int *tab, int n)
{
	int	i;

	i = 0;
	while (i < n)
		ft_putchar(tab[i++] + '0');
	if (tab[0] != 10 - n)
		write(1, ", ", 2);
}

void	ft_print_combn(int n)
{
	int	tab[10];
	int	pos;

	if (n < 1 || n > 9)
		return ;
	pos = 0;
	while (pos < n)
	{
		tab[pos] = pos;
		pos++;
	}
	pos--;
	while (tab[0] <= 10 - n)
	{
		print_comb(tab, n);
		tab[n - 1]++;
		pos = n - 1;
		while (pos > 0 && tab[pos] > 9 - (n - 1 - pos))
		{
			tab[pos - 1]++;
			tab[pos] = tab[pos - 1] + 1;
			pos--;
		}
	}
}
```

**Paso a Paso**
```c
#include <unistd.h>
```
- Incluye la librería para usar `write`.
```c
void ft_print_comb4(void)
```
- Declara la función sin parámetros ni retorno.
```c
char a;
char b;
char c;
char d;
char buf[5];
```
- Declara las variables para los dígitos y `buf` para almacenar la combinación.
```c
a = 0;
```
- Inicializa `a` en 0.
```c
while (a <= 6)
```
- Bucle externo: `a` va de 0 a 6.
```c
b = a + 1;
```
- Inicializa `b` después de `a`.
```c
while (b <= 7)
```
- Bucle para `b`.
```c
c = b + 1;
```
- Inicializa `c` después de `b`.
```c
while (c <= 8)
```
- Bucle para `c`.
```c
d = c + 1;
```
- Inicializa `d` después de `c`.
```c
while (d <= 9)
```
- Bucle para `d`.
```c
buf[0] = a + '0';
buf[1] = b + '0';
buf[2] = c + '0';
buf[3] = d + '0';
```
- Asigna los números como caracteres en el buffer.
```c
write(1, buf, 4);
```
- Imprime la combinación.
```c
if (!(a == 6 && b == 7 && c == 8 && d == 9))
```
- Si no es la última combinación, imprime:
```c
write(1, ", ", 2);
```
- La coma y espacio para separar.
```c
d++;
```
- Incrementa `d`.
```c
c++;
```
- Incrementa `c`.
```c
b++;
```
- Incrementa `b`.
```c
a++;
```gm
- Incrementa `a`.
