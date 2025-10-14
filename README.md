# 7nm FinFET Technology

This repository provides a clear and concise explanation of **7 nm FinFET (Fin Field Effect Transistor)** technology — how it evolved, why it replaced traditional planar MOSFETs, challenges, and advantages.

---

## Table of Contents
1. [Introduction](#Introduction)
2. [Why Did We Start Using FinFETs?](#why-did-we-start-using-finfets)
3. [Structure of FinFET](#structure-of-finfet)
4. [Fabrication Process Overview](#fabrication-process-overview)
5. [Advantages of FinFET Technology](#advantages-of-finfet-technology)
6. [Challenges in 7nm Node](#challenges-in-7nm-node)
7. [Comparison: Planar vs FinFET](#comparison-planar-vs-finfet)
8. [References](#references)

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
Now when the Vgs<Vth the gate voltage will repel the electrons and pull the holes up, forming a depletion region that's the barrier blocking the electrons. This leads the mosfet to turn off and current will be zero, as the technology increases the channel length decreases for the sake of faster switching and many other reasons but when the channel length decreases the source and drain come close to each other this leads to many problems, the major problem being the electric field spreading.  
Electric field spreading: In case of NMOS the drain has positive voltage, which means that the positive electric field extending from drain to channel, but when the channel is long the field dies before reaching the source, so the barrier is only controlled by the gate, but in the case of short channel the drain's electric field penetrates deep into the channel and overlap's the source causing the formation of channel due to the drain's positive voltage leading to the flow of current called as the leakage current even when the gate is trying to off the transistor.  
The above discussed is one of the major short channel effect and is widely called as **Drain Induced Barrier Lowering(DIBL)**.  
### How FinFET Solves This Problem  
In the case of plannar mos we had the gate only on the top of the channel which lead to DIBL and many other problem(majorly leakage of current), now in the case of finfet we the gate wrapped around the channel on three sides(top,right,left) which leads to:  
Stronger electrostatic control of the channel.  
The drain’s field can’t easily penetrate to the source.  
The barrier remains high when off, leakage current drops drastically.

