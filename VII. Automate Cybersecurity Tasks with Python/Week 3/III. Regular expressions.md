# Regular expressions in Python

- **Overview of Previous Learning:** The passage begins by summarizing previous knowledge about working with strings, including positional indices and slicing, and mentions the application of these concepts to extract information from a list of IP addresses in the previous video.
- **Introduction to Regular Expressions (Regex):** Introduces the concept of **[[regular expressions (regex)]]**, defining them as sequences of characters forming patterns. Emphasizes their use in searching within log files and highlights their capability to search for various patterns, such as specific prefixes or lengths, in a security context.
	- **Application of Regex in Security:** Provides examples of how regex can be applied in a security context, such as efficiently searching for specific IP address patterns or extracting email addresses from log files without prior knowledge of the exact addresses.
- **Explanation of Regex Symbols:** Introduces the plus sign (+) in regex, representing one or more occurrences of a specific character. Explains its application through examples. Introduces the `\w` symbol, matching any alphanumeric character, and discusses its combination with the plus sign to create flexible patterns.
	- **Combining `\w` with the Plus Sign (`+`):** Demonstrates how combining `\w` with the plus sign (`\w+`) matches alphanumeric strings of any length, offering flexibility in both character types and string lengths. Provides examples of strings that match this combined pattern.
- **Representing Email Addresses with Regex:** Breaks down the structure of a typical email address and explains how regex patterns can represent each segment, including alphanumeric characters, the @ symbol, the domain name, and the period. Emphasizes the importance of using backslash before special characters in regex.
	- **Constructing Regex Pattern for Email Addresses:** Combines the individual regex patterns for email address segments into a comprehensive regex pattern that matches all email addresses and excludes other strings.
- **Application of Regex in Python (`re.findall(regex, variable)`):** Demonstrates how to use regular expressions in Python by importing the `re` module and applying the `findall()` function to search for email addresses in a given string variable (`email_log`). Walks through the code step by step, explaining the arguments and the result.
- **Encouragement for Further Exploration:** Encourages readers to explore regular expressions further, mentioning the abundance of symbols available in regex and suggesting independent learning.
- **Conclusion:** Concludes by highlighting the introductory nature of the content and the potential usefulness of regular expressions in handling log files with thousands of entries. Encourages continued exploration and learning.

# More about regular expressions

You were previously introduced to regular expressions and a couple of symbols that you can use to construct regular expression patterns. In this reading, you'll explore additional regular expression symbols that can be used in a cybersecurity context. You'll also learn more about the re module and its re.findall() function.

## Basics of regular expressions

A **regular expression (regex)** is a sequence of characters that forms a pattern. You can use these in Python to search for a variety of patterns. This could include IP addresses, emails, or device IDs.

To access regular expressions and related functions in Python, you need to import the re module first. You should use the following line of code to import the re module:

`import re`

Regular expressions are stored in Python as strings. Then, these strings are used in re module functions to search through other strings. There are many functions in the re module, but you will explore how regular expressions work through re.findall(). The re.findall() function returns a list of matches to a regular expression. It requires two parameters. The first is the string containing the regular expression pattern, and the second is the string you want to search through.

The patterns that comprise a regular expression consist of alphanumeric characters and special symbols. If a regular expression pattern consists only of alphanumeric characters, Python will review the specified string for matches to this pattern and return them. In the following example, the first parameter is a regular expression pattern consisting only of the alphanumeric characters "ts". The second parameter, "tsnow, tshah, bmoreno",  is the string it will search through. You can run the following code to explore what it returns:

1

2