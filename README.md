# 🎵 Song Vector Explorer

[![Python](https://img.shields.io/badge/Python-3.12+-blue.svg)](https://python.org)
[![OpenAI](https://img.shields.io/badge/OpenAI-Embeddings-green.svg)](https://openai.com)
[![TensorBoard](https://img.shields.io/badge/TensorBoard-Visualization-orange.svg)](https://tensorboard.dev)

**Explore song lyrics as interactive 3D vector spaces using OpenAI embeddings and TensorBoard visualization.**

Transform your favorite songs into navigable semantic landscapes where similar lyrical themes naturally cluster together. Discover hidden patterns in musical storytelling through the power of AI embeddings.

## ✨ Features

- 🎭 **Multi-Artist Support**: Analyze lyrics from different artists and genres
- 🌌 **3D Vector Visualization**: Interactive exploration of semantic relationships
- 🎯 **Smart Clustering**: Similar themes automatically group together
- 📊 **Cross-Song Analysis**: Compare lyrical patterns across different songs
- 🔍 **Search & Filter**: Find specific lyrics in the vector space
- 🎨 **Artist Comparison**: Visualize how different artists approach similar themes

## 🚀 Quick Start

### Prerequisites

- Python 3.12+
- OpenAI API key
- [uv](https://github.com/astral-sh/uv) (recommended) or pip

### Installation

```bash
git clone https://github.com/Siddhant-K-code/song-vector-explorer.git
cd song-vector-explorer
uv sync
```

### Setup

1. **Set your OpenAI API key:**
   ```bash
   export OPENAI_API_KEY="your-api-key-here"
   ```

2. **Add lyrics:** Place your `.txt` files in the appropriate folders:
   ```
   assets/lyrics/
   ├── the-weeknd/
   │   ├── die-for-you.txt
   │   ├── after-hours.txt
   │   └── blinding-lights.txt
   ├── drake/
   │   └── gods-plan.txt
   └── shakira/
       └── hips-dont-lie.txt
   ```

3. **Generate embeddings:**
   ```bash
   uv run python src/embedding.py
   ```

4. **Create visualization:**
   ```bash
   uv run python src/visualize.py
   ```

5. **Launch TensorBoard:**
   ```bash
   uv run tensorboard --logdir=logs
   # or use the shortcut
   uv run task serve
   ```

6. **Open your browser** and navigate to `http://localhost:6006`

## 🎯 How It Works

1. **Lyrics Processing**: Each line of lyrics is processed individually
2. **AI Embeddings**: OpenAI's `text-embedding-3-large` model converts lyrics to high-dimensional vectors
3. **Vector Storage**: Embeddings are saved as NumPy arrays for efficient processing
4. **Visualization**: TensorBoard's projector displays the multi-dimensional space in 3D
5. **Interactive Exploration**: Navigate, search, and analyze the semantic landscape

## 📁 Project Structure

```
song-vector-explorer/
├── src/
│   ├── embedding.py      # Generate embeddings from lyrics
│   └── regist.py         # Create TensorBoard visualization
├── assets/
│   ├── lyrics/           # Song lyrics organized by artist
│   ├── vectors/          # Generated embedding vectors
│   └── metadata/         # Song and artist metadata
├── logs/                 # TensorBoard log files
├── pyproject.toml        # Project dependencies
└── README.md            # This file
```

## 🎨 What You'll Discover

### Musical Themes Clustering
- **Love & Relationships**: Romantic lyrics cluster together
- **Success & Ambition**: Achievement-focused lyrics form distinct groups
- **Party & Celebration**: Upbeat, energetic lyrics gather in their own space
- **Introspection**: Reflective, personal lyrics create contemplative clusters

### Artist Comparisons
- **The Weeknd**: Dark romance, nightlife, emotional complexity
- **Drake**: Success narratives, vulnerability, Toronto references
- **Shakira**: Dance, celebration, Latin cultural themes

### Cross-Genre Analysis
- See how different genres approach similar themes
- Identify unique linguistic patterns per artist
- Discover unexpected connections between songs

## 🛠️ Advanced Usage

### Adding New Artists

1. Create a new folder in `assets/lyrics/`
2. Add `.txt` files with song lyrics
3. Run the embedding and registration process
4. Explore the updated visualization

### Customizing Embeddings

Edit `src/embedding.py` to:
- Use different OpenAI models
- Adjust preprocessing steps
- Add custom metadata fields

### Visualization Options

In TensorBoard's Projector:
- **PCA**: Linear dimensionality reduction
- **t-SNE**: Non-linear clustering visualization
- **UMAP**: Balanced approach for structure preservation

## 🔧 Configuration

### Environment Variables
```bash
OPENAI_API_KEY=your-api-key-here
```

### Dependencies
- `numpy>=2.3.0` - Numerical computing
- `openai>=1.86.0` - AI embeddings
- `tensorboard>=2.19.0` - Visualization
- `torch>=2.7.1` - Tensor operations

## 📊 Example Analysis

**Expected Clustering Patterns:**

🎵 **The Weeknd Songs:**
- Dark, moody themes cluster in one region
- Relationship complexity forms sub-clusters
- Nightlife references create distinct groupings

🎤 **Drake Songs:**
- Success themes cluster together
- Emotional vulnerability forms separate groups
- Toronto/Canadian references create unique clusters

💃 **Shakira Songs:**
- Dance and celebration themes cluster prominently
- Latin cultural references form distinct groups
- Confidence and empowerment create strong clusters

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🔗 Links

- [OpenAI Embeddings Documentation](https://platform.openai.com/docs/guides/embeddings)
- [TensorBoard Projector Guide](https://www.tensorflow.org/tensorboard/tensorboard_projector_plugin)

---

**Made with ❤️ for music and AI enthusiasts**
