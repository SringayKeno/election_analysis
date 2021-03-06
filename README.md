# election_analysis


## Overview of Election Audit:

I assisted Tom, a Colorado Board of Elections employee in an election audit of the tabulated results for a US Congressional District in Colorado. After the votes were counted it was my job to certify this US Congreessional race. 

I was tasked with reporting the following:
* The total number of votes cast
* The total number of votes and percentage of vote for each candidate
* The winner of the election based on popular vote

The audit is usually done in Excel, but Tom's manager wanted to know if there is a way to automate the process using Python. If this audit is done successfully with Python, the code would be used to audit other districts and local elections.

Below, a sample of the dataset in CSV file. It was this data format that I ran the Python code through to audit the congressional election results.

<img width="250" alt="csv_election_results" src="https://user-images.githubusercontent.com/102890151/164986645-36ee56e9-ee5d-4d31-9008-c8ecfa95008c.png">





## Election-Audit Results


* ### Total votes cast in this congressional election

The audit required working with election data from a CSV file and writing a "for/if" loops to get to the desired outputs using floats on vote counts and percentages. I used Visual Studio to write Python for the audit. After establishing read and write connections to the data and outfiles (election summary and results) the first task was to count of the number of total votes. 

To count up all the votes, I needed to initialize a variable. For convenience, I initialized a variable and called it "total_votes" and equalled it to zero. This variable, which is called an accumulator, increments by 1 as it reads each row in the for loop as it calculates the total votes cast starting with 0. 

Initializing variable in code (below)

<img width="400" alt="total_vote" src="https://user-images.githubusercontent.com/102890151/164986772-4aeee55b-c9c1-4346-b374-35fa4d754050.png">

**The total vote count for this US congressional election was 369,711.**

* ### Number of votes and percentage for each county and highest county voter turnout

As the audit was winding down the election commission requested some additional data to complete the audit which included; voter turnout for each county, percentage of votes from each county out of the total count and finally, the county with the highest turnout.

Snapshot of a portion of the outfile (election_results.txt file) I created summarizing the election results (Image 1 below) for the audit. **Jefferson had 10.5% of the votes at 38,855. Arapahoe had 6.7% of the toal vote or 24,801 votes. Denver county at 82.8% of the votes (largest percent) and 306,055 votes which was the largest number of votes of the three counties.**



Image 3 (below) election summary or election_results.txt file

<img width="325" alt="Screenshot (47)" src="https://user-images.githubusercontent.com/102890151/164957031-fbe5ac78-b22d-48b3-8093-7188413a0b8d.png">

Working from the original dataset (csv file) I used for loops and conditional statements with membership and logical operators to find the number of votes and percentage of total votes for each county (Seen in image below). Then I, "print" the results to the command line and saved them to the election_results.txt file (image 3 above)

<img width="400" alt="county_votes_code" src="https://user-images.githubusercontent.com/102890151/164983603-9651e510-20bc-4dfb-96b4-577635ae2b05.png">


* ### Breakdown of votes and percentage each candidate received

I counted the votes for each candidate while in the if statement. As I iterated through each row of the CSV file, I incremented the votes for each candidate by 1. However, I needed to link those votes with a candidate. A convenient way to do this is to create a dictionary where the key is each candidate's name and the vote count for that candidate is the value for the key.



 (Below) First step in creating the dictionary was declaring an empty dictionary, candidate_votes = {}

<img width="387" alt="declaring_dict_empty" src="https://user-images.githubusercontent.com/102890151/164988388-1220e85a-445e-4f92-89e6-5999e68c333c.png">

After declaring dictionary empty, I created each candidate as a key. I used candidate_votes[candidate_name]. When I added candidate_votes[candidate_name] = 0, I am setting each candidate's vote count to zero. Once I set it to zero, then I could start tallying the votes for each candidate (seen below)

<img width="387" alt="candidate_vote_count" src="https://user-images.githubusercontent.com/102890151/164988886-6b199721-04af-4e96-9427-15d237704468.png">

Print out of Breakdown of candidate votes and percentage of total votes each candidate received (below)

<img width="350" alt="candidate_election_analysis" src="https://user-images.githubusercontent.com/102890151/164989820-8164481d-3653-4990-b2f2-b4644e39fcb9.png">





* ### Winning candidate, their vote count, and percentage of the total votes

 My final task was to determine the winning candidate by the number and percentage of votes. In ordr to do that I first needed to declare the following; (1) a variable that holds an empty string value for the winning candidate, (2) declare a variable for the "winning count" equal to zero and lastly, declare a variable for the "winning_percentage" equal to zero. Code seen below

<img width="417" alt="code-winning_candidate" src="https://user-images.githubusercontent.com/102890151/165010180-868963a6-9829-440b-ba6f-02d9541a071d.png">

 Next in looping through the vote counts, I could use an if statement to check if the first vote count for a candidate is greater than zero. Then if the statement was true, that vote count will be equal to the "winning count." At the same time, I can set that candidate's percentage of the vote equal to the "winning percentage."
Then select the candidate as the "winning candidate" from the candidate_options list.
                                                    
<img width="417" alt="code-winning_candidate" src="https://user-images.githubusercontent.com/102890151/165010037-4f38d150-490c-43fa-b5ec-0f85699a733c.png">


**The winner was candidate, Diana DeGette, with a total of 272,892 votes which was 73.8% of the total votes**

<img width="250" alt="winner_election_analysis_final" src="https://user-images.githubusercontent.com/102890151/164996802-b1ac61f8-8bed-4871-b31e-27949dec8f7f.png">


## Election-Audit Summary:

Below, print of the complete election_results.txt file

<img width="400" alt="winner_election_analysis" src="https://user-images.githubusercontent.com/102890151/164996680-7d3e8d00-a6b5-4a16-a2cc-7d97a4e52301.png">


Tom was pleased with the audit and is going to submit the election audit results to the election commission. Since the audit was done successfully with Python, the code could be used to audit other districts and local elections. I give some xxamples of how this script can be modified to be used for other elections below.


### Examples of how this script can be modified to be used for other elections

* One benefit of the Python code is the ability to look at large quantities of data with ease. This script in the election analysis only looked at two variables; candidate and county, however other variables could be added or taken out of the code as needed, making it very versatile
* Secondly, those variables can be analyzed in additinal ways. For example, taking the two variable mentioned in the irst bullet point, the code could be used to analyze the vote percentage for each candidate in each county.

