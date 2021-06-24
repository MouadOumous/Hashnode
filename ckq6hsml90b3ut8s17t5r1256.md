## Exemple code for inflater Input STream

>See how InflaterInputStream work [visite main article](  https://blog.mouadoumous.online/decompressing-data-in-java-using-inflater-input-stream )

This code is a simple character-mode program that inflates files. Filenames are read from the 
command line. A file input stream is opened from each file that ends in .df l, and this stream is chained to an inflater input stream. A file output stream is opened to that same file minus the .dfl extension. Finally, a stream copier pours the data from the input file through the inflating stream into the output file. 
```
import java.io.*; 
import java.util.zip.*; 
import com.macfaq.io.*; 
public class FileInflater { 
 public static void main(String[] args) { 
 for (int i = 0; i < args.length; i++) { 
 if (args[i].toLowerCase().endsWith(FileDeflater.DEFLATE_SUFFIX)) { 
 try { 
 FileInputStream fin = new FileInputStream(args[i]); 
 InflaterInputStream iis = new InflaterInputStream(fin); 
 FileOutputStream fout = new FileOutputStream( 
 args[i].substring(0, args[i].length()-4)); 
 StreamCopier.copy(iis, fout); 
 fout.close(); 
 } 
 catch (IOException e) {System.err.println(e);} 
 } 
 else { 
 System.err.println(args[i] + " does not appear to be a deflated 
 file."); 
 } 
 } 
 } 
} 
```
