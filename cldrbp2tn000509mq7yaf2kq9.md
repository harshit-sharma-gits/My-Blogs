# What is YAML

YAML stands for *Yet Another Markup Language* or *YAML ain't Markup Language,* and it is a data serialization language used to write configuration files. But what is data serialization??

**Data Serialization:** A process of converting a data object into a series of bytes in a form that is easily transmittable over a network.

In easy terms, data serialization means converting data into a form that can be transmitted easily. We use languages like YAML, JSON, XML for data serialization.

YAML, as I told you above, is also used to write config files for Docker, Kubernetes, Flutter, etc.

## Benefits of YAML

* It is simple and easy to read.
    
* It has Python style indentation format (but we use spaces here, instead of tabs)
    
* YAML is easily convertible to JSON, or XML.
    
* Plenty of tools are available!
    

Check out these tools for working with YAML files: [https://onlineyamltools.com/](https://onlineyamltools.com/)

### Extension of YAML Files

YAML uses these file extensions: `*.yaml` and `*.yml`

### How to write comments in YAML

YAML uses Python like comments as well. You have to write a hashtag `#` to start a comment.

# How to write YAML Files

### Key Value Pairs

You can write key-value pairs as follows:

```yaml
"Harshit": "I am learning DevOps"     # A simple key-value pair

bio: |                                # Multi line string
Hey, my name is Harshit Sharma
I am a pre-final year student

message: >                            # A single line in multiple lines
This is a
single line
```

### List

You can write a list as follows:

```yaml
fruits:
 - Apple
 - Mango
 - mango             # YAML is case sensitive, so this mango is different

# This can also be represented as

fruits: [Apple, Mango, mango]
```

### Different Types

```yaml
# Integers
positiveNumber: !!int 12
negativeNumber: !!int -12
binaryNumber: !!int 0b010101
octalNumber: !!int 05673
hexaNumber: !!int 0x45A
commaValue: !!int +120_000                # Will be represented as 120,000

# Floats
marks: !!float 95.8                       # My board exam marks ;)
not_a_number: !!float .nan
infinite: !!float .inf

# Null
surname: !!null Null                       # or null NULL ~

# Dates
date: !!timestamp 2002-12-14
indiaTime: !!timestamo 2001-11-04T17:30:00 +5:30

# List
student: !!seq
 - name
 - marks
 - hobbies
```

That's all for this article!

Hope you liked it!

Connect with me:

🔗 **LinkedIn:** [https://www.linkedin.com/in/harshit-sharma--/](https://www.linkedin.com/in/harshit-sharma--/?lipi=urn%3Ali%3Apage%3Ad_flagship3_feed%3BDyaAHIP6RTC6XMe1valniA%3D%3D)

🔗 **My YouTube Channel:** [https://www.youtube.com/c/CoderBuddy?sub\_confirmation=1](https://www.youtube.com/c/CoderBuddy?sub_confirmation=1)

🔗 **GitHub:** [https://github.com/harshit-sharma-gits](https://github.com/harshit-sharma-gits)