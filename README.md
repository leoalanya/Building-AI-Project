<!-- This is the markdown template for the final project of the Building AI course, 
created by Reaktor Innovations and University of Helsinki. 
Copy the template, paste it to your GitHub README and edit! -->
# SpiritQuest
Final project for the Building AI course

![image](https://github.com/leoalanya/Building-AI-Project/assets/106389334/5f56cf31-aea9-428f-aa1e-bf57792dff36)

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

![image](https://github.com/leoalanya/Building-AI-Project/assets/106389334/227fbfbf-2a53-4eb2-81a3-b4d821c51426)

### Engagement and Community Building:
7. Connection: Users can explore and connect with like-minded individuals and communities through the platform. SpiritQuest acts more as a launching path for spiritual exploration rather than the actual platform. Spiritual communities may be registered, but users are directed towards third party platforms such as discussion forums, social media pages, physical addresses etc.. 

### Continuous Improvement:
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

![image](https://github.com/leoalanya/Building-AI-Project/assets/106389334/0ba346ba-d758-4716-b0b7-90b616e0ecd4)


## Data sources and AI methods

### Data Sources:

1. User Input: The primary source of data comes from users' responses to interactive questionnaires and reflective writing exercises. These inputs provide insights into their values, preferences, and personal experiences.
2. As training data, we use surveys of spiritually engaged people, who take our questionnaires and rate their experiences (X). We then ask them what communities and practices they are engaged in (y). 
3. Community Engagement: User interactions within the platform's discussion forums, event attendance, and community connections provide valuable data on their engagement and interests.
4. Resource Usage: Tracking the resources users access (books, podcasts, videos) helps refine recommendations and understand their preferred learning formats.

### AI Methods

1. Natural Language Processing (NLP): NLP techniques are used to analyze users' written responses from the reflective writing exercises. This helps identify patterns, sentiments, and themes in their personal reflections.
2. Machine Learning Algorithms: Machine learning algorithms, including collaborative filtering and content-based filtering, are employed to generate personalized recommendations based on users' input, behaviors, and preferences.
3. Psychological Framework - Big Five Model: Incorporating the Big Five personality traits (Openness, Conscientiousness, Extraversion, Agreeableness, Neuroticism) adds a psychological dimension to the recommendations. These traits are determined in our questionaire. This helps alig recoomendations with users' personality traits and psychological profiles.
4. Community Detection Algorithms: To enhance community engagement, AI algorithms identify potential matches between users based on shared interests, location, and practices. With mutual consent, matches can communicate about possibly exploring practices and communities together.
5. Feedback Loop Integration: User feedback on recommended practices, resources, and community experiences is analyzed using sentiment analysis and thematic analysis. This feedback loop helps the AI system refine its recommendations over time.
6. Progress Tracking: The platform could implement progress tracking to monitor users' engagement and growth in their spiritual journey. Specifically, activity logs, engagement patterns and feedback contribute to the platform's ability to adapt and suggest new experiences.

### Core Methods

Let's go into more detail on the technical implementation of some of the AI methods used by SpiritQuest. 

#### Reccomendation algorithm

The central functionality of SpiritQuest is reccomending practices and communities based on questionaires and writing exercises. The main algorithm used is collaborative filtering. Collaborative filtering relies on the principle of user behavior similarity. It recommends items based on the preferences and actions of similar users. Initially, we use surveys of spiritually engaged people for training data, who take our questionnaires and rate their experiences (X). We then ask them what communities and practices they are engaged in (y). 

Once we have enough user engagement, we use the following colaborative filtering algorithm. 

1. User-Item Interaction Matrix: Create a matrix where rows represent users and columns represent spiritual practices, resources, and communities. Entries in the matrix indicate user interactions, such as ratings, clicks, or participation.
2. User Similarity Calculation: Calculate the similarity between users based on their interactions. Common similarity metrics include cosine similarity or Pearson correlation.
3. Neighborhood Selection: Identify a subset of similar users to the target user. This subset is known as the "neighborhood."
4. Item Selection: Recommend items that the neighborhood users have interacted with but that the target user has not yet engaged with. These are items that the target user might find interesting based on the behavior of similar users.

Additionally, content-based filtering involves the following steps:

1. Item Profile Creation: Each spiritual practice, resource, or community is characterized by attributes such as type (meditation, yoga, discussions), keywords, and themes.
2. User Profile Creation: Construct a user profile based on their preferences, as inferred from their responses to questionnaires and writing exercises. These preferences are translated into relevant attributes.
3. Feature Vector Representation: Convert the item profiles and user profiles into numerical feature vectors, where each attribute is assigned a weight based on its importance.
4. Similarity Calculation: Calculate the similarity between the user profile and item profiles using techniques like cosine similarity or Jaccard index.
5. Recommendation: Recommend items that are most similar to the user's profile. These are items that align with the user's indicated preferences and interests.

Hybrid Approach: The hybrid recommendation system combines the collaborative filtering and content-based filtering outputs to provide more accurate and diverse recommendations. It mitigates some of the limitations of each individual method, such as the cold start problem (lack of initial user interactions) in collaborative filtering and the inability to capture new interests in content-based filtering.

**Example:**

```python
import numpy as np
from sklearn.metrics.pairwise import cosine_similarity

# COLLABORATIVE FILTERING

# Each row of the matrix corresponds to a user, and each column corresponds to a specific item (practice, resource, or community).
# 0 and 1 indicate wheter the user has engaged with the item.
interaction_matrix = np.array([[1, 0, 1, 0, 1],
                               [0, 1, 0, 1, 0],
                               [1, 1, 0, 0, 0]])

user_similarities = cosine_similarity(interaction_matrix) # A matrix of user similarities where each element [i, j] represents the similarity between user i and user j
user_neighborhood = np.argsort(user_similarities[0])[::-1][1:2]  # Identifies the neighborhood of similar users to the first user (index 0) and selects the top similar user. 

# CONTENT BASED FILTERING

# Each row corresponds to a specific spiritual practice, resource etc.. 
# Each column represents an attribute of the corresponding item. (The type of practice, keywords, themes, format etc.)
item_attributes = np.array([[1, 1, 0, 0],
                            [0, 1, 1, 0],
                            [1, 0, 1, 1],
                            [0, 0, 1, 1],
                            [1, 0, 0, 1]])

# Sample user preferences. Values indicate the importance of a specific attribute for the user.
user_preferences = np.array([0.8, 0.5, 0.3, 0.2])

# Calculates the similarity between item attributes (rows) and the user's preferences (represented as a vector). It generates a similarity score for each item with respect to the user's preferences.
content_similarities = cosine_similarity(item_attributes, [user_preferences]) 
content_recommendations = np.argsort(content_similarities[:, 0])[::-1] # ranks the items based on their similarity to the user's preferences


# HYBRID RECOMMENDATION

# This score reflects the similarity of the user to the top similar user and the content similarity of items to the user's preferences.
hybrid_scores = user_similarities[0][user_neighborhood] * content_similarities[:, 0]
hybrid_recommendations = np.argsort(hybrid_scores)[::-1]

# Print recommendations
print("Collaborative Filtering Recommendations:", user_neighborhood)
print("Content-Based Filtering Recommendations:", content_recommendations)
print("Hybrid Recommendations:", hybrid_recommendations)
```

#### Community detection algorithm

To enhance community engagement, AI algorithms identify potential matches between users based on shared interests, location, and practices. K-means clustering can be used to create groups of similar users based on their preferences and interactions. Here's a simple Python example demonstrating how K-means clustering might be used in the context of the SpiritQuest recommendation system:

```python
import numpy as np
from sklearn.cluster import KMeans

# Sample user-item interaction matrix 
# Each row of the matrix corresponds to a user, and each column corresponds to a specific item (practice, resource, or community).
# 0 and 1 indicate wheter the user has engaged with the item.
interaction_matrix = np.array([[1, 0, 1, 0, 1],
                               [0, 1, 0, 1, 0],
                               [1, 1, 0, 0, 0],
                               [0, 1, 1, 0, 1],
                               [1, 0, 0, 1, 0]])

# Apply K-means clustering
num_clusters = 3
kmeans = KMeans(n_clusters=num_clusters, random_state=0)
user_clusters = kmeans.fit_predict(interaction_matrix)

# Print user clusters
for user_id, cluster_id in enumerate(user_clusters):
    print(f"User {user_id + 1} belongs to Cluster {cluster_id + 1}")
```








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
