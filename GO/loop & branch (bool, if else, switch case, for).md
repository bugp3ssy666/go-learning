1. true/false
	the **unique** way to declare a bool var in go:
	`var a = true`
	`var b = false`
	or declare the bool var with a comparison expression:
	`var a = b < 10` (b has been assigned with a value)
	any other assignment is not a valid bool var assignment.
2. operations for comparison
	all the same as c++.
3. **BRANCH 1** (if, else if, else) structure
	e.g.
	`if command == "go east"{`
	`	fmt.Println("Plan A")`
	`} else if command = "go inside" {`
	`	fmt.Println("Plan B")`
	`} else {`
	`	fmt.Println("Plan C")`
	`}`
4. logical operator
	the same as c++ (|| for **or**, && for **and**).
	-> ***short-current logic:*** if the former statement of "||" sentence is 	true, ignore the latter statement.
5. **BRANCH 2** (switch + case) structure
	e.g.
	`switch command {`
	`case "Plan A":`
	`	fmt.Println("xx")`
	`case "Plan B", "Plan C":`
	`	fmt.Println("xxx")`
	`default:`
	`	fmt.Println("no solution")`
	`}`
	**note:** the multi-option "case" sentence.
	**note:** the var following "switch" is non-necessary.
	-> ****"fallthrough":**** "descend" -- if the upper condition is at work, the lower one is also to be activated.
	e.g.
	`var room = "lake"`
	`switch {`
	`case room == "cave":`
	`	fmt.Println("dim")`
	`case room == "lake":`
	`	fmt.Println("icy")`
	**`		fallthrough`**
	`case room == "underwater":`
	`	fmt.Println("freezing")`
	`}`
	result:
	`icy`
	`freezing`
	note: the difference, in c++, java etc., the fallthrough mechanism is activated by default and there is no "fallthrough" keyword in them. GO goes opposite.
6. **LOOP** (for) structure
	*e.g. (condition following "for" = finite)*
	`var count = 10`
	`for count > 0 {`
	`fmt.Println(count)`
	****`time.Sleep(time.Second)`**** *<- set duration of 1 sec*
	`count--`
	`}`
	`fmt.Println("Liftoff!")`
	result:
	print from 10 to 1, line by line, every 1 second. then "Liftoff!"" at the end.
	
	*e.g. (no condition = infinite, break)*
	`var degrees = 0`
	`for {`
	`fmt.Println(degrees)`
	`degrees++`
	`if degrees >= 360 {`
	`	degrees = 0`
	`	if rand.Intn(2) == 0 {`
	`		break`
	`		}`
	`	}`
	`}`
	
	**note:** the "for" sentence also writes:
	`for count = 10; count > 0; count-- {...}`
	assignment + condition + action for loop -- in reference to c++ grammar.
	yet in GO, "for" line doesn't support traditional variable declaration, but supports the ****simplized declaration:****
	`for count := 10; count > 0; count-- {...}`
	this makes "count" only a variable within the "for" loop lifespan.
	--"if" & "switch" branch lifespan works the same way.
	*e.g.*
	`if num := rand.Intn(3); num == 0 {`
	`	fmt.Println("...")`
	`} else if ...`
	`...`
	`}`
	*e.g.*
	`switch num := rand.Intn(10); num {`
	`case 0:`
	`	fmt.Println("...")`
	`case 1:`
	`...`
	`case ...`
	`...`
	`default ...`
	`}`
	this is something different from c++.