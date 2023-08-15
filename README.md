<!-- This is the markdown template for the final project of the Building AI course, 
created by Reaktor Innovations and University of Helsinki. 
Copy the template, paste it to your GitHub README and edit! -->
# SpiritQuest
Final project for the Building AI course
## Summary
SpiritQuest is a comprehensive platform designed to assist individuals in discovering meaningful spiritual, religious, and fulfilling experiences that align with their unique preferences. By utilizing interactive questionnaires, writing exercises and your past activity, SpiritQuest provides tailored recommendations for practices, resources, and vibrant communities, both in virtual and physical settings. This platform addresses the contemporary challenges of spiritual emptiness and isolation prevalent in today's society.
## Background
Spiritual disconnection and the quest for meaning are increasingly common challenges in the modern world. The advent of the scientific and technological age have eroded traditional religious traditions, with mixed results. On the other hand, the spiritually curious  find themselves adrift in a sea of options without a clear path to fulfilling their needs. The fast-paced nature of modern life, coupled with the prevalence of digital technology, has led to a disconnection from traditional spiritual practices and communities.

## How is it used?
### Exploration and Discovery:
1. Questionnaires: Users engage in interactive questionnaires that delve into their values, interests, and spiritual inclinations. These questions help the AI system understand their unique needs. 

2. Reflective Writing: Users are encouraged to complete reflective writing exercises that encourage introspection and self-awareness. These exercises also assist the AI in gaining a deeper understanding of the user's aspirations and challenges.

### Personalized Recommendations:
4. Algorithm Analysis: The AI algorithm analyzes the responses from the questionnaires and reflective writing exercises to generate personalized recommendations.

6. Practices, Resources, and Communities: Based on the user's profile, SpiritQuest provides a list of recommended spiritual practices, resources (books, podcasts, videos), and communities (online forums, local groups) that align with their preferences.

### Engagement and Community Building:
7. Connection: Users can explore and connect with like-minded individuals and communities through the platform. SpiritQuest acts more as a launching path for spiritual exploration rather than the actual platform. Spiritual communities may be registered, but users are directed towards third party platforms such as discussion forums, social media pages, physical addresses etc.. 

Continuous Improvement:
8. Feedback Loop: As users engage with recommended practices and communities, they can provide feedback and insights on their experiences in the form of continuing questionnaires and writing exercises. This feedback helps SpiritQuest refine its recommendations and adapt to the user's evolving needs.

## Users & Considerations
SpiritQuest caters to individuals seeking meaningful spiritual experiences, regardless of their current level of engagement. This includes those who are new to exploring spirituality, as well as those looking to deepen their existing practices.

**Needs to Consider:**
* **Diverse Beliefs:** SpiritQuest must be sensitive to users' diverse beliefs, ensuring that recommendations and resources are inclusive and respectful of different spiritual paths.
* **Privacy and Security:** Users' personal information and responses should be securely managed, respecting their privacy and maintaining confidentiality.
* **Cultural Context:** The platform should take into account the cultural context and preferences of users from various backgrounds, offering recommendations that are relevant and respectful.
* **User Empowerment:** The platform should empower users to make their own decisions while offering guidance, avoiding any imposition of specific beliefs or practices. This is enforced by a diversity metric for reccommended practices and communities.
* **User Feedback:** The feedback mechanism should be user-friendly and transparant, encouraging users to provide insights on their experiences, allowing SpiritQuest to continuously enhance its recommendations and sensitivity to users' needs. 
* **User Education:** For those new to spiritual practices, the platform should provide educational resources and explanations to help users understand the terminology and concepts. This should include scientific and popular criticism of recommended practices and communities as well. 
* **Serendipitous discovery:** The platform can introduce users to new practices or ideas that might align with their evolving interests, but also that are novel in some ways. This serendipitous discovery encourages users to explore beyond their comfort zone and prevents the creation of reccomendation bubbles.










## Data sources and AI methods

### Data Sources:

1. User Input: The primary source of data comes from users' responses to interactive questionnaires and reflective writing exercises. These inputs provide insights into their values, preferences, and personal experiences.
2. Community Engagement: User interactions within the platform's discussion forums, event attendance, and community connections provide valuable data on their engagement and interests.
3. Resource Usage: Tracking the resources users access (books, podcasts, videos) helps refine recommendations and understand their preferred learning formats.

### AI Methods

1. Natural Language Processing (NLP): NLP techniques are used to analyze users' written responses from the reflective writing exercises. This helps identify patterns, sentiments, and themes in their personal reflections.
2. Machine Learning Algorithms: Machine learning algorithms, including collaborative filtering and content-based filtering, are employed to generate personalized recommendations based on users' input, behaviors, and preferences.
3. Psychological Framework - Big Five Model: Incorporating the Big Five personality traits (Openness, Conscientiousness, Extraversion, Agreeableness, Neuroticism) adds a psychological dimension to the recommendations. These traits are determined in our questionaire. This helps alig recoomendations with users' personality traits and psychological profiles.
4. Community Detection Algorithms: To enhance community engagement, AI algorithms identify potential matches between users based on shared interests, location, and practices. With mutual consent, matches can communicate about possibly exploring practices and communities together.
5. Feedback Loop Integration: User feedback on recommended practices, resources, and community experiences is analyzed using sentiment analysis and thematic analysis. This feedback loop helps the AI system refine its recommendations over time.
6. Progress Tracking: The platform could implement progress tracking to monitor users' engagement and growth in their spiritual journey. Specifically, activity logs, engagement patterns and feedback contribute to the platform's ability to adapt and suggest new experiences.


```
def main():
   countries = ['Denmark', 'Finland', 'Iceland', 'Norway', 'Sweden']
   pop = [5615000, 5439000, 324000, 5080000, 9609000]   # not actually needed in this exercise...
   fishers = [1891, 2652, 3800, 11611, 1757]
   totPop = sum(pop)
   totFish = sum(fishers)
   # write your solution here
   for i in range(len(countries)):
      print("%s %.2f%%" % (countries[i], 100.0))    # current just prints 100%
main()
```



Where does your data come from? Do you collect it yourself or do you use data collected by someone else?
If you need to use links, here's an example:
[Twitter API](https://developer.twitter.com/en/docs)
| Syntax      | Description |
| ----------- | ----------- |
| Header      | Title       |
| Paragraph   | Text        |
## Challenges
What does your project _not_ solve? Which limitations and ethical considerations should be taken into account when deploying a solution like this?
## What next?
How could your project grow and become something even more? What kind of skills, what kind of assistance would you  need to move on? 
## Acknowledgments
* list here the sources of inspiration 
* do not use code, images, data etc. from others without permission
* when you have permission to use other people's materials, always mention the original creator and the open source / Creative Commons licence they've used
  <br>For example: [Sleeping Cat on Her Back by Umberto Salvagnin](https://commons.wikimedia.org/wiki/File:Sleeping_cat_on_her_back.jpg#filelinks) / [CC BY 2.0](https://creativecommons.org/licenses/by/2.0)
* etc
