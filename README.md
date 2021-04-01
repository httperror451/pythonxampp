https://stackoverflow.com/questions/42704846/running-python-scripts-with-xampp

#Windows:


Run Python in xampp for windows:

STEP-1:[Download Python]

Download & install the latest version of python from www.python.org Download Python & click on the windows installer of any version [ex. python-3.6.2]

STEP 2: [Install Python] Install in any directory of your harddrive [ex. D:\python-3.6.2]

STEP 3: [Configure Python] The XAMPP GUI can quickly access the httpd.conf file like so: enter image description here

Otherwise open the directory where xammp was installed Go to apache >> conf e.g.) D:\xampp\apache\conf\httpd.conf. You'll see a file named httpd.conf. Open it in any text editor & put the below codes in the end of that file:

AddHandler cgi-script .py
ScriptInterpreterSource Registry-Strict
STEP 4:[optional]

In same file search for <IfModule dir_module>. When you've found it put index.py in the end It will look something like this

<IfModule dir_module>
    DirectoryIndex index.php index.pl index.cgi index.asp index.shtml index.html index.htm \
    default.php default.pl default.cgi default.asp default.shtml default.html default.htm \
    home.php home.pl home.cgi home.asp home.shtml home.html home.htm index.py
</IfModule>
STEP 5:[restart apache/xampp]

That's all for editing, now restart apache from your xampp control panel

STEP 6:[Run Python from xammp]

#Linux

open with sudo >>> /opt/lampp/etc/httpd.conf
edit default line with:
>>> AddHandler cgi-script .cgi .pl .py

as well edit line :
>>> 
<IfModule dir_module>
    #DirectoryIndex index.html
    # XAMPP
    DirectoryIndex index.html index.html.var index.php index.php3 index.php4 index.cgi \
    default.php default.pl default.cgi default.shtml default.html default.htm \
    home.php home.pl home.cgi home.shtml home.html home.htm index.py

</IfModule>


>>>restart apache/xampp
1.add this lines in .py file at top:
>>>
#! /usr/bin/python3
print("Content-Type: text/html\n")


2.open http://localhost/PythonProject\test.py




