# 1. How do you distinguish between shutil.copy() and shutil.copytree()?

Ans :  shutil.copy : Copies a single file

shutil.copytree() : will copy an entire folder and every folder and file contained in it

# 2. What function is used to rename files??

Ans  :  import os
    
        os.rename("text.txt","testnew.txt")

# 3. What is the difference between the delete functions in the send2trash and shutil modules?

Ans :--  import shutil
         shutil.retree(): The shutil module’s rmtree() function can be used to delete files or folders. But, this function delete the files permanently. The operations cannot be undone if there were any accidental deletions performed

import send2trash
send2trash.send2trash() : Using send2trash, we can send files to the Trash or Recycle Bin instead of permanently

deleting them. If the directory contains files or other folders, those are also deleted. A TrashPermissionError exception is raised, in case a file could not be deleted due to permission error or any other unexpected reason.


```python
import shutil
import send2trash
shutil.rmtree("path")
send2trash.send2trash("path")
     
```

# 4.ZipFile objects have a close() method just like File objects’ close() method. What ZipFile method is equivalent to File objects’ open() method?
Ans  : from zipfile import Zipfile

with ZipFile(file_name, 'r') as zip: -> this code will open specified zipfile for us. we can use zip object to preform other operation the ziplife. like zip.read()

```python
from zipfile import Zipfile
with ZipFile(file_name, 'r') as zip
     
```

# 5. Create a programme that searches a folder tree for files with a certain file extension (such as .pdf or .jpg). Copy these files from whatever location they are in to a new folder.


```python
# Write a program that walks through a folder tree 
# and searches for files with a certain file extension (such as .pdf or .jpg).
# Copy these files from whatever location they are in to a new folder.

import os, shutil

def selectiveCopy(source, extensions, destination):
    folder = os.path.abspath(source)
    destination = os.path.abspath(destination)
    print('Looking in', source, 'for files with extensions of', ', '.join(extensions))
    for foldername, subfolders, filenames in os.walk(source):
        for filename in filenames:
            name, extension = os.path.splitext(filename)
            if extension in extensions:
                fileAbsPath = foldername + os.path.sep + filename
                print('Coping', fileAbsPath, 'to', destination)
                shutil.copy(fileAbsPath, destination)

extensions = ['.mp4', '.pdf','.jpg']
source = "C:\Users\Desktop"
destination = "C:\Users\Desktop\abc"
selectiveCopy(source, extensions, destination)
```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```
