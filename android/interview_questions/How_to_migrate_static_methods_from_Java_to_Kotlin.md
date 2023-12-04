#готово 

Sphere : [[android]]
Theme : [[static]]
Title: Как перенести статичные методы из Java в Kotlin

### Content
В Kotlin нет статических методов, для этих целей обычно служит `companion object`.  
Для того чтобы метод из Java был представлен как статический используется аннотация `@JvmStatic`. Эта аннотация говорит компилятору Kotlin создать статический метод в байт-коде, что позволяет использовать методы так же, как в Java.

Например, если у нас есть статический метод в Java:
```java

public class MyClass { public static int sum(int a, int b) { return a + b; } }
```

Мы можем использовать этот метод в Kotlin, добавив аннотацию `@JvmStatic`:
```kotlin

object MyClass { @JvmStatic fun sum(a: Int, b: Int): Int { return a + b } }

```

### External Link

- https://kotlinlang.ru/docs/reference/java-to-kotlin-interop.html

### Internal Link

- ....