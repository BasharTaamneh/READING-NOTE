# FileIO & Exceptions
## Reading and Writing Files in Python

**array-insert-shift**

* Files on most modern file systems are composed of three main parts:

![](https://files.realpython.com/media/FileFormat.02335d06829d.png)

**Header:** metadata about the contents of the file (file name, size, type, and so on)

**Data:** contents of the file as written by the creator or editor

**End of file (EOF):** special character that indicates the end of the file

**File Paths**

- When you access a file on an operating system, a file path is required. The file path is a string that represents the location of a file. It’s broken up into three major parts:

**Folder Path:** the file folder location on the file system where subsequent folders are separated by a forward slash / (Unix) or backslash \ (Windows)

**File Name:** the actual name of the file

**Extension:** the end of the file path pre-pended with a period (.) used to indicate the file type

- Here’s a quick example. Let’s say you have a file located within a file structure like this:

```
/
│
├── path/
|   │
│   ├── to/
│   │   └── cats.gif
│   │
│   └── dog_breeds.txt
|
└── animals.csv
```


