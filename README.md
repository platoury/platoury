<div align="center">

<!-- Animated Godot Header -->
<svg width="800" height="200" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <linearGradient id="gradient" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" stop-color="#478CBF">
        <animate attributeName="stop-color" values="#478CBF; #3a6e99; #478CBF" dur="5s" repeatCount="indefinite" />
      </stop>
      <stop offset="100%" stop-color="#2C2C2C">
        <animate attributeName="stop-color" values="#2C2C2C; #1a1a1a; #2C2C2C" dur="5s" repeatCount="indefinite" />
      </stop>
    </linearGradient>
    
    <filter id="glow">
      <feGaussianBlur stdDeviation="3.5" result="coloredBlur"/>
      <feMerge>
        <feMergeNode in="coloredBlur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>
  </defs>
  
  <rect width="100%" height="100%" fill="url(#gradient)" rx="10" />
  
  <!-- Animated Godot Icon -->
  <g transform="translate(400, 100)">
    <rect x="-60" y="-60" width="120" height="120" rx="20" fill="#478CBF" filter="url(#glow)">
      <animate attributeName="fill" values="#478CBF; #3a6e99; #478CBF" dur="3s" repeatCount="indefinite" />
    </rect>
    <text x="0" y="20" text-anchor="middle" fill="white" font-size="50" font-weight="bold">G</text>
    
    <!-- Moving pixel characters -->
    <rect x="-200" y="0" width="15" height="25" fill="#FF6B6B">
      <animate attributeName="x" values="-200; 200; -200" dur="8s" repeatCount="indefinite" />
    </rect>
    <rect x="185" y="-40" width="12" height="20" fill="#4ECDC4">
      <animate attributeName="x" values="185; -215; 185" dur="10s" repeatCount="indefinite" />
    </rect>
    <rect x="-150" y="40" width="10" height="18" fill="#FFE66D">
      <animate attributeName="x" values="-150; 150; -150" dur="7s" repeatCount="indefinite" />
    </rect>
  </g>
  
  <!-- Title Text -->
  <text x="400" y="180" text-anchor="middle" fill="white" font-size="24" font-weight="bold">🎮 Welcome to My Dev World! 🎮</text>
</svg>

## ✨ I'm **Ali Hussein** – a passionate **Game Developer** building worlds with **Godot Engine** 🎮

</div>

---

## 🕹️ About Me  

- 👋 Hi, I'm **Ali Hussein**  
- 🧩 I create **2D / 3D games** with **Godot Engine**  
- 💻 Main programming weapons: **C, Python & GDScript**  
- 📺 Sharing my work on [**YouTube**](https://www.youtube.com/@Platourygo)  
- 💼 Connect with me on [**LinkedIn**](https://www.linkedin.com/in/platoury/)  

---

## 🚀 Tools & Tech  

<div align="center">

![Godot](https://img.shields.io/badge/Godot-478CBF?style=for-the-badge&logo=godot-engine&logoColor=white&labelColor=2C2C2C)
![C](https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white&labelColor=2C2C2C)
![Python](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=black&labelColor=2C2C2C)
![GDScript](https://img.shields.io/badge/GDScript-478CBF?style=for-the-badge&logo=godot-engine&logoColor=white&labelColor=2C2C2C)
![VSCode](https://img.shields.io/badge/VSCode-0078D4?style=for-the-badge&logo=visual-studio-code&logoColor=white&labelColor=2C2C2C)

</div>

---

## 📊 GitHub Stats  

<div align="center">

![Ali's GitHub stats](https://github-readme-stats.vercel.app/api?username=Platourygo&show_icons=true&theme=tokyonight)  
![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=Platourygo&layout=compact&theme=tokyonight)

</div>

---

## 🕹️ Fun Zone  

```gdscript
extends CharacterBody2D

const MAX_SPEED = 125
const ACCELERATION_SMOOTHING = 10

func _process(delta: float) -> void:
    var movement_vector = get_movement_vector()
    var direction = movement_vector.normalized()
    var target_velocity = direction * MAX_SPEED

    # Smoothly interpolate from current velocity → target velocity
    velocity = velocity.lerp(target_velocity, 1.0 - exp(-delta * ACCELERATION_SMOOTHING))

    move_and_slide()

    # Animations
    if movement_vector != Vector2.ZERO:
        $AnimationPlayer.play("walk")
    else:
        $AnimationPlayer.stop()

func get_movement_vector() -> Vector2:
    var x_movement = Input.get_action_strength("move_right") - Input.get_action_strength("move_left")
    var y_movement = Input.get_action_strength("move_down") - Input.get_action_strength("move_up")
    return Vector2(x_movement, y_movement)
