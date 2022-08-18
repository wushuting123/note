# 时间

## 获取某年第一天

### 方法

```java
import java.util.Calendar;
import java.util.Date;

    /**
     * 
     * @param year
     * @return
     */
    public Date getBeginOfYear(int year) {
        Calendar calendar = Calendar.getInstance();
        calendar.clear();
        calendar.set(Calendar.YEAR, year);
        return calendar.getTime();
    }
```

### 输入

```java
2022
```

### 输出

```java
Sat Jan 01 00:00:00 CST 2022
```



## 获取某年最后一天

### 方法

```java
import java.util.Calendar;
import java.util.Date;

   /**
     * 
     * @param year
     * @return
     */
    public Date getEndOfYear(int year) {
        Calendar calendar = Calendar.getInstance();
        calendar.clear();
        calendar.set(Calendar.YEAR, year);
        calendar.roll(Calendar.DAY_OF_YEAR, -1);
        return calendar.getTime();
    }
```

### 输入

```java
2022
```

### 输出

```java
Sat Dec 31 23:59:59 CST 2022
```

