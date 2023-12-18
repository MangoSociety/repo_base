#готово 

Sphere : [[android]]
Theme : [[serialization]]
Title: Serializable vs parcelable

### Content

Основное отличие между **Serializable** и **Parcelable** в Android разработке заключается в способе сериализации объектов. **Serializable** сериализует объекты в формате, который может быть использован для сохранения и восстановления состояния объекта, в то время как **Parcelable** использует механизм передачи данных между процессами (**IPC**) для передачи объектов между компонентами Android.

**Parcelable** обычно более эффективен, чем **Serializable**, так как он использует механизм **IPC** и меньше накладных расходов на маршаллинг и демаршаллинг объектов. Кроме того, **Parcelable** может быть более безопасен, так как он не использует рефлексию для сериализации объектов, что может быть опасным, если сериализуемый объект содержит конфиденциальные данные.

Однако, реализация **Parcelable** более сложна, чем **Serializable**, и требует более многословного кода, так как вам нужно явно описывать, как каждый объект должен быть сериализован и десериализован. **Serializable**, с другой стороны, может быть реализован с помощью простой метки интерфейса и не требует дополнительных усилий по вашей стороне.

Таким образом, если ваши объекты должны передаваться между компонентами **Android**, используйте **Parcelable** для достижения максимальной производительности и безопасности. Если же вы просто сохраняете состояние объектов в файл или память устройства, **Serializable** может быть более удобным и менее трудоемким вариантом.

```kotlin
  

public class MyObjects implements Serializable {

  

    private String name;

    private int age;

    public ArrayList<String> address;

  

    public MyObjects(String name, int age, ArrayList<String> address) {

        super();

        this.name = name;

        this.age = age;

        this.address = address;

    }

  

    public ArrayList<String> getAddress() {

        if (!(address == null))

            return address;

        else

            return new ArrayList<String>();

    }

  

    public String getName() {

        return name;

    }

  

    // return age

    public int getAge() {

        return age;

    }

}

  

public class MyObjects implements Parcelable {

  

    private int age;

    private String name;

    private ArrayList<String> address;

  

    public MyObjects(String name, int age, ArrayList<String> address) {

        this.name = name;

        this.age = age;

        this.address = address;

    }

  

    public MyObjects(Parcel source) {

        age = source.readInt();

        name = source.readString();

        address = source.createStringArrayList();

    }

  

    @Override

    public int describeContents() {

        return 0;

    }

  

    @Override

    public void writeToParcel(Parcel dest, int flags) {

        dest.writeInt(age);

        dest.writeString(name);

        dest.writeStringList(address);

    }

  

    public int getAge() {

        return age;

    }

  

    public String getName() {

        return name;

    }

  

    public ArrayList<String> getAddress() {

        if (!(address == null))

            return address;

        else

            return new ArrayList<String>();

    }

  

    public static final Creator<MyObjects> CREATOR = new Creator<MyObjects>() {

        @Override

        public MyObjects[] newArray(int size) {

            return new MyObjects[size];

        }

  

        @Override

        public MyObjects createFromParcel(Parcel source) {

            return new MyObjects(source);

        }

    };

}

```

  

P.S. Так же стоит отметить что Serializable входит в стандартный пакет инструментов Java. Именно этот пункт может влиять на выбор
### External Link

- ....

### Internal Link

- ....