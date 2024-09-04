## (signed) int:
`var year int = 2024`
simplified:
`year := 2024`
`var year = 2024`

## unsigned int:
`var month uint = 9`


## types of int:
![20240904-003733.jpg](../../_resources/20240904-003733.jpg)
if declare a variable with "int" or "uint" only, GO will automatically choose proper type of int according to the target hardware device.
"int" & "uint" types themselves are respectively different from any other ones in the chart.

## monitor the type:
**"%T"(only Printf):**
`fmt.Printf("Type %T for %v\n", year, year)`
print result: `Type int for 2024`
**note:** a less repetitive solution of codes:
`fmt.Printf("Type %T for %[1]v\n", year)`
-- same parameter used in **fmt.printf** multi times.

## hexadecimal:
- assignment: **"0x" or "0X"**
	`var red, green, blue uint8 = 0x00, 0x8d, 0xd5`
	respectively, 0, 141, 213
- output: **"%x" or "%X"**
	`fmt.Printf("color: #%02x%02x%02x;", red, green, blue)`
	result:
	`color: #008dd5`
	follow same rules as "%v" "%f" see -> [float](../../PROGRAMMING/GO/float.md),  [fmt.print](../../PROGRAMMING/GO/fmt.print.md)

## int wrap:
when assigned value is bigger than stated limitation of the type, it wraps.
`var red uint8 = 255`
`red++`
`fmt.Println(red)`
result: `0`
`var num int8 = 127`
`num++`
`fmt.Println(num)`
result: `-128`
and the operation is reversible:
`num--`
`fmt.Println(num)`
result: `127`

## binary:
- assignment: **"0b" or "0B"**
- output: **"%b"**