# Week 02

## 목표

Data type과 변수에 대해 알아보기

데이터 타입이 실제로 어떻게 표현되고 저장되는지를 알기



### 2진수(Binary Number)

0과 1 두 가지 숫자만을 사용하여 수를 표현하는 체계

논리적으로 1은 참(true), 0은 거짓(false)을 표현하는데 사용되기도 한다.

| bin      | dec | hex  |
| -------- | --- | ---- |
| 000      | 0   | 0x0  |
| 001      | 1   | 0x1  |
| 101      | 2   | 0x2  |
| 1010     | 10  | 0xA  |
| 1011     | 11  | 0xB  |
| 10000    | 16  | 0x10 |
| 01100100 | 100 | 0x64 |



### bit

0 또는 1의 두 가지 값만을 가지는,

컴퓨터에서 정보를 표현하고 처리하는 데 사용하는 최소 단위

즉 bit를 이용하여 2진수 체계로 수(모든 데이터)를 표현한다.



{% code title="check_cpu.c" lineNumbers="true" %}
```c
#include <stdio.h>

int main()
{
    printf("This system is %lu bit. \n", sizeof(void*) * 8);
    return 0;
}
```
{% endcode %}





### int

정수(integer)를 표현하는 데이터 타입

8개의 bit로 표현할 수 있는 가장 큰 수는?

{% code title="max_value_int.c" lineNumbers="true" %}
```c
#include <stdio.h>
#include <limits.h>

// %zu는 부호 없는 정수 타입인 size_t를 표현하기 위한 서식 지정자 (format specifier)
int main() {
    printf("Signed char max:\t\t %21d, Size: %zu bits\n", SCHAR_MAX, sizeof(signed char) * 8);
    printf("Unsigned char max:\t\t %21u, Size: %zu bits\n", UCHAR_MAX, sizeof(unsigned char) * 8);
    printf("Signed short max:\t\t %21d, Size: %zu bits\n", SHRT_MAX, sizeof(signed short) * 8);
    printf("Unsigned short max:\t\t %21u, Size: %zu bits\n", USHRT_MAX, sizeof(unsigned short) * 8);
    printf("Signed int max:\t\t\t %21d, Size: %zu bits\n", INT_MAX, sizeof(signed int) * 8);
    printf("Unsigned int max:\t\t %21u, Size: %zu bits\n", UINT_MAX, sizeof(unsigned int) * 8);
    printf("Signed long max:\t\t %21ld, Size: %zu bits\n", LONG_MAX, sizeof(signed long) * 8);
    printf("Unsigned long max:\t\t %21lu, Size: %zu bits\n", ULONG_MAX, sizeof(unsigned long) * 8);
    printf("Signed long long max:\t\t %21lld, Size: %zu bits\n", LLONG_MAX, sizeof(signed long long) * 8);
    printf("Unsigned long long max:\t\t %21llu, Size: %zu bits\n", ULLONG_MAX, sizeof(unsigned long long) * 8);

    return 0;
}
```
{% endcode %}



### float

[부동 소수점 방식](https://ko.wikipedia.org/wiki/%EB%B6%80%EB%8F%99%EC%86%8C%EC%88%98%EC%A0%90#32%EB%B9%84%ED%8A%B8\_%EC%BB%B4%ED%93%A8%ED%84%B0%EC%97%90%EC%84%9C%EC%9D%98\_%EB%B6%80%EB%8F%99%EC%86%8C%EC%88%98%EC%A0%90\_%EB%B0%A9%EC%8B%9D)(floating-point)으로 실수를 표현하는 데이터 타입

{% code title="max_value_float.c" lineNumbers="true" %}
```c
#include <stdio.h>
#include <float.h>

int main() {
    printf("Size of float:\t\t\t%zu bytes\n", sizeof(float));
    printf("Max value of float:\t\t%g\n", FLT_MAX);
    printf("Min value of float:\t\t%g\n", FLT_MIN);

    printf("Size of double:\t\t\t%zu bytes\n", sizeof(double));
    printf("Max value of double:\t\t%g\n", DBL_MAX);
    printf("Min value of double:\t\t%g\n", DBL_MIN);

    printf("Size of long double:\t\t%zu bytes\n", sizeof(long double));
    printf("Max value of long double:\t%Lg\n", LDBL_MAX);
    printf("Min value of long double:\t%Lg\n", LDBL_MIN);

    return 0;
}
```
{% endcode %}



### 3.40282e+38

$$
3.40282*10^{38} = 340282000000000000000000000000000000000
$$

### Overflow

Data type의 최대 범위보다 큰 수를 대입함으로써 발생하는 문제

{% code lineNumbers="true" %}
```c
#include <stdio.h>
#include <limits.h>

int main() {
    unsigned char max_uchar = UCHAR_MAX;  // 최대값 255

    printf("%d\n", max_uchar);
    printf("%d\n", ++max_uchar);
    printf("%d\n", ++max_uchar);

    return 0;
}
```
{% endcode %}

&#x20;

## 참고

[printf 함수](https://ko.wikipedia.org/wiki/Printf)

[Data type](https://en.wikipedia.org/wiki/C\_data\_types#Main\_types)





## 과제
