# `BigInteger` и `BigDecimal`

- у них теоретически нет максимального размера
```java
public class Main {
    public static void main(String[] args) {
        BigInteger integer = new BigInteger("9999999999999999999999999"); // можно и больше
        System.out.println(integer);

        BigDecimal decimal = new BigDecimal("123.9999999999999999999999999"); // можно и больше
        System.out.println(decimal);
    }
}
```

- Передача строки в качестве параметра — только один из возможных конструкторов.
- Эти объекты являются неизменяемыми (`Immutable`).

```java
import java.math.BigInteger;
public class Main {
   public static void main(String[] args) {
       BigInteger integer = new BigInteger("1111111111111111111111111111111111");
       System.out.println(integer);
       // integer.add(BigInteger.valueOf(33333333)); - так ничего не будет, Immutable!
       BigInteger result = integer.add(BigInteger.valueOf(33333333));
       System.out.println(result);
   }
}
```

- Классы больших чисел не используют в своей работе операторы `+ - * /`, а предоставляют вместо этого набор методов.
`add(), subtract(), multiply(), divide()`

- `doubleValue(), intValue(), floatValue(), longValue()` и т.д. — для преобразования к примитивному типу Java. Не забывать про разницу во вместимости!
- `min()` и `max()` — позволяют найти минимальное и максимальное значение из двух переданных больших чисел.

```java
BigInteger one = new BigInteger("11111");
BigInteger two = new BigInteger("22222");

System.out.println(one.max(two));
```

## Управление округлением BigDecimal

[https://javarush.ru/groups/posts/2274-kak-ispoljhzovatjh-bigdecimal-v-java](https://javarush.ru/groups/posts/2274-kak-ispoljhzovatjh-bigdecimal-v-java)