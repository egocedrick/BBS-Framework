# BBS Framework

**Build. Break. Secure.**  
A personal security methodology for Mobile development.

---

## What is BBS?

BBS is not a library. Not a tool you can install.  
It's a personal security methodology — a three-phase process 
I apply it to every Android app I build.

I came up with it, not because I read about it somewhere,  
But because something broke in production, I had to think fast.

---

## Why I Built This

About a month after I deployed my first production app —
An Application Lock for a bus ticketing POS system —
A user accessed the device in Safe Mode.

At first, I asked myself three questions:

- Is this a machine problem?
- Is this a user problem?
- Or is this a software problem?

Turns out, Safe Mode in Android exists by design.  
It's a built-in last resort — meant to help users remove 
malicious or threatening apps by disabling all third-party 
applications on boot.

The problem? My app lock was a third-party app.  
Which meant in Safe Mode, it was dead.  
The lock was gone. The protected apps were accessible.  
And anyone who knew this could walk right in,  
access sensitive files, delete them, or take them.

I didn't panic. But I did realize something:

> I had built something real, deployed it to real users,  
> and never once thought about how it could be broken  
> — until someone broke it.

That moment is where BBS came from.

---

## The Three Phases

### B — Build
Build the app. But think about security from the first line,  
not the last.

- Define lock state persistence before writing UI
- Consider Safe Mode behavior during architecture planning
- Use Android Device Policy APIs from day one
- Ask: *"How would someone get around this?"*  
  — before someone actually does

### B — Break
Intentionally try to break your own app.  
Be the attacker before someone else is.

- Test in Safe Mode
- Try force uninstall
- Try killing the background service manually
- Try accessing protected storage from another app
- Ask: *"If I wanted to sneak in — how would I do it?"*

### S — Secure
Fix what you found. Document what broke.  
Then go back to Build — and repeat.

- Apply targeted fixes based on real findings
- Don't patch blindly — understand *why* it broke
- Update documentation so the next version starts smarter

---

## Real-World Applications

**[Application Lock](https://github.com/egocedrick/ApplicationLock-Android)**  
The app that started all of this. Built, deployed, and broken by 
Safe Mode, then hardened using BBS.

**[Dual Write Reseed](https://github.com/egocedrick/Dual-Write-Reseed)**  
The direct response to the Safe Mode vulnerability —  
a redundancy layer that protects critical data even when 
device protection is bypassed.

---

## Honest Notes

I'm not a security expert.  
I'm an IT professional who got thrown into Android development  
with zero mobile background — and figured things out as I went.

BBS is a work in progress. It evolves every time I build 
something new, break something I thought was solid,  
or learn something that changes how I think.

That's the point.

*Last updated: May 2026*  
*Created by John Cedrick O. Asad*
