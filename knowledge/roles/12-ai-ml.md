# AI/ML Engineer — Skill Framework

## Tổng quan
- **Tên role:** AI/ML Engineer
- **Level:** Junior → Mid → Senior → Lead
- **Mô tả:** Thiết kế, huấn luyện và triển khai các mô hình Machine Learning và Deep Learning. Xây dựng pipeline dữ liệu, tối ưu mô hình, deploy lên production. Làm việc với Python, các framework ML/DL, MLOps, và LLM/GenAI.
- **Tags:** machine-learning, deep-learning, ai, python, pytorch, tensorflow, nlp, computer-vision, mlops, llm, genai

## Kỹ năng theo cấp độ

### Level 1: Fresher/Junior (0-2 năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Python cho Data Science | NumPy (array operations, broadcasting, slicing), Pandas (DataFrame, GroupBy, Merge, Pivot, Time Series), Matplotlib/Seaborn (visualization cơ bản), Jupyter Notebook | 25% | python, numpy, pandas, visualization |
| 2 | Statistics & Probability | Descriptive statistics (mean, median, std, variance, percentiles), Probability distributions (Normal, Binomial, Poisson), Hypothesis testing (t-test, chi-square, p-value), Correlation vs Causation | 20% | statistics, probability, hypothesis-testing |
| 3 | Machine Learning cơ bản | Supervised vs Unsupervised vs Reinforcement Learning, Train/Validation/Test split, Bias-Variance tradeoff, Overfitting/Underfitting, Regularization (L1/L2), Cross-validation (K-Fold) | 20% | ml-basics, supervised, unsupervised, regularization |
| 4 | Các thuật toán ML cơ bản | Linear Regression, Logistic Regression, Decision Tree, Random Forest, KNN, K-Means Clustering, SVM (intuition), Naive Bayes | 15% | algorithms, regression, classification, clustering |
| 5 | Data Preprocessing | Missing value handling (mean/median/mode imputation, drop), Feature scaling (StandardScaler, MinMaxScaler), One-Hot Encoding, Label Encoding, Outlier detection (IQR, Z-score), Train-test split | 10% | preprocessing, feature-engineering, data-cleaning |
| 6 | Model Evaluation cơ bản | Classification metrics (Accuracy, Precision, Recall, F1, Confusion Matrix, ROC-AUC), Regression metrics (MSE, MAE, RMSE, R²), Clustering metrics (Silhouette Score, Elbow method) | 5% | evaluation, metrics, scoring |
| 7 | Scikit-learn | Pipeline API, fit/transform/predict, GridSearchCV/RandomizedSearchCV, train_test_split, cross_val_score, model persistence (joblib/pickle) | 5% | scikit-learn, sklearn, pipeline |

### Level 2: Junior/Mid (1-4 năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Deep Learning cơ bản | Neural network fundamentals (forward/backward propagation, activation functions: ReLU/sigmoid/tanh/softmax), Gradient Descent variants (SGD, Adam, RMSprop, AdamW), Loss functions (Cross-Entropy, MSE, Hinge), Batch Normalization, Dropout | 20% | deep-learning, neural-network, backpropagation |
| 2 | PyTorch / TensorFlow | Tensor operations, Autograd (PyTorch) / GradientTape (TF), DataLoader/Dataset, nn.Module / tf.keras.layers, Optimizer & Scheduler, Training loop, GPU training (CUDA), Model saving/loading | 20% | pytorch, tensorflow, gpu, cuda |
| 3 | Computer Vision cơ bản | CNN architecture (Conv2D, MaxPool, FC), Transfer Learning (ResNet, VGG, EfficientNet, ViT), Data Augmentation (Albumentations/torchvision transforms), Object Detection concepts (YOLO, RCNN family) | 15% | computer-vision, cnn, transfer-learning, object-detection |
| 4 | NLP cơ bản | Text preprocessing (tokenization, stemming, lemmatization, stopword removal), Word Embeddings (Word2Vec, GloVe, FastText), RNN/LSTM/GRU cho sequence modeling, Seq2Seq, Attention mechanism (intuition), Hugging Face Transformers cơ bản (pipeline API, tokenizer, model card) | 15% | nlp, rnn, lstm, attention, transformers, huggingface |
| 5 | Feature Engineering & Feature Store | Feature engineering techniques (Polynomial, Interaction, Binning, Log transform, Target encoding), Feature selection (Filter/Wrapper/Embedded methods), Feature importance (SHAP, Permutation Importance, MDI), Feature Store concept (Feast/Tecton) | 10% | feature-engineering, feature-selection, shap |
| 6 | Data Engineering cho ML | SQL nâng cao (Window functions, CTE, Subqueries, Pivot), ETL/ELT pipeline concepts, Data versioning (DVC, Delta Lake), Feature pipeline (batch vs streaming), Working with Big Data (Spark/Polars cơ bản) | 10% | data-engineering, sql, etl, dvc, spark |
| 7 | Model Deployment cơ bản | Flask/FastAPI REST API cho model serving, Docker containerization, Request validation & batching, Model versioning, Basic A/B testing setup, Monitoring cơ bản (drift detection concepts) | 10% | deployment, fastapi, docker, serving, mlops |

### Level 3: Mid/Senior (3+ năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | MLOps | CI/CD cho ML (train → validate → deploy), Model Registry (MLflow, W&B), Experiment Tracking (parameters, metrics, artifacts), Feature Store production (Feast), Model monitoring (Data drift: KS-test, PSI; Concept drift; Performance degradation), Automated retraining triggers, Pipeline orchestration (Kubeflow, Airflow, Prefect, ZenML) | 20% | mlops, mlflow, kubeflow, monitoring, feature-store |
| 2 | Advanced NLP & LLM | Transformer architecture chi tiết (Self-Attention, Multi-Head Attention, Positional Encoding, Layer Norm), BERT/GPT/T5 — differences & use cases, RAG (Retrieval-Augmented Generation) architecture, Embedding models (OpenAI, Cohere, Sentence-BERT, E5), Prompt Engineering (Zero-shot, Few-shot, Chain-of-Thought, Tree-of-Thought, ReAct), Fine-tuning LLM (LoRA, QLoRA, Prefix Tuning, Adapter), Quantization (GPTQ, AWQ, GGUF) | 20% | nlp, transformer, llm, rag, fine-tuning, lora, prompt-engineering |
| 3 | Computer Vision nâng cao | Object Detection (YOLOv8, DETR, RT-DETR), Segmentation (UNet, Mask R-CNN, SAM, DeepLabV3), Generative Models (GAN: DCGAN, StyleGAN; Diffusion: Stable Diffusion, ControlNet; VAE), Video Understanding (3D CNN, TimeSformer, VideoMAE), Multi-modal models (CLIP, ALIGN, ImageBind) | 15% | computer-vision, segmentation, gan, diffusion, multi-modal |
| 4 | Model Optimization | Quantization (INT8, FP16, BF16), Pruning (unstructured, structured), Knowledge Distillation (Teacher-Student), ONNX export, TensorRT optimization, TorchScript/JIT, Model compression, Inference optimization (batching, caching, async) | 15% | optimization, quantization, onnx, tensorrt, pruning |
| 5 | ML System Design | End-to-end ML system architecture, Online vs Offline inference, Batch prediction vs Real-time API, Feature engineering pipeline at scale, Model serving infrastructure (TF Serving, Triton, TorchServe, BentoML, Ray Serve), Latency/throughput tradeoffs, Cost optimization (GPU allocation, spot instances) | 15% | system-design, architecture, serving, inference |
| 6 | Cloud ML | AWS SageMaker (Training jobs, Endpoint, Feature Store, Pipelines, Clarify, Model Monitor), GCP Vertex AI (Training, Prediction, Feature Store, Pipelines), Azure ML (Workspace, Compute, Pipeline, Endpoint), Managed GPU services (AWS Inferentia/Trainium, GCP TPU) | 10% | cloud, aws, sagemaker, vertex-ai, azure-ml |
| 7 | Evaluation & Experimentation | Nâng cao: Stratified K-Fold, Time Series cross-validation, Group K-Fold; Statistical testing (McNemar, Wilcoxon signed-rank); Model fairness & bias (Demographic Parity, Equalized Odds); A/B testing thống kê (power analysis, sample size, MDE, peeking problem); LLM evaluation (BLEU, ROUGE, BERTScore, human eval, LLM-as-judge) | 5% | evaluation, experimentation, a-b-testing, fairness |

### Level 4: Senior/Lead (5+ năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | AI/ML Strategy | ML roadmap, Problem framing (bài toán nào nên dùng ML?), Build vs Buy vs Open-source decision, ROI analysis cho dự án ML, Data strategy (collection, labeling, governance), Responsible AI (Fairness, Transparency, Privacy, Accountability), ML maturity assessment | 25% | strategy, roadmap, roi, responsible-ai, governance |
| 2 | ML Team Leadership | ML team structure (Data Scientist, ML Engineer, MLOps, Data Engineer), Hiring & evaluating ML talent, Mentoring & career development, Cross-functional collaboration (Product, Engineering, Business), Research-to-Production handoff process | 20% | leadership, team-building, hiring, mentoring |
| 3 | Production ML at Scale | Distributed training (Data Parallel, Model Parallel, FSDP, DeepSpeed), High-throughput/low-latency serving (500ms SLA at 1k QPS), Feature engineering at scale (Spark/Flink/Beam), Online experimentation platform, ML safety (adversarial robustness, OOD detection, guardrails), Model rollback & incident response | 20% | production-ml, distributed-training, scaling, reliability |
| 4 | Advanced GenAI/LLM Systems | LLM orchestration (LangChain, LlamaIndex, Semantic Kernel), Agent architectures (ReAct, Plan-and-Execute, Multi-agent), LLM evaluation & guardrails (Nemo Guardrails, Guardrails AI), LLM cost optimization (caching, routing, prompt compression), On-device LLM deployment, Multi-modal agents, LLM security (prompt injection, jailbreak, data leakage) | 15% | genai, llm, agents, orchestration, langchain |
| 5 | ML Infrastructure | GPU cluster management, Training platform design (notebooks, job scheduling), Model registry at scale, Feature platform architecture, Experimentation platform, ML observability stack (monitoring, alerting, debugging), Data labeling platform (Label Studio, Scale AI) | 10% | infrastructure, platform, gpu-cluster, training |
| 6 | Research & Innovation | Paper reading & implementation (latest SoTA), Internal research program, Patent/IP strategy, Conference publication (NeurIPS, ICML, ICLR, CVPR), Open-source contributions, University collaboration | 10% | research, innovation, papers, publication |

## Câu hỏi phỏng vấn mẫu theo kỹ năng

### Python & Data Science
#### Basic
- "NumPy array vs Python list — điểm khác biệt về performance và use case?"
- "Các pandas operation cơ bản: groupby, merge, pivot, apply — khi nào dùng cái nào?"
- "Làm sao xử lý missing value trong dataset? Các chiến lược imputation?"
- "Phân biệt StandardScaler, MinMaxScaler, RobustScaler? Khi nào dùng cái nào?"
- "Matplotlib/Seaborn — vẽ biểu đồ phân phối (histogram, KDE, box plot) để khám phá dữ liệu?"

#### Medium
- "Python Generator và iterator — dùng trong ML pipeline xử lý dữ liệu lớn thế nào?"
- "Vectorization trong NumPy — tại sao nó nhanh hơn vòng lặp Python?"
- "Làm sao xử lý categorical feature có high cardinality (1000+ categories)?"
- "Time series resampling và window functions trong pandas?"
- "Multiprocessing vs Multithreading vs asyncio trong Python cho ML workloads?"

#### Advanced
- "Thiết kế data pipeline xử lý 1TB dữ liệu bằng Python — dùng công cụ gì (Dask, Ray, Polars)?"
- "Python Memory profiling — công cụ (memory_profiler, tracemalloc) và cách tối ưu?"
- "Decorator trong Python — ứng dụng trong ML code (caching, logging, timing, retry)?"

### Machine Learning Fundamentals
#### Basic
- "Phân biệt Supervised, Unsupervised, và Reinforcement Learning? Cho ví dụ thực tế?"
- "Bias-Variance Tradeoff là gì? High Bias vs High Variance — dấu hiệu và cách khắc phục?"
- "Overfitting là gì? Các kỹ thuật chống overfitting (Regularization, Dropout, Early Stopping)?"
- "Phân biệt Classification vs Regression? Metrics tương ứng?"
- "K-Fold Cross Validation hoạt động thế nào? Tại sao cần cross-validation?"

#### Medium
- "Gradient Descent — Batch vs Stochastic vs Mini-batch GD khác gì? Adam optimizer hoạt động thế nào?"
- "Decision Tree — Gini impurity vs Entropy? Tại sao cần pruning?"
- "Random Forest vs Gradient Boosting (XGBoost/LightGBM) khác gì? Khi nào chọn cái nào?"
- "Imbalanced dataset — các kỹ thuật xử lý (SMOTE, class weight, threshold tuning)?"
- "Feature Importance — cách tính trong tree-based models? SHAP values là gì?"

#### Advanced
- "XGBoost vs LightGBM vs CatBoost — khác biệt về thuật toán, speed, và use case?"
- "Anomaly Detection — Isolation Forest, LOF, AutoEncoder-based methods?"
- "Causal Inference vs Correlation — tại sao quan trọng? Các phương pháp: A/B test, IV, Diff-in-Diff?"
- "Online Learning — model update liên tục với streaming data? Concept drift handling?"
- "Ensemble methods: Stacking, Blending, Bagging, Boosting — khác biệt và khi nào dùng?"

### Deep Learning
#### Basic
- "Neural Network hoạt động thế nào? Forward propagation và Backpropagation?"
- "Activation functions: ReLU, Sigmoid, Tanh, Softmax — công thức, ưu/nhược?"
- "Batch Normalization là gì? Tại sao giúp training nhanh hơn? Layer Norm vs Batch Norm?"
- "Dropout hoạt động thế nào? Tại sao giảm overfitting? Training vs Inference khác gì?"
- "Loss function: Cross-Entropy, MSE, Hinge loss — dùng cho bài toán gì?"

#### Medium
- "Vanishing/Exploding Gradient — nguyên nhân và cách giải quyết?"
- "Transfer Learning là gì? Fine-tuning vs Feature Extraction? Khi nào dùng?"
- "Learning Rate Scheduler — các loại (Step, Cosine, ReduceLROnPlateau, OneCycle)?"
- "Data Augmentation trong Computer Vision và NLP — các kỹ thuật phổ biến?"
- "Mixed Precision Training (FP16/BF16) — hoạt động thế nào? Lợi ích?"

#### Advanced
- "Distributed Training — Data Parallel, Model Parallel, Pipeline Parallel, FSDP?"
- "Self-Supervised Learning — SimCLR, MoCo, MAE, contrastive learning?"
- "Neural Architecture Search (NAS) — concepts và trade-off?"
- "Meta-Learning / Few-Shot Learning — MAML, Prototypical Networks?"
- "Mixture of Experts (MoE) — kiến trúc, load balancing, routing?"

### NLP & LLM
#### Basic
- "Text preprocessing pipeline cho NLP: tokenization → stemming/lemmatization → stopwords?"
- "Word Embeddings (Word2Vec, GloVe) — hoạt động thế nào? CBOW vs Skip-gram?"
- "RNN / LSTM — hoạt động thế nào? Tại sao LSTM giải quyết vanishing gradient?"
- "Attention mechanism — intuition và công thức self-attention?"
- "Hugging Face Transformers — pipeline API, tokenizer, model card?"

#### Medium
- "Transformer architecture chi tiết — Multi-Head Attention, Feed-Forward, Layer Norm?"
- "BERT — pre-training objectives (MLM, NSP)? Fine-tuning BERT cho classification/NER?"
- "GPT — khác BERT thế nào? Autoregressive generation, temperature, top-p, top-k?"
- "RAG (Retrieval-Augmented Generation) — kiến trúc và trade-off?"
- "Sentence Embeddings — Sentence-BERT, E5, Instructor — khác biệt và use case?"

#### Advanced
- "Fine-tuning LLM: Full fine-tuning vs LoRA/QLoRA vs Prefix Tuning — trade-off?"
- "RLHF (Reinforcement Learning from Human Feedback) — các bước (SFT → Reward Model → PPO)?"
- "Prompt Engineering nâng cao: Chain-of-Thought, Tree-of-Thought, ReAct, DSPy?"
- "LLM Evaluation — Automated eval (BLEU/ROUGE/BERTScore) vs Human eval vs LLM-as-judge?"
- "Quantization: GPTQ vs AWQ vs GGUF — nguyên lý và trade-off (speed vs quality)?"

### Computer Vision
#### Basic
- "CNN architecture: Convolution, Pooling, Fully Connected layers?"
- "Data Augmentation cho ảnh: flip, rotation, crop, color jitter — tại sao cần?"
- "Transfer Learning với ImageNet pre-trained models (ResNet, EfficientNet)?"
- "Object Detection vs Classification vs Segmentation khác gì?"
- "Image preprocessing: resize, normalize, mean/std?"

#### Medium
- "YOLO (You Only Look Once) — kiến trúc và cách hoạt động (grid, anchor boxes, NMS)?"
- "Semantic Segmentation vs Instance Segmentation vs Panoptic Segmentation?"
- "Feature Pyramid Network (FPN) — giải quyết vấn đề gì trong object detection?"
- "Siamese Networks — dùng cho face verification / one-shot learning?"
- "Vision Transformer (ViT) — khác CNN thế nào? Patch embedding + positional encoding?"

#### Advanced
- "GAN — adversarial training, mode collapse, WGAN/WGAN-GP để ổn định training?"
- "Diffusion Models — DDPM, Stable Diffusion, ControlNet — nguyên lý hoạt động?"
- "Multi-modal models (CLIP, ImageBind, LLaVA) — training và ứng dụng?"
- "Video Understanding — 3D CNN vs TimeSformer vs VideoMAE?"
- "Foundation Models cho CV — SAM (Segment Anything), DINOv2, Depth Anything?"

### MLOps & Deployment
#### Basic
- "CI/CD cho ML khác CI/CD truyền thống thế nào? Thêm bước gì?"
- "MLflow — Tracking, Projects, Models, Registry — dùng để làm gì?"
- "Dockerize ML model — viết Dockerfile cho Flask/FastAPI serve model?"
- "Data Drift vs Concept Drift — phân biệt và cách detect?"
- "Feature Store là gì? Tại sao cần Feature Store?"

#### Medium
- "Kubeflow / Airflow — orchestrate ML pipeline (data → train → validate → deploy)?"
- "Model Serving: Batch prediction vs Real-time API — kiến trúc và trade-off?"
- "A/B Testing cho ML model — thiết lập, chọn metrics, tính sample size?"
- "ML Monitoring: những metric nào cần theo dõi (prediction distribution, latency, error rate)?"
- "Model Registry — model versioning, stage transition (Staging → Production → Archived)?"

#### Advanced
- "Thiết kế MLOps platform cho enterprise: multi-tenant, multi-model, auto-retraining?"
- "Shadow Deployment vs Canary Deployment vs Blue-Green Deployment cho ML?"
- "Data Versioning (DVC, LakeFS, Delta Lake) — version control cho dataset và model?"
- "GPU serving tối ưu: dynamic batching, model concurrency, model warming, Triton Inference Server?"
- "ML Observability stack: Prometheus + Grafana + WhyLogs/Evidently/NannyML?"

### ML System Design
#### Basic
- "Thiết kế hệ thống recommender cơ bản: Collaborative Filtering vs Content-Based?"
- "Thiết kế spam detection system: text classification pipeline?"
- "Thiết kế search ranking system: query understanding → retrieval → ranking?"

#### Medium
- "Thiết kế hệ thống fraud detection real-time: feature pipeline + model serving latency < 100ms?"
- "Thiết kế chatbot RAG: document ingestion → embedding → retrieval → generation?"
- "Thiết kế personalized feed (TikTok/Facebook style): candidate generation → scoring → re-ranking?"

#### Advanced
- "Thiết kế hệ thống ML xử lý 1M requests/giây: đánh đổi accuracy vs latency vs cost?"
- "Thiết kế autonomous driving perception pipeline: multi-modal fusion, real-time inference?"
- "Thiết kế large-scale LLM inference service: KV-cache, continuous batching, speculative decoding?"

### Evaluation & Metrics
#### Basic
- "Phân biệt Accuracy, Precision, Recall, F1-Score? Khi nào dùng cái nào?"
- "Confusion Matrix — True/False Positive/Negative? TPR, FPR?"
- "ROC-AUC là gì? Ý nghĩa của AUC = 0.5, 0.8, 1.0?"
- "Regression metrics: MSE, MAE, RMSE, R² — cái nào nhạy với outlier?"
- "Train/Validation/Test split — tỉ lệ bao nhiêu? Tại sao cần validation set?"

#### Medium
- "Precision-Recall Curve vs ROC Curve — khi nào dùng cái nào? Imbalanced data?"
- "Log Loss (Cross-Entropy) vs Brier Score — khác gì?"
- "NLP evaluation: BLEU, ROUGE, METEOR, BERTScore — ưu/nhược từng cái?"
- "Clustering evaluation: Silhouette Score, Davies-Bouldin Index, Adjusted Rand Index?"
- "Calibration của model — Reliability Diagram, Expected Calibration Error (ECE)?"

#### Advanced
- "Statistical significance trong model comparison: McNemar test, 5x2 cross-validation paired t-test?"
- "Multi-objective optimization — làm sao cân bằng nhiều metrics cùng lúc (Pareto front)?"
- "Counterfactual evaluation trong recommendation: offline replay vs online A/B test?"
- "LLM evaluation pipeline: automated (GPT-judge) + human eval + behavioral testing (CheckList)?"
- "Fairness metrics: Demographic Parity, Equal Opportunity, Equalized Odds — trade-off với accuracy?"

## Dự án mẫu để lấp gap

### Level Junior — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "House Price Prediction (Kaggle)" | Regression, EDA, Feature engineering, Scikit-learn | 2-3 tuần | Python, Pandas, Scikit-learn, XGBoost, Matplotlib |
| 2 | "Customer Churn Classification" | Classification, Imbalanced data, Model evaluation, SHAP | 2-3 tuần | Python, Scikit-learn, LightGBM, SHAP, Jupyter |
| 3 | "Image Classifier với Transfer Learning" | CNN, Transfer Learning, PyTorch, Data augmentation | 3-4 tuần | Python, PyTorch, torchvision, Albumentations, GPU |
| 4 | "Sentiment Analysis cho Review Sản Phẩm" | NLP, Text preprocessing, Word embeddings, LSTM/BERT | 3-4 tuần | Python, HuggingFace, Transformers, Pandas, Streamlit |
| 5 | "Recommendation System cơ bản" | Collaborative Filtering, Matrix Factorization, Evaluation | 3-4 tuần | Python, Scikit-learn, Surprise/Implicit, FastAPI, Docker |

### Level Mid — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "ML Pipeline Production với MLOps" | MLflow, Experiment tracking, Model Registry, CI/CD ML | 4-6 tuần | Python, MLflow, FastAPI, Docker, GitHub Actions, DVC |
| 2 | "Object Detection Service (YOLOv8)" | Object Detection, ONNX/TensorRT, FastAPI serving, Docker | 4-6 tuần | Python, YOLOv8, FastAPI, ONNX, Docker, Streamlit |
| 3 | "RAG Chatbot cho Tài Liệu Nội Bộ" | RAG, Embeddings, Vector DB, LLM API, LangChain | 4-6 tuần | Python, LangChain/LlamaIndex, ChromaDB/Pinecone, OpenAI API, Streamlit |
| 4 | "Fraud Detection Real-time Pipeline" | Feature engineering, Imbalanced learn, Real-time inference | 6-8 tuần | Python, LightGBM, Kafka (simulated), Redis, FastAPI, Docker |
| 5 | "NLP Model Fine-tuning Platform" | Fine-tuning, LoRA, HuggingFace, Experiment tracking | 4-6 tuần | Python, HuggingFace, PEFT (LoRA), MLflow, Gradio |

### Level Senior — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "End-to-End MLOps Platform" | Kubeflow/Airflow, Feature Store, Model Registry, Monitoring, Auto-retraining | 8-12 tuần | Python, Kubeflow, MLflow, Feast, Evidently, Prometheus, Grafana |
| 2 | "Multi-Modal Search Engine (Text + Image)" | Multi-modal embeddings, Vector search, Ranking, CLIP | 8-10 tuần | Python, CLIP/ImageBind, FAISS/Milvus, FastAPI, React, Docker |
| 3 | "LLM Fine-tuning & Serving Infrastructure" | Distributed training (DeepSpeed), LoRA/QLoRA, vLLM serving | 8-12 tuần | Python, PyTorch, DeepSpeed, vLLM, PEFT, LangChain, K8s |
| 4 | "Real-Time Personalization System" | Feature pipeline real-time, Multi-stage ranking, A/B testing platform | 10-14 tuần | Python, Spark/Flink, Redis, TensorFlow Serving, Airflow, Grafana |
