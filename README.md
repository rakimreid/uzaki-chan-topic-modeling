<div align = "center">
     <h1>Uzaki-chan Wants to Hang Out! Seasons 1 and 2 Topic Modeling</h1>
 
<img src = "https://www.gamenguides.com/wp-content/uploads/2020/08/uzaki-chan-wants-to-hang-out-0829.jpg" />
</div>


<h2>Background</h2> 

Uzaki-chan Wants to Hang Out! is a Japanese manga series published since December 2017. The anime adaptation first aired from July to September 2020. The second season aired from October to December 2022. 

Topic modeling was done on the transcription for both seasons using Gensim and pyLDAvis in Python. 

<h2> Part I: Data Cleanup and Exploratory Data Analysis <img src ="https://th.bing.com/th/id/OIP.j5Vj7VYXdSuB0Cho-HbMpgHaHa?pid=ImgDet&rs=1" height = 25, width = 25 />

</h2>

<h3>Data Cleanup</h3>

I removed about 63 words beyond NLTK's stop word list -- adverbs and casual words like 'cuz and already -- to improve the topic models revelancy. The initial word cloud prior to removing these words is below. The anime contains casual words and filler phrases throughout the series. 

<b>Initial Word Cloud</b>

![image](https://github.com/rakimreid/uzaki-chan-topic-modeling/assets/23224784/818a875d-3779-47b2-a58f-c6343b35a496)

<h3>Data</h3> 

The dataset comes from recorded audio from season 1 and 2 of the series. The audio was processed to text in Temi. Then I edited each episode file generated. All the episode transcriptions were combined into one text file for analysis. 

Afterwards, I ran an analysis of season 1 only to see how the topic modeling performed on a single season.  

<h2> Part II: Topic Modeling

<img src ="https://th.bing.com/th/id/OIP.4u9QjWljrMuY5CL7nGzRkQHaFj?w=273&h=205&c=7&r=0&o=5&dpr=1.3&pid=1.7" height = 25, width = 25 />
</h2>
     
Final Topics and most common words in each topic:

![image](https://github.com/rakimreid/uzaki-chan-topic-modeling/assets/23224784/0717bae6-74e7-47f0-943d-5c0ffba05d97)

The first five topics are the most relevant for season 1: 

1) Refers to Hana Uzaki's and Sakurai's interactions.
2) Hana talking about her time with Sakurai in college.
3) Hana discussing her next activity with Sakurai.
4) Hana and Sakurai having fun -- likely playing video games.
5) Hana talking about -- probably mocking -- Sakurai for doing activities solo instead of with friends. 
     
The first three topics are the most relevant for both seasons in the combined file: 

1) Sakurai visiting Hana to cook with Hana's mom. 
2) Hana Uzaki takes action - helping and laughing with Sakurai
3) Sakurai discusses completing his day or going out with Hana.      
4) Hana Uzaki offers her impression -- including first impression -- of Sakurai


<h2>Challenges</h2>

* Choosing a single season to develop topics and conduct text analysis may yield better and more relevant results.
* Developing topic models for conversation may be difficult particularly if relying on stop word list.
* Performing topic modeling on anime text requires an in-depth knowledge of the series to accurately label topics. 

<h2>Evaluation & Future Project Ideas 
<img src ="https://th.bing.com/th/id/R.b8644db24930cf9363566896d5253aec?rik=7SL6mGoqlQ0TNQ&riu=http%3a%2f%2fmedia.istockphoto.com%2fvectors%2fsaturn-vector-id165600450%3fk%3d6%26m%3d165600450%26s%3d612x612%26w%3d0%26h%3drEvVMsd4l40ib7bcrQzr1TzjkbLgRpcYPYGpYhJ9Nxo%3d&ehk=KabbCN8zzWnhbNSUIRMIS8eS0lrYNF2gRndPFaAxmOg%3d&risl=&pid=ImgRaw&r=0" height = 25, width = 25 />
</h2> 

Topic modeling is a bit tricky using anime conversation and text. Personally, better results came from Pointwise Mutual Information Collocation (PMI) and RAKE algorithm extracted "topics" aka keywords better than gensim/pyLDAvis. This may be because gensim/pyLDAvis require intense text cleanup to get better results. This analyst suspects keyword extraction algorithms likely do a better job at identifying topics (e.g. udpipe in R) than unsupervised topic modeling in gensim/pyLDAvis. With that said, udpipe performs a variety of text prep to get the keywords. The individual sentences matter less than the whole theme presented in the anime season or series.  

This also makes me wonder if there are particular keywords slipped into characters' speech that may predict a series' success. 

<h2>Part III: BERTopic Analysis</h2>

Recent advances in natural language processing (NLP) spurred my desire to see how contemporary deep learning Python libraries would perform on the Season 1 and Season 2 text file. 
The topics were much more accurate than in the Gensim and pyLDAvis work. Stop words and meaningless words disappeared. Keywords and topics revealed themselves. The image below shows the BERTopic generated 
topics. 

<img width="1000" height="500" alt="BERTopic - Top 8 topics" src="https://github.com/user-attachments/assets/f9fa5cf6-caa0-45c3-b37c-5fe4249371f1" />




<h3>Future Projects</h3>

Future projects may:

* Look at season 2 on its own and compare to season 1.
* Incorporate future seasons into the dataset and compare/contrast them.
* Dashboard the results in Power BI or Tableau.
* Perhaps...a project where series keywords are labeled with a successful or not successful classifier. Classify an anime series on the presence of words in the series.



     

