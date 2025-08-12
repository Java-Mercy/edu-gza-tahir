# edu-gza-tahir


#  Software Requirements Specification

## 1. Introduction

### 1.1 Purpose
The goal of this project is to develop a **peer-to-peer educational storytelling application** designed for children in Gaza, where the education system is severely disrupted. The app will use **Ollama LLM models** to generate interactive, culturally relevant, and age-appropriate stories that help children learn new languages through engaging narratives.

### 1.2 Scope
- **Target Users**:
   Children (ages 5–14) in Gaza with limited or no access to formal education.
- **Core Idea**:
  Use **offline peer-to-peer (P2P)** networking to share educational content without requiring internet connectivity. :)
- **Primary Learning Method**:
  Story-based language learning.
- **Technology Stack**:
   Mobile application (Android-first, optional iOS later), Ollama LLM, local storage, P2P networking (Bluetooth, local Wi-Fi mesh).



## 2. Functional Requirements

### 2.1 Story Generation & Language Learning
-  Generate stories in Arabic and a target language (e.g., English) using Ollama LLM.
-  Provide bilingual story display with side-by-side translation.
-  Include audio narration for both languages (text-to-speech).
-  Adapt stories to child’s reading level and age.
-  Allow children to choose topics (animals, history, culture, science).
-   Create stories based on Gaza’s folklore, historical events, and local heroes.

### 2.2 Peer-to-Peer Content Sharing
-  Share stories between devices using P2P networking without the internet.
-  Allow offline storage of received stories.
-  Auto-sync new stories when two devices are near each other.

### 2.3 Interactive Learning Features
-  Include vocabulary highlight & tap-to-translate.
-  Add quizzes or games at the end of each story.
-  Track child’s progress (words learned, stories completed).
-  Award badges and achievements to motivate learning.

### 2.4 Teacher/Parent Involvement
-  Allow parents/volunteers to add their own stories.
-  Approve or filter AI-generated stories for appropriateness.
-  View child’s progress reports.

---

## 3. Non-Functional Requirements

### 3.1 Usability
-  Simple, child-friendly interface with large icons and minimal text.
-  Support offline-first usage.
-  Provide multilingual UI (Arabic + English).

### 3.2 Performance
-  Story generation should complete within **30 seconds** on local devices or edge servers.
-  P2P file transfer speed should support at least **500 KB/s** for smooth story sharing.

### 3.3 Security & Privacy
-  All data stored locally; no personal data sent to external servers.
-  Provide story content moderation to avoid harmful or culturally inappropriate content.
-  Encrypt data transfers between devices.

### 3.4 Reliability
-  The app should operate with **99% uptime** in offline mode.
-  Handle network dropouts gracefully.

### 3.5 Scalability
-  Support at least **1000 stories** stored locally without performance degradation.
-  Allow easy integration of other AI models if Ollama is replaced.

### 3.6 Maintainability
-  Code should follow modular architecture for easier updates.
-  Support adding new languages without major code changes.

---

## 4. Assumptions & Constraints
- Children may have access to only basic Android devices.
- Internet access may be unavailable most of the time.
- App must work **fully offline** except when downloading new models or updates.
- Stories must be culturally sensitive and free of political bias.

---

## 5. Future Enhancements
- **Multi-device story collaboration** (children write stories together).
- **AR/VR immersive storytelling** for richer engagement.
- **AI voice mimicry** to use familiar voices for narration.
- **Gamified story challenges** between peers.


### 2.5 Exercises, Quizzes & Assessments

**Narration:**  
To make learning more interactive and measurable, the application will include a dedicated **Exercises & Assessment module**. After reading or listening to a story, children will complete small quizzes, word-matching games, and comprehension activities. These activities will help reinforce vocabulary, test understanding, and track progress. The assessments will be adaptive — adjusting difficulty based on the child’s performance over time.

**Functional Requirements:**
- Provide multiple-choice questions (MCQs) after each story to test comprehension.
- Include vocabulary matching exercises (word to meaning, picture to word).
- Add “Fill in the Blank” activities using keywords from the story.
-  Offer pronunciation practice, recording the child’s voice and giving feedback.
-  Track quiz scores and maintain a progress dashboard for each learner.
-  Unlock rewards, badges, or new stories when children complete a set of quizzes.
-  Generate custom revision exercises for weak areas based on past performance.
-  Allow teachers/parents to view performance reports and suggest improvement areas.

# Quiz and assessment
-  Quizzes should load within 3 seconds after story completion.
-  Audio and images used in quizzes should be optimized for low-memory devices.
-  Activities should remain playable without internet access.
-  The system should store at least the last 50 quiz results per child locally.
-  





