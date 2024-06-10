#готово 

Sphere : [[android]]
Theme : #JVM
Title: Аннотация @JvmStatic

### Content
С помощью аннотации `@JvmStatic` есть возможность объявить методы по настоящему статическими, ее можно добавить как к методам `object`, так и к методам `companion object`.
```kotlin

object ObjectWithStatic {
    @JvmStatic
    fun staticFun(): Int {
        return 5
    }
}
```

В этом случае метод `staticFun` будет действительно объявлен статическим:

```java
public final class ObjectWithStatic {
   public static final ObjectWithStatic INSTANCE;
 
   @JvmStatic
   public static final int staticFun() {
      return 5;
   }
 
   private ObjectWithStatic() {
      INSTANCE = (ObjectWithStatic)this;
   }
 
   static {
      new ObjectWithStatic();
   }
}
```

### External Link

- ....

### Internal Link

- ....