# A patch to build macOS native build of ProteoWizard
The patch is provided to build ProteoWizard native executable on macOS Catalina (10.15) and Apple clang 11.0.3.
This patch fixes errors occurred during build of boost 1.67 [1, 2, 3].

## Target macOS Environment
- Targeted ProteoWizard version: 3 0 20306  (pwiz-src-without-v-3_0_20306_f98a963 )  (NO 3rd party reader) obtained from ProteoWizard's download site: http://proteowizard.sourceforge.net/download.html
- My mac environment for software development
  - macOS Catalina 10.15.6
  - Xcode 11.6
　- Apple clang version 11.0.3 (clang-1103.0.32.62)

## References
I made the patch based on following valuable patches and comments.

1. clang: error: unknown argument: '-fcoalesce-templates'
  - https://github.com/macports/macports-ports/commit/d6307dd3c34709aeed8b24af5fbcce6b23118670  
2. /libraries/boost_1_67_0/boost/atomic/detail/ops_gcc_x86_dcas.hpp:408:16: error: address argument to atomic builtin cannot be const-qualified ('const volatile boost::atomics::detail::gcc_dcas_x86_64::storage_type *' (aka 'const volatile unsigned __int128 *') invalid)
  - https://github.com/boostorg/atomic/issues/15
     - https://github.com/boostorg/atomic/commit/6e14ca24dab50ad4c1fa8c27c7dd6f1cb791b534
3. /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/../include/c++/v1/algorithm:2495:5: error: static_assert failed due to requirement 
  - https://github.com/sneumann/mzR/issues/190
     - https://github.com/sneumann/mzR/commit/d9ea53110b65246e20a0fae4c6446a15901a6801
       - this patch call boost::first_max/min_element instead of std::min/max_element at boost::range::min/max_element



