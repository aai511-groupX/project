## Feature Extraction for Composer Classification

Feature selection is based on musicological principles, aiming to capture stylistic nuances that distinguish composers. These features are categorized into various dimensions:

### Basic MIDI Information

* **Total Duration.** The total length of the MIDI file in seconds. This provides an overall sense of the length of the composition. Longer pieces may be characteristic of certain periods or composers.

* **Number of Instruments.** The number of different instruments used in the MIDI file. This feature helps in understanding the orchestration complexity. Composers often have preferred instrumentation reflecting their stylistic choices or the resources available in their time.

### Note-Level Features

This category analyzes individual notes to reveal melodic and rhythmic tendencies.

* **Number of Notes.** Total number of notes in the MIDI file. This feature gives an idea of the note density and activity within the piece. More densely packed notes might indicate a more ornamented style.

* **Average Pitch.** The mean pitch value of all notes. Pitch values range from 0 to 127, with middle C being 60. This feature can indicate the general pitch range favored by the composer.

  \begin{align}
  \text{Average Pitch} = \frac{1}{N} \sum_{i=1}^{N} \text{pitch}_i
  \end{align}

* **Pitch Range.** The difference between the highest and lowest pitch in the piece. This feature captures the pitch span used by the composer.

  \begin{align}
  \text{Pitch Range} = \max(\text{pitch}) - \min(\text{pitch})
  \end{align}

* **Pitch Standard Deviation.** The standard deviation of pitch values, indicating the variability in pitch usage.

  \begin{align}
  \text{Pitch Std} = \sqrt{\frac{1}{N} \sum_{i=1}^{N} (\text{pitch}_i - \text{Average Pitch})^2}
  \end{align}

* **Average Duration.** The mean duration of all notes in seconds. This feature provides insight into the typical note lengths used by the composer.

  \begin{align}
  \text{Average Duration} = \frac{1}{N} \sum_{i=1}^{N} \text{duration}_i
  \end{align}

* **Duration Range.** The difference between the longest and shortest note duration.

  \begin{align}
  \text{Duration Range} = \max(\text{duration}) - \min(\text{duration})
  \end{align}

* **Duration Standard Deviation.** The standard deviation of note durations, indicating the variability in note lengths.

  \begin{align}
  \text{Duration Std} = \sqrt{\frac{1}{N} \sum_{i=1}^{N} (\text{duration}_i - \text{Average Duration})^2}
  \end{align}

* **Average Velocity.** The mean velocity (intensity) of all notes. Velocity values range from 0 to 127 and indicate the dynamic level.

  \begin{align}
  \text{Average Velocity} = \frac{1}{N} \sum_{i=1}^{N} \text{velocity}_i
  \end{align}

* **Velocity Variance.** The variance of note velocities, indicating the dynamic variability.

  \begin{align}
  \text{Velocity Variance} = \frac{1}{N} \sum_{i=1}^{N} (\text{velocity}_i - \text{Average Velocity})^2
  \end{align}

### Time Signature and Key

* **Time Signature.** The time signature of the piece, typically represented as a fraction (e.g., 4/4, 3/4). This feature captures the rhythmic structure. Different composers and periods favor specific time signatures.

* **Key.** The key signature of the piece, represented as an integer (e.g., 0 for C, 1 for C#). While key choice can be influenced by personal preferences, certain keys were historically associated with specific moods or affects.

* **Mode.** The mode of the piece, either major or minor. The prevalence of major or minor modes can be stylistically significant.

### Harmonic Features

* **Harmony Complexity.** The number of unique pitch combinations (chords) used in the piece. This feature captures the harmonic richness.

* **Chord Entropy.** A measure of unpredictability in chord usage, calculated using the Shannon entropy formula. A higher entropy value indicates more unpredictable and potentially more individualistic harmonic language.

  \begin{align}
  H = -\sum_{i=1}^{k} p_i \log_2(p_i)
  \end{align}
  where \( p_i \) is the probability of the \( i \)-th chord.

### Rhythmic Features

* **Note Density.** The number of notes per unit time (notes per second). This feature captures the overall activity level.

  \begin{align}
  \text{Note Density} = \frac{\text{Number of Notes}}{\text{Total Duration}}
  \end{align}

* **Rhythmic Complexity.** The standard deviation of inter-onset intervals (IOI), which are the time differences between consecutive note onsets. Greater variability in IOI often indicates more complex rhythms.

  \begin{align}
  \text{Rhythmic Complexity} = \sqrt{\frac{1}{N-1} \sum_{i=1}^{N-1} (\text{IOI}_i - \text{Average IOI})^2}
  \end{align}

### Dynamic Features

* **Dynamic Range.** The range of note velocities. This measures the difference between the softest and loudest notes, providing insight into the composer's use of dynamics.

  \begin{align}
  \text{Dynamic Range} = \max(\text{velocity}) - \min(\text{velocity})
  \end{align}

* **Staccato Ratio.** The proportion of short notes (e.g., duration < 0.1s). A high staccato ratio might indicate a preference for detached, articulate playing.

  \begin{align}
  \text{Staccato Ratio} = \frac{\sum_{i=1}^{N} \mathbb{1}(\text{duration}_i < 0.1)}{N}
  \end{align}

* **Legato Ratio.** The proportion of long notes (e.g., duration > 0.5s). A high legato ratio suggests smoother, more connected phrasing.

  \begin{align}
  \text{Legato Ratio} = \frac{\sum_{i=1}^{N} \mathbb{1}(\text{duration}_i > 0.5)}{N}
  \end{align}

### Polyphony Features

* **Polyphony Density.** The average number of overlapping notes. This measures the density of the musical texture, which can be a stylistic characteristic.

  \begin{align}
  \text{Polyphony Density} = \frac{1}{N} \sum_{i=1}^{N} (\text{end}_i - \text{start}_i)
  \end{align}

### Tempo Features

* **Tempo Variability.** The standard deviation of tempo changes. This reflects the variability in the pace of the music.

  \begin{align}
  \text{Tempo Variability} = \sqrt{\frac{1}{N} \sum_{i=1}^{N} (\text{tempo}_i - \text{Average Tempo})^2}
  \end{align}

* **Average Tempo.** The mean tempo of the piece in beats per minute (BPM).

  \begin{align}
  \text{Average Tempo} = \frac{1}{N} \sum_{i=1}^{N} \text{tempo}_i
  \end{align}

### Orchestration Features

* **Instrument Diversity.** The number of unique instrument families used in the piece. This directly reflects the composer's choice of instrumentation, which is often era-specific.

### Expressive Features

* **Articulation Variability.** The standard deviation of note durations. This measures how much note lengths vary, providing insights into the composer's articulation style.

  \begin{align}
  \text{Articulation Variability} = \sqrt{\frac{1}{N} \sum_{i=1}^{N} (\text{duration}_i - \text{Average Duration})^2}
  \end{align}

* **Dynamic Variability.** The standard deviation of note velocities. This reflects the variability in dynamic levels, capturing the expressiveness of the composer.

  \begin{align}
  \text{Dynamic Variability} = \sqrt{\frac{1}{N} \sum_{i=1}^{N} (\text{velocity}_i - \text{Average Velocity})^2}
  \end{align}

### Pitch Class Features

* **Pitch Class Histogram.** The distribution of pitch classes (0-11), representing the frequency of each pitch class. This provides a visual representation of the composer's preferred melodic patterns.

### Interval Features

* **Interval Histogram.** The distribution of pitch intervals, representing the frequency of each interval. This feature captures the composer's melodic vocabulary, identifying commonly used intervallic jumps.

### Additional Features

* **Pitch Entropy.** The entropy of pitch distribution, calculated using the Shannon entropy formula. Higher entropy values suggest greater variability and complexity in pitch choices.

  \begin{align}
  H = -\sum_{i=1}^{k} p_i \log_2(p_i)
  \end{align}
  where \( p_i \) is the probability of the \( i \)-th pitch.

* **Duration Entropy.** The entropy of duration distribution.

* **Velocity Entropy.** The entropy of velocity distribution.

* **Key Changes.** The number of key changes in the piece.

* **Tempo Changes Count.** The number of tempo changes in the piece.

* **Pitch Skewness.** The skewness of pitch distribution, indicating the asymmetry of the distribution.

* **Pitch Kurtosis.** The kurtosis of pitch distribution, indicating the "tailedness" of the distribution.

* **Contour Direction.** The sum of the signs of pitch differences, indicating the overall direction of the melodic contour.

  \begin{align}
  \text{Pitch Skewness} &= \frac{1}{N} \sum_{i=1}^{N} \left( \frac{\text{pitch}_i - \text{Average Pitch}}{\text{Pitch Std}} \right)^3 \\
  \text{Pitch Kurtosis} &= \frac{1}{N} \sum_{i=1}^{N} \left( \frac{\text{pitch}_i - \text{Average Pitch}}{\text{Pitch Std}} \right)^4 - 3 \\
  \text{Contour Direction} &= \sum_{i=1}^{N-1} \text{sign}(\text{pitch}_{i+1} - \text{pitch}_i)
  \end{align}
