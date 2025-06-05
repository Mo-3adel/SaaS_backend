# AI-Powered Document-to-Presentation Backend (Django REST API)

This is the backend for a SaaS application that enables users to upload documents (PDF, DOCX, TXT, images), extract their content, process it using **Google Gemini AI**, and generate structured PowerPoint slides. Users can then download the final `.pptx` file — all through a Django REST API.

## 🚀 Key Features

- **User Authentication**  
  Secure user registration and login via Django REST Framework.

- **File Uploads**  
  Upload PDF, DOCX, TXT, or image files. Files are saved and tracked in the database.

- **Content Extraction**  
  Extracts text and images using `PyMuPDF`, `PyPDF2`, and `Pillow`.

- **AI Processing (Google Gemini)**  
  Extracted content is sent to Google Gemini AI, which returns structured slide data.

- **PowerPoint Generation**  
  Uses `python-pptx` to generate `.pptx` files based on AI output.

- **Media Management**  
  Uploaded files and generated presentations are stored in a `/media` directory.

- **RESTful API**  
  All operations are available as REST endpoints via Django REST Framework.

---

## 🧱 Project Structure

📁 backend/
├── backend/ # Django settings and URL config
├── uploads/ # File upload, extraction, AI, and PowerPoint logic
├── userbase/ # User authentication and serializers
├── media/ # Uploaded files and generated .pptx files
├── config.py # API key settings (Google Gemini)
├── manage.py # Django management script
└── README.md


---

## ⚙️ Getting Started

### 1. Create & activate a virtual environment

```bash
python -m venv venv
source venv/bin/activate  # or .\venv\Scripts\activate on Windows

2.Install dependencies
pip install -r requirements.txt

3. Configure your API key
In config.py, add your Google Gemini API key:

GEMINI_API_KEY = "your-api-key-here"

4. Apply migrations
python manage.py migrate

5. Run the development server
python manage.py runserver

🔌 API Endpoints
| Method | Endpoint                           | Description                           |
| ------ | ---------------------------------- | ------------------------------------- |
| `POST` | `/auth/register/`                  | Register a new user                   |
| `POST` | `/auth/login/`                     | Log in an existing user               |
| `POST` | `/uploads/uploads/`                | Upload a document and generate slides |
| `GET`  | `/media/generated_pptx/<filename>` | Download generated PowerPoint         |


📁 Notes

All uploaded and generated files are stored in the media/ folder.
Ensure your Google Gemini API key is properly set in config.py.
For production:
Use cloud storage for media
Secure API keys using environment variables
Add authentication and permissions

📄 License

This project is licensed under the MIT License.
Feel free to fork, use, and extend it!
