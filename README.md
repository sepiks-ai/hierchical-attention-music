Music, especially Bach's compositions, follows a complex dependency structure: Consider his cantata "Widerstehe doch der Sünde" (Resist sin, then), where motifs introduced in the opening bars find their resolution minutes later, or where harmonic progressions set up expectations that are fulfilled only after extensive development.

Standard token-by-token generative approaches simply cannot capture these relationships. By the time the model reaches the resolution point, the context that set it up has long fallen outside its attention window.

Let's illustrate this with a concrete example from transformer architecture. If we tokenize a Bach cantata into musical elements (notes, chords, rests), we might end up with thousands of tokens. A typical transformer might have an attention window of 2048 or 4096 tokens. But the musical resolution of a motif introduced at the beginning might occur 6000 or 8000 tokens later - well beyond what the model can "see" during generation. This is why merely scaling up the attention window isn't a practical solution for music generation.


The Hierarchical Solution
Our approach tackles this problem by modeling Bach's music as a hierarchical structure with multiple levels of abstraction:

1. Structural Level (Top)
At the highest level, we model the overall musical architecture: the rising and falling arcs, tonal relationships (minor/major shifts), sectional boundaries, and large-scale repetition patterns. These elements form the "skeleton" upon which all other musical details depend.

2. Phrasal Level (Middle)
The middle level captures harmonic progressions, cadential patterns, and motivic development within the constraints established by the structural level. Here we model how Bach develops thematic material and creates meaningful musical sentences.

3. Note Level (Bottom)

Only at the lowest level do we finally generate the individual notes, chords, and rests that make up the actual musical surface—all constrained and guided by the higher-level structures.

https://paulharrald.substack.com/p/towards-solving-the-long-range-dependency






