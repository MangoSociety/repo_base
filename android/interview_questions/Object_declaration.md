#готово 

Sphere : [[android]]
Theme : #Object
Title: Объявление объекта (object declaration), object как Singleton

### Content
Объявляется объект при помощи ключевого слова `object`, после которого следует `имя объекта`.

Файл, содержащий только `object` представляет из себя **Singleton**, т.е. будет создан **только один экземпляр** этого класса. Пример:

```kotlin

object One { 
	val cats = arrayListOf<Cat>() 
	fun callCat() { 
		for (cat in cats) { ... } 
	} 
}
```

Можно обращаться к методам и свойствам класса через имя объекта:

```kotlin

One.cats.add(Cat(...)) 
One.callCat()
```

Инициализация объявления объекта потокобезопасна и выполняется при первом доступе (лениво).
### External Link

- ...

### Internal Link

- ....