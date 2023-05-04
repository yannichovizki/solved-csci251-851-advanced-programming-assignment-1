Download Link: https://assignmentchef.com/product/solved-csci251-851-advanced-programming-assignment-1
<br>
<strong>Aim: </strong>

<ul>

 <li>Design a solution to a problem from a partially complete framework.</li>

 <li>Gain some experience writing a database application in C++.</li>

 <li>Using binary I-O in C++ programs.</li>

</ul>




<strong>Instructions: </strong>

<strong> </strong>

To receive 2 marks for the demo you must complete Step-1 and demonstrate it to your lab supervisor in week-3. The week-4 submission instructions are provided at the end of this document. Please read the Ass1 Q/As on moodle regularly in case suggestions are provided or changes are made to the assignment specification.




You are to write a student enrollment system for a university. For each student the system is to keep the following information:

<ol>

 <li>First Name</li>

 <li>Last Name</li>

 <li>Number of Subjects</li>

 <li>Subjects (Codes; Status,  Marks;};</li>

</ol>

In the Ass1 folder you will find an incomplete implementation of the enrollment system and a datafile called ass1.txt for testing the program.  Examine the data file to get a feel for the data in this system. You may assume that the file contains no errors.  All work for this assignment should be done in the ass1.cpp file. Do not modify main.cpp or ass1.h. To compile on linux/unix:  g++ main.cpp ass1.cpp.  To run on linux: ./a.out. The file: “How to compile with DevCpp.pdf” explains how to compile all the files on DevC++.

(Marking: Step 1 is worth 4 marks (including the demo). Steps 2 and 3 are worth 3 marks each.)




Step 1     Implement the functions: ReadFile(), FindRecord(), DisplayRecord() and PrintRecord() according to the pseudo code provided. Information and example code on reading and writing text files can be found in the C++ Guide in the Wk 1 Lecture folder. Test that your program can correctly load the array from the data file and display records on the screen. Example output is given below:




13 records read




Commands Available:   d – Display Record   u – Update Record   q – Quit the program




Command: d

Enter student number: 4734455

Student No.      4734455

First Name       Kieren Last Name        Legrande

Subjects:

CSCI104  Provisional  65

IACT123  Enrolled     67

CSCI121  Enrolled     98







<table width="631">

 <tbody>

  <tr>

   <td width="57">Step 2  </td>

   <td width="575">Implement the UpdateRecord() and SaveFile() functions and test your program to ensure that it can amend student records and save all records to the file ass1.txt.Command: uEnter student number: 4734455Student No.      4734455First Name       Kieren Last Name        LegrandeSubjects:CSCI104  Provisional  65IACT123  Enrolled     67CSCI121  Enrolled     98 Enter subject code: CSCI104Select status or mark (s/m): s Select new status     e: enrolled     p: provisional     w: withdrawnStatus: eRecord 4734455 Updated.</td>

  </tr>

  <tr>

   <td width="57">Step 3 </td>

   <td width="575">Requires implementation of binary file I-O into the program. If you are unfamiliar with binary file I-O, information on this can be found in BinaryFiles.pdf and the <em>C++ Guide</em> available in the Lecture Notes folder. To implement binary file I-O follow these steps.</td>

  </tr>

  <tr>

   <td width="57">    </td>

   <td width="575">(a) Add four more private functions to ass1.cpp:bool ReadTextFile(char Filename[]); //reads text data from file to gRecs[] array bool WriteTextFile(char Filename[]); //writes text data from gRecs[] to file bool ReadBinaryFile(char Filename[]); //reads binary data from file to gRecs[] array bool WriteBinaryFile(char Filename[]); //writes binary data from gRecs[] to file To do this, copy the code in the ReadFile()  and SaveFile() functions  to ReadTextFile and WriteTextFile() respectively. Modify this code so that it uses the passed filename and return false if the file or path is not found when opened. ReadBinaryFile() and WriteBinaryFile() should read/write the binary contents of gRecs[] to the passed filename (see lecture notes: BinaryFiles.pdf) (Note: the binary file should store the number of records followed by the record data.)Rewrite the ReadFile() function so that it uses the above functions and attempts to read the binary file (named in global cBinaryFileName). If this fails, it then attempts to read the text file (named in global cTextFileName) and then writes the binary file. If ReadFile() fails to read the binary file and the text file it should print an appropriate error message and exit.</td>

  </tr>

  <tr>

   <td width="57">   </td>

   <td width="575">(b) Add one more private function named: void WriteBinaryRecord(char Filename[], int Pos); This function should:</td>

  </tr>

  <tr>

   <td width="57"> </td>

   <td width="575">          open the binary file (named in global cBinaryFileName)</td>

  </tr>

  <tr>

   <td width="57"> </td>

   <td width="575">          seek() to the appropriate record at Pos</td>

  </tr>

  <tr>

   <td width="57"> </td>

   <td width="575">          write the record to the binary file</td>

  </tr>

  <tr>

   <td width="57">   </td>

   <td width="575">          close the fileThen alter the UpdateRecord() function so that it <u>also</u> updates the binary file by calling the above function.(c) Modify the SaveFile() function so that it attempts to write the gRecs[] array to the binary file.If this fails it then attempts to write the data to the text file.</td>

  </tr>

  <tr>

   <td width="57"> </td>

   <td width="575">(d) Test your program to ensure that the binary data is being appropriately saved to the file.</td>

  </tr>

 </tbody>

</table>

<strong>           </strong>

<strong>Submit: </strong>




Before submitting check the format of your source files to ensure tabs, spaces and newlines appear correct on an editor like nedit or notepad++. Submit your files using the submit facility on UNIX ie:




<strong>$ submit -u login -c CSCI251 –a 1 ass1.cpp main.cpp ass1.h </strong>

<strong> </strong><strong>where ‘login’ is your UNIX login ID.  </strong>

<strong> </strong>


