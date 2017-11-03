# YouTubeRecommendation
Predict the top 20 recommended videos using NetworkX and other methods

Training data contains 26901 videos' top 20 recommended videos. Testing data are constructed by removing portion of training data and adding fake pairs. The performance of the model is evaluated by area under the ROC curve.

There are 218344 videos (nodes), 466970 edges in traning data and 100000 edges in test data.

Project approaches:

Collect and visualize graph properties.
* Assume the top 20 recommended videos would have shorter path to the parent videos than other nodes. The prediction is done by setting a threshold the shortest path between test pairs.
* Bench mark by using undirected graph constructed from the training data, and calculate the shortest path bewteen each testing pairs.
* For the videos in testing data also exist in training data, perform shorttest parth to label the edge.
* For those edges are already exist in training data, label that edge 1
* For those target video exist in train data and shares the same category with source video and the target video's rate is higher than source video, label that edge 1
* For those target video exist in train[video_id] and shares the same uploader with source video, label that edge 1
