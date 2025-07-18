# Music Composer Classification Dataset Analysis

## Dataset Overview

This dataset contains **1,530 MIDI files** from four major classical composers, organized for a deep learning composer classification project using LSTM and CNN techniques.

## Dataset Structure

### Composer Distribution
- **Bach**: 122 MIDI files (16MB)
- **Beethoven**: 133 MIDI files (14MB) 
- **Chopin**: 136 MIDI files (3.2MB)
- **Mozart**: 90 MIDI files (12MB)

**Total**: 481 MIDI files across all composers

### Data Organization
```
data/
├── Bach/          # Johann Sebastian Bach (1685-1750)
├── Beethoven/     # Ludwig van Beethoven (1770-1827)
├── Chopin/        # Frédéric Chopin (1810-1849)
└── Mozart/        # Wolfgang Amadeus Mozart (1756-1791)
```

## Composer-Specific Content Analysis

### Johann Sebastian Bach (Baroque Period)
- **File Count**: 122 MIDI files
- **Size**: 16MB
- **Key Works Included**:
  - Chorales (BWV 001-400)
  - Well-Tempered Clavier (Books 1 & 2)
  - Goldberg Variations
  - Brandenburg Concertos
  - Orchestral Suites
  - Mass in B minor
  - St. Matthew Passion
  - Two and Three Part Inventions
  - Organ works (Toccatas, Preludes, Fugues)
  - Harpsichord Concertos

### Ludwig van Beethoven (Classical/Romantic Period)
- **File Count**: 133 MIDI files
- **Size**: 14MB
- **Key Works Included**:
  - Piano Sonatas (including "Moonlight Sonata")
  - Symphonies (1-9)
  - String Quartets
  - Piano Concertos
  - Bagatelles
  - Variations
  - Violin Concerto
  - Chamber music

### Frédéric Chopin (Romantic Period)
- **File Count**: 136 MIDI files
- **Size**: 3.2MB
- **Key Works Included**:
  - Études (Op. 10 and Op. 25)
  - Nocturnes
  - Preludes (Op. 28)
  - Ballades
  - Polonaises
  - Mazurkas
  - Piano Concertos
  - Waltzes
  - Impromptus

### Wolfgang Amadeus Mozart (Classical Period)
- **File Count**: 90 MIDI files
- **Size**: 12MB
- **Key Works Included**:
  - Piano Sonatas
  - Piano Concertos
  - Symphonies
  - Operas (Don Giovanni, Magic Flute)
  - Requiem
  - Serenades (Eine Kleine Nachtmusik)
  - Chamber music
  - Church music

## Technical Characteristics

### MIDI File Format
- **Format**: Standard MIDI data (format 1)
- **Tempo**: Various (typically 1/120 to 1/240)
- **Tracks**: Multiple tracks per file (typically 6+ tracks)
- **File Sizes**: Range from ~1KB to ~200KB per file

### Data Quality Observations
1. **Comprehensive Coverage**: Each composer has a substantial collection of their major works
2. **Historical Periods**: Spans Baroque, Classical, and Romantic periods
3. **Genre Diversity**: Includes solo piano, orchestral, chamber, and vocal works
4. **File Organization**: Well-structured with descriptive filenames
5. **Size Variation**: Files range from small pieces to large orchestral works

## Machine Learning Considerations

### For LSTM Models
- **Sequential Data**: MIDI files contain temporal musical sequences
- **Variable Length**: Pieces range from short to long compositions
- **Multi-track**: Can process multiple instruments simultaneously
- **Feature Extraction**: Can extract note sequences, timing, velocity, and duration

### For CNN Models
- **Piano Roll Representation**: MIDI can be converted to 2D piano roll images
- **Spatial Patterns**: Musical patterns can be detected as spatial features
- **Multi-channel**: Different instruments can be separate channels
- **Fixed-size Input**: Can be resized to standard dimensions

### Data Preprocessing Requirements
1. **MIDI Parsing**: Extract note events, timing, and velocity
2. **Normalization**: Standardize tempo and key
3. **Sequence Padding**: Handle variable-length sequences
4. **Feature Engineering**: Create musical features (chord progressions, intervals, etc.)
5. **Data Augmentation**: Transpose, stretch, or modify timing

## Challenges and Opportunities

### Challenges
1. **Class Imbalance**: Uneven distribution across composers
2. **Variable Complexity**: Simple pieces vs. complex orchestral works
3. **Style Overlap**: Some composers have similar periods/styles
4. **File Quality**: Some files may have transcription errors

### Opportunities
1. **Rich Musical Features**: MIDI provides detailed musical information
2. **Multi-modal Learning**: Can combine LSTM and CNN approaches
3. **Transfer Learning**: Pre-trained models on music data
4. **Interpretability**: Musical patterns are human-interpretable

## Recommended Approach

### Data Preprocessing Pipeline
1. **MIDI Loading**: Use libraries like `pretty_midi` or `mido`
2. **Feature Extraction**: 
   - Note sequences (pitch, duration, velocity)
   - Chord progressions
   - Rhythm patterns
   - Melodic contours
3. **Normalization**: Standardize tempo and key
4. **Augmentation**: Transpose, stretch, add noise

### Model Architecture
1. **LSTM Branch**: Process sequential note data
2. **CNN Branch**: Process piano roll representations
3. **Fusion Layer**: Combine both approaches
4. **Classification**: 4-class output (one per composer)

### Evaluation Metrics
- Accuracy, Precision, Recall, F1-score
- Confusion matrix analysis
- Per-composer performance analysis

This dataset provides an excellent foundation for exploring the intersection of music theory and deep learning for composer classification. 