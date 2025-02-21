set(MLIR_BINARY_DIR ${CMAKE_BINARY_DIR})

set(LLVM_TARGET_DEFINITIONS Passes.td)
mlir_tablegen(Passes.h.inc -gen-pass-decls --name TritonToTritonGPU)
add_public_tablegen_target(TritonConversionPassIncGen)
add_mlir_doc(Passes TritonToTritonGPUPasses passes/ -gen-pass-doc)
