
# 🎮 Project Little Adventurer – Unity 3D RPG Game

## 🧩 Overview

**Project Little Adventurer** is a top-down isometric 3D action-adventure game developed in Unity 2022 LTS. It features a single-level gameplay loop focusing on **exploration**, **enemy AI combat**, **coin collection**, and **UI transitions**. This project was built as my final year capstone submission and serves as a polished portfolio artifact to demonstrate my skills in **C# scripting**, **Unity game mechanics**, **FSM-driven AI**, **animation**, and **game design documentation**.

## 📷 Screenshots


- Main Menu(![Screenshot 2025-02-22 141036](https://github.com/user-attachments/assets/5fca9bc0-38e0-4182-92f4-7e6a8a19d070)
- Gameplay with Enemy AI(![Screenshot 2025-02-22 141052](https://github.com/user-attachments/assets/01175568-e119-4566-9393-0b62f162792d)
- Victory Screen(![Screenshot 2025-02-22 141315](https://github.com/user-attachments/assets/e09e333f-6636-4399-8e42-b2e28f6ed28f)
- Pause_Menu(![Screenshot 2025-02-22 141155](https://github.com/user-attachments/assets/c30ea7e3-3014-4e4d-9c9c-b17ef57c16b5)
- Game Loop Flowchart(![May 18, 2025, 02_10_24 PM](https://github.com/user-attachments/assets/00243152-30b6-4217-adb7-7c2fa494a053)

## 🛠️ Tech Stack

- **Engine**: Unity 2022 LTS (URP pipeline)
- **Language**: C#
- **IDE**: Visual Studio
- **Version Control**: Git / GitHub
- **Tools**: Unity Animator, NavMesh, Cinemachine, Canvas UI
- **Art Style**: Stylized Sci-fi with glowing emissive accents

## 🧑‍💻 Developer Role

As a solo developer, I was responsible for:

- Designing and implementing game mechanics
- Scripting player movement, AI, and combat
- Creating UI flow and transitions (Pause, Game Over, Victory)
- Animating player and enemies using state machines
- Debugging performance issues
- Creating all documentation (GDD, flowcharts, diagrams)

## 🕹️ Game Features

### 🧭 Core Gameplay Loop

- **Start Menu ➝ Level Spawn ➝ Coin Collection & Combat ➝ Portal Exit ➝ Victory/Game Over**

### ⚙️ Mechanics

- **Movement**: WASD-controlled top-down movement with Rigidbody physics
- **Combat**: Simple melee attack system with FSM-driven animations
- **Health System**: Damage/Death with UI sync (player & enemies)
- **Coin Collection**: Adds to score and encourages exploration
- **AI System**: Patrol → Chase → Attack (FSM logic with NavMesh)

## 🔧 Systems Breakdown

### 1. 🎮 PlayerController.cs
```csharp
void Update() {
    float moveX = Input.GetAxis("Horizontal");
    float moveY = Input.GetAxis("Vertical");
    // Apply movement and animation here
}
```

### 2. 🤖 EnemyAI.cs
```csharp
switch(currentState){
    case Patrol:
        PatrolToNextPoint();
        break;
    case Chase:
        ChasePlayer();
        break;
}
```

### 3. ❤️ HealthManager.cs
```csharp
public void TakeDamage(int amount) {
    currentHealth -= amount;
    UpdateUI();
    if(currentHealth <= 0) TriggerDeath();
}
```

### 4. 💰 CoinCollect.cs

- Collision with player triggers score update
- Coins disappear on collection
- Particle effect and SFX on pickup

### 5. 🧠 GameManager.cs

- Handles transitions between menus and gameplay states
- Tracks player state: playing, paused, won, lost
- Controls scene management using UnityEngine.SceneManagement

## 🎨 Visual Design

- Stylized ruins with moss, glowing tech, and lighting effects
- Fog zones add depth and mood
- Emissive lights highlight coins and gates
- Animated UI buttons with hover effects
- Health and score HUD floats on screen

## 🔁 Game Flowchart

```
START
 ↓
Main Menu → Start Game
 ↓
Spawn Player → Begin Exploration
 ↓
Enemy Encounters → Coin Collection
 ↓
Survive or Die?
 → Victory → End Screen
 → Game Over → Restart/Quit
```

## 🧠 FSM AI Logic

- **Idle**: Stationary state
- **Patrol**: Walk between points using NavMesh
- **Chase**: Target player if within detection radius
- **Attack**: Damage player when close
- **Reset**: Resume patrol if player escapes

## 🧪 Testing & Debugging

- **Unity Profiler**: Tracked FPS, CPU load, rendering bottlenecks
- **Debug Logs**: Collision testing, FSM state switches
- **Peer Testing**: Feedback on difficulty, movement responsiveness
- **UI Bug Fixes**: Sorting layers for overlapping menus

## 🧩 Design Philosophy

- **Keep it tight**: One polished level > many unfinished ones
- **Player clarity**: Visual & audio feedback for all interactions
- **Replayable**: Scoring, coin collection, and optimized runs
- **Modular Scripting**: Future-ready for scaling to more levels or features

## 🎯 Development Timeline

| Week | Milestone |
|------|-----------|
| 1    | GDD Planning, Sketching, Scope Design |
| 2    | Greyboxing, Movement + Camera Logic |
| 3    | Enemy AI, Animation FSM |
| 4    | UI Screens, Score System, Coin Logic |
| 5    | Particle FX, Post-processing, Polish |
| 6    | Testing, Debugging, Final Export |

## 🧾 Documentation Included

- ✅ Full Game Design Document (40 pages)
- ✅ FSM AI Diagram (PNG)
- ✅ Game Loop Flowchart (PNG)
- ✅ 5+ Screenshots for demo
- ✅ All Source Code in `/Scripts/` folder
- ✅ Build-ready Unity project

## 🧠 Future Enhancements

- Add mini-boss or time-based wave AI
- Introduce checkpoint save system
- Expand coin use into currency for upgrades
- Add level timer + achievements

## 💼 Portfolio Value

This game represents my ability to:

- Build and complete a playable Unity game from scratch
- Implement FSM logic, NavMesh, and Canvas UI
- Handle animation, audio, and camera transitions
- Create clear, responsive UX with polish
- Manage scope, testing, and final build delivery

## 📁 Repository Structure

```
/Assets
  /Scenes
  /Scripts
  /Animations
  /Prefabs
  /UI
  /Materials
  /Audio

/Docs
  Game_Design_Document.pdf
  Game_Loop_Flowchart.png
  FSM_Enemy_AI_Diagram.png

README.md
ProjectSettings/
```

## 📎 License

This project is for educational and portfolio use only. All code authored by me is open for non-commercial use under [MIT License].
