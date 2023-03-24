# Lab5_202001247
<h1>IT314 - Software Engineering<br>
<h6><hr>

Date:24-03-23<br>
ID-202001247<br>
Name:- Gaurang Ganvit<br>

static Analysis:
<br>
git repository:https://github.com/jassics/learning-python.git
<br>
Language:Python<br>
Tool:mypy/mypy playground<br>
<br>

<h1>1.<br>
<h1>Code:</h1><br>

@@ -0,0 +1,22 @@
#!/usr/bin/python


num_list = [2, 1, 3, 5, 6, 11, 2, 13, 4, 15]
target = 12

def twoSum(arr, t):
    index_dict = {}
    length = len(arr)
    index = 0

    while index < length:
        if (t - arr[index]) in index_dict:
            return index dict[t - arr[index]], index
        index dict[arr[index]] = index
        index += 1

print(twoSum(num_list, target))

<br>
<h1>Errors:</h1><br>
main.py:1: error: invalid syntax; you likely need to run mypy using Python 3.11 or newer  [syntax]
Found 1 error in 1 file (errors prevented further checking)<br>
<br>
In this code array name  index dict has space thats why it give the error so there no space when we give the name of array

![image](https://user-images.githubusercontent.com/123666770/227476846-f2c22e32-0e2e-4f7b-8efa-669d999a8c67.png)
<br>





<h1>2.</h1><br>
<h1>Code:</h1><br>

#!/usr/bin/python3

<h6># Function to check If a number is prime against already given prime number list
def prime(num, primes):<br>
    # loop to test if num is prime number against given primes list<br>
    for prime in primes:<br>
        if  (num % prime) == 0:<br>
            return False<br>
    # We got new prime number, add it in list primes[]<br>
    primes.append(num)<br>
    return True<br>

def n_primes(n):<br>
    primes = []<br>
    start_num, prime_counter = 2, 0<br>
    while True:<br>
        if prime(start_num, primes):<br>
            prime_counter += 1<br>
            if prime_counter == n<br>
                return primes<br>
        start num += 1<br>
<br>
try:<br>
    nprimes = int(input("Enter how many prime numbers you want to display: "))
except:<br>
    exit("Must be an integer only")<br>


if nprimes < 0:<br>
    exit("Number must be postive one!")<br>
else:
    primes_list = n_primes(nprimes)<br>
    print(primes_list)<br>
    
 <h1>Error:</h1><br>
    <br>
    
main.py:19: error: expected ':'  [syntax]
Found 1 error in 1 file (errors prevented further checking)<br>
    ![image](https://user-images.githubusercontent.com/123666770/227480769-1c015016-520d-4261-bbef-9076cdf5837c.png)
    
   <br>
<h1>3.</h1><br>
<h1>Code:</h1><br>

import PyPDF2


filename = "owasp-api-security-top-10.pdf"
with open(filename, 'rb') as pdf_file:
    pdf_reader = PyPDF2.PdfFileReader(pdf_file)
    num_pages = pdf_reader.getNumPages()

    print(f"Number of pages in {filename}: {num_pages}")

    # get the first page
    page = pdf_reader.getPage(2)
    print(page)
    print('Page type: {}'.format(str(type(page))))
    text = page.extractText()
    print(text)

    # reading all the pages content one by one
    # for page_num in range(pdf_reader.numPages):
    #    pdf_page = pdf_reader.getPage(page_num)
    #    print(pdf_page.extractText())

with open(filename, 'rb') as pdf_file:<br>
    pdf_reader = PyPDF2.PdfFileReader(pdf_file)<br>
    print(f'Number of Pages in PDF File is {pdf_reader.getNumPages()}')<br>
    #print(f'PDF Metadata is {pdf_reader.documentInfo}')<br>
    try:<br>
        print(f'PDF File Title is {pdf_reader.documentInfo["/Title"]}')<br>
        print(f'PDF File Author is {pdf_reader.documentInfo["/Author"]}')<br>
        print(f'PDF File Creator is {pdf_reader.documentInfo["/Creator"]}')<br>
    except Exception as e:<br>
        print(f'Issue while fetching pdf info :{e}')<br>


<br>

<h1>Error</h1><br>   
main.py:16: error: Missing parentheses in call to 'print'. Did you mean print(...)?  [syntax]
Found 1 error in 1 file (errors prevented further checking)
LOG:  Could not load plugins snapshot: @plugins_snapshot.json

LOG:  Mypy Version:           1.1.1
LOG:  Config File:            Default
LOG:  Configured Executable:  None
LOG:  Current Executable:     /layers/google.python.runtime/python/bin/python3
LOG:  Cache Dir:              /dev/null
LOG:  Compiled:               True
LOG:  Exclude:                []
LOG:  Found source:           BuildSource(path='main.py', module='__main__', has_text=False, base_dir=None, followed=False)
LOG:  Could not load cache for __main__: __main__.meta.json
LOG:  Metadata not found for __main__
LOG:  Parsing main.py (__main__)
LOG:  Bailing due to parse errors
LOG:  Build finished in 0.006 seconds with 0 modules, and 1 errors<br>
<br>
![image](https://user-images.githubusercontent.com/123666770/227483544-962d5a66-46de-42eb-9019-816dc53ef6bf.png)



<h1>4.</h1><br>
<h1>Code:</h1><br>

#!/usr/bin/python


import os

def rename_files():
  #(1) get fle names in an array from a directory
 
  file_list = os.listdir(r"/home/sanjeev/prank")
  saved_path = os.getcwd()
  print("Current working directory is "+saved_path )
  os.chdir(r"/home/sanjeev/prank")
   
  #(2) Rename each file by removing integer from it from the beginning of the file
  for file_name in file_list:
    print("Old File Name - "+file_name)
    print("New File Name - "+file_name.translate(NONE, 0123456789")) 
    os.rename(file_name, file_name.translate(NONE, "0123456789") )

rename_files()

<h1>Error</h1><br> 
main.py:17: error: leading zeros in decimal integer literals are not permitted; use an 0o prefix for octal integers  [syntax]
Found 1 error in 1 file (errors prevented further checking)
LOG:  Could not load plugins snapshot: @plugins_snapshot.json

LOG:  Mypy Version:           1.1.1
LOG:  Config File:            Default
LOG:  Configured Executable:  None
LOG:  Current Executable:     /layers/google.python.runtime/python/bin/python3
LOG:  Cache Dir:              /dev/null
LOG:  Compiled:               True
LOG:  Exclude:                []
LOG:  Found source:           BuildSource(path='main.py', module='__main__', has_text=False, base_dir=None, followed=False)
LOG:  Could not load cache for __main__: __main__.meta.json
LOG:  Metadata not found for __main__
LOG:  Parsing main.py (__main__)
LOG:  Bailing due to parse errors
LOG:  Build finished in 0.005 seconds with 0 modules, and 1 errors<br>

![image](https://user-images.githubusercontent.com/123666770/227485988-3efdb8dd-e609-4232-9ec7-d98c4b720a0b.png)



<h1>5.</h1><br>
<h1>Code:</h1><br>
<h6>#!/usr/bin/python
import re

 Password Criteria<br>
 1. Should contain alphanumeric<br>
 2. At least one Capital Letter<br>
 3. At least one small letter<br>
 4. 8-20 characters<br>
 5. at least one special character !@#$%^&*_<br>
 6. No whitespace please<br>

passwords = ['JassiSidhu', 'Jassi Sidhu0$','JassiSidhu0$', 'Jalantu_123*', '12Falcon#', 'Sh0rt5!','Sh0rt5!89***^AWS+', 'short']
special_chars = ['!', '@', '#', '$', '%', '^', '&', '*', '_']

# Using Regular Expression
pattern = '^((?=.*\d)(?=.*[a-z])(?=.*[A-Z])(?=.*[!@#$%^&*_])(?=.*[\S])[0-9a-zA-Z!@#$%^&*_]{8,20})$'
for password in passwords:
    print(password)
    result = re.match(pattern,password)
    if result:
        print("Password Accepted")
    else
        print("Password Denied")</h6>


<h1>Error</h1><br> 
main.py:22: error: expected ':'  [syntax]
Found 1 error in 1 file (errors prevented further checking)
LOG:  Could not load plugins snapshot: @plugins_snapshot.json

LOG:  Mypy Version:           1.1.1
LOG:  Config File:            Default
LOG:  Configured Executable:  None
LOG:  Current Executable:     /layers/google.python.runtime/python/bin/python3
LOG:  Cache Dir:              /dev/null
LOG:  Compiled:               True
LOG:  Exclude:                []
LOG:  Found source:           BuildSource(path='main.py', module='__main__', has_text=False, base_dir=None, followed=False)
LOG:  Could not load cache for __main__: __main__.meta.json
LOG:  Metadata not found for __main__
LOG:  Parsing main.py (__main__)
LOG:  Bailing due to parse errors
LOG:  Build finished in 0.005 seconds with 0 modules, and 1 errors<br>
![image](https://user-images.githubusercontent.com/123666770/227489761-bcce21e8-9385-4c44-ad5a-b064cd7b5d83.png)





