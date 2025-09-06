# Style Finder: Multimodal Fashion Analysis & Retrieval

This project is a multimodal AI application that analyzes fashion images, finds visually similar outfits, and suggests affordable alternatives from online stores. It combines computer vision, large language models, and web search to deliver an interactive fashion analysis experience.

## Features

- **Image Analysis:** Upload a fashion image to extract visual features using a pre-trained ResNet50 model.
- **Similarity Matching:** Finds the closest matching outfit from a curated dataset using cosine similarity.
- **AI-Powered Description:** Uses IBM watsonx Llama 3.2 Vision Instruct model to generate detailed, educational fashion analysis.
- **Shopping Alternatives:** Integrates with SerpAPI to search for similar items online and present affordable alternatives.
- **Interactive Gradio UI:** User-friendly web interface for uploading images, viewing results, and exploring example outfits.

## Project Structure

```
.
├── app.py                  # Main Gradio application
├── config.py               # Configuration settings
├── requirements.txt        # Python dependencies
├── README.md               # Project documentation
├── models/
│   ├── image_processor.py  # Image encoding and similarity logic
│   └── llm_service.py      # LLM (Llama Vision) service integration
├── services/
│   └── search_service.py   # SerpAPI-based product search
├── utils/
│   └── helpers.py          # Utility functions
├── examples/               # Example images for demo
│   ├── test-6.png
│   └── test-7.png
└── swift-style-embeddings.pkl # (Not included) Fashion dataset with embeddings
```

## Setup Instructions

1. **Clone the Repository**

   ```sh
   git clone <repo-url>
   cd style-finder
   ```

2. **Install Dependencies**

   It is recommended to use a virtual environment.

   ```sh
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   pip install -r requirements.txt
   ```

3. **Prepare the Dataset**

   - Place your `swift-style-embeddings.pkl` file (fashion dataset with precomputed embeddings) in the project root directory.

4. **Configure API Keys**

   - For full functionality (shopping alternatives), obtain a [SerpAPI](https://serpapi.com/) key.
   - Set your SerpAPI key as an environment variable or modify `app.py` to pass it to `StyleFinderApp`.

5. **Run the Application**

   ```sh
   python app.py
   ```

   The Gradio interface will launch locally at [http://127.0.0.1:5000](http://127.0.0.1:5000).

## Usage

- **Upload an Image:** Use the Gradio UI to upload a fashion image or select an example.
- **Analyze Style:** Click "Analyze Style" to receive a detailed breakdown and shopping alternatives.
- **Explore Results:** Review the AI-generated analysis and links to similar products.

## Customization

- **Model & API Settings:** Adjust model IDs, region, and thresholds in [`config.py`](config.py).
- **Dataset:** Replace `swift-style-embeddings.pkl` with your own dataset for different fashion domains.

## Dependencies

See [`requirements.txt`](requirements.txt) for the full list.

Key packages:
- `torch`, `torchvision`, `pillow`, `scikit-learn`, `pandas`, `numpy`
- `ibm-watsonx-ai` (for Llama Vision)
- `google-search-results` (for SerpAPI)
- `gradio` (for the web UI)

## License

This project is for educational purposes. See the repository for license details.

---

**Acknowledgments:**  
Built as part of the IBM RAG Agentic AI Certification course on