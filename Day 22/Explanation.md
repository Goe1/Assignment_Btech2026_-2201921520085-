"Explanation here..." 
So, to design a DS we only need to support 3 function's for this data structure.

One is theconstructorthat's gonna intialize the object.
One isAddingtheword's, but all of them are lower case froma to z
One isSearchingaword, and the word can contains any character froma - z. But there is1 additional characterit contains,"."character[And what they told "." character is a wild card, can match any character easily in the string]
The brute force way to solve this problemis pretty simple, "having a list of words & then just for every search we would just see, if this search match any of the word in input list."[But it's not an efficient way]

Let's talk about,efficient way to solve this problem. And for that we requireTrie data structurea.k.aPrefix tree

Let's understandTrie first,
Trieis basically atreethat has some kind ofroot node& each node can have up to26 children in this problem. Because we havelower case character from a to z. So, basically eachnode represent's a single character. And each node could have up to 26 additional children:

image

And basically word in this example means, let's take"a"having child"b" -> with "c", so that's will be asingle word. And if we insert the word"abc"in ourtrie, so basically how's it looks like:

image

One additional thing we have to say is, for a particular node such as"c"this is theend of the word. Because if weadded another wordexample:-"ab". So, we don't add them back again as if you notice they are already available to us, we justgonna re-usethese characters. So, we have 2 word's along thispath "abc" & "ab"
Basically, all words start with"a"are gonna be here, that's what it make itefficient. That's why it's calledprefix tree.

Now, you have understood how Trie aka Prefix Tree work.

Now let's take an example & build our tree,
Input

["WordDictionary","addWord","addWord","addWord","search","search","search","search"]
[[],["bad"],["dad"],["mad"],["pad"],["bad"],[".ad"],["b.."]]
Output

[null,null,null,null,false,true,true,true]
The first word we add is"bad". "b" -> "a" -> "d"

Next we adding another word"dad". So, we have to start withdifferent path. As, these two word's have adifferent prefix. One start with"b"and one start with"d". So, let's add it:"d" -> "a" -> "d"

We have one last word before we start searching, this one gonna be"mad". So, we don't have"m", then let's add it:"m" -> "a" -> "d"

image

So far we have3 word'sand all of them end with different"d". But they all3 of them have different prefixthat's why they are along different path's.

image

Now let's go for searching path:-

So, first word we gonna search for"pad". We gonnastartatbeginning. First we gonna try are there any"p"in this. That means immediately wereturn falseas"pad"doesn't exist in our input.

Now, we search another word"bad". So, westart at the rootand see there are any"b". Yes, we have"b". now we check does this"b"have a child"a", yes it does. Now last character"d"does"a"has a child"d", yes it does have. Lastly we have to say the last character"d"is in ourtrie, which designated as the end of the word. Sice it'smarked red. Therefore, wereturn truefor this input"bad"

Now, in this search we have".ad", the dot"."character matches any character. So, we start at the root and go to any of the path and to do that we have to useDFS or backtracking approach. So, let's say first path we decided"b". now we check does this"b"have a child"a", yes it does. Now last character"d"does"a"has a child"d", yes it does have. Lastly we have to say the last character"d"in our trie, is designated as the end of the word. Therefore, wereturn truefor this input".ad"

One last search, In this we have"b..". So, we start at the root and see there are any"b". Yes, we have"b". Now we check do we have any character to go below for our current dot".", yes we have"a". Now we are looking for any character for our lastdot "."Yes we have"d"& it is end of the word. Therefore, wereturn truefor this input"b.."

Now understand thisVISUALLY, it's not super hard.