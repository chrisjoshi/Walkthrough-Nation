# PicoCTF Walkthrough: Server Log Reconstruction

## Description of the challenge

Our server seems to be leaking pieces of a secret flag in its logs. The parts are scattered and sometimes repeated. Can you reconstruct the original flag?
Download the logs and figure out the full flag from the fragments.

## Step 1 — Viewing the Log File

We start by opening the log file and filtering only the lines that contain the keyword **FLAG**:

```
cat server.log | grep FLAG
```

This reveals multiple repeated entries of four distinct fragments:

- `picoCTF{us3_`
- `y0urlinux_`
- `sk1lls_`
- `cedfa5fb}`

These fragments appear throughout the log but in the **same consistent order**, only repeated due to logging.  

![Pico Image](PicoCTF/Media/Picolevel0201.png)

---

## Step 2 — Reconstructing the Flag

Since each FLAGPART repeats but maintains the same sequence, we simply combine the unique fragments in the correct order:

```
picoCTF{us3_ + y0urlinux_ + sk1lls_ + cedfa5fb}
```

---

## Final Flag

```
picoCTF{us3_y0urlinux_sk1lls_cedfa5fb}
```

---

## Summary

1. **Grep searched** for “FLAG” inside the log.  
2. Observed **four repeating fragments**.  
3. **Combined** the fragments into one full flag.

---

**End of walkthrough**
