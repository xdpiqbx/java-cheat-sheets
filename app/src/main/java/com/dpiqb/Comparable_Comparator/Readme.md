# [Comparator](https://docs.oracle.com/javase/8/docs/api/java/util/Comparator.html)

`@FunctionalInterface`

A comparison function, which imposes a total ordering on some collection of objects

Функція порівняння, яка накладає загальне впорядкування на деяку колекцію об’єктів.

- `(x, y)` such that `c.compare(x, y) <= 0`
- `(x, y)` such that `c.compare(x, y) == 0`
- `(x, y) `such that `x.equals(y)`

```java
Collections.sort(list, new IdComparator());
Collections.sort(list, new NameComparator());
Collections.sort(list, new SalaryComparator());
```

```java
class IdComparator implements Comparator<Employee>{
  @Override
  public int compare(Employee emp1, Employee emp2){
    if(emp1.id == emp2.id){
      return 0;
    }else if(emp1.id < emp2.id){
      return -1;
    }else{
      return 1;
    }
  }
}
```

```java
class NameComparator implements Comparator<Employee>{
  @Override
  public int compare(Employee emp1, Employee emp2){
    int res = emp1.name.compareTo(emp2.name);
    if(res == 0){
      res = emp1.surname.compareTo(emp2.surname);
    }
    return res;
  }
}
```

```java
class SalaryComparator implements Comparator<Employee>{
  @Override
  public int compare(Employee emp1, Employee emp2){
    return emp1.salary - emp2.salary;
  }

}
```


# [Comparable](https://docs.oracle.com/javase/8/docs/api/java/lang/Comparable.html)

This interface imposes a total ordering on the objects of each class that implements it

Інтерфейс накладає загальний порядок впорядкування на об’єкти кожного класу, який його реалізує.

- `(x, y)` such that `x.compareTo(y) <= 0`
- `(x, y)` such that `x.compareTo(y) == 0`
- `(x, y)` such that `x.equals(y)`

```java
class Employee implements Comparable<Employee>{
  // ...
  @Override
  public int compareTo(Employee obj){
    int res = this.name.compareTo(obj.name);
    if(res == 0){
      res = this.surname.compareTo(obj.surname);
    }
    return res;
  }
}
```