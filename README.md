# Similarity-Learning_Applications

What is Similarity Learning 

Similarity Learning involves training machine learning models to discern and quantify the similarities and dissimilarities among data points. This process entails transforming data points into vector representations. Subsequently, the model performs calculations on these vectors to evaluate their similarity. A common method is to measure the distance between pairs of data points; a smaller distance typically indicates greater similarity (for instance, calculating the Euclidean distance or cosine similarity between two vectors).
Unlike traditional supervised learning, which relies heavily on labeled data for training, Similarity Learning operates somewhat differently. It does not require a predefined labeling mechanism for learning purposes. Instead, it often employs a reference point or example as a basis for comparison. This approach allows the model to understand and gauge how similar or dissimilar a new data point is in relation to the reference point. This technique is particularly useful in applications where direct comparisons are more critical than categorizing data into predefined labels, such as in recommendation systems, anomaly detection, or image matching tasks

Methods of Similarity Learning

Cosine Similarity 


 ![cosine-similarity-vectors original](https://github.com/AmdPathirana/Similarity-Learning_Applications/assets/64656686/5395fceb-3831-4bc6-a652-3328f9d4cfc8)



Cosine similarity is a measure used in various fields including data analysis, information retrieval, and machine learning, to quantify the similarity between two vectors. It essentially measures the cosine of the angle between these two vectors. The key reasons for its use are:
1.	Independence from Magnitude: Cosine similarity focuses on the orientation of vectors, not their magnitude. This means that it considers the direction of the data points rather than their scale or length.
2.	Useful for Sparse Data: In high-dimensional spaces, such as text data represented as word vectors, cosine similarity is particularly useful because it is less affected by the dimensionality of the data.
The cosine similarity is calculated as follows:

<img width="237" alt="image" src="https://github.com/AmdPathirana/Similarity-Learning_Applications/assets/64656686/8a671c1f-2008-4cfc-ba5b-0ded20713af9">

•	Given two vectors, A and B, the cosine similarity, cos(θ), is represented by the dot product of A and B divided by the product of their magnitudes (or lengths).
The formula is:
 

Here, Ai and  Bi are components of vectors A and B respectively, and n is the dimension of the vectors.
In terms of interpretation:
•	If the cosine similarity is close to 1, it means the angle between the two vectors is small, indicating they are similar or have a high degree of similarity.
•	If it is around 0, the vectors are orthogonal, indicating no similarity.
•	If the value is close to -1, the vectors are diametrically opposed, suggesting they are very dissimilar



cosine similarity can be used for image comparison when dealing with simplified or abstracted representations of images (like color histograms or basic texture features), it's often not the best choice for more complex or nuanced image comparisons involving scale, rotation, and spatial distribution of objects 







Siamese networks

 <img width="394" alt="image" src="https://github.com/AmdPathirana/Similarity-Learning_Applications/assets/64656686/e17abcab-9b47-4801-a6ef-6ba8805f4c90">


A Siamese Network is a type of neural network architecture that is particularly effective in tasks that involve finding similarities or relationships between two comparable things. This architecture is especially popular in applications such as face recognition, signature verification, and similarity checking in general. Let's delve into its key characteristics:

Twin Networks: The term "Siamese" comes from the concept of conjoined twins. In this context, it refers to two identical sub-networks within the architecture. These sub-networks have the same configuration with the same parameters and weights. Weight sharing ensures that both sub-networks process their respective inputs similarly.

Input and Output: A Siamese Network takes in a pair of inputs, which are processed through these twin networks. The outputs are then compared to determine the relationship between the inputs. For example, in face verification, the inputs would be two different images, and the output would be a measure of how similar these images are.

Loss Function: Siamese Networks often use a specialized loss function, like the contrastive loss or triplet loss. These loss functions are designed to ensure that the network learns to differentiate between similar and dissimilar pairs effectively. For example, the contrastive loss will try to ensure that the network outputs high similarity for pairs of inputs that are similar and low similarity for pairs that are not.

Feature Extraction: Each sub-network in a Siamese Network acts as a feature extractor. They transform the raw input data (like images) into a more abstract representation (feature vector). The comparison is then made at this feature level.


Triplet Loss

<img width="266" alt="image" src="https://github.com/AmdPathirana/Similarity-Learning_Applications/assets/64656686/0eb063ed-7a9e-4b0f-a59a-e4ce59a5539d">

 

Triplet loss is a loss function used primarily in deep learning applications, particularly in the training of models that need to learn fine-grained similarities between examples, such as in face recognition or similarity learning tasks. It's most commonly associated with Siamese Networks and their variants. The goal of triplet loss is to ensure that an anchor example is closer to examples of the same class (positive examples) than to examples of different classes (negative examples) in the feature space.

 <img width="338" alt="image" src="https://github.com/AmdPathirana/Similarity-Learning_Applications/assets/64656686/e73a9b6a-a82f-4634-a495-dcf506dbe126">
 

Here's a breakdown of how triplet loss works:
1.	Triplet of Examples: In this context, a "triplet" refers to three items - an anchor (A), a positive example (P), and a negative example (N).
o	Anchor: A reference example.
o	Positive: Another example of the same class as the anchor.
o	Negative: An example of a different class.
2.	Objective of Triplet Loss: The goal is to learn feature representations such that the distance between the anchor and the positive example is smaller than the distance between the anchor and the negative example by some margin.
3.	The Triplet Loss Formula: The loss is defined mathematically as follows:
 
Here, d(A,P)d(A,P) is the distance between the anchor and the positive example, and d(A,N)d(A,N) is the distance between the anchor and the negative example. The "margin" is a hyperparameter that specifies the minimum distance between the negative and positive pairs.


4.	Distance Metric: The distance dd can be any metric, but in practice, it is often the Euclidean distance or cosine distance. The choice of metric can depend on the specific application and the nature of the input space.
5.	Training: During training, the network adjusts its weights to reduce the loss, which in turn ensures that the anchor and positive examples are brought closer together in the feature space, while the anchor and negative examples are pushed apart.
6.	Selection of Triplets: Effective training requires careful selection of triplets. Hard triplets, where the negative example is very similar to the anchor, or the positive example is quite different from the anchor, are often more informative for training.








