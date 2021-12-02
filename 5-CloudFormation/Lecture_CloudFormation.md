# What is CloudFormation?
- CloudFormation (cfn) is an AWS language to create **infrastructure as code** (IAC). 
	- **Infrastructure as code**: Allows one to specify resources that can be created on the cloud, and version control them
- When you create a CloudFormation "*template*", you deploy it as a "*stack*"
- Can be written in [YAML](https://yaml.org/) or [JSON](https://www.json.org/json-en.html)

---

## YAML/YML
- Main page: https://yaml.org/
- General mappings use a colon and a space (key:value)
- Lists begins with a dash and then a space
```
MyItems:
- EntryOne
- EntryTwo
```
- An alternative way of referencing a list of sequences is through square brackets "\[\]" separated by commas
`MyItems: [EntryOne, EntryTwo]`
- `#` Begins a comment
- Pipe "|" symbol in YML: What follows is a multi-line scalar value
- Greater than ">" symbol in YML: Gets rid of newlines in what follows
```
include_newlines: |
		exactly as you see
		will appear these three
		lines of poetry

fold_newlines: >
		this is really a
		single line of text
		despite appearances
```

---
# Sections
![](https://i.imgur.com/uE4jjMG.png)

# Intrinsic Functions
There are a number of [intrinsic functions](https://www.ibm.com/docs/en/cobol-zos/6.3?topic=functions-intrinsic) for CloudFormation.  Short-hand version uses an explanation point before the function name

1. **Ref** - returns the value of the parameter or resource.  

```
!Ref MyResource
```

2. **Base64** - returns the Base64 representation of the input string. (Commonly used with !Sub and the YAML pipe character to provide several lines user data)

3. **Sub** - substitutes variables in an input string with values you specify.  
Example #2:
```
UserData: 
	Fn::Base64: 
		!Sub |
			#!/bin/bash -xe
			# other commands
```

4. **Join** - Appends a set of values into a single value, separated by the specified delimiter
5. **GetAtt** - Returns the value of an attribute from a resource in a template (some resources have attributes)

```
!Join [ '', [ 'http://', !GetAtt MyELB.DNSName ] ]
```