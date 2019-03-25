## Getting started with Lab 10
1. Use an ssh terminal such as <a href="https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html">PuTTY</a> to connect to apollo.humber.ca
2. Once logged in create and change to an appropriate directory similar to the one that you used for JSP on munro:
```
[n12345678@apollo ~]$ mkdir ceng254
[n12345678@apollo ~]$ cd ceng254
```
3. create a file rand.java containing:
```
public class rand
{
  public static String rand (Double n){
    Double answer=java.lang.Math.random()*n;
    return answer.toString();
  }
  public static void main (String[] args){
    System.out.println(rand(Double.valueOf(args[0])));
  }
}

```
3. compile it using:
```
[n12345678@apollo ceng254]$ javac -bootclasspath $ORACLE_HOME/jdk/jre/lib/rt.jar -target 1.6 -source 1.6 rand.java
```
4. Load it using:
```
[n12345678@apollo ceng254]$ loadjava -user n12345678 rand.class
```
5. Note that the blank password prompt does include an initial unremoveable "*" this is okay, enter your oracle password:
```

Password:
*
```
6. Run the following SQL:
```
CREATE OR REPLACE FUNCTION rand(n NUMBER) RETURN VARCHAR2
AS LANGUAGE JAVA NAME 'rand.rand(java.land.Double) return java.lang.String';
/
SELECT rand(5) FROM DUAL;
```
(you may have to run this command twice.)