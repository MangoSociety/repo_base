#в_процессе 

Sphere : [[android]]
Theme : [[Nothing]]
Title: Есть ли аналог Nothing на Java

### Content

Тип `Nothing` является особенным, поскольку **в Java ему нет аналогов**.

Действительно, каждый ссылочный тип Java, включая `java.lang.Void`, принимает в качестве значения `null`, а `Nothing` не принимает даже этого. Таким образом, этот тип не может быть точно представлен в мире Java. Вот почему Kotlin генерирует необработанный тип, в котором используется аргумент типа `Nothing`:

```kotlin
fun emptyList(): List<Nothing> = listOf()
// is translated to
// List emptyList() { ... }
```
### External Link

- ....

### Internal Link

- ....