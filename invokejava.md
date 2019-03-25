## Getting started with Lab 10
1. Use an ssh terminal such as <a href="https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html">PuTTY</a> to connect to apollo.humber.ca
2. Once logged in create and change to an appropriate directory similar to the one that you used for JSP on munro:
```
[n12345678@apollo ~]$ mkdir ceng254
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
[n12345678@apollo ceng254]$ javac -bootclasspath $ORACLE_HOME/jdk/jre/lib/rt.jar -target 1.6 -source 1.6 Hello.java
```
4. Load it using:
```
[n12345678@apollo ceng254]$ loadjava -user n12345678 Hello.class
```
5. Note that the blank password prompt does include an initial unremoveable "*" this is okay, enter your oracle password:
```

Password:
*
```
6. Run the following SQL:
```
CREATE OR REPLACE FUNCTION helloworld RETURN VARCHAR2
AS LANGUAGE JAVA NAME 'Hello.world () return java.lang.String';
/
SELECT helloworld() FROM DUAL;
```
