#готово 

Sphere : [[android]]
Theme : #Nothing #Unit
Title: Расскажите про типы Unit Nothing

### Content

Тип `Unit` в Kotlin выполняет ту же функцию, что и `void` в Java.

Возвращаемый тип можно не указывать, если функция ничего не возвращает. По умолчанию там будет `Unit`:

```kotlin
fun knockKnock() {
   println("Who’s there?")
}

// то же самое, но с указанным типом Unit
fun knockKnock(): Unit = println("Who’s there?")
```

В стандартной библиотеке Kotlin `Unit` определён как объект, наследуемый от `Any` и содержащий единственный метод, переопределяющий `toString()`

`Unit` **является синглтоном** (ключевое слово `object`). `Unit` ничего не возвращает, а метод `toString` всегда будет возвращать `“kotlin.Unit”`. При компиляции в java-код `Unit` всегда будет превращаться в `void`.

```kotlin
public object Unit {
   override fun toString() = "kotlin.Unit"
}
```

`Nothing` является типом, который полезен при объявлении функции, которая **ничего не возвращает и не завершается**.

Примеры:

- функция, которая выбрасывает `exception` или в которой запущен бесконечный цикл;
    
- функция `TODO()` — `public inline fun TODO(): Nothing = throw NotImplementedError()`;
    
- в тестах есть функция с именем `fail`, которая выдает исключение с определенным сообщением:

```kotlin
fun fail(message: String): Nothing {
    throw IllegalStateException(message)
}
```

`Nothing` в Kotlin — это т.н. **bottom type**, то есть он является подтипом любого другого типа. Наличие `Nothing` в системе типов позволяет типизировано выражать то, что без него принципиально невозможно.

**Bottom type** — это тип, который не имеет значений и предназначен для обозначения невыполнимых ситуаций в программе.

`Nothing` — класс, который является наследником любого класса в Kotlin, даже класса с модификатором `final`. При этом `Nothing` **нельзя создать** — у него **приватный конструктор**. В коде он объявлен так:

```kotlin
public class Nothing private constructor()
```
### External Link

- ....

### Internal Link

- ....