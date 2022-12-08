## Recommendation System for Fashion Apparel
<p>A recommender system, or a recommendation system, is a subclass of information filtering system that provide suggestions for items that are most pertinent to a particular user.Typically, the suggestions refer to various decision-making processes, such as what product to purchase, what music to listen to, or what online news to read. Recommender systems are particularly useful when an individual needs to choose an item from a potentially overwhelming number of items that a service may offer.</p>
<p><b>Recommender Systems can be broadly classified into 3 types</b></p>
<li>Collaborative Filtering</li>
<li>Content-Based Filtering</li>
<li>Hybrid</li>
<br><p>This project demonstrates the Content-Based filtering, which are based on the description of an item and a profile of the user’s preferred choices. In a content-based recommendation system, features are used to describe the items, besides, a user profile is built to state the type of item this user likes. In other words, the algorithms try to recommend products that are similar to the ones that a user has liked in the past.</p>
<p>Although we do not have any kind of user profile data, we will use pretrained ResNet50 algorithm along side cosine simmilarity to find and recommend products which have visually similar features, such as the ones you see in shopping websites e.g. "Products that are similar to this"</p>
<p>Here we are basically creating a Fashion Embedding now this embedding can eventually be used to in ML algorithms with higher semantic quality and similarity between Objects. We will use embeddings to identify similar items, this information will be used to recommend similar content in RecSys.</p>

<h3><b>Now what is Embedding?</b></h3>
<p>An embedding is a relatively low-dimensional space into which you can translate high-dimensional vectors. Embeddings make it easier to do machine learning on large inputs like sparse vectors representing words. Ideally, an embedding captures some of the semantics of the input by placing semantically similar inputs close together in the embedding space. An embedding can be learned and reused across models.</p>
<p>So a natural language modelling technique like Word Embedding is used to map words or phrases from a vocabulary to a corresponding vector of real numbers. As well as being amenable to processing by learning algorithms, this vector representation has two important and advantageous properties:</p>
<li><b>Dimensionality Reduction</b>: It is a more efficient representation</li>
<li><b>Contextual Similarity</b>:  It is a more expressive representation</li><br>
<p>We can use the Embedding as input of the model, containing a reduced dimensionality but with much semantic information.</p>

<h3><b>ResNet Model</b></h3>
<p>Residual Network (ResNet) is one of the famous deep learning models that was introduced by Shaoqing Ren, Kaiming He, Jian Sun, and Xiangyu Zhang in their paper. The paper was named “Deep Residual Learning for Image Recognition” [1] in 2015. The ResNet model is one of the popular and most successful deep learning models so far.</p>
<li><b>Residual Blocks</b></li><br>
 <p>The problem of training very deep networks has been relieved with the introduction of these Residual blocks and the ResNet model is made up of these blocks.</p>
 <p>The problem of training very deep networks has been relieved with the introduction of these Residual blocks and the ResNet model is made up of these blocks.</p>
 <p>There is a direct connection that skips some layers of the model. This connection is called ’skip connection’ and is the heart of residual blocks. The output is not the same due to this skip connection. Without the skip connection, input ‘X gets multiplied by the weights of the layer followed by adding a bias term.</p>
 <p>Then comes the activation function, f() and we get the output as H(x)</p>
 <p><b>H(x)=f( wx + b ) or H(x)=f(x)</b></p>
 <p>Now with the introduction of a new skip connection technique, the output is H(x) is changed to</p>
 <p><b>H(x)=f(x)+x</b></p>
 <p>But the dimension of the input may be varying from that of the output which might happen with a convolutional layer or pooling layers. Hence, this problem can be handled with these two approaches:</p>
 <li>Zero is padded with the skip connection to increase its dimensions.</li>
 <li>1×1 convolutional layers are added to the input to match the dimensions. In such a case, the output is: <b>H(x)=f(x)+w1.x</b></li>
 <p>Here an additional parameter w1 is added whereas no additional parameter is added when using the first approach.</p>
 <p>These skip connections technique in ResNet solves the problem of vanishing gradient in deep CNNs by allowing alternate shortcut path for the gradient to flow through. Also, the skip connection helps if any layer hurts the performance of architecture, then it will be skipped by regularization.</p>
