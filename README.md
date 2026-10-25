# luau-compile-rbx

Automated CI cross-compilation pipeline for a customized Luau compiler that natively emits Roblox-compatible Luau bytecode.

## Specifications
- **Base Version:** Luau `0.744` (Bytecode Version 14)
- **Opcode Cipher:** $\text{rbx\_op} = (\text{std\_op} \times 227) \pmod{256}$
- **Mechanism:** Integrates `RobloxBytecodeEncoder` directly into `Luau::BytecodeBuilder` inside `Compile.cpp`, guaranteeing 100% compliant emission across all optimization levels (`-O0`, `-O1`, `-O2`), function closures, and proto hierarchies with zero post-processing.
- **Binaries:** Statically linked ELF binaries for `aarch64` (Linux/Android Termux) and `x86_64`.
