<div align="center">
<img src="https://media1.giphy.com/media/v1.Y2lkPTc5MGI3NjExZXppYTNhcDNnNTQ5NWQyeHFydnVyaW93ZjRuaGEwNHd6bWt5MXppZSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/xT0xeMIcsHFxsN5M8E/giphy.gif" width="600" alt="Cool Dev Animation"/></div>

<div align="center">
  <h1>✨ Welcome to My GAME DEV World! ✨</h1>
  <h3>🎮 A passionate <strong>Game Developer</strong> crafting immersive worlds with <span style="color:#478CBF;">Godot Engine and Raylib</span></h3>
</div>

---

## 🕹️ About Me  

- 👨‍💻 Hi, I’m **Ali Hussein**  
- 🎮 I create **2D games** with **Godot Engine**  
- 💻 Main programming weapons: **GDScript, Python & C**  
- 📚 **Raylib** (C library for game programming)  
- 📺 Sharing my work on [**YouTube**](https://www.youtube.com/@Platourygo)  
- 💼 Connect with me on [**LinkedIn**](https://www.linkedin.com/in/platoury/)  

---

## 🚀 Tools & Tech  

<div align="center">
  <img src="https://img.shields.io/badge/Godot-478CBF?style=for-the-badge&logo=godot-engine&logoColor=white&labelColor=2C2C2C" alt="Godot"/>
  <img src="https://img.shields.io/badge/Raylib-000000?style=for-the-badge&logo=raylib&logoColor=white&labelColor=2C2C2C" alt="Raylib"/>
  <img src="https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white&labelColor=2C2C2C" alt="C"/>
  <img src="https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=black&labelColor=2C2C2C" alt="Python"/>
  <img src="https://img.shields.io/badge/GDScript-478CBF?style=for-the-badge&logo=godot-engine&logoColor=white&labelColor=2C2C2C" alt="GDScript"/>
</div>

---

## 📊 GitHub Stats  

<div align="center">

<!-- Overall Stats -->
![Ali's GitHub stats](https://github-readme-stats.vercel.app/api?username=Platoury&show_icons=true&theme=tokyonight&hide_border=true&count_private=true)

<!-- Streak Stats -->
![GitHub Streak](https://streak-stats.demolab.com?user=Platoury&theme=tokyonight&hide_border=true&date_format=M%20j%5B%2C%20Y%5D)

</div>

---

## 🕹️ Fun Zone  

```gdscript
# A small snippet from my engine (Godot 💙)
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
