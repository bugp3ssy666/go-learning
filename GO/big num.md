## exponential:
`var distance int64 = 41.3e12`
`fmt.Println(distance)`
result: `41300000000000`

## pkg -> big:
- ****big.Int****
	much higher limitation than int64, less convenience, lower speed.
	initialization:
	`a := new(big.Int)`
- big.****NewInt()****
	takes in a **int64** value and return a **big.Int** value:
	`lightSpeed := big.NewInt(299792)`
	**note:** input value -> int64 limitation. so by this way one could only initialize big.Int variable within int64 limitation.
- big.Int -> ****.SetString( , )****
	input larger value than **int64** limitation:
	`distance := new(big.Int)`
	`distance.SetString("24000000000000000000", 10)`
	v.SetString("a", b): a -> the big number, b -> the number system the big number uses.
- big.Int -> ****.Div( , )****
	*`... (follows as above)`*
	`seconds := new(big.Int)`
	`seconds.Div(distance, lightSpeed)`
	`secondsPerDay := big.NewInt(86400)`
	`days := new(big.Int)`
	`days.Div(seconds, secondsPerDay)`
	`fmt.Println("That is", days, "days of travel at light speed.")`
	result:
	`That is 926568346 days of travel at light speed.`
	
## const & literal value
const & literal value has no limitation of overflow, because they are classified automatically as **"untyped"** type as they are stated.
const & literal value calculations happen during GO compilation.
*e.g.* this works:
`const distance = 24000000000000000000`
this works:
`fmt.Println(".....", 24000000000000000000/299792/86400, "...")`
result: `...... 926568346 ......`
this works:
`const distance = 24000000000000000000`
`const lightSpeed = 299792`
`const secondsPerDay = 86400`
`const days = distance / lightSpeed / secondsPerDay`
`fmt.Println("...", days, "...")`
**note:** here "days" is not a const or literal value when getting printed by "fmt.Println" but it's within the limits of int type, so it works. "fmt.Print..." cannot convert **untyped** type of variable into int-like type to print it out. (overflow)