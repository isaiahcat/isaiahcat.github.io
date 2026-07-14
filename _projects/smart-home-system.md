---
layout: project
permalink: /projects/smart-home-system/
image: /assets/images/stm32nucleo.png
title: Smart Home System - STM32 Embedded IoT Controller
description: Modular embedded system with real-time locks, HVAC, lighting, fire alarm, and security.
tech: [C, STM32, Embedded Systems, Real-Time Systems]
type: academic
educational: false
featured: true
priority: 3
link: https://github.com/isaiahcat
date: 2025-05-01
date_range: "Apr 2025 - May 2025"
---
Designed and implemented a modular embedded system on an STM32F429ZI microcontroller, integrating multiple real-time subsystems including automated locking, lighting control, HVAC, fire alarm, intrusion detection, and an automatic front door. Built a hierarchical menu interface on an I2C LCD with keypad-driven navigation for user interaction.

Technical Highlights:
 - Wrote interrupt-driven input handling (EXTI) for smoke, vibration, and PIR motion sensors.
 - Configured multiple timers:
  --- TIM1 for ultrasonic echo timing (input capture)
  --- TIM3/TIM4 for PWM (servo motors, buzzer)
  --- TIM6/TIM7 for periodic tasks and µs-level trigger pulses
 - Designed state machines for fire alarm, security alarm, and door automation with priority resolution (fire > intrusion).
 - Developed parameterized subsystems: lock scheduling, motion-activated lighting with timeout, HVAC mode switching.
 - Implemented debouncing, asynchronous alert popups, and safe fallback states for partial sensor failures.
 - Added hardware workarounds (LED door indicator, manual fire trigger) to maintain full system functionality with limited components.

Video demo and code available upon request.
