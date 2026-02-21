### Enlaces para la clase 2

#### 1. Fundamentos de redes neuronales (Perceptrón/MLP/activaciones/pérdidas)

* **PyTorch - Build the Neural Network** (MLP, `Linear`, `ReLU`, estructura base) ([PyTorch Docs][1])
* **PyTorch - `torch.nn` (documentación general)** (capas, activaciones, losses, normalización, etc.) ([PyTorch Docs][2])
* **Dive into Deep Learning - Multilayer Perceptrons (MLP)** ([D2L AI][3])
* **PyTorch - `CrossEntropyLoss`** ([PyTorch Docs][4])
* **PyTorch - `BCEWithLogitsLoss`** ([PyTorch Docs][5])

#### 2. Entrenamiento, retropropagación y gradientes

* **PyTorch - Automatic Differentiation with `torch.autograd`** ([PyTorch Docs][6])
* **PyTorch - A Gentle Introduction to `torch.autograd`** ([PyTorch Docs][7])
* **Pascanu et al. (2012) - On the difficulty of training RNNs** (vanishing/exploding gradients) ([arXiv][8])
* **Bengio et al. (1994) - Learning Long-Term Dependencies with Gradient Descent is Difficult** (referencia clásica; ver nota de disponibilidad abajo) ([dl.acm.org][9])
* **Hochreiter - Gradient Flow in Recurrent Nets** (muy útil como lectura complementaria de contexto) ([bioinf.jku.at][10])

#### 3. Regularización y generalización (L2, dropout, normalización, early stopping)

* **Dropout (Srivastava et al., JMLR 2014)** - página del paper ([Journal of Machine Learning Research][11])
* **Batch Normalization (Ioffe & Szegedy, 2015)** ([arXiv][12])
* **Keras - EarlyStopping** (muy clara para entender `patience`, `monitor`, `min_delta`) ([Keras][13])
* **Layer Normalization** (clave para Transformers/LLMs) ([arXiv][14])
* **GELU (Gaussian Error Linear Units)** (activación común en BERT/LLMs) ([arXiv][15])

#### 4.  Optimizadores modernos y programación de tasa de aprendizaje

* **Adam (Kingma & Ba, 2014)** ([arXiv][16])
* **AdamW / Decoupled Weight Decay Regularization** ([arXiv][17])
* **PyTorch - `torch.optim.SGD`** (incluye momentum; útil para comparar con Adam/AdamW) ([PyTorch Docs][18])
* **PyTorch - `torch.optim.AdamW`** ([PyTorch Docs][19])

#### 5.  Limitaciones de RNN/LSTM y motivación para la atención

* **Bahdanau et al. (2014) - Neural Machine Translation by Jointly Learning to Align and Translate**. (atención en seq2seq) ([arXiv][20])
* **Vaswani et al. (2017) - Attention Is All You Need** ([arXiv][21])

#### 6. Tutoriales de Transformers (arquitectura + código)

* **The Illustrated Transformer (Jay Alammar)** (visual, excelente para clase) ([Jay Alammar][22])
* **The Annotated Transformer (Harvard NLP)**  ([Harvard NLP][23])
* **Hugging Face LLM Course - How Transformers solve tasks** ([Hugging Face][24])
* **Hugging Face Transformers - Fine-tuning** ([Hugging Face][25])

#### 7.  Papers clave de LLMs (ruta mínima)

* **BERT (2018)** ([arXiv][26])
* **GPT-3 / Language Models are Few-Shot Learners (2020)** ([arXiv][27])
* **Llama 2 (2023)** ([arXiv][28])
* **Scaling Laws for Neural Language Models** ([arXiv][29])
* **Chinchilla / Training Compute-Optimal Large Language Models** ([arXiv][30])
* **InstructGPT (RLHF)** ([arXiv][31])
* **LoRA** ([arXiv][32])
* **QLoRA** ([arXiv][33])
* **FlashAttention** ([arXiv][34])

[1]: https://docs.pytorch.org/tutorials/beginner/basics/buildmodel_tutorial.html "Build the Neural Network - PyTorch Tutorials 2.10.0+cu128 documentation"
[2]: https://docs.pytorch.org/docs/stable/nn.html "torch.nn - PyTorch 2.10 documentation"
[3]: https://d2l.ai/chapter_multilayer-perceptrons/mlp.html "5.1. Multilayer Perceptrons - Dive into Deep Learning 1.0.3 documentation"
[4]: https://docs.pytorch.org/docs/stable/generated/torch.nn.CrossEntropyLoss.html "CrossEntropyLoss - PyTorch 2.10 documentation"
[5]: https://docs.pytorch.org/docs/stable/generated/torch.nn.BCEWithLogitsLoss.html "BCEWithLogitsLoss - PyTorch 2.10 documentation"
[6]: https://docs.pytorch.org/tutorials/beginner/basics/autogradqs_tutorial.html "Automatic Differentiation with torch.autograd - PyTorch Tutorials 2.10.0+cu128 documentation"
[7]: https://docs.pytorch.org/tutorials/beginner/blitz/autograd_tutorial.html "A Gentle Introduction to torch.autograd - PyTorch Tutorials 2.10.0+cu128 documentation"
[8]: https://arxiv.org/abs/1211.5063 "[1211.5063] On the difficulty of training Recurrent Neural Networks"
[9]: https://dl.acm.org/doi/10.1109/72.279181 "Learning long-term dependencies with gradient descent is ..."
[10]: https://www.bioinf.jku.at/publications/older/ch7.pdf "ch7.dvi"
[11]: https://www.jmlr.org/papers/v15/srivastava14a.html "Dropout: A Simple Way to Prevent Neural Networks from Overfitting"
[12]: https://arxiv.org/abs/1502.03167 "[1502.03167] Batch Normalization: Accelerating Deep Network Training by Reducing Internal Covariate Shift"
[13]: https://keras.io/api/callbacks/early_stopping/ "EarlyStopping"
[14]: https://arxiv.org/abs/1607.06450 "[1607.06450] Layer Normalization"
[15]: https://arxiv.org/abs/1606.08415 "[1606.08415] Gaussian Error Linear Units (GELUs)"
[16]: https://arxiv.org/abs/1412.6980 "[1412.6980] Adam: A Method for Stochastic Optimization"
[17]: https://arxiv.org/abs/1711.05101 "[1711.05101] Decoupled Weight Decay Regularization"
[18]: https://docs.pytorch.org/docs/stable/generated/torch.optim.SGD.html "SGD - PyTorch 2.10 documentation"
[19]: https://docs.pytorch.org/docs/stable/generated/torch.optim.AdamW.html "AdamW - PyTorch 2.10 documentation"
[20]: https://arxiv.org/abs/1409.0473 "[1409.0473] Neural Machine Translation by Jointly Learning to Align and Translate"
[21]: https://arxiv.org/abs/1706.03762 "[1706.03762] Attention Is All You Need"
[22]: https://jalammar.github.io/illustrated-transformer/ "The Illustrated Transformer - Jay Alammar - Visualizing machine learning one concept at a time."
[23]: https://nlp.seas.harvard.edu/2018/04/03/attention.html "The Annotated Transformer"
[24]: https://huggingface.co/learn/llm-course/en/chapter1/5 "How  Transformers solve tasks - Hugging Face LLM Course"
[25]: https://huggingface.co/docs/transformers/en/training "Fine-tuning"
[26]: https://arxiv.org/abs/1810.04805 "[1810.04805] BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding"
[27]: https://arxiv.org/abs/2005.14165 "[2005.14165] Language Models are Few-Shot Learners"
[28]: https://arxiv.org/abs/2307.09288 "[2307.09288] Llama 2: Open Foundation and Fine-Tuned Chat Models"
[29]: https://arxiv.org/abs/2001.08361 "[2001.08361] Scaling Laws for Neural Language Models"
[30]: https://arxiv.org/abs/2203.15556 "[2203.15556] Training Compute-Optimal Large Language Models"
[31]: https://arxiv.org/abs/2203.02155 "[2203.02155] Training language models to follow instructions with human feedback"
[32]: https://arxiv.org/abs/2106.09685 "[2106.09685] LoRA: Low-Rank Adaptation of Large Language Models"
[33]: https://arxiv.org/abs/2305.14314 "[2305.14314] QLoRA: Efficient Finetuning of Quantized LLMs"
[34]: https://arxiv.org/abs/2205.14135 "[2205.14135] FlashAttention: Fast and Memory-Efficient Exact Attention with IO-Awareness"
[35]: https://www.comp.hkbu.edu.hk/~markus/teaching/comp7650/tnn-94-gradient.pdf "Learning long-term dependencies with gradient descent is ..."
