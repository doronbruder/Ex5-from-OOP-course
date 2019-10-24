# Ex5-from-OOP-course
Files processor Sort &amp; Filter by given Instruction file
doronbruder

doron bruder‬

‪=============================‬
‪=      File description     =‬
‪=============================
The jar files contains the follow :
2 README 3
3 filesprocessing/DirectoryProcessor.java 5
4 filesprocessing/Section.java 7
5 filesprocessing/handelssections/ErrorType1.java 8
6 filesprocessing/parsing/BadForamtException.java 9
7 filesprocessing/parsing/InvalidHeadLineException.java 10
8 filesprocessing/parsing/Parser.java 11
9 filesprocessing/parsing/ParsingException.java 13
10 filesprocessing/toolbox/MySort.java 14
11 filesprocessing/handelssections/filters/Filter.java 15
12 filesprocessing/handelssections/filters/FilterAll.java 16
13 filesprocessing/handelssections/filters/FilterBetween.java 17
14 filesprocessing/handelssections/filters/FilterContains.java 18
15 filesprocessing/handelssections/filters/FilterDecorator.java 19
16 filesprocessing/handelssections/filters/FilterExecutable.java 20
17 filesprocessing/handelssections/filters/FilterFactory.java 21
18 filesprocessing/handelssections/filters/FilterFile.java 23
19 filesprocessing/handelssections/filters/FilterGreaterThan.java 24
20 filesprocessing/handelssections/filters/FilterHidden.java 25
21 filesprocessing/handelssections/filters/FilterNot.java 26
22 filesprocessing/handelssections/filters/FilterPrefix.java 27
23 filesprocessing/handelssections/filters/FilterSmallerThan.java 28
24 filesprocessing/handelssections/filters/FilterSuffix.java 29
25 filesprocessing/handelssections/filters/FilterWritable.java 30
26 filesprocessing/handelssections/orders/Order.java 31
27 filesprocessing/handelssections/orders/OrderAbs.java 32
28 filesprocessing/handelssections/orders/OrderFactory.java 33
29 filesprocessing/handelssections/orders/OrderReverse.java 35
30 filesprocessing/handelssections/orders/OrderSize.java 36
31 filesprocessing/handelssections/orders/OrderType.java


‪=============================‬
‪=          Design           =‬
‪=============================‬
The program is running by its main class - the DirectoryProcessor class that uses 
 Parser class that parse the commands from the commands file 
into list of Sections-A Section is also a class
That represents a section from the command file a section is 
defined by the index of the line it starts and 
Its Order and Filter object according their textual representation.
The Section class has a method that gets list of file and filter&order them 
according to the filter and order of the section
For the Filter class that represents a filter of files I used a 
decorator pattern since it is very natural to think of using 
several filterers together even though in this Ex there 
was not such a requirement‫-‬ It's good for modularity purposes
In the Order I didn't use a decorator pattern since it is not
 natural to use orders one after the other in a row
Or toghther like it is natural in the filter case .

Exceptions: 
For the "type one" Exception I created a single class that 
located in a sub-package with the orders and filters 
Since these kind of exception is raised only in the 
factory classes of filters and orders
Moreover I didn't create more sub-exceptions for the type one
 because in my opinion both in filter factory and 
Order factory the same idea of exception is thrown - 
"InvalidSubsectionLine" which is also its name. 

 For the "Type two" Exceptions I used inheritance the main Exception of the
 family called "parsingException" Exception and all of
Them located in the same package with the Parser since
 all of them thrown only in this class
The two sub-exceptions are : "InvalidHeadlineException" and "BadFormatException"
Every  type 2 exception types received their own exception
, because they need different messages

‪=============================‬
‪=  Implementation details   =‬
‪=============================‬
In order to use the single-choice
 pattern I used factories(both Order and FIlter)
Which means that if a future version would l
ike to add orders or filters they may only change 
The factory classes.
In addition to save memory and prevent unwanted
 situations I used Singleton In the Filter factory 
And Objects pool in the Order factory .
‪=============================‬
‪=    Answers to questions   =‬
‪=============================‬
For Sorting the data I implemented my own version of Quick-Sort
And used  ArrayList Data Structure
I used this data structure mainly because its a flexible 
sized data structure  and it is well correlated
With method of java.io.files, java.util,
 java.nio.file classes which I used many times.
Note: It might not be the optimal running time choice  but are 
dealing with a specific directory and I assumed 
That the number of files there Is not too big




