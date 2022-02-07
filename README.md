# Excel-to-C
Convert Excel text resources and meta data to C code using a Powershell script

Background: It is convenient to store an embedded device's HMI user parameter info
in an Excel file. This info can be the language text resources and meta data.
With Excel, ii is relatively easy to get an overview of all the user parameter data.
But it is required for this data to somehow be converted to C/C++ code and compiled
and be part of the executable firmware image.

Description: A Powershell script is used to convert Excel user parameter data to a C
source and header file. This C code can later be used by the HMI module part of the
embedded SW. The Powershell script first exports the Excel user parameter data to an
XML file. Then using Powershell's built-in XML functionality, the XML data is copied to
memory and subsequently parsed when generating the C code. The script does other things
such as extracting the built-in properties of the Excel file and posting them in the
generated C code. Also measuring the script execution time and creating a log file.
As an example, I have used some of the user parameters found in the ABB ACS880 AC Drive.

Tools: Powershell 5.1, Visual Studio Code (with the Powershell extension)

Instructions: The user parameters and their related data are stored in the
UserParameters.xlsx file. 

Use this command in the Powershell console:
powershell -ExecutionPolicy Bypass -File pathToTheScript

Debugging the Powershell script can be done in the Visual Studio Code environment.

Note: The UserParameters.ps1 Powershell script has only been tested in the Windows 10.

I have tested compiling the generated code with the Visual Studio 2022 C++/C compiler.
