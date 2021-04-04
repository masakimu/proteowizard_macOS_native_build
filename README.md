# proteowizard_macOS_native_build
how to build ProteoWizard native executable on macOS Catalina (10.15) and Apple clang 11.0.3

## Target macOS Environment
- Targeted ProteoWizard version: 3 0 20306  (pwiz-src-without-v-3_0_20306_f98a963 )
- My mac environment for software development
  - macOS Catalina 10.15.6
  - Xcode 11.6
　- Apple clang version 11.0.3 (clang-1103.0.32.62)


## References
- related to build error from boost 1.67
  - clang: error: unknown argument: '-fcoalesce-templates'
    - https://github.com/macports/macports-ports/commit/d6307dd3c34709aeed8b24af5fbcce6b23118670  
  - /libraries/boost_1_67_0/boost/atomic/detail/ops_gcc_x86_dcas.hpp:408:16: error: address argument to atomic builtin cannot be const-qualified ('const volatile boost::atomics::detail::gcc_dcas_x86_64::storage_type *' (aka 'const volatile unsigned __int128 *') invalid)
    - https://github.com/boostorg/atomic/issues/15
     - https://github.com/boostorg/atomic/commit/6e14ca24dab50ad4c1fa8c27c7dd6f1cb791b534
    - https://github.com/sneumann/mzR/issues/190
     - https://github.com/sneumann/mzR/commit/d9ea53110b65246e20a0fae4c6446a15901a6801
       - call boost::first_max/min_element instead of std::min/max_element at boost::range::min/max_element



