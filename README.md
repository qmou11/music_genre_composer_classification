# Classical Composer Classification Using Hybrid LSTM-CNN Deep Learning

## Project Overview

This project implements a deep learning system to automatically classify classical music composers using a hybrid approach combining Long Short-Term Memory (LSTM) and Convolutional Neural Network (CNN) architectures. The system analyzes MIDI files from four major classical composers to identify distinctive compositional patterns and styles.

## Objectives

- **Primary Goal**: Achieve high accuracy in predicting the composer of unknown musical pieces
- **Secondary Goals**: 
  - Implement multi-modal learning using LSTM and CNN
  - Extract meaningful musical features from MIDI data
  - Develop an interpretable model for musical pattern recognition

## Dataset

The project uses a comprehensive dataset of **1,530 MIDI files** from four classical composers:

| Composer | Period | Files | Size | Key Works |
|----------|--------|-------|------|-----------|
| **Bach** | Baroque (1685-1750) | 122 | 16MB | Chorales, Well-Tempered Clavier, Goldberg Variations |
| **Beethoven** | Classical/Romantic (1770-1827) | 133 | 14MB | Piano Sonatas, Symphonies, String Quartets |
| **Chopin** | Romantic (1810-1849) | 136 | 3.2MB | Études, Nocturnes, Preludes, Ballades |
| **Mozart** | Classical (1756-1791) | 90 | 12MB | Piano Sonatas, Symphonies, Operas |

**Total**: 481 MIDI files across all composers

## Methodology

### 1. Data Collection
- **Status**: ✅ Complete
- **Source**: Provided dataset with MIDI files organized by composer
- **Format**: Standard MIDI data (format 1) with multiple tracks
- **Coverage**: Major works from each composer spanning different genres and periods

### 2. Data Pre-processing
- **MIDI File Processing**: Convert MIDI files to suitable formats for deep learning
- **Data Augmentation**: 
  - Transpose pieces to different keys
  - Stretch/compress timing
  - Add noise variations
  - Normalize tempo and velocity
- **Format Conversion**:
  - LSTM: Extract sequential note data (pitch, duration, velocity, timing)
  - CNN: Convert to piano roll representations (2D images)

### 3. Feature Extraction
Extract musical features from MIDI files using music analysis tools:

**Sequential Features (for LSTM)**:
- Note sequences and timing
- Melodic contours
- Rhythm patterns
- Velocity variations

**Spatial Features (for CNN)**:
- Chord progressions
- Harmonic relationships
- Piano roll representations
- Multi-channel instrument data

### 4. Model Building
Develop a hybrid deep learning architecture:

**LSTM Branch**:
- Process sequential musical data
- Capture temporal patterns (melody, rhythm progression)
- Handle variable-length sequences

**CNN Branch**:
- Process piano roll images
- Detect spatial patterns (chord structures, harmonic relationships)
- Multi-channel processing for different instruments

**Fusion Layer**:
- Combine LSTM and CNN features
- Weighted combination of both approaches
- Final classification layer

### 5. Model Training
- **Architecture**: Hybrid LSTM-CNN model
- **Input**: Pre-processed MIDI data in dual formats
- **Output**: 4-class classification (one per composer)
- **Training Strategy**:
  - Split data into training/validation/test sets
  - Handle class imbalance
  - Use appropriate loss functions
  - Implement early stopping

### 6. Model Evaluation
Evaluate model performance using multiple metrics:

**Primary Metrics**:
- Accuracy
- Precision (per composer)
- Recall (per composer)
- F1-score (per composer)

**Additional Analysis**:
- Confusion matrix
- Per-composer performance analysis
- Feature importance analysis

### 7. Model Optimization
Fine-tune the model for optimal performance:

**Hyperparameter Optimization**:
- Learning rate
- Batch size
- Network architecture (layers, units)
- Dropout rates
- Fusion weights

**Techniques**:
- Grid search/random search
- Cross-validation
- Learning rate scheduling
- Regularization techniques

## Technical Implementation

### Requirements
```
Python 3.8+
TensorFlow 2.x / PyTorch
pretty_midi / mido (MIDI processing)
numpy, pandas, matplotlib
scikit-learn
```

### Project Structure
```
music_genre_composer_classification/
├── data/                    # MIDI dataset
│   ├── Bach/
│   ├── Beethoven/
│   ├── Chopin/
│   └── Mozart/
├── src/
│   ├── preprocessing/       # Data preprocessing modules
│   ├── feature_extraction/ # Feature extraction modules
│   ├── models/            # LSTM, CNN, and hybrid models
│   ├── training/          # Training scripts
│   └── evaluation/        # Evaluation and visualization
├── notebooks/             # Jupyter notebooks for exploration
├── results/              # Model outputs and visualizations
└── README.md
```

## Expected Outcomes

1. **Trained Model**: A hybrid LSTM-CNN model capable of accurate composer classification
2. **Performance Metrics**: Comprehensive evaluation results with detailed analysis
3. **Musical Insights**: Understanding of distinctive patterns that differentiate composers
4. **Framework**: Reusable codebase for music analysis using deep learning
5. **Documentation**: Complete implementation guide and results analysis

## Applications

- **Music Education**: Automated composer identification for learning
- **Digital Libraries**: Enhanced metadata for classical music collections
- **Composition Analysis**: Understanding musical style characteristics
- **AI in Arts**: Bridging computational methods and artistic expression

## Future Enhancements

- Expand to more composers and periods
- Real-time classification capabilities
- Integration with audio files (not just MIDI)
- Style transfer between composers
- Interactive web application

---

*This project explores the intersection of music theory and artificial intelligence, demonstrating how deep learning can understand and classify human artistic expression in classical music.*