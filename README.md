# py_test
test pip install for myself package

1,Generating distribution archives

Make sure you have the latest versions of setuptools and wheel installed:
'''
python3 -m pip install --user --upgrade setuptools wheel
'''

Now run this command from the same directory where setup.py is located:
'''
python3 setup.py sdist bdist_wheel
'''

This command should output a lot of text and once completed should generate two files in the dist directory:
dist/
  example_pkg_YOUR_USERNAME_HERE-0.0.1-py3-none-any.whl
  example_pkg_YOUR_USERNAME_HERE-0.0.1.tar.gz
  
2,Uploading the distribution archives
  
Get account first, Now that you are registered, you can use twine to upload the distribution packages. You’ll need to install Twine:
'''
python3 -m pip install --user --upgrade twine
'''
  
Once installed, run Twine to upload all of the archives under dist:
'''
python3 -m twine upload --repository testpypi dist/*
python3 -m twine upload dist/*
'''

install your package from TestPyPI:
'''
python3 -m pip install --index-url https://test.pypi.org/simple/ --no-deps example-pkg-name
'''
or 
'''
pip3 install example-pkg-name
'''

3, if upload failed, you can try(ubuntu18.04):
'''
python3 -m pip install keyring

python3 -m pip install --upgrade keyrings.alt

#python3 -m pip install --upgrade keyring.util
#python3 -m pip install --upgrade keyring.util.escape
'''
