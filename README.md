# 🖼️ AI Image Enhancer

A React-based web application that allows users to upload an image and get an AI-enhanced version within seconds. Built with a clean, responsive UI and real-time feedback using a loading spinner and a polling mechanism.

---

## 🚀 Features

- Upload an image and get a higher quality version enhanced by AI.
- Uses Axios for API integration with an external enhancement service.
- Shows real-time loading indicator while processing.
- Clean and responsive UI with Tailwind CSS.
- Error handling for failed enhancements or network issues.

---

## 🧠 How It Works

1. User uploads an image using the UI.
2. The image is sent to the AI Image Enhancement API (`https://techhk.aoscdn.com/api/tasks/visual/scale`) via a POST request.
3. In return, the API sends a `task_id` which is used to **poll** the API every 2 seconds to check the status of the enhancement.
4. When enhancement is complete (`state !== 4`), the enhanced image URL is returned and shown to the user.
5. A loading spinner is displayed until the enhanced image is ready.

---

## 🧰 Tech Stack

- **Frontend**: React.js
- **Styling**: Tailwind CSS
- **HTTP Requests**: Axios
- **API**: TechHK Image Enhancement API
- **State Management**: React Hooks (`useState`)
- **File Uploads**: JavaScript FormData

---

## 🌐 API Key Setup

1. Create a `.env` file in the root directory.
2. Add your API key like this:
```env
VITE_ENHANCE_API_KEY=your_actual_api_key_here
```

Access it in your code:
```const API_KEY = import.meta.env.VITE_ENHANCE_API_KEY;```


Project Structure:

├── public/
├── src/
│   ├── components/
│   │   ├── Home.jsx
│   │   ├── ImageUpload.jsx
│   │   ├── ImagePreview.jsx
│   │   ├── Loading.jsx
│   ├── utils/
│   │   └── enhanceImageApi.js
│   ├── App.js
│   └── main.jsx
├── .env
├── .gitignore
├── package.json
└── README.md


 Run Locally:
   ``` npm install```
   ``` npm run dev```

⚠️ Note
Only image files (JPG/PNG) are supported.
You need a valid API key from techhk.aoscdn.com to use the enhancer.
You can customize the retry delay, max retry attempts, and error messages inside enhanceImageApi.js.






