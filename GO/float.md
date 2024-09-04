## float64:
`var days float64 = 365.2425`
`var days = 365.2425`
`days := 365.2425`
--- if the rvalue is a decimal, automatically set as **float64** type
`var answer float64 = 42` <- "float64" is necessary
`answer := 42.0` <- automatically set as float64



## float32:
less accurate than float64
less RAM
`var pi32 float32 = math.Pi`
**float32** keyword is necessary
`var pi64 = math.Pi`
`fmt.Println(pi64)`
`fmt.Println(pi32)`
result:
`3.141592653589793` <- float64
`3.1415927` <- float32



## zero:
any variable without initialization of assignment, is assigned with "0"
`var _price` <- illegal
`var price float64` <- legal
`fmt.Println(price)`
result:
`0`



## printf float:
`third := 1.0/3`
`fmt.Println(third)`
`fmt.Printf("%v\n",third)`
`fmt.Printf("%f\n",third)`
`fmt.Printf("%.3f\n",third)`
`fmt.Printf("%3.f\n",third)`
`fmt.Printf("%4.2f\n",third)`
`fmt.Printf("%6.2f\n",third)`
`fmt.Printf("%2.4f\n",third)`
`fmt.Printf("06.2f\n",third)`
result:
`0.3333333333333333`
`0.3333333333333333`
`0.333333`
`0.333`
`__0`
`0.33`
`__0.33`
`0.3333`
`000.33`
*explanation:*
a. {%v}: normal.
b. {%f}: by default, keep first 6 digits of decimal.
c. {%****m****.f} (m is a parameter): abandon all decimal part, m stands for print length, if not long enough, use space to fill in left part.
d. {%****m****.****n****f}: m stands for print length, n stands for accuracy of kept decimal part, if **[m>n+i(int digit num)+1(decimal point occupy one digit)]**, use space to fill in to the left, **otherwise**, print as accurate as needed.
e. {%****0m****.****n****f}: use 0 to fill in to the left, the other parts all same to "d."

****note:**** add "-" after any "%" above, "left" turns into "right", see ->  [fmt.print](../../PROGRAMMING/GO/fmt.print.md)


****note:**** put multiplication before division will make float calculation more accurate.


****note:**** given the inaccuracy of float calculation, provided here is a idea to compare two float var:
`fmt.Println(math.Abs(piggyBank-0.3)<0.0001)`
if the error is subtle enough to ignore, perceive the two variable equal to each other. print `true` on the console