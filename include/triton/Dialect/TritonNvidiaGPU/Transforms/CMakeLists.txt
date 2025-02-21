set(MLIR_BINARY_DIR ${CMAKE_BINARY_DIR})

set(LLVM_TARGET_DEFINITIONS Passes.td)
mlir_tablegen(Passes.h.inc -gen-pass-decls -name TritonNvidiaGPU)
add_public_tablegen_target(TritonNvidiaGPUTransformsIncGen)
add_mlir_doc(Passes TritonNvidiaGPUPasses passes/ -gen-pass-doc)
