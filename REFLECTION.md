1. For every function you wrote (TODO 1 to 19), explain in your own words what it does and
give its time complexity in terms of n, the number of scenes. One short paragraph each.
-TODO 1: esentially  the scene itself is a constructor to store everything the scene has inside of it like the data itself and choices user will make
and making the initial value for every choice a nullptr (if nothing)! I believe it has a time complexity of O(1) 

-TODO 2: The scene destructor's job like destructor suggests deletes every scene inside child then deletes the choices with it and the data inside the scene (aka the child) but if the scene is 
the root then it ends up deleting every scene in the story. Time compelxity of O(n) since its deleting over and over meaning sequential.

-TODO 3: the isEnding function's literal sole purpose is to just check whether the numChoices is zero or not where is my story (the cat simulator) a scene with
zero choices (aka making the function true) then it ends the story. An exmaple of this being the scene where the cat ends up becoming the most pamperd cat thus ending the story!
Time complexity being O(1) since it has no loops or anything with one line just checking if numChoices is 0.

-TODO 4: the getChoice function checks whether or not the index place its at is legal or not (in terms or args) and returns the scene if it is. Time complexity of O(1) since it searches once to look
at the position!

TODO 5: setChoice function (setter methid) also checks the index like getChoice but stores (sets) the child scene in the index its at if allowed.
Time compelxity is O(1) since it simply sets!

TODO 6: countScenes function is one of the recursive functions adding up all the scenes making it a time complexity of O(n) if you take away all constants. But it basically just takes the scene its at and visits the next one adding the next one it
goes to into its count over and over. 

TODO 7: countEndings is also a recursive function but instead of counting every scene it only checks for a scene that is an ending before adding to that count. In my story, countEndings counts the scenes like the cat contest, house cat, and thundercloud storm scenes 
as endings and adds them together. Also a time complexity of O(n) since it adds over and over (leaving behidn constants making it O(n)).

TODO 8: height function works to check the height of a story and also a recursive function! The function checks for when it finds a child over and over until it finds the largest child height. 
Example being in my story where the longest path the user can take being five choices long making it a height of 5. In my story this path is the path that one takes when exploring the alleyways as a stray cat to winning the cat contest and slaying the cat world. 
Time complexity being O(n) since it counts and adds each time leaving behind constants again.

TODO 9: The clear function starts by deleting the root before deleting every scene and thus leaving the entire story empty after its done. Time complexity is O(n) since it subtracting 

TODO 10: load function is the stage manager in my opinion since it does the "hard" work of opening up the story files, reads everything inside it to set up the story like HP and builds up the entire story
using the readScene function within it to put together and ACTUALLY makes it a tree since it labels a whole completed story as a tree after it makes root to tree. Time complexity should be O(n) since its just adding every scene together?

TODO 11: Helping the load function, the readScene function is the assistant where it reads the scene's data, including hp, loot, item, and number of choices before reading each child scene again and again to then at the end add it all together (putting it together as a story)
with help from setters/getters like setChoice. The cat story I went with after intial start (root) is only read once which means the time compelxity has to be O(n) since its only adding up.

TODO 12: askChoice function just asks the user the avaliable choices for the story (aka 1-3 choices) and makes sure choices are legal meaning only 1-3 and not more than 3! Time complexity of O(1) I think with this function
because 

TODO 13: play function is shown to the user at the beginning which (when selected) allows the player to play through the story, constantly updating the user's hp, loot, and inventory following the path's choices via user choice. 
I have a lot of if-else nested ones inside this function checking these updated data's like when searching through the user's inventory. I think this function is a time complexity of O(n) considering that its just going scene by scene through the tree.

TODO 14: printStats function is very simplistic acting as one of the getter's printing out how many scenes there are, endings, and the height of the tree in the story. It has a time complexity of O(n) following no loops of any other than just havung the function of printing and grabbing data from other functions.

TODO 15: printSpoliers function (the one line function) is actually another one of the recursive functions repeatedly using/calling printEndings right onto the root (hence the root_) basically visiting every story scene's to find every path's ending (and all the endings) making it a spolier! 
Time complexity of O(n) again since its just printing and "counting" scnenes.

TODO 16: printEndings uses 2 if statements and one loop but works as a recursive function via repeatedly going to every scene and printing a path when it reaches one. So esentially, it looks for an ending scene and prints out the path user followed. For my cat story, 
this is 1-1-1-1 and 2-1-1-1-1. Time complexity of O(n) with print functions and sequential adding of O making it O(n) without constants.

TODO 17: greedyFunction uses the larger while true loop so it'll only follow an entire path if the scnee/node isn't null. So, while it isn't a nullptr, it updates loot and hp before using all if statements to look for ending scene or scene with hp that is 0 (or less)
before the for loop looks for the child with the most loot regardless! I think the time complexity is O(n) since the loops are sequential ratehr than nested.

TODO 18: bestLoot function follows plenty of if statements and a loop all going through every child path over and over until it finds the heighest loot total and an ending where story is alive (so not a bad ending). Thus returning the bestTotal for that path run. 
Time complexity of O(n) with sequential loops.

TODO 19: optimalRun uses the bestLoot to then print the best surviving path with the best loot (bestLoot). If there are no paths, then the if statement using a loot of -1 will return such message that no good paths have a then "optimal" run.
Time complexity of O(n) with mostly just printing and searching.

2. Why does each scene allocate exactly numChoices slots instead of declaring Scene<T>*
   choices[3]? What does an ending hold in choices_, and why?
3. Walk through your Scene destructor. What gets deleted, and in what order? What would
   go wrong if choices_ were deleted first?
4. Show the path greedy took and the path optimal took on your story, with the loot for each.
   Explain why greedy lost. If greedy did not lose, change your story until it does, and explain
   what you changed.
5. bestLoot tries every path, yet it runs in O(n) time. Explain why it is not exponential, using
   what you know about paths and leaves in a tree.
6. Which List methods does your game use, and why? What does one search cost as the bag
   grows?