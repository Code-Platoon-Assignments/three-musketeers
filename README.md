# 📝 **NLP Assignment: Processing *The Three Musketeers* with Python and NLTK**

## 📌 **Objective**

In this assignment, you will apply essential NLP techniques to the text of *The Three Musketeers* using Python and the NLTK library. Your goal is to process and analyze the text step-by-step, preparing it for deeper linguistic analysis.

---

## 📚 **Tools You Will Use**

* `re` (Python's Regular Expressions)
* `nltk.tokenize.word_tokenize`, `nltk.tokenize.sent_tokenize`
* `nltk.corpus.stopwords`
* `nltk.pos_tag`
* `nltk.stem.WordNetLemmatizer`
* `nltk.RegexpParser`
* `collections.Counter`

---

## 🛠 **Tasks**

### 1️⃣ **Noise Removal**

* Use **regular expressions** to clean the raw text.
* Focus on removing:

  * Numbers
  * Special characters (except periods that mark sentence ends)
  * Extra whitespace
* Think about which `re` functions (e.g., `re.sub`, `re.findall`, `re.search`, `re.match`) will help you identify and replace/remove these patterns.

---

### 2️⃣ **Sentence and Word Tokenization**

* First, split the cleaned text into **sentences** using `nltk.tokenize.sent_tokenize`.
* Then, break each sentence into **words** using `nltk.tokenize.word_tokenize`.

---

### 3️⃣ **Stop Words Removal**

* Load the English stop words from `nltk.corpus.stopwords`.
* Filter out stop words from your tokenized word list.
* Consider whether you want to apply this step to **all words**, or selectively depending on the type of analysis.

---

### 4️⃣ **POS Tagging**

* Apply `nltk.pos_tag` to your list of word tokens.
* This will assign part-of-speech tags (e.g., noun, verb) to each word.
* Keep track of both the word and its tag for the next steps.

---

### 5️⃣ **Lemmatization**

* Initialize a `WordNetLemmatizer`.
* Lemmatize each word using its POS tag (you may need to convert NLTK tags to WordNet-compatible tags).
* This will reduce words to their base or dictionary form (e.g., *running* → *run*).

---

### 6️⃣ **Chunking**

* Write chunking patterns using `nltk.RegexpParser` to identify:

  * **Noun Phrases** (e.g., determiner + adjectives + noun)
  * **Verb Phrases** (optional)
* Apply your chunk parser to your tagged tokens.
* Inspect and print the resulting chunks to see which phrases were found.

---

### 7️⃣ **Finding Top 10 Most Common Phrases**

* Your goal is to **identify the top 10 most common Noun Phrases (NP)** or **Verb Phrases (VP)** found in the text.
* After chunking, extract these phrases from your chunk trees.
* Use `collections.Counter` to:

  * Count how many times each phrase appears in the text.
  * Identify and return the top 10 most frequent phrases of the type you choose (Noun Phrases or Verb Phrases).
* **Write a function** that:

  1. Takes a list of chunked trees.
  2. Extracts phrases that match a given label (e.g., `"NP"` or `"VP"`).
  3. Returns the top 10 most common phrases as a list of tuples: `[(phrase_string, count), ...]`.
* Display the results in a readable format (e.g., phrase text and frequency).
