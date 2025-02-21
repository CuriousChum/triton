set(MLIR_BINARY_DIR ${CMAKE_BINARY_DIR})

set(LLVM_TARGET_DEFINITIONS Passes.td)
mlir_tablegen(Passes.h.inc -gen-pass-decls -gen-pass-docs -name TritonGPU)
add_public_tablegen_target(TritonGPUTransformsIncGen)
add_mlir_doc(Passes TritonGPUPasses passes/ -gen-pass-doc)
