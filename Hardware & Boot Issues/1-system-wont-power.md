# 💀 Issue #1: System Won’t Power On  
> *"You press the button. Nothing. No fan spin. No flicker of light. Just silence. The machine is dead."*

Welcome to ground zero of hardware failure.

When a system won’t power on, you’re not dealing with software, logs, or configuration — you’re facing **electrical silence**. No BIOS, no POST, no beeps. Just void.

But here’s the truth:  
**The system isn’t broken — it’s waiting for you to speak its language.**

Your job isn’t to guess. It’s to **diagnose like a detective**, starting from the outside and working inward.

---

## 🎯 What You’re Dealing With

This issue means:
- No response from the power button  
- No LEDs (on case, keyboard, or motherboard)  
- No fan movement  
- No display signal  

> ⚠️ **Not the same as**:  
> - Fans spin but no display → That’s a *boot* issue  
> - Beeps on startup → That’s *POST feedback*  
> - Blue screen after boot → That’s *OS-level*  

This is deeper.  
This is **power path failure**.

---

## 🔍 The Survivor Diagnosis: 7 Steps to Find the Pulse

Use the **Outside-In Method** — eliminate possibilities layer by layer, like peeling an onion.

---

### ✅ Step 1: Confirm the Obvious — Is the Outlet Dead?

Start where the power begins.

**Action**:
- Plug in a lamp, phone charger, or fan.
- If it doesn’t work, the problem is environmental.
- Try a different outlet.

> **Survivor Tip**: 30% of “dead PCs” are just plugged into a switched-off power strip.

---

### ✅ Step 2: Swap the Power Cable

The IEC C13 cable (the “kettle cord”) is a common failure point.

**Action**:
- Replace it with a known-good cable.
- Test on another machine if possible.

> **Survivor Tip**: These cables fail at the ends from bending. Wiggle the connector — if it flickers, it’s dying.

---

### ✅ Step 3: Check the PSU Switch (Yes, Really)

Many PSUs have a physical **on/off switch on the back**.

**Action**:
- Is it accidentally turned off?
- Flip it and try again.

> **Survivor Tip**: Label it with red tape: “ON = | , OFF = O” — saves future headaches.

---

### ✅ Step 4: Listen for Standby Power

Even when “off,” a healthy PSU provides **+5VSB (standby voltage)**.

**Listen for**:
- A faint click when pressing the power button
- A small green LED on the motherboard (if visible)
- A slight hum from the PSU

If you hear or see nothing, the PSU or motherboard may be dead.

---

### ✅ Step 5: The Paperclip Test — Is the PSU Alive?

This is your **definitive test** for PSU functionality.

**How to do it**:
1. Unplug the PSU from the motherboard and all drives.
2. Find the **24-pin ATX connector**.
3. Bend a paperclip to bridge:
   - **Green wire (PS_ON)** → to any **Black wire (Ground)**
4. Plug the PSU back into the wall.
5. Flip the rear switch.

✅ If the PSU fan spins → PSU is good  
❌ If nothing happens → PSU is likely dead

> ⚠️ **Warning**: Only do this if you’re comfortable with high-voltage components.  
> Never touch internal PSU parts — capacitors can hold charge for days.

> **Survivor Tip**: Carry a labeled paperclip in your toolkit. Call it your “PSU defibrillator.”

---

### ✅ Step 6: Bypass the Power Button

The front panel button can fail — especially on older cases.

**How to test**:
1. Open the case.
2. Locate the **front panel header** on the motherboard.
3. Find the two pins labeled `PWR_BTN` (usually near `F_PANEL`).
4. Briefly touch them with a screwdriver (metal tip).

✅ If the system powers on → power button is faulty  
❌ If nothing → problem is deeper (motherboard, PSU, CPU)

> **Survivor Tip**: Use a jumper wire or dedicated power switch for testing.

---

### ✅ Step 7: Build the Minimum System

Strip it down to the essentials.

**Keep only**:
- Motherboard
- CPU
- One stick of RAM
- GPU (if no integrated graphics)
- PSU

**Remove**:
- All drives
- Extra RAM
- USB devices
- Case fans (except CPU)
- Any add-on cards

Try to power on.

✅ If it works → something you removed was causing a short  
❌ If still dead → motherboard or CPU is likely dead

> **Survivor Tip**: Test outside the case (on cardboard) to rule out grounding issues from bad standoffs.

---

## 🚨 When to Walk Away

If you’ve done all this and still:
- No fan spin
- No LED
- No response to paperclip or pin short

Then:
> 💀 The **motherboard or CPU** is likely dead.

Time to:
- Replace the motherboard
- Consider a new build
- Document the failure for procurement
