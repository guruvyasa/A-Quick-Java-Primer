# NIO package

##Path class
 The Path class is a programmatic representation of a path in the file system. A Path object contains the file name and directory list used to construct the path, and is used to examine, locate, and manipulate files.

A Path instance reflects the underlying platform. In the Solaris OS, a Path uses the Solaris syntax (/home/guru/foo) and in Microsoft Windows, a Path uses the Windows syntax (C:\home\guru\foo). A Path is not system independent. You cannot compare a Path from a Solaris file system and expect it to match a Path from a Windows file system, even if the directory structure is identical and both instances locate the same relative file.

The file or directory corresponding to the Path might not exist. You can create a Path instance and manipulate it in various ways: you can append to it, extract pieces of it, compare it to another path. At the appropriate time, you can use the methods in the Files class to check the existence of the file corresponding to the Path, create the file, open it, delete it, change its permissions, and so on.

