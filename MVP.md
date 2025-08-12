# Gaza Story Learning App - MVP 


This Minimum Viable Product is an offline-first mobile app that delivers short, culturally-rooted audio stories (seeded and LLM-assisted) followed by mini-quizzes and simple story-driven decision games. Content spreads via peer-to-peer (P2P) transfers so children and families in connectivity-constrained areas can exchange learning resources. The MVP’s goal is to validate whether story-driven, local-LLM-assisted learning plus P2P distribution improves vocabulary and basic problem-solving understanding for children (ages 5–14).



# Goal
Deliver the smallest, testable product that:  
1. Teaches language and cultural values via short stories,  
2. Reinforces learning with mini-quizzes and decision scenarios, and  
3. Enables offline local sharing (P2P) so learning content can spread without internet.

# Target users
- **Primary:** Children aged 5–14 in Gaza using low-spec Android phones (intermittent power/Internet).  
- **Secondary:** Parents/guardians, local volunteers/teachers who upload/record seed content.

# Key customer pain points (MVP focus)
- Interrupted or absent formal schooling.  
- Unreliable or no internet access.  
- Need for culturally appropriate, trustworthy learning material.  
- Need for measurable, simple learning outcomes.

# Core MVP Scope (Must-haves)

## 1. Story Playback (Core learning)  
**Description:** Short audio stories (2–6 minutes) in Arabic with optional simple English phrases; story text available locally. Seed stories are created by volunteers and optionally adapted by Ollama templates (pre-generated).  
**Acceptance Criteria:**  
- Story audio plays and text displays for downloaded stories.  
- Story metadata visible: title, age-range, duration, language.  
- Playback works fully offline once content is downloaded.

## 2. Mini-Assessment per Story  
**Description:** Immediately after each story, the app shows a 3-item mini-quiz (e.g., 1 matching, 1 MCQ, 1 decision scenario linked to life skills).  
**Acceptance Criteria:**  
- Quiz triggers after story completion.  
- Immediate feedback (correct/incorrect + one-sentence explanation).  
- Quiz result stored locally with timestamp and score (0–3).

## 3. Local Progress Tracking  
**Description:** Simple per-child profile and a local progress view showing stories completed, average score, and 3 weakest words.  
**Acceptance Criteria:**  
- User can create a local profile (name, age-group).  
- Progress screen shows: stories completed count, average quiz score, top 3 weakest words.  
- Data persists offline and survives app restarts.

## 4. Peer-to-Peer Sharing  
**Description:** Share downloaded story packages (audio + text + metadata + quiz) directly via Bluetooth or Wi-Fi Direct.  
**Acceptance Criteria:**  
- Device discovery and consent-based transfer.  
- Recipient gets confirmation and story appears in library after accept.  
- Transfer includes integrity check (checksum/hash) and completes reliably for a typical 2–6 MB package within ~90s on reasonable hardware.

## 5. Seed Content & Local Authoring  
**Description:** Volunteers/admins preload at least 10 seed stories. Parents/volunteers can record narration locally (simple recorder).  
**Acceptance Criteria:**  
- Admin/volunteer can add seed stories to the app before pilot.  
- In-app recorder creates an audio file linked to a story; saved locally and playable.

## 6. Minimal Moderation Flow  
**Description:** Local reviewers (volunteers) can mark submitted stories as Approved/Rejected on-device before sharing widely.  
**Acceptance Criteria:**  
- Submitted stories appear as “pending”; reviewer can mark status.  
- Pending stories are not available to general library until approved.

# Stretch Goals (Nice-to-have if time permits)
- Adaptive quiz difficulty based on recent performance.  
- Side-by-side bilingual text and simple TTS for English phrases.  
- Badges for milestones (e.g., 3 stories completed).  
- Pronunciation practice with recorded attempts and basic scoring.

# Non-functional requirements (MVP-level)
- Core app binary ≤ 20 MB (excl. downloaded media).  
- Offline-first: all learning flows work without internet after downloads.  
- Target Android API 21+ (low-end phones supported).  
- App usable state loads in ≤ 3 seconds on typical target devices.  
- Local data encrypted at rest.  
- P2P transfers encrypted and integrity-checked.  
- App stable: no crashes in 95% of sessions during pilot.

# Excluded from MVP (explicit)
- Cloud-hosted dashboards and centralized analytics (local summaries only).  
- Rich graphics, animations, or heavy illustrations.  
- Full multi-language support beyond Arabic + basic English phrases.  
- Complex multi-role editorial workflows or remote moderation.  
- Monetization, external social sharing, or ads.

# Minimal technical stack (recommended)
- Frontend: **Android (Kotlin)** or **Flutter**.  
- Local DB: **SQLite / Room**.  
- Audio: **ExoPlayer** or native MediaPlayer.  
- P2P: Native **Bluetooth / Wi-Fi Direct** libraries.  
- LLM content generation: **Ollama** used off-device to pre-generate/adapt templates; volunteers run generation on laptops/edge nodes and seed content to devices.  
- Repo & CI: Git + simple build pipeline for APK.

# Rationale
Avoid shipping heavy LLM models on low-end phones in MVP; use Ollama for content authoring on accessible hardware then distribute packages P2P.

# Success criteria (measurable)
- ≥ 10 seed stories available in the shipped APK or initial distribution.  
- Offline playback works without crashes for 95% of sessions in pilot.  
- Pilot group: 50 children across 2–3 communities using the app for 2 weeks.  
- Learning signal: average quiz score improves by ≥10% between week 1 and week 2 for ≥40% of active users.  
- At least 30 successful P2P transfers in pilot.

# Validation plan (Build → Measure → Learn)
1. Prepare 10 verified seed stories and deliver APK to pilot group.  
2. Train local volunteers/parents to install app and use P2P sharing.  
3. Run pilot for 2 weeks; collect local metrics (stories played, quiz scores, transfers) and conduct interviews with 10+ parents.  
4. Analyze: story relevance, cultural resonance, technical reliability, learning improvement.  
5. Iterate: refine story length, quiz types, and moderation flow.

# Minimal timeline (suggested)
- **Week 0:** Define UX flows, select tech, prepare 10 seed stories.  
- **Weeks 1–2:** Implement playback, quiz flow, local DB, simple UI.  
- **Week 3:** Implement P2P sharing, recording feature, and basic moderation.  
- **Week 4:** QA + pilot rollout to small community.  
- **Weeks 5–6:** Collect feedback, fix critical issues, prepare next iteration.

# Risks & Mitigations
- **Risk:** LLM-generated stories may contain culturally sensitive content.  
  **Mitigation:** Human review before distribution; seed content verified by local reviewers.  
- **Risk:** Low-end devices lack storage or audio performance.  
  **Mitigation:** Use compressed audio formats (e.g., AAC/ogg), allow save-to-SD, warn on low storage.  
- **Risk:** P2P transfer fails across diverse devices.  
  **Mitigation:** Support both Bluetooth and Wi-Fi Direct; robust retries and integrity checks; fallback to audio-only transfer if needed.

# What to test first (priority)
1. Full offline story playback → quiz flow end-to-end.  
2. P2P transfer reliability and integrity checks.  
3. Local progress persistence and basic reporting.  
4. Recorder + add-seed-story flow and local moderation.

# Bootcamp demo checklist (one-page demo)
- APK with 3 seed stories playable offline.  
- One story has the 3-question mini-quiz; score saved and visible under “My Progress.”  
- P2P demo: transfer one story between two phones; recipient accepts and sees the story in library.  
- Short scripted demo: show a child improving score across two sessions.

# Quick comparison
- **This MVP:** Focused on *offline resilience*, *cultural relevance*, *P2P distribution*, and *simple measurable learning* — optimized for Gaza constraints.  
- **Broader/cloud-first MVPs:** Usually prioritize centralized analytics, richer UIs, and cloud sync; valuable later but not suitable as first step in low-connectivity contexts.
