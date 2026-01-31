# Xenit ai
1. Problem Statement
Modern web browsing involves repetitive manual tasks such as filling out redundant forms, drafting emails, and navigating complex interfaces. Additionally, the increasing prevalence of intrusive advertisements degrades user experience and performance. XeNit Browser aims to solve these issues by integrating an AI assistant directly into the browser core to automate productivity tasks and a built-in ad-blocking engine to ensure a fast, clean browsing experience.

2. Simple Architecture Diagram
UI Layer (PyQt6): Handles the window management, tab system, and custom styling.

Browser Engine (QtWebEngine/Chromium): The core rendering engine for displaying web content.

AI Agent (Python/LLM): Injects scripts via runJavaScript to interact with the DOM for form-filling and content generation.

Network Interceptor: Uses QWebEngineUrlRequestInterceptor to block ad-related URLs before they load.

3. Tech Stack
Language: Python 3.10+

GUI Framework: PyQt6 (Standard for robust desktop apps).

Browser Core: PyQt6-WebEngine (Based on Chromium).

AI Integration: (Suggested: LangChain or Gemini API for the "Agent" capabilities).

Styling: CSS-based QSS (Qt Style Sheets).

4. Setup Instructions
To set up the development environment, follow these steps:

Clone the repository:

Bash

git clone https://github.com/your-repo/xenit-browser.git
cd xenit-browser
Create a virtual environment:

Bash

python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
Install dependencies:

Bash

pip install PyQt6 PyQt6-WebEngine


5. AI Tools & Prompt Strategy
AI Tools Used: Used for generating the initial browser scaffold, optimizing OpenGL performance settings in main.py, and drafting DOM injection scripts for the form-filler.

Prompt Strategy: * Contextual Specification: Providing specific PyQt6 class requirements to ensure compatibility with high-DPI displays.

Iterative Refinement: Testing various AA_UseDesktopOpenGL configurations to find the smoothest rendering for WebGL-heavy sites.


6. Build Reproducibility 
To ensure the build is reproducible across different machines:

Pinning Dependencies: We use a requirements.txt with exact versions.

Environment Isolation: All execution must occur within the venv to prevent system-level library conflicts.

Hardware Acceleration: The main.py explicitly sets AA_ShareOpenGLContexts to ensure consistent GPU behavior across different hardware.

To reproduce the environment exactly:

Bash

pip install -r requirements.txt --require-hashes



7. Final Output
The final application is a high-performance desktop browser that features:

High DPI Scaling: Sharp UI on 4K/Retina displays.

AI Integration: A sidebar or shortcut that triggers autonomous form-filling.

Ad-Blocker: Native blocking of trackers and banner ads using URL interception.
