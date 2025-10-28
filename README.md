<H3>ENTER YOUR NAME</H3> Prem Kumar G
<H3>ENTER YOUR REGISTER NO.</H3> 212223230158
<H3>EX. NO.6</H3>
<H3>DATE:</H3> 28/10/2025
<H1 ALIGN =CENTER>Implementation of Semantic ANalysis</H1>
<H3>Aim: to perform Parts of speech identification and Synonym using Natural Language Processing (NLP) techniques. </H3> 
 <BR>
<h3>Algorithm:</h3>
Step 1: Import the nltk library.<br>
Step 2: Download the 'punkt', 'wordnet', and 'averaged_perceptron_tagger' resources.<br>
Step 3:Accept user input for the text.<br>
Step 4:Tokenize the input text into words using the word_tokenize function.<br>
Step 5:Iterate through each word in the tokenized text.<br>
•	Perform part-of-speech tagging on the tokenized words using nltk.pos_tag.<br>
•	Print each word along with its corresponding part-of-speech tag.<br>
•	For each verb , iterate through its synsets (sets of synonyms) using wordnet.synsets(word).<br>
•	Extract synonyms and antonyms using lemma.name() and lemma.antonyms()[0].name() respectively.<br>
•	Print the unique sets of synonyms and antonyms.
<H3>Program:</H3>

```
import nltk
from nltk.tokenize import word_tokenize
from nltk.corpus import wordnet

# Download necessary NLTK data
nltk.download('punkt')
nltk.download('wordnet')
nltk.download('averaged_perceptron_tagger')

# Input sentence
sentence = input("Enter a sentence: ")

# Tokenize the sentence
words = word_tokenize(sentence)

# Print the original sentence
print("\n", sentence)

# POS tagging
pos_tags = nltk.pos_tag(words)

# Print POS tags in the required format
print()
for word, tag in pos_tags:
    print(f"{word} {tag}")

# Identify synonyms and antonyms
synonyms = []
antonyms = []

for word in words:
    for syn in wordnet.synsets(word):
        for lemma in syn.lemmas():
            synonyms.append(lemma.name())
            if lemma.antonyms():
                antonyms.append(lemma.antonyms()[0].name())

# Print synonyms and antonyms
print("\nSynonyms :", set(synonyms))
print("Antonyms :", set(antonyms))

```

<H3>Output</H3>

<img width="1735" height="567" alt="Screenshot 2025-10-28 071929" src="https://github.com/user-attachments/assets/e558d58e-dbf5-41e3-959d-ae0fd5bf6ab5" />


<H3>Result:</H3>

Thus ,the program to perform the Parts of Speech identification and Synonymis executed sucessfully.
