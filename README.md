# LSE-Department-of-Statistics
For this question, we want to collect some data about LSE Statistics academic staff via web scraping, and find out the distribution of different types of staff, gender balance, etc

Do the following:

[Data collection via web scraping] Use web scraping with Python modules requests and BeautifulSoup to extract the information about the academic staff of the Department of Statistics from https://www.lse.ac.uk/Statistics/People (and the linked pages). For simplicity, we only consider:

All the staff under the tab "Academic faculty"
Guest lecturers/teachers and LSE fellows under the tab "Academic associates - Emeritus Professors, Guest Lecturers and Visiting Staff"
 * i.e. we DO NOT consider any of the emeritus or visiting staff, as they are less involved and/or only joining for a short period

For each staff fulfilling the requirements above, do the following:

(a) Get the URL of the staff's page from "More information". Example:

For example, for Dr. James Abdey, the link is https://www.lse.ac.uk/Statistics/People/Dr-James-Abdey * You may get some shorter version of the path first (like Statistics/People/Dr-James-Abdey), but you can construct the full URL from the short version

(b) With the URLs collected from (a), use web scraping with python modules requests and BeautifulSoup to scrape the following information and store the result in a pd.DataFrame with 3 columns:

Name of the staff (e.g. James Abdey, with or without the title prefix)
Job title (e.g. Associate Professorial Lecturer)
Gender - depending on the page, you may be able to deduce the gender of the staff from the content of "About me"
You may want to use np.nan to represent those you cannot find the gender automatically

[Data exploration] Calculate the descriptive statistics on title and gender. Based on the descriptive statistics only, answer the following:

Are there any issues with the data collected? If yes, what are they?
Is the gender ratio of academic staff close to 50:50 within the department?
[Data wrangling] Cleaning and organise the data:

(a) Handle any issues of the data collected from part (1) based on what you have discovered in part (2), including:
If you have discovered that you did not collect the data correctly in part (1), fix it
If you are not able to fix the code in part (1), at the very least try to fix the data manually so that you can get reasonable results (and marks) in part (3) and (4)
If there is any missing data, handle them appropriately and explain your rationale
(b) Extract the "role" and the "rank" of each staff from the pd.DataFrame in (3a):
"Role" of the staff (based on https://info.lse.ac.uk/staff/divisions/Human-Resources/The-recruitment-toolkit/Role-profiles):
"teaching" (the job title should have the words like "Lecturer", "Teacher", "Teaching Fellow" or "LSE Fellow"), e.g. Associate Professorial Lecturer
"faculty" (the job title should have the word "Professor"), e.g. Assistant Professor
"Rank" of the staff:
"non-tenure" (non tenure-track, should contain the words like "Guest" or "Fellow"), e.g. Guest Teacher, LSE fellow
"assistant" (entry-level tenure-track, should contain the word "Assistant"), e.g. Assistant Professor
"associate" (mid-level tenure-track, should contain the word "Associate"), e.g. Associate Professorial Lecturer
"full" (senior-level tenure-track, does not have any of the keywords above), e.g. Professor
and put the information about the role and rank as two additional columns to the data frame in (3a)

(c) Store the pd.DataFrame from (3b) into a csv file in the data folder, with the name of the file to be lse_statistics_2022mmdd.csv with mm the month and dd the day you have collected the data. This file will help us to verify your result
[Simple analysis] Use the pd.DataFrame from part (3b), find out if the gender ratio depends on the roles and/or the rank

Based on your results in this part, do you think the Department of Statistics has a good gender balance among its staff?
Please state the limitations of your answers.

Note
Data should be extracted as automatically as possible
If you are not able to do some parts, you can hard code the values and continue to work on the rest of the question
You will lose marks for not being able to solve the corresponding part, but at least you may get some marks from the other parts of the question
For example, if you cannot get the URLs from part 1(a), you may manually figure out the URLs of the staff to allow you to continue to work on part 1(b) and the rest of the question - but of course you will lose marks for part 1(a)
Hints
When finding the gender from the content of "About me", what pronouns do you expect to see with higher frequency if the staff is male? If the staff is female?
You may find .str.contains() and/or .str.split() useful for (3b)
