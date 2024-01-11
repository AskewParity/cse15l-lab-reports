# Lab Report

## `cd`

```
~/Desktop/School 2023-2024/CSE 12/week1Discussion] cd

~/]
```

The working directory was `/Users/chris/Desktop/School 2023-2024/CSE 12/week1Discussion`

The command changes the current working directory to the home directory. This was not an error.

```
~/Desktop/School 2023-2024/CSE 12/week1Discussion] cd lib

~/Desktop/School 2023-2024/CSE 12/week1Discussion/lib]
```

The working directory was `/Users/chris/Desktop/School 2023-2024/CSE 12/week1Discussion`

The command changes the current working directory to the
folder prompted (must be adjacent to the current working directory).
This was not an error.

```
~/Desktop/School 2023-2024/CSE 12/week1Discussion] cd Course.class

cd: not a directory: Course.class

~/Desktop/School 2023-2024/CSE 12/week1Discussion]
```

The working directory was `/Users/chris/Desktop/School 2023-2024/CSE 12/week1Discussion`

It did not change the working directory. This was an error, as `Course.class` is not a directory, therefore the terminal can not enter it.

## `ls`

```
~/Desktop/School 2023-2024/CSE 12/week1Discussion] ls

Course.class              DemoArray.java            DemoArrayImpl.java        DemoArrayImplTester.java  lib
DemoArray.class           DemoArrayImpl.class       DemoArrayImplTester.class README.md                 libs

~/Desktop/School 2023-2024/CSE 12/week1Discussion]
```

The working directory was `/Users/chris/Desktop/School 2023-2024/CSE 12/week1Discussion`

It outputs all of the folders and files that are in (direct children) of the current working directory [in alphabetical order]. This is not an error.

```
~/Desktop/School 2023-2024/CSE 12/week1Discussion] ls lib

hamcrest-core-1.3.jar junit-4.13.2.jar

~/Desktop/School 2023-2024/CSE 12/week1Discussion]
```

The working directory was `/Users/chris/Desktop/School 2023-2024/CSE 12/week1Discussion`

It outputs all the folders and files that are in (direct children) in the folder specified. This is not an error.

```
~/Desktop/School 2023-2024/CSE 12/week1Discussion] ls Course.class

Course.class

~/Desktop/School 2023-2024/CSE 12/week1Discussion]
```

The working directory was `/Users/chris/Desktop/School 2023-2024/CSE 12/week1Discussion`

It just repeats the name of the class. This is not an error.

## `cat`

```
~/Desktop/School 2023-2024/CSE 12/week1Discussion] cd Course.class

```


The working directory was `/Users/chris/Desktop/School 2023-2024/CSE 12/week1Discussion`

```
~/Desktop/School 2023-2024/CSE 12/week1Discussion] cat lib

cat: lib: Is a directory

~/Desktop/School 2023-2024/CSE 12/week1Discussion]
```

The working directory was `/Users/chris/Desktop/School 2023-2024/CSE 12/week1Discussion`

This is an error, it can not print out the contents of the directory itself.

```
~/Desktop/School 2023-2024/CSE 12/week1Discussion] cd DemoArray.java

public interface DemoArray<E extends Comparable<E>>{
    
    /* Get the smallest element in the array*/
    public E min();
  
    /* Get the ith element in the array*/
    public E get(int i);

}%     

~/Desktop/School 2023-2024/CSE 12/week1Discussion]
```

The working directory was `/Users/chris/Desktop/School 2023-2024/CSE 12/week1Discussion`

It prints out the text (or content) in the file onto the console. This is not an error
