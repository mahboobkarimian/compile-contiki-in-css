# Setup and compile Contiki-NG in Code Composer Studio

1. Clone Contiki-NG according to their instructions in the GitHub repo.
2. Download and install the latest CSS.
3. Run CSS and go to View→CSS App Center. Search for `gcc` and install `ARM GCC` compiler.
4. If you are in Windows, install “Git Bash” from [https://gitforwindows.org/](https://gitforwindows.org/)
5. Follow the instructions from pages [3 to 6] of the attached document. But wait:
    
    5.1. In Linux, the PATH elements in CSS needs to be separated with a `:`
    
    5.2. In Windows the separator is `;`
    
6. Now do pages 7.
7. For page 8, DO NOT exclude other executable formats from being made. Let it stay “all”. Also, note that our setup can not create the HEX file; to fix this a quick workaround is:
    
    Remove all occurrences of `$(OUT_HEX)` from the `/contikiONcss/arch/cpu/arm/Makefile.arm` file. This will avoid creating HEX executable format and so the error will be eliminated.
    
8. For page 9, If you use SimpleLink platform you need to do the following instead:

```makefile
TARGET=simplelink
BOARD=launchpad/cc1312r1
CFLAGS += -g
```

Note that this is for SimpleLink cc1312r1

1. Continue with page 10 to build the project. If any error happens, go to check the PATH environment variable. Maybe you also need to add the path to arm gcc binary.
2. Continue with the document for debugging.

The document is available here.

Reference to document: https://e2e.ti.com/cfs-file/__key/communityserver-discussions-components-files/156/contiki_2D00_ccs_2D00_debugging.pptx I found it in TI Forum.
