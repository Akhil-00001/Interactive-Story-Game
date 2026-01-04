# 🕯️ Shadows Over Anthea  
### A Hybrid Story-Driven Game Engine using **C + Node.js + Web UI**

> **Shadows Over Anthea** is a story-driven interactive game that uniquely combines a **C-based game engine** with a **modern web interface**, demonstrating low-level systems programming, backend integration, and frontend interaction in a single cohesive project.

---

## 🚀 Why This Project Stands Out (HR Perspective)

- Demonstrates **strong fundamentals in C & Data Structures**
- Real-world **C ↔ Node.js ↔ Browser integration**
- Uses **process-level communication (stdin/stdout pipes)**
- Correct implementation of **Undo / Redo / Save / Restart**
- Clean separation of **engine, backend bridge, and frontend UI**

> This project reflects **systems-level thinking**, not just UI scripting.

---

## 🧠 Architecture Overview

Browser (HTML + Tailwind + JS)
↓
Express Server (Node.js)
↓
C Game Engine (anthea.exe)

yaml
Copy code

### Communication Model
- Node.js **spawns the C engine once**
- Uses **stdin/stdout piping** for continuous interaction
- Game state is **persisted in memory** inside the C process
- Each user action sends **one command** to the engine
- Engine responds with **JSON output** consumed by the frontend

---

## ⚙️ Technologies Used

| Layer | Technology |
|------|------------|
| Game Engine | C (Structures, Pointers, Dynamic Memory) |
| Backend Bridge | Node.js, Express |
| Frontend | HTML, Tailwind CSS, Vanilla JavaScript |
| Communication | stdin / stdout piping |
| Data Format | JSON |

---

## 🎮 Game Engine Features (C)

- Scene graph implemented using **structs & pointers**
- Choice-based navigation (`choice1`, `choice2`, `choice3`)
- **Undo / Redo** using stack data structures
- **Save & Go-to-Save** checkpoints
- **Restart story without restarting the process**
- **Display full story progression**
- Continuous execution using `while(fgets(stdin))`

> The C engine behaves like a **persistent backend service**, not a one-time executable.

---

## 🔄 Supported Commands

| Command | Action |
|--------|--------|
| `1 / 2 / 3` | Choose story path |
| `U` | Undo |
| `R` | Redo |
| `S` | Save current scene |
| `G` | Go to saved scene |
| `D` | Display full journey |
| `EXIT` | Restart the story |

---

## 🖥️ Frontend Capabilities

- Dynamic story rendering
- Background image updates per scene
- Invalid choice handling
- Full journey visualization
- Clean, responsive UI with Tailwind CSS
- No page reloads (SPA-like behavior)

---

## 📂 Project Structure

├── anthea.c # Core C game engine
├── anthea.exe # Compiled engine
├── bridge.js # Node.js C ↔ Web bridge
├── game.js # Frontend logic
├── index.html # UI
├── images/ # Scene background images
└── README.md

```yaml
Copy code
```

---

## ▶️ How to Run

### 1️⃣ Compile the C Engine
```bash
gcc anthea.c -o anthea.exe
```
### 2️⃣ Start the Backend Bridge
```bash
Copy code
node bridge.js
```
### 3️⃣ Launch the Frontend
```bash
Copy code
Open index.html in your browser
```
### 🧩 Key Learning Outcomes
- Inter-process communication (IPC)
- State management in long-running processes
- Memory-safe pointer-based traversal
- Backend–frontend separation
- Designing scalable command-driven systems

## Author
**Akhil Kotnala**
