🛍️ Project Title: Survey Feedback Analyzer
📘 Project Overview
This project aims to help you apply core Python programming concepts to build a text-based feedback analysis tool.
📂 Source:
https://drive.google.com/file/d/1jsRhgw6uRvVeGS_6XF9tk08CpPUJdQoL/view?usp=sharin
g


Problem Statement:
In any data-driven domain, especially in Data Science, analysing textual feedback is a critical step for extracting insights, improving services, and understanding user sentiment. This project aims to help you apply core Python programming concepts to build a text-based feedback analysis tool. You will work with survey feedback entries stored in a dictionary of lists, perform basic data cleaning, extract meaningful insights, and apply logic using loops, conditionals, string operations, and user-defined functions.

🧮Project Steps and Objectives:
Step 1: Preloaded Feedbacks 

Step 2: Add More Feedbacks 

Step 3: Text Cleaning 

Step 4: Word Count Insights 

Step 5: Final Summary & Insights

FINAL PROGRAMME

🧠Project Steps and Objectives
Step 1: Preloaded Feedbacks 

Start your program with the following dictionary of lists, preloaded with 10 feedbacks:

feedback_data = {
'S_No': [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
'Name': ['Ravi', 'Meera', 'Sam', 'Anu', 'Raj', 'Divya', 'Arjun', 'Kiran', 'Leela', 'Nisha'],
'Feedback': [
' Very GOOD Service!!!',
'poor support, not happy ',
'GREAT experience! will come again.',
'okay okay...',
' not BAD',
'Excellent care, excellent staff!',
'good food and good ambience!',
'Poor response and poor handling of issue',
'Satisfied. But could be better.',
'Good support... quick service.'
],
'Rating': [5, 2, 5, 3, 2, 5, 4, 1, 3, 4]
}

Python programme:

# Step 1: Preloaded Feedbacks (Given Data)
feedback_data = {
'S_No': [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
'Name': ['Ravi', 'Meera', 'Sam', 'Anu', 'Raj', 'Divya', 'Arjun', 'Kiran', 'Leela', 'Nisha'],
'Feedback': [
'Very GOOD Service!!!',
'Poor support, not happy   ',
'GREAT experience! will come again.',
'okay   okay...',
'not   BAD',
'Excellent care, excellent staff!',
'good food and good ambience!',
'Poor response and poor handling of issue',
'Satisfied. But could be better.',
'Good support... quick service.'
    ],
'Rating': [5, 2, 5, 3, 2, 5, 4, 1, 3, 4]
}


Step 2: Add More Feedbacks 
Ask the user to enter how many more feedbacks they want to add.
For each feedback, collect the following inputs from the user:
•	Name
•	Written Feedback (text)
•	Rating (1–5)

Python programme:
# Step 2: Add more feedbacks from user
n = int(input("How many more feedbacks do you want to add? "))

start_sno = len(feedback_data['S_No']) + 1

for i in range(n):
name = input("Enter Name: ")
feedback = input("Enter Feedback: ")
rating = int(input("Enter Rating (1-5): "))

•	Automatically increment S_No starting from 11 onward.
•	Append all new data into the feedback_data dictionary.

Python programme:
    feedback_data['S_No'].append(start_sno)
    feedback_data['Name'].append(name)
    feedback_data['Feedback'].append(feedback)
    feedback_data['Rating'].append(rating)

    start_sno += 1

Step 3: Text Cleaning 
•	Clean all feedback entries as follows:
•	Remove punctuation (., ,, !, ?)
•	Replace multiple spaces with a single space
•	Remove leading and trailing spaces
 Convert all text to lowercase        	Tip: Use .replace(), .split() and ' '.join() creatively.

Python programme:
# Step 3: Text Cleaning
cleaned_feedbacks = []
punctuations = [".", ",", "!", "?"]

for fb in feedback_data['Feedback']:
    fb = fb.lower()  # convert to lowercase

    for p in punctuations:
        fb = fb.replace(p, "")  # remove punctuation

    fb = " ".join(fb.split())  # remove extra spaces
    cleaned_feedbacks.append(fb)

feedback_data['Feedback'] = cleaned_feedbacks

 Step 4: Word Count Insights 
Create a function count_word_in_feedbacks(word) that:
•	Takes a word as input.
•	Returns how many feedbacks contain that word (case-insensitive match).
Python programme:
# Step 4: Word Count Function
def count_word_in_feedbacks(word):
    word = word.lower()
    count = 0
    for fb in feedback_data['Feedback']:
        if word in fb.split():
            count += 1
    return count

Use this function to print:
•	Number of feedbacks containing "good"
•	Number of feedbacks containing "poor"
•	Number of feedbacks containing "excellent"

print("\n--- Word Count Insights ---")
print("Feedbacks containing 'good':", count_word_in_feedbacks("good"))
print("Feedbacks containing 'poor':", count_word_in_feedbacks("poor"))
print("Feedbacks containing 'excellent':", count_word_in_feedbacks("excellent"))

Step 5: Final Summary & Insights

•	Display the final cleaned feedback_data (dictionary of lists).
•	Print the average rating from all feedbacks.
•	Find and display the feedback with the longest comment (in terms of word count).
•	Print the list of unique words used across all feedbacks (avoid duplicates).
Python programme:
# Step 5: Final Summary & Insights
print("\n--- Final Cleaned Feedback Data ---")
print(feedback_data)


# Average Rating
avg_rating = sum(feedback_data['Rating']) / len(feedback_data['Rating'])
print("\nAverage Rating:", round(avg_rating, 2))

# Longest Feedback (word count)
word_counts = [len(fb.split()) for fb in feedback_data['Feedback']]
max_index = word_counts.index(max(word_counts))

print("\nLongest Feedback Comment:")
print("S_No:", feedback_data['S_No'][max_index])
print("Name:", feedback_data['Name'][max_index])
print("Feedback:", feedback_data['Feedback'][max_index])

# Unique Words Extraction
all_words = set()
for fb in feedback_data['Feedback']:     
    for w in fb.split():
        all_words.add(w)

print("\nUnique Words Used in All Feedbacks:")
print(all_words)

(Optional): Sort feedbacks by rating (highest to lowest) using zip() and sorted().
Display the sorted entries.

# BONUS: Sort feedback by rating (descending)
sorted_data = sorted(zip(feedback_data['Rating'], feedback_data['Name'], feedback_data['Feedback']), reverse=True)


print("\n--- Feedbacks Sorted by Rating ---")
for entry in sorted_data:
    print(entry)
FINAL PROGRAMME:

# Step 1: Preloaded Feedbacks (Given Data)
feedback_data = {
    'S_No': [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
    'Name': ['Ravi', 'Meera', 'Sam', 'Anu', 'Raj', 'Divya', 'Arjun', 'Kiran', 'Leela', 'Nisha'],
    'Feedback': [
        '  Very GOOD Service!!!',
        'poor support,   not happy   ',
        'GREAT experience! will come again.',
        'okay   okay...',
        '  not   BAD',
        'Excellent care, excellent staff!',
        'good food and good ambience!',
        'Poor response and poor handling of issue',
        'Satisfied. But could be better.',
        'Good support... quick service.'
    ],
    'Rating': [5, 2, 5, 3, 2, 5, 4, 1, 3, 4]
}

# Step 2: Add more feedbacks from user
n = int(input("How many more feedbacks do you want to add? "))

start_sno = len(feedback_data['S_No']) + 1

for i in range(n):
    name = input("Enter Name: ")
    feedback = input("Enter Feedback: ")
    rating = int(input("Enter Rating (1-5): "))

    feedback_data['S_No'].append(start_sno)
    feedback_data['Name'].append(name)
    feedback_data['Feedback'].append(feedback)
    feedback_data['Rating'].append(rating)

    start_sno += 1

# Step 3: Text Cleaning
cleaned_feedbacks = []
punctuations = [".", ",", "!", "?"]

for fb in feedback_data['Feedback']:
    fb = fb.lower()  # convert to lowercase

    for p in punctuations:
        fb = fb.replace(p, "")  # remove punctuation

    fb = " ".join(fb.split())  # remove extra spaces
    cleaned_feedbacks.append(fb)

feedback_data['Feedback'] = cleaned_feedbacks

# Step 4: Word Count Function
def count_word_in_feedbacks(word):
    word = word.lower()
    count = 0
    for fb in feedback_data['Feedback']:
        if word in fb.split():
            count += 1
    return count

print("\n--- Word Count Insights ---")
print("Feedbacks containing 'good':", count_word_in_feedbacks("good"))
print("Feedbacks containing 'poor':", count_word_in_feedbacks("poor"))
print("Feedbacks containing 'excellent':", count_word_in_feedbacks("excellent"))

# Step 5: Final Summary & Insights
print("\n--- Final Cleaned Feedback Data ---")
print(feedback_data)

# Average Rating
avg_rating = sum(feedback_data['Rating']) / len(feedback_data['Rating'])
print("\nAverage Rating:", round(avg_rating, 2))

# Longest Feedback (word count)
word_counts = [len(fb.split()) for fb in feedback_data['Feedback']]
max_index = word_counts.index(max(word_counts))

print("\nLongest Feedback Comment:")
print("S_No:", feedback_data['S_No'][max_index])
print("Name:", feedback_data['Name'][max_index])
print("Feedback:", feedback_data['Feedback'][max_index])

# Unique Words Extraction
all_words = set()
for fb in feedback_data['Feedback']:
    for w in fb.split():
        all_words.add(w)

print("\nUnique Words Used in All Feedbacks:")
print(all_words)


# BONUS: Sort feedback by rating (descending)
sorted_data = sorted(zip(feedback_data['Rating'], feedback_data['Name'], feedback_data['Feedback']),
                     reverse=True)

print("\n--- Feedbacks Sorted by Rating ---")
for entry in sorted_data:
    print(entry)

Result:
How many more feedbacks do you want to add? 5
Enter Name: boopathi
Enter Feedback: good
Enter Rating (1-5): 4
Enter Name: raj
Enter Feedback: good
Enter Rating (1-5): 3
Enter Name: ravi
Enter Feedback: super
Enter Rating (1-5): 4
Enter Name: farina
Enter Feedback: verygood
Enter Rating (1-5): 5
Enter Name: vetrivel
Enter Feedback: good
Enter Rating (1-5): 4

--- Word Count Insights ---
Feedbacks containing 'good': 6
Feedbacks containing 'poor': 2
Feedbacks containing 'excellent': 1

--- Final Cleaned Feedback Data ---
{'S_No': [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15],
 'Name': ['Ravi', 'Meera', 'Sam', 'Anu', 'Raj', 'Divya', 'Arjun', 'Kiran', 'Leela', 'Nisha', 'boopathi', 'raj', 'ravi', 'farina', 'vetrivel'],
 'Feedback': ['very good service', 'poor support not happy', 'great experience will come again', 'okay okay', 'not bad', 'excellent care excellent staff', 'good food and good ambience', 'poor response and poor handling of issue', 'satisfied but could be better', 'good support quick service', 'good', 'good', 'super', 'verygood', 'good'],
 'Rating': [5, 2, 5, 3, 2, 5, 4, 1, 3, 4, 4, 3, 4, 5, 4]}

Average Rating: 3.6

Longest Feedback Comment:
S_No: 8
Name: Kiran
Feedback: poor response and poor handling of issue

Unique Words Used in All Feedbacks:
{'satisfied', 'but', 'not', 'handling', 'service', 'issue', 'of', 'and', 'care', 'be', 'good', 'excellent', 'food', 'great', 'poor', 'response', 'quick', 'staff', 'very', 'verygood', 'could', 'okay', 'support', 'better', 'experience', 'super', 'ambience', 'happy', 'bad', 'come', 'again', 'will'}

--- Feedbacks Sorted by Rating ---
(5, 'farina', 'verygood')
(5, 'Sam', 'great experience will come again')
(5, 'Ravi', 'very good service')
(5, 'Divya', 'excellent care excellent staff')
(4, 'vetrivel', 'good')
(4, 'ravi', 'super')
(4, 'boopathi', 'good')
(4, 'Nisha', 'good support quick service')
(4, 'Arjun', 'good food and good ambience')
(3, 'raj', 'good')
(3, 'Leela', 'satisfied but could be better')
(3, 'Anu', 'okay okay')
(2, 'Raj', 'not bad')
(2, 'Meera', 'poor support not happy')
(1, 'Kiran', 'poor response and poor handling of issue')

✅ Conclusion
This project aims to help you apply core Python programming concepts to build a text-based feedback analysis tool. You will work with survey feedback entries stored in a dictionary of lists, perform basic data cleaning, extract meaningful insights, and apply logic using loops, conditionals, string operations, and user-defined functions.
👩‍💻 Author
Project Title:  Survey Feedback Analyzer
Author: Boopathiraja suresh
Tools: python
Year: 2025
