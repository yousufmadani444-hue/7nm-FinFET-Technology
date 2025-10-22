# 7nm FinFET Technology

This repository provides a clear and concise explanation of **7 nm FinFET (Fin Field Effect Transistor)** technology — how it evolved, why it replaced traditional planar MOSFETs, challenges, and advantages.

---

## Table of Contents
1. [Introduction](#introduction)
2. [Why Did We Start Using FinFETs?](#why-did-we-start-using-finfets)
3. [Structure of FinFET](#structure-of-finfet)
4. [FinFET Physical Parameters and Equations](#finfet-physical-parameters-and-equations)
5. [Fabrication Process Overview](#fabrication-process-overview)
6. [Advantages of FinFET Technology](#advantages-of-finfet-technology)
7. [Challenges in 7nm Node](#challenges-in-7nm-node)
8. [FinFET Physical Parameters and Electrical Equations](#finfet-physical-parameters-and-electrical-equations)
9. [Comparison: Planar vs FinFET](#comparison-planar-vs-finfet)
10. [References](#references)
    
---

## Introduction
As semiconductor devices continued to scale beyond the limits of planar CMOS technology, maintaining performance and controlling leakage became increasingly difficult. FinFETs emerged as a **3D transistor design** that enabled further scaling into the **7 nm and beyond** technology nodes.

---

## Why Did We Start Using FinFETs?
This becomes even more important — why did FinFET come into existence, and what were the challenges in planar MOSFETs?
So now, let us look at the challenges of planar MOSFETs:  
In a normal planar MOSFET:  
The source has electrons (in an nMOS).  
The drain is at a higher voltage.  
The gate controls whether electrons can flow from source drain by forming or removing a conductive channel in the silicon under the gate.  
Now when the Vgs<Vth the gate voltage will repel the electrons and pull the holes up, forming a depletion region that's the barrier blocking the electrons. This leads the mosfet to turn off and current will be zero, as the technology increases the channel length decreases for the sake of faster switching and many other reasons but when the channel length decreases the source and drain come close to each other this leads to many problems, the major problem being the **electric field spreading**.  
**Electric field spreading**: In case of NMOS the drain has positive voltage, which means that the positive electric field extending from drain to channel, but when the channel is long the *field dies* before reaching the source, so the barrier is only controlled by the gate, but in the case of short channel the drain's electric *field penetrates* deep into the channel and overlap's the source causing the formation of channel due to the drain's positive voltage leading to the flow of current called as the *leakage current* even when the gate is trying to off the transistor.  
The above discussed is one of the major short channel effect and is widely called as **Drain Induced Barrier Lowering(DIBL)**.  
### How FinFET Solves This Problem  
In the case of plannar mos we had the gate only on the top of the channel which lead to DIBL and many other problem(majorly leakage of current), now in the case of finfet, gate is wrapped around the channel on three sides(top,right,left) which leads to:  
Stronger electrostatic control of the channel.  
The drain’s field can’t easily penetrate to the source.  
The barrier remains high when off, leakage current drops drastically.  

## Structure of Finfet:  
A FinFET is a type of 3D MOSFET where the channel is a thin vertical “fin” of silicon instead of a flat horizontal layer.  
The gate wraps around the fin on three sides: top + both sidewalls.  
This gives much stronger electrostatic control of the channel potential compared to planar MOSFETs.  
It’s called “FinFET” because the vertical channel looks like a fin under the gate.  
The point to remember is that the *principle is same* as plannar mosfet, the only difference is that the fin structure which gives better gate control.  
Let’s look at how an nMOS and pMOS FinFET are structured:  
In an nMOS FinFET:  
The source and drain are heavily n-type doped (to supply electrons).  
The channel (fin) is made of p-type silicon, so that when a positive gate voltage is applied, electrons are attracted to form an inversion layer in the p-type fin.  
This inversion layer is what actually conducts current from source to drain.  
Similarly, for a pMOS FinFET:  
Source and drain are p-type, and the channel is n-type.  
A negative gate voltage creates a whole inversion layer to conduct current.  
<img width="800" height="647" alt="image" src="https://github.com/user-attachments/assets/c58b9a65-4074-44a7-8ca2-4bd087077ecd" />


## FinFET Physical Parameters and Equations:  
Finfet being a 3D structure we should be clear with the dimensions that define the finfet:  
1. Fin height(Hfin) - Tells us about how much does the sidewall area contributes to current.
2. Fin thickness(Wfin) - Controls gate control strength and channel electrostatics.
3. Gate length(Lg) - Channel length.
4. Number of fins(Nfin) - Multi fins one finfet with a single gate control increasing the total drive current.
5. Oxide thickness(Tox) - Determines the gate capacitance and controls the strength.  

In the above mentioned structural dimensions **channel lenght, fin height, fin thickness, and oxide thickness** become the important geometrical knobs of how tightly the gate can control the channel.  

**Effective Channel Width:**  
$$W_{eff} = 2H_{fin} + W_{fin}$$  
The effective channel width represents the total area of the fin that is controlled by the gate. As we know that the gate wrap arounds around the fin now therefore increasing the effective width that is either increasing the height or number of fins can lead to greater gate control and increase the drive current, current is directly proportional to the effective width of the finfet. Current in the case of finfet flows along the top and both sidewalls. Now for a single finfet there can be more than one fin increasing the current then the effective width becomes, $$W_{total} = N \times W_{eff} = N \times (2 H_{fin} + W_{fin})$$  
This shows that by adding more fins, the total width can be increased **without increasing the footprint** of the transistor, As a result, FinFETs can provide **more current per unit area** compared to planar MOSFETs, while maintaining strong gate control and reducing short-channel effects.  

**Oxide Capacitance:**  
In case of plannar mosfet the gate capacitance per unit area is $$C_{ox} = \frac{\varepsilon_{ox}}{T_{ox}}$$  
Where:
- εox → Permittivity of the oxide layer.
- Tox → Thickness of the oxide layer.
- Here, basically what Cox tells is capacitance per unit area of gate oxide that is how much charge can be stored in a tiny square of gate area, in the case of plannar mosfet the gate is only present on the top surface of channel so the charge accumulated is lesser compared to a finfet where the gate has more area covered of the channel.
  
The total gate capacitance is given by the total area times the gate capacitance per unit area that is  
Ctotal ​= Cox​ × W × L.  
This tell how much charge the gate capacitance can hold per unit voltage.  

But in the case of finfets the gate capacitance is defined as follows  
The total gate capacitance is the capacitance per unit area times the total area of the gate that is  
Weff ​= 2Hfin ​+ Wfin​, Coxeff ​= Cox ​× Weff​  
From the above formula we can conclude that the effective capacitance is more which leads to more control over the channel charge, hence better gate control and more drive current with shorter channel. And in case of multi fins the gate capacitance can be given by   
Ctotal = N × Coxeff ​× L where N is the number of fin.  

**Threshold Voltage:**  
The voltage below which the transistor is off and when the Vgs is greater than or equal to the threshold voltage Vth the inversion layer is formed leading to the flow of current.  
In an nMOS FinFET (or planar nMOS):  
The substrate (or fin) is p-type — it has holes.  
The gate has to attract electrons to the surface to form a conductive path (inversion layer).  
But before electrons can gather, the gate voltage must first:  
Cancel the charge in the depletion region, and then pull in enough electrons to invert the surface to n-type. That total required voltage is what we call Vth.  
Basically what we can say is that the concept of the threshold voltage remains the same in plannar and finfet, the difference is FinFETs achieve the threshold condition more efficiently because the gate wraps around the channel and has stronger control.  

**Drain Current:**  
In the saturation region, the drain current of a FinFET is similar to a MOSFET:

$$I_D = \frac{1}{2} \mu_n C_{ox,eff} \frac{W_{eff}}{L} (V_{GS} - V_{th})^2$$  
Where:  
- **μ<sub>n</sub>** → Electron mobility  
- **C<sub>ox,eff</sub>** → Effective gate capacitance (stronger control due to gate wrapping around the fin)  
- **W<sub>eff</sub>** → Effective channel width (depends on fin height and number of fins)  
- **L** → Channel length  
- **V<sub>GS</sub> − V<sub>th</sub>** → Gate voltage above threshold.
In the case of finfet the Cox and Weff increase the current, due to gate wrapping a larger area of the channel which leads to more drive current per unit area than plannar mosfet.







