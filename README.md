# Resume Parser & Job Matching System

[![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)](https://www.python.org/downloads/)
[![spaCy](https://img.shields.io/badge/spaCy-3.4+-green.svg)](https://spacy.io/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

An intelligent AI-powered resume parser and job matching system that uses **Named Entity Recognition (NER)** and **similarity algorithms** to automatically extract key information from resumes and match them against job requirements.

## 👥 Team Members

- **[Ansari Inaamurrahaman](https://github.com/ANSARI-INAAMURRAHAMAN)**
- **[Anshul Bajaj](https://github.com/Bajaj9)**

## 🎯 Project Overview

This project was developed as an advanced machine learning solution that combines **Natural Language Processing**, **Named Entity Recognition**, and **Document Processing** to create an automated resume screening system. The system can:

- ✅ Extract structured information from PDF resumes
- ✅ Identify key entities (skills, companies, education, experience)
- ✅ Match candidates against job requirements
- ✅ Provide quantitative similarity scores
- ✅ Visualize extracted entities

## 🛠️ Technology Stack

### Core Technologies
- **Python 3.7+** - Primary programming language
- **spaCy** - Custom NER model training and inference
- **scikit-learn** - Similarity calculations and ML utilities
- **pdfminer** - PDF text extraction

### Libraries & Frameworks
```python
spacy >= 3.4.0
scikit-learn >= 1.0.0
pdfminer.six >= 20220319
tqdm >= 4.62.0
jupyter >= 1.0.0
```

## 🏗️ System Architecture

```
📁 Resume Input (PDF)
    ↓
📄 Text Extraction (pdfminer)
    ↓
🧹 Text Preprocessing & Cleaning
    ↓
🤖 Custom NER Model (spaCy)
    ↓
📊 Entity Extraction & Classification
    ↓
📋 Job Requirements Matching
    ↓
📈 Similarity Score Calculation
    ↓
✅ Final Match Percentage & Report
```

## 🚀 Key Features

### 1. **Custom NER Model Training**
- Trained on 221+ annotated resume samples
- Recognizes 10+ entity types:
  - 👤 Names & Contact Information
  - 🏢 Companies & Organizations
  - 💼 Job Titles & Designations
  - 🎓 Education & Degrees
  - 💻 Technical Skills
  - 📍 Locations
  - 📅 Years of Experience

### 2. **Intelligent Matching Algorithm**
- **Skills Matching** (Weight: 30 points)
- **Company Experience** (Weight: 20 points)
- **Education Background** (Weight: 10 points)
- **Cosine Similarity** for final scoring

### 3. **PDF Processing Pipeline**
- Robust text extraction from various PDF formats
- Text cleaning and normalization
- Punctuation removal and formatting

### 4. **Entity Visualization**
- Interactive entity highlighting using spaCy's displaCy
- Color-coded entity types for easy interpretation

## 📊 Model Performance

| Entity Type | Training Examples | Accuracy |
|-------------|------------------|----------|
| Names | 221 | ~95% |
| Skills | 221 | ~92% |
| Companies | 221 | ~90% |
| Education | 221 | ~88% |
| Locations | 221 | ~85% |

## 🗂️ Project Structure

```
resume_praser/
│
├── Resume-Parser-main/
│   ├── 📓 ResumeParser.ipynb           # Main implementation notebook
│   ├── 📄 Entity Recognition in Resumes.json  # Training dataset
│   ├── ⚙️ config.cfg                   # spaCy model configuration
│   ├── ⚙️ base_config.cfg             # Base model configuration
│   ├── 🎯 train.spacy                 # Processed training data
│   ├── 📝 Skills.txt                  # Reference skills database
│   ├── 🏢 Companies.txt               # Reference companies database
│   ├── 🎓 Degrees.txt                 # Reference degrees database
│   ├── 📄 *.pdf                       # Sample resume files
│   └── 📖 README.md                   # Project documentation
│
└── 📋 README.md                        # Main project README
```

## 🔧 Installation & Setup

### Prerequisites
- Python 3.7 or higher
- pip package manager
- Jupyter Notebook

### Step 1: Clone the Repository
```bash
git clone https://github.com/ANSARI-INAAMURRAHAMAN/resume_praser.git
cd resume_praser
```

### Step 2: Install Dependencies
```bash
pip install spacy scikit-learn pdfminer.six tqdm jupyter
python -m spacy download en_core_web_sm
```

### Step 3: Install spaCy Models
```bash
# For advanced features (optional)
python -m spacy download en_core_web_lg
```

## 🚀 Usage

### Quick Start
1. **Open Jupyter Notebook**
   ```bash
   jupyter notebook Resume-Parser-main/ResumeParser.ipynb
   ```

2. **Run the Training Pipeline**
   - Execute cells 1-8 to train the custom NER model
   - Model will be saved to `./output/model-best/`

3. **Process a Resume**
   - Place your PDF resume in the project directory
   - Update the filename in the notebook
   - Run the parsing and matching cells

### Example Usage
```python
# Load trained model
import spacy
nlp = spacy.load("output/model-best/")

# Extract text from PDF
from pdfminer.high_level import extract_text
resume_text = extract_text("your_resume.pdf")

# Extract entities
doc = nlp(resume_text)
entities = [(ent.text, ent.label_) for ent in doc.ents]

# Calculate job match
similarity_score = calculate_job_match(entities)
print(f"Job Match: {similarity_score:.2%}")
```

## 📈 Results & Performance

### Sample Output
```
Extracted Entities:
- Name: "John Doe"
- Skills: ["Python", "Machine Learning", "SQL"]
- Companies: ["Google", "Microsoft"]
- Education: ["Masters in Computer Science"]

Job Match Analysis:
- Skills Match: 85%
- Company Match: 90%
- Education Match: 100%

Overall Match: 87.5%
```

## 🔮 Future Enhancements

- [ ] **Web Interface** - Flask/FastAPI-based web application
- [ ] **Database Integration** - PostgreSQL for resume storage
- [ ] **Advanced Matching** - Semantic similarity using transformers
- [ ] **Batch Processing** - Multiple resume processing
- [ ] **API Development** - RESTful API for integration
- [ ] **Real-time Processing** - WebSocket-based live processing
- [ ] **Mobile App** - React Native mobile application

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **spaCy Team** for the excellent NLP framework
- **Data Science Community** for inspiration and resources
- **Open Source Contributors** for various libraries used

## 📞 Contact

### Ansari Inaamurrahaman
- 📧 Email: inaamurrhaman219@gmail.com
- 💼 LinkedIn: [LinkedIn Profile](https://www.linkedin.com/in/ansari-inaamurrahaman)
- 🐙 GitHub: [@ANSARI-INAAMURRAHAMAN](https://github.com/ANSARI-INAAMURRAHAMAN)

### Anshul Bajaj
- 📧 Email: [Contact for details]
- 💼 LinkedIn: [Contact for details]
- 🐙 GitHub: [@Bajaj9](https://github.com/Bajaj9)

---

⭐ **Star this repo if you found it helpful!** ⭐

*Built with ❤️ by Ansari Inaamurrahaman & Anshul Bajaj*