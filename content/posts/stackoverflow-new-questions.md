---
date: '2025-01-09'
title: 'StackOverflow New Questions'
cover:
    image: "/blog/pics/StackOverflow-Decline-in-New-Questions.jpeg"
---

I saw this [StackOverflow Dec 2024 stats](https://gist.github.com/hopeseekr/f522e380e35745bd5bdc3269a9f0b132) pass by.

It reports data on the number of new questions created on StackOverflow from July 2008 to December 2024.

The raw data shows a dramatic drop in new questions in recent years.

The data was collected and commented on by Theodore R. Smith, who is complaining that his reasonable new question posted to the site was closed and that aggressive closing of questions is the reason for the decrease in new questions on the site:

> If someone with 20,000+ karma has their nicely-formatted questions closed so quickly, what must the newbies and rank-in-file encounter? This is probably a big reason why it's declining.

Generally, it's thought that the decline is caused by ChatGPT and similar LLMs.

The thesis is that programmers are turning to chat to solve technical questions, not google and not online communities like StackOverflow.

The thesis is very plausible.

Anyway. I copy and pasted the data from the gist into chatgpt and asked it to create a line plot.

Here it is:

![StackOverflow Decline in New Questions](/blog/pics/StackOverflow-Decline-in-New-Questions.jpeg)

Here's the code:

```python
import pandas as pd
import matplotlib.pyplot as plt

# Replace this with the local path to the downloaded file
file_path = 'path_to_downloaded_file.csv'

# Load the CSV file
data = pd.read_csv(file_path)

# Combine Year and Month into a single datetime column
data['date'] = pd.to_datetime(data[['Year', 'Month']].assign(Day=1))

# Sort the DataFrame by date
data = data.sort_values('date')

# Plot the data
plt.figure(figsize=(12, 6))
plt.plot(data['date'], data['NumQuestions'], marker='o', linestyle='-')
plt.title('Stack Overflow New Questions Over Time (2009-2024)')
plt.xlabel('Date')
plt.ylabel('Number of New Questions')
plt.grid(True)
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
```

Oh man, that is a massive drop off.

I shared the pic on twitter.

{{< twitter user="jason2brownlee" id="1877054113340358707" >}}

Henk Poley picked it up and ran with it plotting the data and drop off in new questions in all kinds of great ways.

For example:

{{< twitter user="HenkPoley" id="1877087567985754211" >}}

Interesting days ahead for user-generated content. For technical/programming blog posts.

Not sure where this goes.