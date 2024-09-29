# Assignment3SNA

GitHub : https://github.com/TheJojoJoseph/Assignment3SNA/blob/main/Assignment3SNA.ipynb

DataSet :https://figshare.com/articles/dataset/Datasets_Politicsuk_Olympics_Karate_Dolphins_Football_Polbooks_Polblogs_/4993895?file=8410949


### Implementation Steps of the InfoNode Algorithm
1.
Step 1: Seed Selection :
a) Find local degree central nodes as seed candidates.
b) Compute Jaccard coefficients between each seed node and its neighbouring nodes.
c) Normalize the value of the Jaccard coefficient and pick the seeds using a threshold (ε).
Step 2: Community Extension.
a) Find neighbourhood nodes for each selected seed.
b) Calculate internal forces between each seed and its neighbour nodes.
Start using the fitness function to iteratively add nodes to the community of the seed to maximize internal cohesion or the fitness value of the community.
3. Pre-Extension Stage
Determine the top k nodes in terms of the fitness function in the pre-extension stage to optimize the process of expanding the community.
4. Community Labeling
Once the communities have been extended, label the nodes to identify the detected communities.
5. Comparative Evaluation
Calculate the NMI of the extracted communities by comparing algorithm output with ground truth.
Also, calculate the NMI of the GN algorithm for comparison of performance.
Datasets for Experimenting:
Select three datasets from the paper that have community labels. Here are three that could be utilized:
• Karate Club Dataset: It is one of the most classic datasets used in the study of community detection with clearly defined communities of two.
• Dolphins Social Network: It contains two overlapping communities of dolphins.
• Polbooks: It is a political book network that is divided into three well-known communities.
1. Karate Club Dataset:
Description: Karate Club Data Set This is a small social network with 34 nodes and 78 edges. This network consists of club members as nodes, with the edges representing interaction. Two communities formed the ground truth, meaning in this case that a split between a group resulted from a conflict.
2. Dolphins Social Network
• Description: This social interaction dataset is about 62 dolphins. It has 159 edges, where there exist two overlapping communities that the dolphins are associated with.
3. Polbooks Dataset:
• Description: This dataset contains information related to books sold on Amazon based on a political subject during the U.S. presidential election of 2004. The 105 nodes are books, and the edges refer to the edges of frequent co-purchases that exist amongst books. There are three communities liberal, conservative, and neutral books these books are spread amongst them.
Algorithm Comparison Steps:
1. Run the InfoNode Algorithm:
follows the steps described above
 computes NMI values for each community detected and corresponding communities in the ground truth for every dataset
2. Run the Girvan Newman Algorithm:
 This is the original Girvan Newman (GN) algorithm that removes, recursively, the edges with the highest betweenness centrality to split the network into communities.
o computation of the NMI for the same datasets for the GN algorithm
3.
Comparison:
Compare the results obtained from NMI values both for InfoNode and GN algorithms with those in the paper.
Observations:
•Accuracy: Compare the NMI scores you obtained from both algorithms with those that have been reported in this paper for the same datasets. Discuss whether InfoNode does better in terms of accuracy (i.e., NMI) compared to GN since it should be able to handle overlapping communities more effectively.
•Efficiency: Comment on the time complexity and efficiency of InfoNode, especially in seed selection and community extension phases.
•Community Structure: The communities found by InfoNode and GN have structural differences. GN often finds non-overlapping communities whereas InfoNode is expected to be superior for overlapping communities (e.g., in the Dolphins dataset).
InfoNode Algorithm Python Code

The InfoNode algorithm can be implemented in Python using libraries like NetworkX. Here is a general structure of the algorithm.
