# 🌍 Transformer Neural Machine Translation

> An end-to-end Neural Machine Translation (NMT) system implementing an Encoder–Decoder Transformer architecture using TensorFlow/Keras. The project demonstrates sequence-to-sequence learning, attention mechanisms, tokenization, positional embeddings, and autoregressive translation for English-to-Marathi sentence translation.

![Python](https://img.shields.io/badge/Python-3.x-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)
![NLP](https://img.shields.io/badge/NLP-Transformer-success)
![Deep Learning](https://img.shields.io/badge/Deep%20Learning-Sequence--to--Sequence-red)

---
 
# 📖 Project Overview

This project implements a complete Transformer-based Neural Machine Translation (NMT) pipeline using TensorFlow/Keras.

Rather than implementing only the Transformer layers, the project demonstrates the complete translation workflow:

- Dataset preparation
- Text vectorization
- Vocabulary generation
- Token & positional embeddings
- Transformer encoder
- Transformer decoder
- Multi-head attention
- Model training
- Greedy autoregressive inference

The implementation provides an educational, end-to-end view of how modern Transformer-based sequence-to-sequence models operate.

---

# 🎯 Problem Statement

Machine Translation aims to automatically convert text from one language into another while preserving semantic meaning.

Traditional recurrent sequence-to-sequence models struggle with long-range dependencies and limited parallelization.

This project addresses these limitations by implementing an Encoder–Decoder Transformer architecture based entirely on attention mechanisms.

---

# 🎯 Objectives

- Build a complete Transformer-based translation model
- Understand Encoder–Decoder interaction
- Learn attention-based sequence modeling
- Implement tokenization and vocabulary generation
- Train an end-to-end NMT model
- Generate translations using autoregressive decoding

---

# ✨ Features

- English → Marathi translation
- Encoder–Decoder Transformer
- Multi-Head Self-Attention
- Encoder–Decoder Attention
- Learned Token + Positional Embeddings
- Feed Forward Networks
- Layer Normalization
- Dropout Regularization
- Text Vectorization
- Vocabulary Generation
- Greedy sequence generation
- End-to-end TensorFlow/Keras implementation

---

# 🏗 High-Level Architecture

```text
English Sentence
        │
        ▼
Text Vectorization
        │
        ▼
Token IDs
        │
        ▼
Token + Position Embedding
        │
        ▼
Transformer Encoder
        │
        ▼
Encoder Context
        │
        ▼
Transformer Decoder
        │
        ▼
Dense + Softmax
        │
        ▼
Predicted Marathi Tokens
        │
        ▼
Generated Translation
```

---

# 📊 Data Pipeline

The implementation follows a simple supervised translation workflow:

1. Create paired English and Marathi sentences.
2. Add `start` and `end` tokens to target sequences.
3. Learn vocabularies using `TextVectorization`.
4. Convert text into token IDs.
5. Pad sequences to a fixed length.
6. Prepare encoder inputs, decoder inputs, and decoder targets.

---

# 🔤 Tokenization Pipeline

The project uses TensorFlow's `TextVectorization` layer.

The pipeline performs:

- Vocabulary learning
- Tokenization
- Integer encoding
- Sequence padding
- Fixed-length sequence generation

Separate vectorizers are created for:

- Source (English)
- Target (Marathi)

---

# 📚 Vocabulary Creation

Separate vocabularies are automatically learned for both languages.

The implementation also creates an index-to-word lookup dictionary used during inference to convert predicted token IDs back into words.

---

# 🤖 Transformer Architecture

The model consists of:

### Encoder

- Token Embedding
- Positional Embedding
- Multi-Head Self-Attention
- Feed Forward Network
- Residual Connections
- Layer Normalization

### Decoder

- Token Embedding
- Positional Embedding
- Masked Multi-Head Self-Attention
- Encoder–Decoder Attention
- Feed Forward Network
- Residual Connections
- Layer Normalization
- Softmax Output Layer

---

# 🔄 Encoder–Decoder Workflow

The Encoder processes the complete source sentence and generates contextual representations.

The Decoder then:

1. Receives previously generated target tokens.
2. Applies causal masking.
3. Attends to encoder outputs.
4. Predicts the next target token.
5. Repeats until the translation is complete or an end token is produced.

---

# 🎯 Attention Mechanism

The implementation demonstrates two types of attention:

### Self-Attention

Allows tokens within a sequence to attend to one another and capture contextual relationships.

### Encoder–Decoder Attention

Allows the Decoder to focus on relevant Encoder representations while generating translations.

---

# 🧠 Multi-Head Attention

The project uses TensorFlow's `MultiHeadAttention` layer.

Multiple attention heads enable the model to learn different contextual relationships simultaneously before combining the results.

---

# 📍 Positional Encoding

Since attention mechanisms do not inherently model sequence order, the project incorporates learned positional embeddings that are added to token embeddings before entering the Transformer layers.

---

# 🏋️ Training Workflow

Training follows the standard sequence-to-sequence paradigm:

1. Vectorize source and target sentences.
2. Shift target sequences to create decoder inputs and decoder targets.
3. Train using teacher forcing.
4. Optimize using Adam.
5. Minimize sparse categorical cross-entropy loss.

---

# 📈 Validation & Evaluation

The implementation reports:

- Training loss
- Training accuracy

The project does **not** implement BLEU score evaluation or a separate validation dataset, so no such metrics are claimed.

---

# 🔮 Inference Pipeline

During inference:

1. Encode the English sentence.
2. Initialize the decoder with the `start` token.
3. Predict one token at a time.
4. Append each predicted token to the decoder input.
5. Stop when the `end` token is generated or the maximum sequence length is reached.

This implements greedy autoregressive decoding.

---

# 🌐 Translation Workflow

```text
English Sentence
        │
        ▼
Text Vectorization
        │
        ▼
Transformer Encoder
        │
        ▼
Decoder initialized with "start"
        │
        ▼
Predict next word
        │
        ▼
Append prediction
        │
        ▼
Repeat until "end"
        │
        ▼
Final Marathi Translation
```

---

# 📂 Project Structure

```text
transformer-neural-machine-translation/

├── src/
│   └── transformer_machine_translation.py
│
└── README.md
```

---

# 🛠 Technologies Used

### Languages

- Python

### Frameworks

- TensorFlow
- Keras

### Libraries

- NumPy

---

# 🧠 NLP Concepts Demonstrated

- Neural Machine Translation
- Sequence-to-Sequence Learning
- Tokenization
- Vocabulary Generation
- Teacher Forcing
- Greedy Decoding
- Text Vectorization

---

# 🤖 Deep Learning Concepts Demonstrated

- Transformer Architecture
- Encoder–Decoder Networks
- Multi-Head Attention
- Self-Attention
- Masked Attention
- Feed Forward Networks
- Embedding Layers
- Positional Embeddings
- Layer Normalization
- Dropout

---

# 💻 Software Engineering Concepts Demonstrated

- Custom Keras Layers
- Modular Layer Design
- Pipeline-Based Workflow
- Reusable Components
- End-to-End Model Construction

---

# 📊 Results

The implementation demonstrates successful end-to-end model training and translation inference on the provided dataset.

No BLEU scores or external evaluation metrics are included in the project.

---

# 🌍 Sample Translations

The project includes inference on several example English sentences after training.

As the implementation uses a very small demonstration dataset, translation quality should be viewed as educational rather than production-ready.

---

# ▶️ Installation

```bash
pip install tensorflow numpy
```

---

# 🚀 Training

Run:

```bash
python src/transformer_machine_translation.py
```

The script performs:

- Dataset creation
- Vocabulary generation
- Model construction
- Training
- Translation inference

---

# 🔍 Evaluation

Evaluation currently consists of observing training metrics and generated translations.

---

# 🌐 Inference

The project exposes a translation function that performs greedy autoregressive decoding to generate translated sentences from English input.

---

# 🚀 Future Improvements

Potential enhancements include:

- Larger multilingual datasets
- Validation dataset
- BLEU score evaluation
- Beam Search decoding
- Model checkpointing
- Configuration files
- Separate training and inference scripts
- GPU training support
- Model export for deployment
- REST API or web interface

---

# 📄 License

This project is intended for educational purposes.

---

# 👨‍💻 Author

**Niraj Vijaysinh Nale**

B.Tech in Robotics & Automation  
MIT World Peace University, Pune

Interested in Software Engineering, Backend Development, Artificial Intelligence, Deep Learning, and Natural Language Processing.

---

⭐ If you found this project useful, consider giving it a star.
