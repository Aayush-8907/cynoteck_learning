
A container is like a small package that contains everything needed to run an application.

It includes:
- Application Code
- Required Libraries
- Runtime (Python,etc.)
- System Tools
- Configuration Files

This is called a *Standalone Package*  
(Meaning: Ready-to-use package that runs anywhere)

---

## How to Stop a Running Container?

Command:

```bash
docker stop <container_name_or_id>
```

## How to Remove a Container?

Command:

``` bash 
docker rm <container_name_or_id>
```

## Difference Between Container and Virtual Machine (VM)


| Container                      | Virtual Machine (VM)         |
| ------------------------------ | ---------------------------- |
| Lightweight Package            | Heavy Package                |
| Shares Host OS Kernel          | Has its Own Full OS + Kernel |
| Fast Start Time                | Slow Start Time              |
| Runs App Only                  | Runs Full Operating System   |
| Uses Less Memory & Resources   | Uses More Memory & Resources |
| Small in Size (MBs)            |  Large in Size (GBs)         |
| Isolation at Application Level | Isolation at Hardware Level  |
|                                |                              |
