# SEVENSINS

![Difficulty](https://img.shields.io/badge/difficulty-medium--hard-orange)
![Platform](https://img.shields.io/badge/platform-VirtualBox%20%7C%20VMware-blue)
![Status](https://img.shields.io/badge/status-active-brightgreen)

> A deliberately vulnerable e-commerce web app, built as a multi-stage CTF machine for anyone who wants to practice real-world web and infrastructure exploitation from the ground up.

---

## Table of Contents

- [Project Overview](#project-overview)
- [About the Machine](#about-the-machine)
- [What You'll Learn](#what-youll-learn)
- [Who Is This Machine For?](#who-is-this-machine-for)
- [What Makes It Fun?](#what-makes-it-fun)
- [Prerequisites and Recommended Knowledge](#prerequisites-and-recommended-knowledge)
- [Download](#download)
- [How to Get Started](#how-to-get-started)

## Project Overview

SEVENSINS is themed around the seven deadly sins, with seven flags, each one tied to a sin and to a distinct stage of the attack. It's meant to be a full chain, not a quick win. You won't just find one bug and call it a day. You'll start with a foothold on a public-facing web app, then pivot, enumerate, and escalate your way across several services to reach the end.

Think of it as a small slice of a real target: a web app with a genuine bug in it, an admin panel that's looser than it should be, internal services that trust each other a bit too much, and a privilege escalation waiting at the very end.

## About the Machine

The target is a PHP/Apache/MySQL e-commerce app, with an admin panel backed by Node.js and a browser-automation "admin bot." That last part matters, because some of what you do as an attacker needs to actually be seen by something that looks like a real user, not just queried directly. Past the web layer, there are a few more services sitting on the box, the kind you'd expect on a small internal network, and what you learn on one tends to carry over to the next.

Each flag marks a step along that chain, from the first web app compromise all the way to full control of the system.

## What You'll Learn

Working through SEVENSINS, you'll get practice with:

- Spotting and weaponizing client-side bugs in a real-feeling web app, including thinking from another user's browser and session instead of just your own
- Manually probing a web app's inputs and behavior rather than leaning on automated scanners
- Getting into a database once you've got a foothold, and actually doing something with it
- Handling credentials: recognizing what kind of hash you're looking at, cracking it efficiently, and following reused passwords wherever they lead
- Reading configs, logs, and leftover files for the small details that matter
- Pulling useful info out of a compiled binary without needing a full reverse-engineering pass
- Spotting a misconfigured permission and using it to escalate

## Who Is This Machine For?

SEVENSINS is a good fit if you're:

- A CTF player who's comfortable with basic web exploitation and wants something longer and more connected
- A pentester wanting to run through a full engagement flow somewhere safe and self-contained
- A student or self-learner ready to move past single-bug boxes into something more realistic
- Someone who just likes a machine with a bit of a story to it, not only a checklist of flags

Having some background in common web vulnerabilities and basic Linux will smooth out the early stages, but you don't need to walk in already knowing every technique. The machine teaches as you go.

## What Makes It Fun?

This isn't one bug sitting on its own, it's a chain. Every flag gives you something you'll actually need next: a credential, a username, a service you didn't even know was there. Nothing's wasted, nothing's just for show, and nothing's going to sit around waiting for you to stumble on it. You have to go looking for it. The admin-bot piece also means thinking from someone else's point of view, which is a different kind of thinking than just hammering a server directly. By the time you're done, you'll have gone through a real spread of attacker tradecraft, all building toward one last payoff at the end.

## Prerequisites and Recommended Knowledge

- Comfortable in a Linux attacker environment (Kali or similar)
- Know your way around common web vulnerability classes
- Have used hash cracking tools before, at least the basics
- Can connect to and enumerate common network services

## Download

The machine ships as a VM image, ready to drop into whichever hypervisor you use.

**[Download SEVENSINS VM](https://tinyurl.com/Seven5ins)**

> Only run this in an isolated lab (host-only or NAT network). It's intentionally vulnerable, so keep it off anything shared or production-facing.

## How to Get Started

1. Download and import the VM into VirtualBox, VMware, or whatever you've got.
2. Boot it on an isolated or host-only network and find its IP.
3. Start with normal recon against the web app. Don't rush through it, even if it's tempting.
4. Pay attention to how the app responds to your input, not just whether it responds at all. That's where the real work is.
5. Hang onto everything you find along the way, even if it doesn't seem useful yet. It will.
6. Take the chain one flag at a time.

---

*Good luck, and enjoy the sins.*
