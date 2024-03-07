# Hex Value Regex Tutorial

Regular expressions, commonly abbreviated as Regex, serve the purpose of parsing and specifying the criteria for text searches. They encompass a range of elements, including literals for exact matches and meta characters for identifying specific types of characters. Regular expressions comprise distinct components that facilitate the exploration of text patterns.

# **Summary**


In this tutorial, we will examine the various components of a Hex Value Regex. A Hex Value Regex specifies the permissible characters for identifying a hexadecimal color. This is particularly useful in coding tasks to ensure the inclusion of required characters and to notify the user of invalid inputs. We will delve into the following regex:
/^#?([a-f0-9]{6}|[a-f0-9]{3})$/

**Table of Contents**

[Anchors](https://github.com/fderosier/Regex-Tutorial/blob/main/gist-template.md)

[Quantifiers](https://github.com/fderosier/Regex-Tutorial/blob/main/gist-template.md#quantifiers)

[Grouping Constructs](https://github.com/fderosier/Regex-Tutorial/blob/main/gist-template.md#grouping-constructs)

[Bracket Expressions](https://github.com/fderosier/Regex-Tutorial/blob/main/gist-template.md#bracket-expressions)

[Character Classes](https://github.com/fderosier/Regex-Tutorial/blob/main/gist-template.md#character-classes)

[The OR Operator](https://github.com/fderosier/regex-example/main/gist-template.md#the-or-operator)

[Flags](https://github.com/fderosier/Regex-Tutorial/blob/main/gist-template.md#flags)

[Character Escapes](https://github.com/fderosier/Regex-Tutorial/blob/main/gist-template.md#character-escapes)

[Overview](https://github.com/fderosier/Regex-Tutorial/blob/main/gist-template.md#overview)

# **Regex Components**
# **Anchors**

Anchors define the start and the begining of the regular expression that will be used in the search. Firstly, a rejex is consitered a literal, so the entire expression is wrapped in slashes /. The anchors are the next components within the literal. The character ^ defines the start of the expression, while $ defines the end.

In the hex value regex above we can see the entire expression wrapped in these anchors: /^...ext...$/

# **Quantifiers**

Quantifiers are the components of the regex that set the limits to the search. There are four types of quantifiers:

The * symbol quanifies the search to match the pattern zero or more times.

The + symbol quanifies the search to match the pattern one ore more times.

The ? symbol quanifies the search to match the pattern zero or one time.

The {} quanitfiers specify a specific range (eg. between 2 and 27).

In our regex we see the ? symbol used. This tells us that the symbol before it will be matched zero or one time.

We also see two different {} expressions, {6}and {3}. Both of these quantifiers define a rigid number of characters to returned, wither 6 or 3.

# **Grouping Constructs**

Grouping constructs are used to isolate certain aspecs of the regex. As the expressions get more complex, this become more nessisary. Parentheses () are used to group constructs within the regex. If, for instance, it is nessisary to find two componants each of which have different parameters, we have to use grouping. For example, if I would like to find one number first from 6 to 9 and another number second from 2 to 8 we could write the expression /^(([6-9]?)([2-8]?)$/.

In our regex we can see almost the entire expression is wrapped in a grouping constraint. In this case, we see # outside of the group. This is a literal, meaning this will literally search for the # symbol. After that, everything preceding the ? will be found zero or once and returned after the #.

# **Bracket Expressions**

In the previous section, you may have noticed the use of []; these are bracket expressions. Bracket expressions are used to define a set of characters that can match any individual character of the set. Use an use these to create a range or list of characters you want met.

in our hex regex we can see two bracket expressions, both displayed as[a-f0-9]. The only difference is the quantifiers are determining different lengths.

# **Character Classes**

Character classes are shorthands to match specific types or groups of characters.

. -Matches any character except (/n).

/d -is equivelent to [0-9].

/w -is equivelent to [A-Za-z0-9_], meaning it matches any upercase or lowercase letter, any number, and an underscore.

/s -Matches a single whitespace character such as a space.

We do not have any of these character classes in our regex, however, we could replace our [0-9] expression with /d.

# **The OR Operator**

The OR | operator is very useful in regex. This is used to provide a more dynamic search in the regex. For instance, if the user needed to find a phone number separated by '-' OR '.'.

In our regex, we see an OR operator separating two expressions. This tells us that we will try to match the first criteria, but if it is not satisfied we will check the second.

# **Flags**

The only component of a regex that is placed outside of the / wrap is a flag. Flags define additional functionality or limits to the regex and are placed at the very end after the econd /. The most common are:

g -This si a global search defining that the regex should be comppared to any and all possible matches in a string.

i -This flag can be used in lieu of the [A-Z] expression. This marks the expression with case insensitivity.

m -This creates a multi-line search. Strings input as multi-line will be treated as multipe lines.

u -This enables unicode match support, allowing matches of characters outside of the basic multilingual plane.

y -This flag stands for sticky-mode. This is useful to ensure the search happens at a specific position in the string (the position is defined by the lastIndex property of the regex).

We have not implemented flags in our regex

# **Character Escapes**

Character escapes are characters that may have other meanings in the regex, but need to be interpreted literally. For instance, the ^ symbol is an anchor, but with the use of the backslash \ we can search for this character in our string-- \^.

We have not implemented a character escape in our regex, but this is very common in many other types such as email regex.

# **Overview**
Now that we have defined all the different parts of a regex, lets break apart our hex value regex /^#?([a-f0-9]{6}|[a-f0-9]{3})$/
First, the entire expression is wrapped in slashes / and our anchors; ^ defining the start, and $ defining the end.
The first peice of the expression after the begining anchor is #. This is a literal, meaning the expression will literally match that symbol.
Following this is the ? symbol, indicating that the # symbol is optional in the resulting string.
After this expression we have a group ([a-f0-9]{6}|[a-f0-9]{3}), within this we have two bracket expressions with two quantifiers separated by an OR operator. This states that we are trying to match a lower case number from 'a' to 'f' or a single digit number with a length of 6 characters OR the same but of a length of 3 characters.
# Author
https://github.com/Fderosier/regex-example.git