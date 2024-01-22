# Company About Us

This early project of mine was inspired by hearing about how different companies can be described as having different
types of cultures, and how to estimate them based on the companies website. 
Some thoughts of mine were if this could be automated and if it was really justified to say that there were 8 types of company culture
or whatever the number was. I also wanted to get some practice with some tools in Natural Language Processing (NLP) and building a dataset.

I picked a set of companies to get data on, the S&P 500, and used a table from wikipedia as a starting point. 
From there, I built a web-crawler (using beautiful-soup) to follow links in wikipedia to get to each company's home page. 
From there, I had a script to find and download each company's about us page. From there, I wrote a acript to scan for the relevant paragraph blocks, 
and merge them into a single spreadsheet with the text for each company. 
The most recent version of this pipeline successfully downloaded the relevant text from 215 of the 500 companies.

I applied several tools I had learned in a course on NLP to vectorize the text, apply k-means clustering, and produce word-cloud visualizations of the resulting clusters.
I was disappointed with the results, as most clustering's resulted it almost all entries in one cluster, and several one entry clusters.
I wanted to try and make the process of trying more options for clustering and quickly quantify the usefulness of the clustering. 
To this end, I took an idea commonly used in physics, that of entropy or information content, and defined a metric estimating the information gained in a clustering.
For example, a clustering where almost all entries are in a single cluster tells you very little, where I more balanced clustering should give you more information.
My plan was then to try the k-means clustering with different k options, and see which k-value resulted in the highest entropy.
However, it occured to me that increasing the k value might generally increase the range of entropy values that could be found, regardless of actual clusters.
So, I derived a new entropy function, scaled by the minimum and maximum possible entropy values for clustering, given the restrictions of clustering.

## Clustering Metric Study

To study whether the metric I devised was useful for studying clustering, I started a new notebook to create artificial clusters in n-dimensions and apply clustering algorithms.
I then applied the clustering entropy function to see if it was useful for identifying the 'correct' number of clusters.
I found that it did not work well in 2-dimenions, but it did seem to do well with a larget number of dimensions.
My suspicion is that this is related to the generally greater difficulty in separating clusters in fewer dimensions.

Some future work I am planning on for this is to apply the tf-idf tool for vectorizing text and to study the 'elbow' method for estimating a good number of clusters.
My hope is that with better filtering of the dataset and the tf-idf metric, I can produce more meaningful clusters.
I suspect the result of this will really correspond more with the industry the company is in rather than the company's culture. 

