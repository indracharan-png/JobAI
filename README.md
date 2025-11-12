# JobAI
JobAI - Everything you need to apply to a Job

# File Structure
JobAI/
│
├── frontend-extension/               ← Indra’s Chrome Extension (React + Tailwind + Manifest V3)
│   ├── manifest.json
│   ├── package.json
│   ├── vite.config.js
│   └── src/
│       ├── popup/
│       │   ├── Popup.jsx
│       │   ├── App.jsx
│       │   └── popup.css
│       ├── content/
│       │   └── content.js            ← Extract job description from LinkedIn
│       ├── components/
│       │   ├── ReportCard.jsx
│       │   └── Loader.jsx
│       ├── services/
│       │   └── api.js                ← Sends data to backend API
│       └── styles/
│           └── tailwind.css
│
│
├── backend-api/                      ← Rohith’s FastAPI backend (main controller)
│   ├── main.py                       ← Entry point for FastAPI server
│   ├── requirements.txt
│   ├── routers/
│   │   └── job_analysis.py           ← API endpoint logic
│   ├── core/
│   │   └── config.py                 ← Configuration / constants
│   ├── utils/
│   │   ├── pdf_generator.py          ← Generate PDF report
│   │   ├── data_parser.py            ← Parse resume & JD text
│   │   └── response_formatter.py     ← Clean structured JSON
│   ├── services/
│   │   ├── model_inference.py        ← Calls Jaideep’s prompt engine & Hugging Face model
│   │   └── prompt_loader.py          ← Loads Jaideep’s prompt templates
│   └── prompts/                      ← Linked folder or copy of Jaideep’s prompts
│       ├── resume_prompts.json
│       ├── outreach_prompts.json
│       └── interview_prompts.json
│
│
├── prompt-engine/                    ← Jaideep’s module (prompt handling + LLM inference)
│   ├── __init__.py
│   ├── prompt_engine.py              ← Combines prompt + user data → calls model
│   ├── model_manager.py              ← Loads Hugging Face model on GPU
│   ├── prompts/
│   │   ├── resume_prompts.json
│   │   ├── outreach_prompts.json
│   │   └── interview_prompts.json
│   ├── notebooks/
│   │   └── prompt_testing.ipynb      ← For local prompt research (not used in production)
│   └── utils/
│       └── text_cleaner.py
│
│
├── shared/                           ← Common resources shared across backend & prompt engine
│   ├── config.yaml                   ← Model paths, API ports, settings
│   ├── constants.py
│   └── logs/
│       └── jobai.log
│
│
├── docs/                             ← Documentation, design files
│   ├── architecture_diagram.png
│   ├── api_flow.md
│   └── setup_instructions.md
│
├── .gitignore
├── README.md
└── LICENSE
