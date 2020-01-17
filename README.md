# How to package your python code
At some point, you may want to make your python module(s) available as a package. Let's take the most simple possible package, with only one function `hello_world()` which just writes "Hello world!" to the console. Lets make it available as a pip package called `helloworld`. 

## Make your code pip-installable from source

First, put your source code in a folder with the name of the package (`helloworld`). In the same directory, write a `setup.py` file with the following structure: 

    from setuptools import setup
    setup(name='helloworld',
        version='0.1',
        description='A trivial hello world package for learning how to make a pip-installable python package',
        url='http://github.com/Mchristos/hello_world',
        author='mChristos',
        license='MIT',
        packages=['helloworld'],
        zip_safe=False)
        
In this case we just put our hello world function in a file called `__init__.py` inside the `helloworld` directory. 
        
Now you can use the following pip command to install your package. 

    pip install .
The same statement with a `-e` flag makes changes in the source code immediately available on importing the package

    pip install -e . 
    
Now, your package is available on your system. In your python console, test it by doing:

    >>> import helloworld
    >>> helloworld.hello_world()
    ### Hello world!
