# py2sec

[中文 Readme](https://github.com/cckuailong/py2sec/blob/master/README_zh.md)

## OS Support

Linux && MacOS && Windows

P.S. Windows User May encounter the error

```
error: command 'cl.exe' failed: No such file or directory
```

Please install Visual C++ Build Tools matches your Win version

## What is py2sec

1. py2sec is a Cross-Platform, Fast and Flexible tool to change the .py to .so(Linux and Mac) or .pdy(Win).
2. You can use it to hide the source code of py.
3. py2sec can transfer a single file, more of this, it can certainly transfer the whole project at one time!.
4. The .so(or .pyd) file generated by the .py file can be called by the main func as "from module import * ".
5. py2sec can detect the .py file and transfer to .so(or .pyd) file, also you can determin which file or directory you don't want to change.
6. py2sec doesn't affect the origin code, it generate a new file or directory.
7. py2sec work well with python2 and python3, use -p(--py) to change the python version you want to encrypt.
8. Provide the multithread option to accelerate the speed of py encryption.

## How to config it

```
pip install requirements.txt
```

## How to use py2sec

### Usage

```
python py2sec.py [options] ...
```

### Options

```
-v,  --version    Show the version of the py2sec
-h,  --help       Show the help info
-p,  --py         Python version, default value == 3
                  Example: -p 3  (means you tends to encrypt python3)
-d,  --directory  Directory of your project (if use -d, you change the whole directory)
-f,  --file       File to be transfered (if use -f, you only change one file)
-m,  --maintain   List the file or the directory you don't want to transfer
                  Note: The directories should be surrounded by '[]', and must be the relative path to -d's value
                  Example: -m __init__.py,setup.py,[poc,resource,venv,interface]
-x,  --nthread    number of parallel thread to build jobs
```

### Example

```
python py2sec.py -f test_file.py
python py2sec.py -f test/test_file.py
python py2sec.py -d test_dir -m __init__.py,setup.py,[poc/,resource/,venv/,interface/]
```

### Project Structure

- build/              temp files, .o, .so files
- tmp_build/          temp files, .c files
- result/             the final result dir, the results store here
- py2sec.py           main run file
- setup.py.template   to generate setup.py file
- requirements.txt    env to run py2sec

### Demo

The whole project before:

![demo1](https://github.com/cckuailong/py2sec/blob/master/img/1.png)

After py2sec:

![demo2](https://github.com/cckuailong/py2sec/blob/master/img/2.png)
