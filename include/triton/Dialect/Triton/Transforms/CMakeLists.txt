set(MLIR_BINARY_DIR ${CMAKE_BINARY_DIR})

set(LLVM_TARGET_DEFINITIONS Passes.td)
mlir_tablegen(Passes.h.inc -gen-pass-decls -name Triton)
add_public_tablegen_target(TritonTransformsIncGen)
add_mlir_doc(Passes TritonPasses passes/ -gen-pass-doc)
