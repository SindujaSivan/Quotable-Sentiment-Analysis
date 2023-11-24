# Problem Statement

<div style="text-align: justify;">

In the era of vast digital content, extracting meaningful insights from a diverse range of sources is crucial for understanding public sentiments and opinions. One valuable source of expressive content is quote websites, where individuals share their thoughts and perspectives on various aspects of life. The challenge lies in efficiently analyzing and visualizing the sentiments expressed by different authors in these quotes.
<br>
Our project aims to address this challenge by conducting sentiment analysis on a collection of quotes gathered from a prominent quote website. Through web scraping, we have obtained a dataset containing quotes along with their respective authors. The primary goal is to explore the sentiments conveyed by these authors and visualize the emotional tone of their quotes.

</div>
<br>
![Quote Scrape Image](assets/Quotes_Scrape.png)
<span style="font-size: 8pt; text-align: left; display: block;">*Picture reference: [Quotes to Scrape](https://quotes.toscrape.com/)*</span>

# Implementation

## 1. Web Scraping for Quote Analysis
<div style="text-align: justify;">
The first step involved web scraping from the target website [Quotes toscrape](http://quotes.toscrape.com) to collect a rich dataset of quotes along with relevant metadata. Utilizing the Python programming language and libraries such as requests and BeautifulSoup, we sent an HTTP request to the target URL and successfully retrieved the HTML content of the page. The subsequent steps involved parsing the HTML to extract quote-related information.
</div> 

### Quote Containers
<div style="text-align: justify;">
Located and extracted all the quote containers on the page using BeautifulSoup. Each container encapsulates a quote, its author, associated tags, and a link to additional details.
</div> 

### Data Extraction
<div style="text-align: justify;">
Extracted quote text, author name, tags, and link for each quote container. Organized the extracted data into lists for subsequent analysis and presentation.
</div> 

### DataFrame Creation
<div style="text-align: justify;">
Compiled the extracted data into a structured DataFrame using the Pandas library. The DataFrame includes columns for Quote, Tags, Link, and Author, providing a clear overview of the gathered information.
</div>

![Webscrapped Image](assets/webscrapped_data.png)

## 2. Feature Engineering 
<div style="text-align: justify;"> </div>
  
### Total Characters, Words, and Sentences  
<div style="text-align: justify;">  Calculated the total number of characters, words, and sentences for each quote.These metrics provide a quantitative understanding of the length and structure of the quotes.   </div>
    
### Stopword Count
<div style="text-align: justify;"> Determined the count of stopwords in each quote using the NLTK library.Stopwords are common words that may not contribute significant meaning and can be indicative of writing style.</div>
    
### Uppercase Words and Letters
<div style="text-align: justify;">Identified the count of uppercase words and individual uppercase letters in each quote.This feature sheds light on the use of emphasis and the presence of acronyms or proper nouns. </div>
      
### Words Starting with '@' (At the Rate)
<div style="text-align: justify;"> Quantified the occurrence of words starting with '@' in each quote.This is particularly relevant for identifying user mentions or references in social media-like contexts. </div>
        
### Hashtags,Numeric Characters & Punctuation Count
<div style="text-align: justify;"> 
- Counted the occurrence of words starting with '#' in each quote. Hashtags may indicate trending topics or thematic emphasis within the quotes. <br>
- Computed the count of numeric characters in each quote. <br>
- Useful for understanding the inclusion of numerical information in the quotes. <br>
- Calculated the count of punctuation marks in each quote.Punctuation analysis provides insights into writing style and the emotional tone of the quotes.
</div>
<br>
![featured Image](assets/featured_data.png)

## 3. Text Preprocessing and Advance analysis
In our ongoing effort to refine the dataset for sentiment analysis and insightful exploration, we implemented advanced text preprocessing techniques. Specifically, we focused on removing stopwords and conducted a comprehensive analysis of the updated text.

### Stopword Removal:
<div style="text-align: justify;"> 
- Utilized NLTK's list of English stopwords to remove common words that may not contribute significant meaning.
- Implemented a custom function to remove stopwords from each quote.
</div>

### Updated Quote Column:
<div style="text-align: justify;"> 
- Created a new column, 'Quote_Upd,' containing quotes after the removal of stopwords.
</div>

### Stopword and Uppercase Analysis After Preprocessing:
<div style="text-align: justify;"> 
- Calculated the count of stopwords, uppercase words, and uppercase letters in the updated quotes.
- This analysis provides insights into the impact of stopword removal on the composition of the quotes.
</div>

### Words Starting with '@' (At the Rate) and Hashtags After Preprocessing:
<div style="text-align: justify;"> 
- Quantified the occurrence of words starting with '@' and '#' in the updated quotes.
- This analysis reveals changes in social media-style content after stopword removal.
</div>

### Numeric Characters and Punctuation After Preprocessing:
<div style="text-align: justify;"> 
- Examined the count of numeric characters and punctuation marks in the updated quotes.
- This analysis highlights shifts in numerical information and punctuation usage.
</div> 
<br>
![featured after Image](assets/featured_aft_data.png)
