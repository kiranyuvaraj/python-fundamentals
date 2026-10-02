# Natural Language Processing (NLP)
## Understanding Text Processing & Word Embeddings

> Prepared from the uploaded presentation. The PDF is image-based, so this Markdown is a structured transcription and summary of readable slide content; some small labels and examples may be omitted where OCR was unclear.

## 1. NLP and its use cases

Natural Language Processing helps turn unstructured text into information that machines can process.

Common use cases:
- **Customer review sentiment analysis:** detect complaints and identify unhappy customers from negative feedback.
- **FAQ chatbots:** automatically suggest relevant answers from a knowledge base.
- **Social media monitoring:** identify trending topics across platforms.
- **Brand sentiment tracking:** understand how people feel about a brand.
- **Server log analysis and issue classification:** extract patterns, detect anomalies, and monitor system health.

## 2. Why text must be converted into numbers

Machines and machine-learning models do not understand raw language directly. They work with numerical features. NLP converts text into numerical representations (vectors), allowing models to find patterns in data.

Techniques introduced:
- **TF-IDF:** measures a word's importance in a document relative to a corpus.
- **Word2Vec:** learns word representations from context in large text corpora.
- **Embeddings:** dense vector representations that capture semantic meaning.

## 3. Text preprocessing

### Text cleaning
Typical cleaning steps:
1. Convert text to lowercase.
2. Remove punctuation.
3. Remove special characters.
4. Remove non-alphanumeric noise where appropriate.

Cleaning reduces noise and can improve model accuracy and pattern learning.

### Stop-word removal
Stop words are common words that may carry little meaning for a particular task. Removing them can reduce noise, improve efficiency, and focus processing on meaningful terms.

Examples shown include `a`, `the`, `is`, `an`, `this`, `that`, `and`, `to`, and `in`.

**Important:** stop words should not always be removed. Words such as **“not,” “no,” and “never”** can change meaning. Consider the task and context before filtering them.

### Stemming
Stemming reduces word forms to a root or base form, often by removing prefixes or suffixes.

Examples from the presentation:
- `studies` → `studi`
- `retrieved` → `retriev`
- `running` → `run` (illustrative normalization)

Benefits:
- Normalizes different forms of a word.
- Reduces vocabulary size.
- Improves feature consistency so models can learn patterns more easily.

The stem is not necessarily a valid dictionary word; the goal is to reach a form representing the core meaning.

## 4. Feature extraction

Feature extraction transforms cleaned text into numerical features that machine-learning models can use.

Common techniques:
- **Bag of Words (BoW) / Count Vectorizer:** represents text using word counts.
- **TF-IDF Vectorizer:** represents words using their importance in a document relative to the corpus.

A typical workflow is:

`Raw text → Cleaning → Stop-word removal → Stemming → Feature extraction → Numerical feature matrix`

The output is a document-term matrix:
- Rows represent documents.
- Columns represent terms/features.
- Cells contain counts or weights.

The choice of technique depends on the problem and dataset.

## 5. Bag of Words (BoW / Count Vectorizer)

Bag of Words represents a document as a collection of its words, ignoring grammar and word order.

How it works:
1. Collect the documents in a corpus.
2. Build a vocabulary of unique words.
3. Count each vocabulary word in each document.
4. Store the counts in a document-term matrix.

**Strengths**
- Simple, fast, and effective for many applications.
- Easy to implement.
- A useful baseline for NLP tasks.

**Limitations**
- Vocabulary grows as more documents and unique words are added.
- Produces high-dimensional, often sparse matrices.
- Can require substantial memory and computation.
- Ignores word order and context.
- Treats words such as “good” and “great” as unrelated features despite their similar meanings.

The presentation motivates moving from sparse word counts to dense embeddings that capture semantic relationships.

## 6. Word2Vec

Word2Vec is a family of models that learns word embeddings from large text corpora. It maps each word to a dense, fixed-size numerical vector.

Key ideas:
- Words used in similar contexts tend to have similar vectors.
- Semantically similar words are located near each other in vector space.
- Dense vectors can represent meaning and relationships more compactly than sparse count vectors.

Examples of related words shown include:
- `king` and `queen`
- `car` and `vehicle`
- `doctor` and `hospital`
- `cat`, `dog`, and `puppy`

Word vectors can be compared using **cosine similarity**. The presentation also illustrates word relationships and analogies, such as:

`king − man + woman ≈ queen`

Typical embedding sizes mentioned are **100, 200, or 300 dimensions**, depending on the use case and data.

### Word2Vec architectures

#### CBOW (Continuous Bag of Words)
CBOW predicts the center/target word from surrounding context words.

Basic flow:
1. Take context words around the target.
2. Look up their vectors.
3. Average the context vectors (as illustrated).
4. Predict the center word.

The presentation describes CBOW as generally faster to train than Skip-Gram and useful for frequent words.

#### Skip-Gram
Skip-Gram predicts surrounding context words from a center word.

The two architectures learn embeddings from word usage in context:
- **CBOW:** context → center word.
- **Skip-Gram:** center word → context words.

## 7. Word2Vec limitations

Word2Vec has a fixed learned vocabulary. A word not seen during training may be **out of vocabulary (OOV)** and have no available embedding.

Consequences:
- New or rare words may lose important information.
- Models can struggle to interpret sentences containing unknown terms.
- Chatbots, sentiment analysis, and text classification can be affected.

The presentation points to contextual models such as BERT and GPT as examples of approaches that can handle language more effectively in such situations.

## 8. FastText

FastText extends Word2Vec by representing words using **character n-grams (subwords)**.

Instead of relying only on a whole-word vector, it builds a word representation from its subword components. The presentation illustrates splitting a word such as `walking` into character fragments and combining their embeddings.

Benefits:
- Can generate representations for some words not seen as whole words during training.
- Learns subword and morphological information.
- Can generalize better for rare words and domain-specific terms.
- Is especially useful for morphologically rich languages and works across many languages.

FastText uses the same broad training architectures as Word2Vec:
- CBOW
- Skip-Gram

The word vector is computed from its n-gram vectors, helping preserve useful word-structure information.

## 9. Key takeaways

- NLP bridges human language and machine learning by converting text into numerical representations.
- Preprocessing may include cleaning, stop-word removal, and stemming; each step should be chosen with the task in mind.
- BoW is straightforward but ignores word order and semantic similarity and can create large sparse feature spaces.
- Word2Vec learns dense vectors from context using CBOW or Skip-Gram.
- Word2Vec can struggle with out-of-vocabulary words.
- FastText uses character n-grams to incorporate subword information and improve handling of rare or unseen word forms.

---
*Source: uploaded presentation `20418428-NLP.pdf` (18 pages).*
