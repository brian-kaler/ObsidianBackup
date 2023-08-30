Using this for the Windows Store/Calculator download
```
Create a list of text/value pairs formatted below with every possible UTC timezone found in the US:

<Variable>ComputerTimezone</Variable>
<Label>Computer Timezone:</Label>
	<Option>
	
		<Text>Pacific Standard Time</Text>
		<Value>Pacific Standard Time</Value>
	</Option>
	<Option>
		<Text>Mountain Standard Time</Text>
		<Value>Mountain Standard Time</Value>
	</Option>
	<Option>
		<Text>Central Standard Time</Text>
		<Value>Central Standard Time</Value>
    </Option>
    <Option>
        <Text>Eastern Standard Time</Text>
        <Value>Eastern Standard Time</Value>
    </Option> 
    <Option> 
        <Text>Alaska Standard Time</Text> 
        <Value>Alaska Standard Time</Value> 
    </Option> 
    <Option> 
        <Text>Hawaii-Aleutian Standard Time</Text> 
        <Value>Hawaii-Aleutian Standard Time</Value> 
    </Option> 
    <Option> 
        <Text>Samoa Standard Time</Text> 
        <Value>Samoa Standard Time</Value> 
    </Option>
```


```
#powershell (tested)
Set-Timezone -name "TEXTHERE"

```

[UWP]