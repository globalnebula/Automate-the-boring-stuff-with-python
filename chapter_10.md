## Question 1

   - `shutil.copy(src, dst)` is used to copy a specific file from the source path (`src`) to the destination path (`dst`).
   - `shutil.copytree(src, dst)` is used to copy an entire directory tree from the source path (`src`) to the destination path (`dst`), including all its contents.

## Question 2

   - The `os.rename(src, dst)` function is used to rename files. It takes the source file path (`src`) and the destination file path (`dst`).

## Question 3

   - `send2trash` module's `send2trash()` function moves a file or directory to the trash or recycle bin, allowing for potential recovery.
   - `shutil` module's `shutil.rmtree()` function deletes a directory and its contents permanently.

## Question 4

   - The `ZipFile` method equivalent to File objects’ `open()` method is `ZipFile()` itself. We use `ZipFile(filename, mode)` to create or open a ZIP file.

### Practice Problems

## Selective Copy

```python
import os
import shutil

def selective_copy(source_folder, destination_folder, file_extension):
    for foldername, subfolders, filenames in os.walk(source_folder):
        for filename in filenames:
            if filename.endswith(file_extension):
                source_path = os.path.join(foldername, filename)
                shutil.copy(source_path, destination_folder)

source_folder = "" #path of the folder location
destination_folder = "" #path of teh folder destinationn
file_extension = ".pdf"
selective_copy(source_folder, destination_folder, file_extension)
```

## Deleting Uneeded files

```python
import os

def find_large_files(folder, size_threshold):
    for foldername, subfolders, filenames in os.walk(folder):
        for filename in filenames:
            file_path = os.path.join(foldername, filename)
            file_size = os.path.getsize(file_path) / (1024 * 1024)  # Convert to MB
            if file_size > size_threshold:
                print(f"Large file found: {file_path} ({file_size:.2f} MB)")

folder_to_search = "" #folder path to search
size_threshold = 100  # in mb
find_large_files(folder_to_search, size_threshold)

```

## Filling the Gaps

```python
import os
import re

def fill_gaps(folder, prefix):
    files = [f for f in os.listdir(folder) if f.startswith(prefix)]
    files.sort()

    for index, filename in enumerate(files, start=1):
        expected_filename = f"{prefix}{index:03d}.txt"
        if filename != expected_filename:
            new_filename = os.path.join(folder, expected_filename)
            os.rename(os.path.join(folder, filename), new_filename)
            print(f"Renamed: {filename} to {expected_filename}")

folder_to_fill_gaps = "" #Path of the reqd folder
prefix_to_match = "spam"
fill_gaps(folder_to_fill_gaps, prefix_to_match)

```