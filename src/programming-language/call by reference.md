# What


> 참조에 의한 호출

call by reference 호출 방식은 함수 호출 시 인자로 전달되는 **변수의 레퍼런스를 전달**함

따라서 함수 안에서 인자 값이 변경되면, 아규먼트로 전달된 객체의 값도 변경됨

```c
void func(int *n) {
    *n = 20;
}

void main() {
    int n = 10;
    func(&n);
    printf("%d", n);
}
```

> printf로 출력되는 값은 20이 된다.

# Why


# How