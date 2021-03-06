# ABAP Editor Configuration

## Default ABAP Scheme Workbench Editor
![Default Editor](/img/default_editor.png)

## How To Enable The New ABAP Editor
The SAP GUI ABAP Editor for LISP enables
* syntax highlighting
* code completion

![Default Editor](/img/new_editor.png)

## SAP GUI Configuration Folder

The SAP GUI configuration files are located in the roaming user application directory. They can be reached using the environment variable %APPDATA%.
 
    cd %APPDATA%\SAP\SAP GUI\ABAP Editor
    Windows 10 => [ C:\Users\<username>\AppData\Roaming\SAP\SAP GUI\ABAP Editor ]

## Configuration Steps
1. You must manually copy two configuration files provided here in your local SAP GUI configuration folder for the ABAP Editor

* lisp_spec.xml
* lisp_user.xml

2. Change in the first lines of ABAP Include YY_LISP_IDE

      c_new_abap_editor TYPE flag VALUE abap_true,
      c_source_type TYPE string VALUE 'LISP'.

3. Restart the workbench.

## Configuration Files

To create your own theme files

* lisp_spec.xml
* lisp_user.xml

read

* https://wiki.scn.sap.com/wiki/display/NWTech/SAP+GUI+Logon+Configuration
* https://github.com/lucattelli/ab4-themes
* https://github.com/alexey-arseniev/ab4-code-templates
* https://blogs.sap.com/2017/08/01/old-new-abap-editor/

The comments in the blog post 

* https://blogs.sap.com/2015/06/24/a-lisp-interpreter-in-abap/

give useful hints:

    In lisp_spec.xml,
    
    add
    <TextType id="52" name="Keywords" ...>
      <Keywords>
    …
        <Keyword text="define"/>
        <Keyword text="set!"/>
        <Keyword text="lambda"/>
    …
      </Keywords>
    </TextType>
    
    <keywords>
    </>
   
    <structures>
      <structure open="(" close==")"\>
      <structure open="[" close=="]"\>
    </structures>
