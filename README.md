* https://docs.microsoft.com/en-us/cpp/build/reference/zp-struct-member-alignment?view=msvc-160#remarks
> :warning: Warning
> 
> The C/C++ headers in the Windows SDK assume `/Zp8` packing internally. Don't change the setting from the default when you include the Windows SDK headers, either by using `/Zp` on the command line or by using `#pragma pack`. Otherwise, your application may cause memory corruption at runtime.

* https://docs.microsoft.com/en-us/cpp/cpp/align-cpp?redirectedfrom=MSDN&view=msvc-160#remarks
> Without `__declspec(align(#))`, the compiler generally aligns data on natural boundaries based on the target processor and the size of the data, up to 4-byte boundaries on 32-bit processors, and 8-byte boundaries on 64-bit processors. Data in classes or structures is aligned in the class or structure at the minimum of its natural alignment and the current packing setting (from `#pragma pack` or the `/Zp` compiler option).

* https://docs.microsoft.com/en-us/cpp/preprocessor/pack?view=msvc-160#parameters
> If the compiler option /Zp isn't set for the module, the default value for `n` is 8.

* https://docs.microsoft.com/en-us/windows/win32/winprog/using-the-windows-headers?redirectedfrom=MSDN#controlling-structure-packing
> Projects should be compiled to use the default structure packing, which is currently 8 bytes because the largest integral type is 8 bytes. Doing so ensures that all structure types within the header files are compiled into the application with the same alignment the Windows API expects. It also ensures that structures with 8-byte values are properly aligned and will not cause alignment faults on processors that enforce data alignment.
