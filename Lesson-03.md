# Circuit Explorer Series: Lesson 3: The Breadboard & Ohm’s Law

## Lesson Content

### Step 1: Rebuilding and The Breadboard

- **Concept**: Before we move to a cleaner workspace, we will practice our circuit construction and learn a simulation shortcut. Then, we will transition to a breadboard.
- **Activity**:
  1. Rebuild the Lesson 2 circuit (9V Battery &larr; 1k&Omega; Resistor &larr; LED) in Tinkercad.
  2. Add a Push Button between the battery and the resistor.
  3. **Simulation Trick**: To keep the button "pressed" during the simulation without your mouse, hold the **Shift** key while clicking the button. This "locks" the button in the pushed position.
  4. Stop the simulation and delete all existing wires to clear your workspace.
  5. Bring a **Breadboard** into the workspace.
  6. Connect the 9V battery terminals to the breadboard's power rails.
  7. Connect jumper wires from the positive and negative rails on one side of the breadboard to the corresponding rails on the opposite side to ensure current flows everywhere.

<video
  src="video/L03/01-9V-to-Breadboard.mp4"
  controls
  playsinline
  preload="metadata"
  width="100%"
  style="max-width: 900px; height: auto; border-radius: 8px;">
Your browser does not support the video tag.
<a href="video/L03/01-9V-to-Breadboard.mp4">Download the video</a>.
</video>

### Step 2: Breadboard Assembly

- **Concept**: Professionalizing our circuit by placing components into the breadboard grid.
- **Activity**:
  1. Place the Push Button so it bridges the center gap of the breadboard.
  2. Place the Resistor so one leg connects to a terminal row of the button.
  3. Place the LED so its Anode (bent leg) connects to the other leg of the resistor.
  4. Connect the Cathode (straight leg) of the LED back to the negative rail of the breadboard.
  5. Use jumper wires to complete the path from the positive rail to the button.
  6. Click "Start Simulation" and use the **Shift + Click** trick to test the circuit.

<video
  src="video/L03/02-Wiring-The-Breadboard-Circuit.mp4"
  controls
  playsinline
  preload="metadata"
  width="100%"
  style="max-width: 900px; height: auto; border-radius: 8px;">
Your browser does not support the video tag.
<a href="video/L03/02-Wiring-The-Breadboard-Circuit.mp4">Download the video</a>.
</video>

### Step 3: The Battery’s "Toll Booths" (Voltage Drop)

- **Instructor Note**: Move beyond the "squeezed pipe" to explain that a resistor doesn't just block flow in one spot—it changes the "speed" of the entire circuit. Also, introduce the idea that every component (LEDs) "takes" a specific amount of voltage as it works.

- **Concept**: Think of the 9V battery as a car trip with 9 units of energy.
  - If you just connect a wire, the "current" flows too fast and "crashes" the circuit.

<video
  src="video/L03/03-Single-Wire-Loop.mp4"
  controls
  playsinline
  preload="metadata"
  width="100%"
  style="max-width: 900px; height: auto; border-radius: 8px;">
Your browser does not support the video tag.
<a href="video/L03/03-Single-Wire-Loop.mp4">Download the video</a>.
</video>

- When you add a resistor, it’s like putting a speed limit on the whole road—the entire circuit slows down to a safe speed.

<video
  src="video/L03/04-Loop-with-1kohm-resistor.mp4"
  controls
  playsinline
  preload="metadata"
  width="100%"
  style="max-width: 900px; height: auto; border-radius: 8px;">
Your browser does not support the video tag.
<a href="video/L03/04-Loop-with-1kohm-resistor.mp4">Download the video</a>.
</video>

- **The "Toll Booth" Rule**: Every LED acts like a toll booth. To turn on, it _must_ take 2 volts of energy from the battery.
- **The Waterfall Activity (4 LEDs)**:
  1. Imagine 9V of energy at the top of a waterfall.
  2. The 1st LED takes 2V (9V - 2V = 7V left).
  3. The 2nd LED takes 2V (7V - 2V = 5V left).
  4. The 3rd LED takes 2V (5V - 2V = 3V left).
  5. The 4th LED takes 2V (3V - 2V = 1V left).
- **Discussion**: If we had 5 LEDs, we wouldn't have enough energy left! The last one would be too dim to light up.

![Wateerfall Analogy](images/L03/waterfall-explanation.png)

### Step 4: Picking the Right Resistor (The "Goldilocks" Math)

- **Concept**: The resistor’s job is to "soak up" the leftover voltage so the LEDs don't get too much and "pop."
- **The Math (Simplified)**:
  1. Start with the Battery Power: **9V**.
  2. Subtract the "Tolls" taken by the LEDs: **8V** (4 LEDs × 2V each).
  3. That leaves **1V** that the resistor needs to "soak up" to keep the circuit safe.
- **The Activity**:
  1. If we have too much leftover voltage, we use a **bigger** resistor to soak it up.
  2. If we have almost no leftover voltage, we use a **smaller** resistor.
- **Scientist Challenge**: If you had a 9V battery and only **one** LED (that takes 2V), how much energy is "leftover" for the resistor to soak up? (Answer: 7V). Do we need a bigger or smaller resistor than the one we used for 4 LEDs?

### Step 5: Finding the "Flow" (Current/Amps)

- **Instructor Note**: Professionals do not guess; they look up the "Datasheet" for a part before building. In this lesson, we are specifically working with standard LEDs.

- **The "Three-Jump Rule"**: To change **milliamps (mA)** into **Amps (A)** for our math, imagine a decimal point at the end of your number and jump it 3 spots to the left:
  - Start with: **20**
  - Jump 1: **2.0**
  - Jump 2: **.20**
  - Jump 3: **.020**
  - **Result: 0.020A**

- **Tinkercad Tip**: If you ever forget the standard amperage for an LED, you can "overload" the circuit in Tinkercad until the LED pops. If you hover your mouse over the "popped" LED, a small note will appear telling you: "Current through the LED is X, while absolute maximum is 20mA." That **20mA** is your "Magic Number."

### Step 6: Ohm’s Law (The Resistor Balance)

- **Concept**: Now we use a simple equation to pick the perfect resistor so our LED gets exactly the flow it needs without popping.
- **The Equation**:
  Resistor Value (Ω) = Leftover Voltage (V) ÷ Target Current (A)

![Ohm's Law Finding the Resistance](images/L03/ohms-law-resistance.png)

- **Experiment 1: The Single LED Test**
  1. Build a circuit with a 9V battery, a 1kΩ resistor, and 1 LED.
  2. Before you close the circuit to the ground, insert a **Multimeter** at the end.
  3. Set the Multimeter to **Amperage (A)** mode.
  4. **The Math**: We want 0.020A. With a 9V battery and a 2V LED, we have 7V left to soak up.
     Calculation: 7V ÷ 0.020A = 350Ω.
  5. Change your 1kΩ resistor to 350Ω. Your Multimeter should now read right around 20mA!

- **Experiment 2: The 4 LED Series Chain**
  1. Clear your breadboard. Connect your 9V battery to a string of 4 LEDs in series (use jumper wires to connect the "negative" leg of one LED to the "positive" leg of the next).
  2. Add the Multimeter after the 4th LED, then connect the other side of the Multimeter to the battery's Ground.
  3. **The Math**: Each LED takes 2V, so 4 LEDs = 8V. Leftover: 9V - 8V = 1V.
     Calculation: 1V ÷ 0.020A = 50Ω.
  4. Place a 50Ω resistor between the Power (Positive) and the first LED.
  5. Run the simulator. Your Multimeter should read 20mA!

- **Quick Recap**:
  - **Look it up**: Always check your device's "Goldilocks" flow (20mA for LEDs).
  - **Jump the Decimal**: Use the "Three-Jump Rule" to turn 20mA into 0.020A.
  - **Find the Toll**: Subtract the LED voltage "tolls" from the battery voltage to find the leftover voltage the resistor needs to soak up.
  - **Calculate**: Use the equation (Leftover Voltage ÷ 0.020) to find your perfect resistor value.

- **Scientist Challenge**: If you had a 9V battery and you wanted to light up **two** LEDs (each taking 2V), how much voltage does the resistor need to soak up? Calculate the resistor value needed, build it, and check your work with the Multimeter!
