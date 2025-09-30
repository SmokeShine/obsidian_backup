202403211435
Status: #idea
Tags: [[Transformer]]

# Byte Pair Representation

1. Split all the tokens into 1 character
2. Use a window of 2
3. Do a frequency count
4. Merge the top frequency tokens into 1 (here the assumption is that they occur together)
	1. Now, we have all the tokens from 1 and new more tokens from merging
5. Do a frequency count again
6. Repeat Step 4 till finished

For new text, split into 1 character, then do a lookup from token for window 2. Merge, repeat.

---
# References

7. https://www.youtube.com/watch?v=HEikzVL-lZU