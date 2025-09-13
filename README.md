<div align="center">
  <img src="https://media1.giphy.com/media/v1.Y2lkPTc5MGI3NjExZXppYTNhcDNnNTQ5NWQyeHFydnVyaW93ZjRuaGEwNHd6bWt5MXppZSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/xT0xeMIcsHFxsN5M8E/giphy.gif" width="600" alt="Cool Dev Animation"/>
<div class="tenor-gif-embed" data-postid="15232731949332559730" data-share-method="host" data-aspect-ratio="1" data-width="100%"><a href="https://tenor.com/view/godot-plush-godot-plush-makeship-gif-15232731949332559730">Godot Plush GIF</a>from <a href="https://tenor.com/search/godot-gifs">Godot GIFs</a></div> <script type="text/javascript" async src="https://tenor.com/embed.js"></script>

## 🎮 Welcome to My Dev World!  

<div align="center">

<h1>✨ I'm <span style="color:#00BFFF;">Ali Hussein</span> ✨</h1>

<h3>🎮 A passionate <strong>Game Developer</strong> crafting immersive worlds with <span style="color:#478CBF;">Godot Engine and Raylib</span> 🎮</h3>

</div>

</div>

---

## 🕹️ About Me  

- 👋 Hi, I’m **Ali Hussein**  
- 🧩 I create **2D / 3D games** with **Godot Engine**  
- 💻 Main programming weapons: **C, Python & GDScript**  
- 📚 **Raylib** (C library for game programming)  
- 📺 Sharing my work on [**YouTube**](https://www.youtube.com/@Platourygo)  
- 💼 Connect with me on [**LinkedIn**](https://www.linkedin.com/in/platoury/)  

---

## 🚀 Tools & Tech  

<div align="center">

![Godot](https://img.shields.io/badge/Godot-478CBF?style=for-the-badge&logo=godot-engine&logoColor=white&labelColor=2C2C2C)
![Raylib](https://img.shields.io/badge/Raylib-000000?style=for-the-badge&logo=raylib&logoColor=white&labelColor=2C2C2C)
![C](https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white&labelColor=2C2C2C)
![Python](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=black&labelColor=2C2C2C)
![GDScript](https://img.shields.io/badge/GDScript-478CBF?style=for-the-badge&logo=godot-engine&logoColor=white&labelColor=2C2C2C)

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

