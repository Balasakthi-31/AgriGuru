
AgriGuru - Smart Farming Assistant
==================================

🌱 Overview:
------------
AgriGuru is an integrated agriculture advisory system built using Flask, TensorFlow, and HTML/JS. It helps farmers by providing:
- 🪲 Pest Detection (via image)
- 🌾 Crop Sale Management (saved to Excel)
- ⛅ Weather Information (GPS/manual)
- 🌱 Crop Recommendation (via ML model)
- 🧑‍🌾 Multi-language support in frontend

📁 Project Structure:
---------------------
AgriGuru/
├── backend/
│   ├── app.py                   # Main Flask app
│   ├── routes/
│   │   ├── crop.py              # Crop recommendation logic
│   │   └── weather.py           # Weather info logic
│   ├── models/
│   │   ├── pest_model.keras     # Pest classification model
│   │   ├── class_indices.json   # Class labels
│   │   ├── pest_advice.json     # Cure/solution for pests
│   │   └── crop_model.pkl       # ML model for crop recommendation
│   └── sales_data.xlsx          # Auto-created file storing crop sale info
├── frontend/
│   ├── index.html               # Location + intent selection
│   ├── crop.html                # Crop recommendation UI
│   ├── dashboard.html           # Weather & pest dashboard
│   ├── sell-crop.html           # Crop selling page
│   ├── language.js              # Language toggle script
│   └── script.js                # Location & intent handling

⚙️ Requirements:
----------------
Install Python 3.9+ and use a virtual environment.
Install required packages:

    pip install flask flask-cors tensorflow pillow openpyxl scikit-learn joblib

🚀 How to Run Backend:
----------------------
1. Activate your virtual environment:
    - Windows:    venv\Scripts\activate
    - Mac/Linux:  source venv/bin/activate

2. Navigate to backend directory:
    cd backend

3. Run the app:
    python app.py

4. Server runs at:
    http://127.0.0.1:5000

🌾 Crop Sale API:
------------------
- Endpoint: /submit-sale
- Method: POST
- Payload (JSON):
    {
        "crop": "Potato",
        "amount": "50",
        "phone": "9876543210"
    }
- Saves entry to sales_data.xlsx

🪲 Pest Detection API:
-----------------------
- Endpoint: /detect
- Method: POST (form-data)
- Key: image (as image file)
- Returns: Pest name and advice

⛅ Weather API:
---------------
- Endpoint: /weather?lat=22.57&lon=88.36
- Method: GET
- Returns: Weather data for the given location (mock or real)

🌐 Frontend Usage:
-------------------
1. Open frontend/index.html in a browser.
2. Choose location (GPS or manual).
3. Select your intent (recommendation or dashboard).
4. Use crop.html, dashboard.html, or sell-crop.html accordingly.

🧠 Notes:
---------
- All predictions rely on trained ML models inside the models/ folder.
- Make sure to place proper .keras, .json, .pkl model files before starting.
- Crop sale data will be saved even offline in sales_data.xlsx.

📦 Model Download:
------------------
Due to GitHub file size limits, download the pest detection model from:

🔗 https://drive.google.com/file/d/1g0FSWTzsoyFMAsituB6YXlaa4nWYDHJU/view?usp=sharing
After downloading, place it inside the models folder:
→ backend/models/pest_model.keras


👨‍💻 Developed By:
---------------------
AgriGuru Devolt Team
---------------------
Team Lead: 
P.P.Gowri Shankar
------------------
Team Members:
 1.K.Maha
 2.R.Balasakthi
 ------------------