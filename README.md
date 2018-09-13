# illumio-coding-challenge-aarsh

Thoughts and Explanation:
When I first read the spec, the naive solution I thought of would to just add all the rules and then compare the given inputs to each of the rules. However, this would be O(n) time and if there were many rules and many packets this would create a very slow checking procedure. In order to improve this we can use a hashmap. Searching would on average be 0(1) if we assumed a faily diverse set of rules but then in order to check all the values within a range we would have to add all of those rules to the dictionary which would then be very costly memory wise. In order to fix this instead of storing all the rules in a range, I just added a boolean to the object that says whether or not the rule contains ranges for the port and IP_address, and then when I retrieve the rule i can check whether or not its a range or not. If not I check the inputs directly against the rule otherwise check within the range. This saves space and also allows to check for ranges efficiently. However, if all the rules have the same direction and protocol and all happen to include ranges, we may still get a worst case runtime of n where n is the number of rules. 

Testing:
I just tested this by creating print statements and checking if the created the right outpout. Usually I use this as a first step to see if the code worked and if it didn't I go through the code, verifying what each part did. If i had more time I would have created some randomied inputs and then check if those inputs resulted in the right answer based on the rules. Also, would have created some more rules, and testing some edge cases like overlapping rules. 

Potential Optimizations:
When I started the challenge using a list was the immediate naive solution that came to my head. Then given the fact that we had distringuishable inputs, a dictionary was the optimization that came to mind because it had the potential to significantly decrease the runtime complexity. Another idea I had was trying to use BST. By creating a rule class and then putting all the rules into a tree based on some comparision on the port, direction, IP, and protocol. However, creating a robust comparision method would be hard in order to create a tree thats balanced. Our amortized run time would be logn but worst case would still be n, which might make the dictionary approach a bit better with the higher upside. 

Team:
I would be mostly interested in either the Policy or Data team. I just took the machine learning course over summer and am currently taking computer security (CS161), data science (CS186), and databases (CS100). Two careers in computer science that I would be really excited for are Security and Data Science, and I think the Policy and Data teams, respectively, would allow me to do so!

Overall I really enjoyed the style of this coding challenge!
