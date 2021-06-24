## Exemple of using the DeflaterOutputStream

>See the how DeflaterOutputStream work 
[visite main article](https://blog.mouadoumous.online/how-to-compresse-data-in-java-using-deflateroutputstream  )

This code is a simple character-mode program that deflates files. Filenames are read from the command line. A file input stream is opened to each file; a file output stream is opened to that same filename plus .df l (for deflated). Finally, the file output stream is chained to a **deflater output stream**, then a stream copier pours the data from the input file into the output file. 

```
import java.io.*; 
import java.util.zip.*; 
import com.macfaq.io.*; 
public class FileDeflater { 
 public final static String DEFLATE_SUFFIX = ".dfl"; 
 public static void main(String[] args) { 
 for (int i = 0; i < args.length; i++) { 
 try { 
 FileInputStream fin = new FileInputStream(args[i]); 
 FileOutputStream fout = new FileOutputStream(args[i] + 
 DEFLATE_SUFFIX); 
 DeflaterOutputStream dos = new DeflaterOutputStream(fout); 
 StreamCopier.copy(fin, dos); 
 dos.close(); 
 fin.close(); 
 } 
 catch (IOException e) {System.err.println(e);} 
 } 
 } 
} 
```
This program is a lot simpler than the code that use Deflater class derectly, even though the two programs do the same thing. In general, a `DeflaterOutputStream` is preferable to a raw `Deflater` object for reasons of simplicity and legibility, especially if you want to use the default strategy, algorithm, and compression level. However, using the Deflater class directly does give you more control over the strategy, algorithm, and compression level. You can get the best of both worlds by passing a custom-configured `Deflater` object as the second argument to the 
``DeflaterOutputStream() ``constructor. 