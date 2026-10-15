---
title: Orphaned VBA Projects Inside DWG Files
date: 2026-10-14
categories: [RESEARCH]
tags: [VBA,DWG,OLE,AUTOCAD,SCRIPTING]
---

## Orphaned VBA Projects Inside DWG Files

In a nutshell: the VBA code is stored inside an OLE file, which is embedded inside the DWG file. You can perform a brute-force search for the embedded OLE file, or you can follow a pointer inside the header of the DWG file. I wrote a small Python script (**autocad.py**) for this second case. It examines a 32-bit pointer at position **0x24** inside the DWG file. This points to a 16-byte long header, followed by the embedded file. This 16-byte long header contains the length of the embedded file. When the pointer is zero, there is no embedded OLE file, and **cut-bytes.py** returns nothing.

Recently, I discovered 2 DWG files that are exceptions: their pointer to the embedded OLE file is zero, but if you perform a brute-force search, you will find an embedded OLE file with a VBA project. Its pointer to the embedded VBA project is zero, but it contains an embedded OLE file. Right in front of the embedded OLE file, there is the 16-byte long header that contains the length of the embedded file. Using the AutoCAD script to extract the file yields nothing. However, **oledump.py** can find the embedded OLE file and analyze it.

So while using **oledump.py** to analyze DWG files where you find a VBA project embedded inside a DWG file, also verify if it is not orphaned: check that the pointer at **0x24** is not zero (or use the **autocad.py** script). Because when a DWG file contains an orphaned VBA project, the VBA code cannot execute when someone opens the DWG file with AutoCAD. AutoCAD "does not see" orphaned VBA projects. 

Notice that a default installation of AutoCAD does not support VBA. VBA for AutoCAD is a separate install. I don't know how orphaning occurs, but I did find an AutoLISP command to remove a VBA project from a DWG file: `(dictremove (namedobjdict) "ACAD_VBA")`. Maybe this **dictremove** command clears the pointer but does not remove the embedded OLE file.

For more details, check out the full article here: [Read full article](https://isc.sans.edu/forums/diary/Orphaned%20VBA%20Projects%20Inside%20DWG%20Files/33420/) 

🚀 Happy coding!