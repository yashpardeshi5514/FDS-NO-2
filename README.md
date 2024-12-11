marks = []
n = int(input("Enter the number of students: "))
for i in range(n):
    enter = int(input("Enter your marks (if absent, score = 0): "))
    marks.append(enter)
# The average score of class  
def calculate_average(marks):
    total = 0
    count = 0
    for mark in marks:
        if mark != -1:
            total += mark
            count += 1
    if count == 0:
        return 0
    return total / count
average_score = calculate_average(marks)
print("Average Score of the class:", average_score)
 
# Highest score and lowest score of class  
def find_highest_lowest(marks):
    valid_marks = [mark for mark in marks if mark != -1]
    if not valid_marks:
        return None, None
    highest_score = max(valid_marks)
    lowest_score = min(valid_marks)
    return highest_score, lowest_score
highest_score, lowest_score = find_highest_lowest(marks)
print("Highest Score:", highest_score)
print("Lowest Score:", lowest_score)
 
#Count of students who were absent for the test 
def count_absent(marks):
    return marks.count(0) 
absent_count = count_absent(marks)
print("Number of students who were absent:", absent_count)
 
#Display mark with highest frequency
def highest_frequency(marks):
    freq = {}
    for mark in marks:
        if mark != -1:  
            if mark in freq:
                freq[mark] += 1
            else:
                freq[mark] = 1
    max_freq = max(freq.values()) if freq else 0
    most_frequent = [mark for mark, count in freq.items() if count == max_freq]
    return most_frequent, max_freq
most_frequent_marks, max_frequency = highest_frequency(marks)
 
print("Marks with the highest frequency:", most_frequent_marks, "with frequency:", max_frequency)
