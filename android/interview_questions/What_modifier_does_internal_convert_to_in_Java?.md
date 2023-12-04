#готово 

Sphere : [[android]]
Theme : [[Modifier]]
Title: В какой модификатор преобразуется internal в Java

### Content
В Java нет эквивалента модификатору доступа `internal` из Kotlin. При компиляции Kotlin-кода в Java-байткод, модификатор доступа `internal` преобразуется в модификатор `public` в Java.

Таким образом, все члены класса, отмеченные как `internal`, будут видны из любого места в том же пакете, а также из любого другого модуля, которому был разрешен доступ к этому модулю. Члены `internal` классов проходят через искажение имен, чтобы усложнить случайное использование их из Java и позволить перегрузку для членов с одинаковыми сигнатурами, которые не видят друг друга в соответствии с правилами Kotlin.

### External Link

- https://4comprehension.com/kotlins-internal-visibility-modifier-and-java-interoperability/
- https://kotlinlang.ru/docs/reference/java-to-kotlin-interop.html

### Internal Link

- ....