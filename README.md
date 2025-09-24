# Chemical-Reaction-Mechanism

## AI Chemistry Visualizer step by step mechanism


![Language](https://img.shields.io/badge/Code-HTML%2C%20CSS%2C%20JS-blue)
![License](https://img.shields.io/badge/License-MIT-green)

An interactive, AI-powered web application for visualizing complex chemical reaction mechanisms. This tool streamlines the process of learning and teaching chemistry by converting natural language topics into dynamic, narrated animations.

---

### Live Demo

**[View Live Demo](https://your-username.github.io/AI-Chemistry-Visualizer/)** 
*(Note: Replace with your actual GitHub Pages link after deployment.)*

---

### Screenshot

 
*(Replace this with a high-quality screenshot or GIF of your application in action.)*

---

## Core Features

-   **AI Prompt Generation:** Enter a chemistry topic (e.g., "SN2 reaction") to generate a detailed, structured prompt for a large language model (LLM).
-   **Automatic JSON Parsing:** Simply paste the entire response from an AI, and the application automatically finds, validates, and uses the largest valid JSON object it contains.
-   **Interactive Canvas:** The visualization is rendered on a p5.js canvas that you can pan by clicking and dragging or using your mouse wheel.
-   **Step-by-Step Playback:** Control the animation with play, pause, next, and previous step buttons.
-   **Text-to-Speech Narration:** Each step of the mechanism is narrated using the browser's built-in Web Speech API for an enhanced learning experience.
-   **Modern UI:** A clean, responsive interface featuring a collapsible sidebar and glassmorphism effects for all controls.

## How It Works (Workflow)

The application is designed for a simple, streamlined workflow:

1.  **Enter Topic:** Open the sidebar and type a chemical reaction topic into the input field (e.g., "E2 elimination of 2-bromobutane").
2.  **Generate & Copy Prompt:** Click the "Generate AI Prompt" button. The app creates a detailed prompt. Copy it to your clipboard.
3.  **Use an AI:** Paste the prompt into your preferred AI chatbot (like Perplexity, ChatGPT, Gemini, etc.) and get its response.
4.  **Paste Response:** Copy the entire text response from the AI and paste it back into the application's "AI Response" text area.
5.  **Visualize:** Click the "Start Visualization" button. The app automatically filters the pasted text to find the mechanism JSON, validates it, and renders the interactive animation.

## Technology Stack

This project is built with modern web technologies and avoids any backend or build steps, making it incredibly simple to run and deploy.

| Technology        | Purpose                                                              |
| ----------------- | -------------------------------------------------------------------- |
| **HTML5**         | Provides the core structure and layout of the application.           |
| **CSS3**          | Handles all styling, including the glassmorphism UI and responsiveness. |
| **JavaScript (ES6+)** | Powers all application logic, DOM manipulation, and user interactions. |
| **p5.js**         | A JavaScript library used for rendering the interactive visualization.  |
| **Web Speech API**| A browser API used for the text-to-speech narration feature.         |
| **Bootstrap Icons** | Provides the clean and modern icons used throughout the interface.   |

## Local Setup

Running this project locally is very simple:

1.  Clone the repository:
    ```bash
    git clone https://github.com/your-username/AI-Chemistry-Visualizer.git
    ```
2.  Navigate to the directory:
    ```bash
    cd AI-Chemistry-Visualizer
    ```
3.  Open the `index.html` file in a modern web browser (like Chrome, Firefox, or Edge).

> **Important Note:** For the "Paste from Clipboard" and "Text-to-Speech" features to work reliably, you should open the `index.html` file via a local web server. Many code editors (like VS Code with the "Live Server" extension) can do this easily. Browsers often restrict these APIs on files opened directly from the local filesystem (`file:///...`).

## AI Prompt Structure

The core of this application's AI integration is the detailed and structured prompt it generates. This ensures the AI returns data in a predictable format that the visualizer can parse.

<details>
<summary>Click to see the detailed AI Prompt Structure</summary>

```json
{
  "meta": {
    "reactionName": "Complete reaction name",
    "reactionType": "Mechanism type",
    // ... other metadata
  },
  "conditions": {
    "temperature": {
      "value": 298,
      "unit": "K",
      // ... other conditions
    }
  },
  "mechanism": [
    {
      "step": 1,
      "title": "Step title",
      "narration": "Clear 2-3 sentence explanation for text-to-speech",
      "description": "Detailed technical description",
      "actions": [
        {
          "type": "ELECTRON_ARROW",
          "from": {"x": 300, "y": 250},
          "to": {"x": 450, "y": 280},
          "controlPoint": {"x": 375, "y": 220},
          // ... other action properties
        }
      ]
    }
  ],
  "molecules": {
    "molecule_id": {
      "name": "Molecule Name",
      "atoms": [
        {
          "id": "C1",
          "element": "C",
          "position": {"x": 400, "y": 300}
        }
      ],
      "bonds": [
        {
          "id": "bond1",
          "from": "C1",
          "to": "C2",
          "type": "single"
        }
      ]
    }
  }
}
