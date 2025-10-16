# 7nm FinFET Technology

This repository provides a clear and concise explanation of **7 nm FinFET (Fin Field Effect Transistor)** technology — how it evolved, why it replaced traditional planar MOSFETs, challenges, and advantages.

---

## 📘 Table of Contents
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
5. Oxide thickness(Tox) - Determines the gate capacitance and controls the strength.  In the above mentioned structural dimensions **channel lenght, fin height, fin thickness, and oxide thickness** become the important geometrical knobs of how tightly the gate can control the channel.







