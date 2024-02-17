---
title: Terminals
published: false
tags: [terminals, ascii]
---

### Introduction

I write this as a personal brain-dump, a warning to my past self, and to others in the now. 

### Mental Model

Any program that can "read keystrokes" or "write to the console" has a teleprinter tangled into its evolution. 
A teleprinter is a keyboard attached to a dot-matrix printer (tick, tick, tick, buzz...), and no screen.
Screens came later with video display terminals or "VDTs".
Wow, a remote printer. How cool is that?

A VDT is backward-compatible w/ a teleprinter. Its key events and display commands are a superset of its predecessor.

An XTerm is backward-compatible w/ a VDT. Its key events and display commands are a superset of its predecessor.

And so on w/ later incarnations to this day.

```C
printf("hello world\n");
```

This code works because when run, it is attached to something that can print.
This code works fine on an actual teleprinter from 1970. In fact, it's designed for it. It expects a teleprinter.

### Keyboards

### We Might Go to Tahoe One Day

The remote case + back compat vs crap UIs

### It Was All We Had

Terminals were used, not because they are awesome, but because it was the only that existed at the time.

### Eight Data Bits, No-parity, One Stop Bit

### Double-Buffered

### Not Eight-bit Clean

Remarkable, but true. You'd think this notion was gone decades ago, but to have a fighting chance at
end-to-end fidelity, one must Base-64 binary payloads, even ones that each end of the channel have a
protocol for defining.

### ASCII

### modifyOtherKeys

### 

