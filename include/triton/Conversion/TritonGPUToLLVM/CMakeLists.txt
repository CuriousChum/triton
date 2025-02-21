set(MLIR_BINARY_DIR ${CMAKE_BINARY_DIR})

set(LLVM_TARGET_DEFINITIONS Passes.td)
mlir_tablegen(Passes.h.inc -gen-pass-decls --name TritonGPUToLLVM)
add_public_tablegen_target(TritonGPUConversionPassIncGen)
add_mlir_doc(Passes TritonGPUToLLVMPass passes/ -gen-pass-doc)
