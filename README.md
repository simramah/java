package jnahelloworldtest;

import com.sun.jna.Library;
import com.sun.jna.Native;
import com.sun.jna.NativeLong;
import com.sun.jna.Platform;
import com.sun.jna.*;

/** Simple example of native library declaration and usage. */
public class Main {
    public interface simpleDLL extends Library {
        simpleDLL INSTANCE = (simpleDLL) Native.loadLibrary(
            (Platform.isWindows() ? "simpleDLL" : "simpleDLLLinuxPort"), simpleDLL.class);
        // it's possible to check the platform on which program runs, for example purposes we assume that there's a linux port of the library (it's not attached to the downloadable project)
        byte giveVoidPtrGetChar(Pointer param); // char giveVoidPtrGetChar(void* param);
        int giveVoidPtrGetInt(Pointer param);   //int giveVoidPtrGetInt(void* param);
        int giveIntGetInt(int a);               // int giveIntGetInt(int a);
        void simpleCall();                      // void simpleCall();
    }
