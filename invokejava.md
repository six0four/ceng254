## Getting started with Lab 10
1. Use an ssh terminal such as <a href="https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html">PuTTY</a> to connect to apollo.humber.ca
2. Once logged in change to an appropriate directory such as the one that you used for JSP:
```
[n12345678@apollo ~]$ cd ceng254
```
3. create a file Hello.java containing:
```
public class Hello
{
  public static String world()
  {
    return "Hello world";
  }
}

```
3. compile it using:
```
javac -target 1.6 -source 1.6 Hello.java
```
(returns a warning: bootstrap class path not set)
4. Load it using:
```
loadjava -user n12345678 Hello.class
```
5. Note that the blank password prompt does include an initial unremoveable "*" this is okay, enter your oracle password:
```

Password:
*
```
