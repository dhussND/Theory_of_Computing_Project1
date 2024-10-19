Copy Paste of README submission

Project Hamiltonian Path Readme Team dhuss
Version 1 9/11/24
A single copy of this template should be filled out and submitted with each project submission, regardless of the number of students on the team. It should have the name readme_”teamname”
Also change the title of this template to “Project x Readme Team xxx”
1
Team Name: dhuss
2
Team members names and netids: Daniel Huss, dhuss
3
Overall project attempted, with sub-projects: Hamiltonian Path
4
Overall success of the project: Overall, I felt the problem was very successful. 

From the professor’s announcement: “A successful outcome for this project is thus for each student, regardless of the number in a team, to gain an appreciation of how quickly such problems can grow to consume huge amounts of computer time.”

This project really demonstrated that. It took my program 1 hour to process 10 graphs of size 13 nodes. I allowed my program to run overnight for 8 hours and attempt to process 10 graphs of size 14, and it did not complete a single graph. This really drove home Kogge’s point.
5
Approximately total time (in hours) to complete: 

Figuring out Hamiltonian path detector algorithm: 2 hours
Testing: 1.5 hours

Extra Credit:
Generating and validating test cases for the class: 2 hours
Converting test cases to .cnf: .5 hours

Other: 1.5 hours

Total:  ~7.5 hours
6
Link to github repository: https://github.com/dhussND/Theory_of_Computing_Project1 
7
List of included files (if you have many files of a certain type, such as test files of different sizes, list just the folder): (Add more rows as necessary). Add more rows as necessary.





File/folder Name
File Contents and Use
Code Files
hamiltonianPath.py
Checks for hamiltonian path, generates random graphs, times each case, plots results

./hamiltonianPath.py > destination.txt

(will also produce a .png of the plot: 'hamiltonian_path_times.png')
Test Files
hamiltonian_path_test_cases_2.txt, hamiltonian_path_test_cases_2.cnf,
hamiltonianPath.py
hamiltonianPath.py generated the test cases and did the timing tests.

The test cases were generated using networkx. I passed in 10 graphs each for graphs of size 1-13 nodes (130 graphs total). The number of nodes was randomly selected by picking a number in the range of possible edges:
(0, (n*(n-1)) / 2).

I validated these results by manually re-creating a number of the graphs, and verifying the result.

hamiltonian_path_test_cases_2.txt contains the graphs that were generated and whether they had a Hamiltonian path. 

hamiltonian_path_test_cases_2.cnf: same as hamiltonian_path_test_cases_2.txt, but converted to .cnf. 
Output Files
output.txt,
hamiltonian_path_times.png
output.txt: contains the graphs that were tested, whether it contained a Hamiltonian path, and the amount of time taken for each case. 

hamiltonian_path_times.png: plot outputted by program
Plots (as needed)
hamiltonian_path_times.png
Plot showing exponential relationship between size of graph and time taken to process.



8
Programming languages used, and associated libraries: 
Python, networkx, itertools, matplotlib, random, time
9
Key data structures (for each sub-project):
The input type for my hamiltonian path solver was directed graphs. 

I didn’t have any “key” data structures beyond lists to store relevant information about each graph. The challenge had more to do with iterating through all permutations of the nodes and checking for edges between them. This relates more to with complete search algorithms than data structures, though.
10
General operation of code (for each subproject)
Basic:
./hamiltonianPath.py > file_name.txt

Advanced:
Setting size of graphs (line 36)
Setting number of graphs for each size (line 37)
Changing name of scatter plot file output (line 74)
Including or commenting out the optimization for quickly identifying certain non-Hamiltonian graphs (line 11-12)

The code generates 10 graphs for each size of graph between 1 and 13 (130 total). It generates a random graph of the specified size using networkx. It then times the amount of time taken to check for a hamiltonian path. Checking for a Hamiltonian path is done by iterating through all permutations of the nodes in the graph and checking that there is an edge between the two nodes. The time taken is then plotted in green or red depending on if there is a Hamiltonian path or not.
11
What test cases you used/added, why you used them, what did they tell you about the correctness of your code.
I wrote code that generates my own test cases. I used this to generate 130 graphs, 10 each between size 1 and 13. I included graphs of size 1 to see if my algorithm would exhibit any odd behavior. It correctly identified these edge cases as containing a Hamiltonian path. I then viewed the output and plotted these graphs in python and manually confirmed whether or not a Hamiltonian path existed. After confirming many test cases, I shared my results with Professor Kogge who provided my results as test cases for the class.
12
How you managed the code development
The development process was easy to manage as I worked by myself. 
I first focused on making a function for determining if a graph contained a Hamiltonian path. I then tested on some basic test cases I manually came up with. 

I then wrote a function for generating random graphs, which enabled more rigorous testing.

Lastly I focused on timing and plotting the results. 

This was a fairly straightforward process. 
13
Detailed discussion of results:

I found there was a clear exponential relationship between the number of nodes in the graph and the time taken to detect a Hamiltonian path. 
Within the results, there is another clear trend. Graphs containing a hamiltonian path took a moderate amount of time relative to other graphs of the same size to process. This is because the program had to iterate through some of the permutations of the nodes until a Hamiltonian path was found.
Graphs not containing a Hamiltonian path were either extremely slow or extremely quick to process. This is due to an optimization I added. If the number of edge-pairs, e, in a graph was less than n - 2 (n = # nodes), then a Hamiltonian path is impossible. This is because there would not be enough edges to connect every node (i.e. there would be at least one node on an island). This optimization should handle about 12.8 % of cases given a graph of size n=13. This is because the number of edges was a randomly generated number between 0 and (n * (n-1)) / 2. Otherwise, the graph would have to iterate through all permutations of the nodes.

Also, based on how the graphs were generated, there was a bias towards creating Hamiltonian graphs (hence why the majority of the points are green). This is due to the fact that the number of edges generated was a random number between 0 and 
n*(n-1) / 2. You only need n - 1 edges for a Hamiltonian path to be possible. Each additional edge randomly added increases the likelihood of a Hamiltonian path existing. 
14
How team was organized 
Not applicable. 
15
What you might do differently if you did the project again:
I might try to resolve the bias towards generating Hamiltonian paths, though it was only a minor issue as the exponential trend was still very clear.
16
Any additional material:
Professor Kogge asked me to include the test cases and .cnf I provided for the class in my submission. Those files are:
convert_to_cnf.py, hamiltonian_path_test_cases2.txt and hamiltonian_path_test_cases2.cnf


