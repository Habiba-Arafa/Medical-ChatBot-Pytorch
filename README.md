
# Medical Chatbot (Doctor-Patient Dialogue)

This project implements a medical chatbot using a fine-tuned T5 model to generate doctor responses based on patient queries. The backend is built using **Flask** and serves the model via a web interface for easy interaction.

## Features

- **Doctor-Patient Interaction**: Provides AI-generated responses from a doctor based on patient queries.
- **Flask Web Interface**: Simple interface for querying the chatbot via a web page.
- **T5 Model**: Fine-tuned version of the T5 model for conditional text generation.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Setup](#setup)
- [Usage](#usage)
- [Deployment](#deployment)
- [Contributing](#contributing)
- [Limitations](#limitations)
- [License](#license)

## Prerequisites

Before running the project, ensure you have the following installed:

- **Python** 3.6 or later
- **PyTorch** (with CUDA support for GPU acceleration)
- **Flask** web framework
- **Transformers** library from Hugging Face
- **faiss-gpu** for efficient vector search

You can install the necessary dependencies by running the following commands:

```bash
pip install torch flask transformers faiss-gpu
```

## Setup

1. **Clone the Repository**:
    ```bash
    git clone https://github.com/Habiba-Arafa/Medical-ChatBot-Pytorch.git
    cd Medical-ChatBot-Pytorch
    ```

2. **Download the Fine-Tuned T5 Model**:
    - You need a fine-tuned T5 model that is trained for generating doctor responses. Place the model in a folder, and set the path in the code accordingly.

3. **Set Up Templates**:
    Ensure you have a folder named `templates` containing the `index.html` file for the frontend interface. This will allow users to interact with the chatbot.

## Usage

### Running the Flask Application

To run the application locally, use the following command:

```bash
python app.py
```

This will start the Flask application on `http://0.0.0.0:5000/`.

### Interacting with the Chatbot

1. Open the URL in your web browser: `http://localhost:5000/`.
2. Type your query in the input field and press submit.
3. The chatbot will generate a response from the model based on your input.

### Example Queries:
- "What are the symptoms of diabetes?"
- "How can I manage hypertension?"

### Model Input and Output
- **Input**: The model expects the query in the format: `Patient: <query>`
- **Output**: The model generates a response in the format: `Doctor: <response>`

### Sample Interaction:
```bash
Patient: What are the symptoms of flu?
Doctor: Common symptoms include fever, chills, sore throat, fatigue, and body aches.
```

## Deployment

### How to Deploy on a Web Server

1. **Install Dependencies**: Ensure all required libraries are installed (refer to the "Setup" section).
2. **Run the Application**: Start the Flask app with:
    ```bash
    python app.py
    ```
3. The server will be available at your server's IP address, for example, `http://<your-server-ip>:5000/`.


## Contributing

Contributions are welcome! To contribute to the project:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes and commit them.
4. Push to the branch (`git push origin feature-branch`).
5. Create a Pull Request describing your changes.

## Limitations

- **Model Size**: The model is limited by the hardware resources available. For faster and more accurate results, a GPU is highly recommended.
- **Data Limitations**: The model is trained on a smaller dataset compared to available large datasets (45,000 queries instead of 2 million). The quality and variety of responses might be impacted by this.
- **Domain-Specific Knowledge**: The chatbot may not always provide accurate medical advice, as it is trained only on general datasets and might lack deep medical expertise.
- **Response Generation Time**: Depending on server load and model size, response time may vary.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
