# Some useful regexes when migrating from mockito to mockk

##### Constructor
```
mock\<(.+)\>(.+)
mockk\<$1\>$2
```
------------
##### Mock method
```
on\(it.(.+)\).thenReturn\((\w+)\)
every { $1 } returns $2
```
------------
##### Verify block
```
verify\((\w+)\)(.*)
verify {
    $1$2
}
```
------------
##### Inverse verify block
```
verify\((\w+), never\(\)\)(.*)
verify(inverse = true) {
    $1$2
}
```
