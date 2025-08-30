# Sysadmin Survivor Guide – Issue #2  
## 🔴 No Display After Power-On (Black Screen)  
> *“The machine breathes… but the screen is dead.”*

---

⚠️ **WARNING**: Panic is contagious. Do not look at the black screen for more than 5 seconds without a plan.

You press the power button. The fans spin. The lights come on. You hear life.  
But the screen?  
*Pitch black.*  
No logo. No BIOS. No flicker. Nothing.  

You’re not sure if it’s possessed, broken, or just ignoring you.  
Welcome to one of the most common — and most terrifying — hardware mysteries in the IT world.

This isn’t Windows failing. This isn’t a driver crash.  
This is **pre-OS silence**. And silence is dangerous.

But fear not, survivor.  
We’ve got a **battle-tested checklist**, a **path of logic**, and the **tools to bring it back from the void**.

---

## 🔍 Symptoms: What You’re Seeing (Or Not Seeing)

- ✅ Power LED is on  
- ✅ Fans spin up (briefly or continuously)  
- ❌ No video output on built-in or external display  
- ❌ No POST beep codes (or no speaker to hear them)  
- ❌ No backlight, no logo, no flicker — just void  
- ❌ HDMI/DisplayPort not detected by external monitor  

> 🚩 **Red Flag**: The system seems alive, but refuses to speak.  
> This is not a software problem. This is *hardware mutiny*.

---

## 🧰 Tools You’ll Need (The Survival Kit)

Here’s what to gather before you begin:

- Known-good power adapter – to rule out PSU or charger failure  
- External monitor with HDMI or DisplayPort cable – to test video output  
- USB keyboard – useful if the screen returns and you need to navigate BIOS  
- Flashlight – helps inspect RAM slots, dust buildup, or corrosion  
- Pencil eraser (gomme blanche) – for cleaning RAM contacts  
- Phillips #0 and #1 screwdrivers – for opening the case  
- Spare RAM (if available) – to test stick-by-stick  
- Multimeter (optional) – for checking power delivery  
- Bootable USB drive – useful later to confirm the OS isn’t the root cause  

> 💡 **Pro Tip**: Keep a “black screen emergency kit” in your admin drawer. You will need it.

---

## 🧪 Step-by-Step Diagnosis: The 7 Circles of Black Screen Hell

### Circle 1: Confirm It’s Not Just You  
> “Is the monitor even on?”

- Check that the monitor is powered on and set to the correct input (HDMI 1, HDMI 2, DP, etc.)  
- Try a different HDMI or DisplayPort cable — cables fail more often than you think  
- Test the monitor with another device like a phone, laptop, or gaming console  

> 🧠 **Survivor Thought**: Humans assume. Machines don’t. Always rule out the obvious.

---

### Circle 2: External Display Test (The Litmus Test)  
> “If the screen is dead, is the body still alive?”

- Connect the device to an external monitor using HDMI or DisplayPort  
- Plug in the cable *before* powering on the machine  
- Press the display toggle key (often `Fn + F4`, `F5`, or `F7` — look for a monitor icon)  
- Wait at least 30 seconds and watch closely for any sign of life  

👉 **If an image appears**:  
The internal display, lid sensor, or internal video cable (LVDS/eDP) is likely the issue.  
Good news: the CPU and GPU are probably working.  

👉 **If still black**:  
The problem lies earlier in the boot process — before video initialization.  
Proceed to deeper diagnostics.

---

### Circle 3: RAM Ritual (The Holy Grail of Fixes)  
> 60% of black screens are caused by RAM issues.

1. Power off the machine, unplug the charger, and remove the battery (if it’s a laptop).  
2. Open the case and locate the RAM slots.  
3. Remove all RAM sticks.  
4. Gently clean the gold contacts with a pencil eraser to remove oxidation.  
5. Reinsert one stick at a time, pressing firmly until it clicks into place.  
6. Test boot after each reinsertion.  

> 🚨 **Critical**: Test each RAM stick **individually**. One may be dead while others work.

---

### Circle 4: CMOS Reset (Exorcise the BIOS)  
> BIOS corruption is silent. But deadly.

1. Unplug the AC adapter and remove the main battery (if accessible).  
2. Open the chassis and locate the CMOS battery (a small silver coin cell, usually labeled CR2032).  
3. Remove the battery and wait **exactly 10 minutes** — set a timer. No shortcuts.  
4. Reinsert the battery, reconnect power, and attempt to boot.  

👉 This clears corrupted BIOS settings, failed overclocks, and firmware glitches.

---

### Circle 5: GPU & Integrated Graphics Check  
> “Is the graphics heart still beating?”

**For desktops:**  
- Remove the dedicated GPU.  
- Connect your monitor to the motherboard’s video port (only works if your CPU has integrated graphics).  
- Power on.  

👉 If the display appears: the dedicated GPU is likely dead or not seated properly.  

**For laptops:**  
- If the external display works: the integrated GPU is alive — issue is likely internal display or cable.  
- If no output: possible GPU, chipset (PCH), or motherboard failure.

---

### Circle 6: Power & PSU Stress Test  
> “No volts, no votes.”

- Try a **known-good power adapter** with matching voltage and wattage.  
- Remove the battery and run on AC power only.  
- Remove AC and run on battery only.  
- Watch for sudden shutdowns or weak fan response.  

For desktops:  
- Use a PSU tester or perform a paperclip test (only if trained).  
- Swap in a known-working PSU if possible.  

> 🚩 **Sign of death**: Fans spin for 1–2 seconds then cut out — points to PSU or motherboard power regulation failure.

---

### Circle 7: Motherboard & CPU (The Final Boss)  
> If all else fails, the core is compromised.

Look for:  
- Burn marks, bulging capacitors, or a burnt smell (ozone or plastic)  
- No POST, no fan ramp-up, no response to the power button  
- History of power surge, lightning strike, or liquid damage  

At this point, if you’ve already tried:  
- RAM cleaning and testing  
- CMOS reset  
- External display test  
- Power adapter swap  

👉 The issue is likely **motherboard or CPU failure**.  
Repair options: professional board-level repair or full replacement.

---

## 🧩 Common Causes & Fixes (The Cheat Sheet)

- **Loose or dirty RAM**  
  → Reseat sticks, clean contacts, test one at a time  

- **BIOS corruption**  
  → Perform CMOS reset  

- **Dead dedicated GPU**  
  → Remove GPU and use integrated graphics (if available)  

- **Faulty internal display cable (laptops)**  
  → Replace LVDS or eDP cable  

- **Bad power adapter or PSU**  
  → Swap with a known-good unit  

- **Motherboard failure**  
  → Requires replacement or professional repair  

- **CPU failure**  
  → Rare, but possible after electrical surge — usually means full board replacement  

---

## 🛡️ Survivor Tip: The 10-Second Rule

> *If the fans spin for more than 10 seconds and no display appears, it’s not the monitor.*

That’s your signal to:
1. Grab the HDMI cable  
2. Find an external monitor  
3. Begin the RAM ritual  

Don’t waste time. Don’t reboot 10 times.  
Follow the protocol.  
***Speed saves systems.***

---

## ✅ Final Words

A black screen is not the end.  
It’s a puzzle.  
And every puzzle has a solution — if you don’t panic, don’t guess, and follow the path.

You’ve got the tools.  
You’ve got the steps.  
Now go *resurrect that machine*.
