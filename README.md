Document Title: Sentiment Analysis of Hindustan Times Headlines

1. Problem Statement
The goal of this project is to:
• Scrape live data from Hindustan Times to extract the latest news headlines.
• Perform sentiment analysis on the headlines to classify them as positive, negative,
or neutral.
• Visualize the sentiment distribution to gain insights into the general sentiment of
the news.

2. How Your Web Scraper Works
The web scraper works in the following steps:
1. Scraping the website:
o We use Python's requests library to send an HTTP GET request to the
Hindustan Times latest news page.
o The BeautifulSoup library is used to parse the HTML content of the page and
extract the headlines.
o We search for all <h3> tags with the class 'hdg3' to find the headline text.
2. Data Collection:
o After parsing the HTML, the scraper loops through the found tags and
extracts the text of each headline.
o We clean the text and append it to a list for further processing.
3. Output:
o The scraped headlines are stored in a DataFrame (pandas), making it easy to
process and visualize.

3. Machine Learning Approach and Justification
We apply sentiment analysis to classify the headlines into three categories: Positive,
Negative, and Neutral.

• TextBlob is used for sentiment analysis. TextBlob computes the polarity of the text,
which ranges from -1 (most negative) to 1 (most positive).
• The polarity score is used to determine the sentiment:
o Positive: Sentiment polarity > 0
o Negative: Sentiment polarity < 0
o Neutral: Sentiment polarity = 0

Justification:
• TextBlob is lightweight and fast, making it suitable for this task where the headlines

can vary in length and structure. It uses a lexicon-based approach, leveraging pre-
defined positive and negative words to calculate sentiment.

4. Mathematical Concepts Used
Several key mathematical concepts were applied:
1. Polarity Calculation:
o The core mathematical concept here is polarity, which is a measure of the
sentiment of the text.
o The polarity score is computed based on the frequency of positive and
negative words in the text using Natural Language Processing (NLP).

2. Data Visualization:
o A bar plot was used to represent the distribution of sentiments.
o This involves basic probability theory where we count the occurrences of
each sentiment and visualize the frequency distribution.

5. Key Challenges and How You Solved Them
1. Challenge:
o Extracting dynamic or JavaScript-generated content from the website.
o Solution:
▪ Hindustan Times' headlines are static HTML content, so we could use
requests and BeautifulSoup. However, if JavaScript was involved, we
would need to use libraries like Selenium to simulate browser
interaction.

2. Challenge:
o Handling noisy or incomplete data (e.g., missing headlines).
o Solution:
▪ Added checks to ensure that the headlines extracted are not empty or
malformed before appending them to the list.

3. Challenge:
o Sentiment analysis misclassification (neutral headlines being classified
incorrectly).
o Solution:
▪ Improved the classification by tweaking the polarity threshold or
considering a more advanced sentiment analysis model in the future.

6. Screenshots of the Working Code and Outputs
• Screenshot 1:

The working code for scraping and performing sentiment analysis.

o (Include a screenshot of the code snippet.)
• Screenshot 2:

Output of the scraped headlines.
o (Include a screenshot of the printed headlines list or DataFrame preview.)
