# Document Digitization Pipeline: A Comparative Analysis of OCR Approaches

## 1. Executive Summary
This report presents a comprehensive analysis of five different OCR approaches tested on various document types, including handwritten forms, handwritten receipts, printed receipts, and printed forms. The study evaluates performance metrics, computational efficiency, and practical considerations for each approach.

## 2. Introduction
### 2.1 Problem Statement
Organizations need efficient and accurate methods to convert physical documents into structured, machine-readable data. This study evaluates multiple OCR approaches across different document types to identify optimal solutions.

### 2.2 Approaches Evaluated
1. Google Gemini Vision API
2. PaddleOCR
3. Florence-2
4. Llama 3.2 Vision
5. Qwen-2 VL

## 3. Methodology
### 3.1 Datasets
- **Handwritten Dataset**: 10 images (5 forms, 5 receipts) with manual annotations
- **Printed Receipts Dataset**: 20 images
- **Printed Forms Dataset**: 50 images

### 3.2 Evaluation Metrics
- ROUGE-1, ROUGE-2, and ROUGE-L F1 scores
- Inference time
- Computational requirements (GPU memory, RAM usage)

## 4. Results Analysis

### 4.1 Handwritten Forms Performance

| Model | ROUGE-1 F1 | ROUGE-2 F1 | ROUGE-L F1 | Inference Time | GPU Required |
|-------|------------|------------|------------|----------------|--------------|
| Gemini | 0.9333 | 0.8951 | 0.9319 | 4.21s | No |
| PaddleOCR | 0.7795 | 0.6550 | 0.7705 | 2.14s | No |
| Llama 3.2 | 0.6962 | 0.5330 | 0.6471 | 33.83s | Yes (15GB+) |
| Florence-2 | 0.4698 | 0.3696 | 0.4698 | 2.21s | Yes (5GB) |
| Qwen-2 | 0.7634 | 0.7269 | 0.7634 | 46.49s | Yes (15GB+) |

### 4.2 Handwritten Receipts Performance

| Model | ROUGE-1 F1 | ROUGE-2 F1 | ROUGE-L F1 | Inference Time | GPU Required |
|-------|------------|------------|------------|----------------|--------------|
| Gemini | 0.8782 | 0.7502 | 0.7770 | 3.95s | No |
| PaddleOCR | 0.5962 | 0.3689 | 0.5300 | 1.43s | No |
| Llama 3.2 | 0.4054 | 0.2140 | 0.3079 | 14.15s | Yes (15GB+) |
| Florence-2 | 0.1890 | 0.0989 | 0.1827 | 0.90s | Yes (5GB) |
| Qwen-2 | 0.5951 | 0.4614 | 0.5407 | 38.67s | Yes (15GB+) |

### 4.3 Printed Receipts Performance

| Model | ROUGE-1 F1 | ROUGE-2 F1 | ROUGE-L F1 | Inference Time | GPU Required |
|-------|------------|------------|------------|----------------|--------------|
| Gemini | 0.4867 | 0.3748 | 0.2456 | 5.60s | No |
| PaddleOCR | 0.3517 | 0.1837 | 0.1758 | 2.10s | No |
| Llama 3.2 | 0.3427 | 0.1877 | 0.1767 | 32.77s | Yes (15GB+) |
| Florence-2 | 0.1936 | 0.0532 | 0.1137 | 2.23s | Yes (5GB) |
| Qwen-2 | 0.3071 | 0.2179 | 0.1639 | 45.22s | Yes (15GB+) |

### 4.4 Printed Forms Performance

| Model | ROUGE-1 F1 | ROUGE-2 F1 | ROUGE-L F1 | Inference Time | GPU Required |
|-------|------------|------------|------------|----------------|--------------|
| Gemini | 0.9701 | 0.7361 | 0.6852 | 4.08s | No |
| PaddleOCR | 0.8821 | 0.6221 | 0.6271 | 3.65s | No |
| Llama 3.2 | 0.0159 | 0.0000 | 0.0144 | 23.11s | Yes (15GB+) |
| Florence-2 | 0.6014 | 0.3480 | 0.4872 | 8.13s | Yes (5GB) |
| Qwen-2 | 0.8256 | 0.6285 | 0.6079 | 34.31s | Yes (15GB+) |

## 5. Key Findings

### 5.1 Performance Analysis
1. **Handwritten Documents**:
   - Gemini consistently performs best across both forms and receipts
   - PaddleOCR shows strong performance considering its lightweight nature
   - Large vision-language models (Llama, Qwen) show mixed results despite high computational requirements

2. **Printed Documents**:
   - Gemini and PaddleOCR show consistent performance
   - Florence-2 performs well on forms but struggles with receipts
   - Larger models don't necessarily translate to better performance

### 5.2 Computational Efficiency
1. **Resource Requirements**:
   - PaddleOCR: Lightweight, CPU-only operation
   - Gemini: API-based, no local compute needed
   - Florence-2: Moderate GPU requirements (≈5GB)
   - Llama 3.2 & Qwen-2: Heavy GPU requirements (15GB+)

2. **Inference Time**:
   - PaddleOCR: Fastest (1-3s)
   - Gemini: Fast (3-5s)
   - Florence-2: Moderate (2-8s)
   - Llama 3.2 & Qwen-2: Slowest (15-45s)

## 6. Recommendations

### 6.1 Use Case Specific Recommendations
1. **Handwritten Documents**:
   - Primary: Gemini Vision API
   - Budget/Offline: PaddleOCR

2. **Printed Documents**:
   - Primary: PaddleOCR or Gemini
   - High-Resource Settings: Florence-2


