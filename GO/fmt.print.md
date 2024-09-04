## **1\. fmt.Print**

`...`  
`fmt.Print("this is a text line \n")`  
`fmt.Print(10 / 2)`  
`fmt.Print("this is another text line", 3*3)`

`result:`  
`this is a text line`  
`5this is another text line9`  
*property:  
\-- supports text and variable/equation output  
\-- no output content limitation  
\-- multiple output but no spacing  
\-- no auto line feed*

* * *

## **2\. fmt.Println**

`...`  
`fmt.Println("this is a text line")`  
`fmt.Println(10 / 2)`  
`fmt.Println("this is another text line", 3*3)`

`result:`  
`this is a text line`  
`5`  
`this is another text line 9`  
*property:  
\-- supports text and variable/equation output  
\-- no output content limitation  
\-- multiple output with one spacing each  
\-- auto line feed (redundant '\\n' at the end of a text string is illegitimate)*

* * *

## **3\. fmt.Printf**

`...`  
`fmt.Printf("this is a text line")`  
`fmt.Printf("this is test line number %v and... \n", 6/3)`  
`fmt.Printf("this is the %v line and %v okay...", "last", 12345)`

`result:`  
`this is a text linethis is test line number 2 and...`  
`this is the last line and 12345 okay...`  
*property:  
\-- supports text and variable/equation output  
\-- output content limitation (A. only one text string. or B. first off a main-body text string with a compulsory '%v', more '%v's are optional, and secondly text string/variable/equation(s) which will be printed into the '%v' position in order, single comma between every two output parts.)  
\-- multiple output  
\-- no auto line feed*  
`fmt.Printf("%-15v $%4v \n", "SpaceX", 94)`  
`fmt.Printf("%-15v $%4v \n", "Virgin Galactic", 100)`  

`result:`
`SpaceX ________ $ _94` 
`Virgin Galactic $ 100`
*\-- set aligning/justification:  
%-15v: left-justification, with set width of 15 chars  
%4v: right-justification, with set width of 4 chars  
note: if the content length exceeds the set width, auto-adapt to the actual length by occupying more spaces to the right*