# Siegefend

**Siegefend** is a Java‑based tower defense game developed for an object‑oriented programming course. Players must deploy turrets along a predefined path to stop successive waves of enemies before they breach the endpoint.

---

## 🎮 Gameplay Overview
- Enemies spawn in timed waves and follow a fixed route.
- Players place turrets of different types (e.g., basic, slow, splash) alongside the route.
- Turrets automatically target enemies within range.
- Enemy types scale in health, speed, and point value across waves.
- The player loses if too many enemies reach the end; survives to clear all waves to win.

---

## 🧱 Architecture & Object‑Oriented Design

The code follows clean OO principles:
- **`GameEngine` / `GameController`**: Initializes and manages game loop (ticks, rendering, updates).
- **`WaveManager`**: Reads wave configurations, spawns enemies per timing rules.
- **`Enemy`** (abstract) + subclasses: defines shared behavior for enemies (e.g. movement, health) and specialized stats.
- **`Turret`** (abstract) + subclasses: different turret behaviors (range, fire rate, damage, splash, slowing effect).
- **`Projectile`**: Logic for tracking, applying damage/effects, and collision detection.
- **`Map` / `Path`**: Handles graphical layout and enemy path logic.
- **`GameState`**: Tracks player life, money, score, and wave progression.
- **Utility & config classes**: Parses JSON or text files for turret specs, wave definitions, map layout, etc.

Style conventions such as Javadoc usage (`@param`, `@return`, inline `{@code ...}` and `{@link ...}`) follow Java standards :contentReference[oaicite:1]{index=1}.

---

## 🚀 Setup & Running the Game

### Development builds
1. Clone the repo:
    ```bash
    git clone https://github.com/FabioNotaro2001/Siegefend.git
    cd Siegefend
    ```
2. Ensure you have **JDK 11+** and your project build system (e.g. Eclipse, IntelliJ, Maven, Gradle).
3. Import the project into your IDE or run via build script.
4. Configure resource folder (e.g. `res/`) to be in your classpath.
5. Run the `main()` method in the `GameLauncher` or `Siegefend` class.

### Executable jar (if provided)
- Locate `Siegefend.jar` in the `target/` or `dist/` folder.
- Run:
    ```bash
    java -jar Siegefend.jar
    ```

---

## ⚙ Configuration

- **Wave configuration** files define spawn timing, types, and count of enemies.
- **Turret definitions** specify cost, range, fire rate, damage, and additional effects.
- **Map layout** defines the path and coordinates for nodes where turrets can be placed.
- You can tweak balance by editing config files and restarting the game.

---

## ✅ How to Play
1. Start the game – main menu appears.
2. Select level/map.
3. Place turrets before waves begin and optionally during breaks.
4. Earn money by defeating enemies; use it to upgrade or place new turrets.
5. Prevent enemies from reaching the endpoint.
6. Clear all waves to win; if too many pass, the game ends in defeat.

---

## 🧪 Development & Extension Ideas

- **Add new turret types**: e.g. area‑damage, piercing, or elemental effects.
- **Design diverse enemy classes** with resistances or special abilities.
- **Support multiple maps**, interactive UI, or mouse‑based upgrades.
- **Balance configuration** through adjustable resource, cost, and timing parameters.
- Share gameplay data/logs, high‑scores, or export wave-defeat statistics.

---

## 📂 Project Structure

