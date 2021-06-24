## How to compresse data in Java using DeflaterOutputStream

The `Inflater` and `Deflater` classes are a little raw for easy digestion. It would be more convenient to write uncompressed data onto an *output stream* and have it compressed by the stream itself, without having to worry about the mechanics of deflation. Similarly, it would be useful to have an *input stream* class that could read from a compressed file but return the uncompressed data. Java, in fact, has several classes that do exactly this. The 

``java.util.zip.DeflaterOutputStream``
 class is a filter stream that compresses the data it receives in deflated format before writing it out to the underlying stream. The 

``java.util.zip.InflaterInputStream``
class inflates deflated data before passing it to the reading program. 
``java.util.zip.GZIPInputStream `` and 
``java.util.zip.GZIPOutputStream ``do the same thing except with the gzip format. 
 
** The DeflaterOutputStream Class** 
`DeflaterOutputStream` is a filter stream that deflates data before writing it onto the underlying stream: 

``public class DeflaterOutputStream extends FilterOutputStream``

Each stream uses a protected `Deflater` object called def to compress data stored in a 
protected internal buffer called buf: 
``protected Deflater def; ``
``protected byte[] buf; ``
The same deflater must not be used in multiple streams at the same time, though Java takes no 
steps to guarantee this. 
The underlying output stream that receives the deflated data, the deflater object def, and the length of the byte array buf are all set by one of the three `DeflaterOutputStream `constructors: 

``public DeflaterOutputStream(OutputStream out, Deflater def, int 
bufferLength) ``

``public DeflaterOutputStream(OutputStream out, Deflater def) ``

``public DeflaterOutputStream(OutputStrea
m out) ``

The underlying output stream must be specified. The buffer length defaults to 512 bytes, and 
the Deflater defaults to the default compression level, strategy, and method. Of course, the 
`DeflaterOutputStream` has all the usual output stream methods like `write()`, `flush()`, and 
`close()`. It overrides three of these methods, but as a client programmer, you don't use them 
any differently than you would in any other output stream: 

``public void write(int b) throws IOException ``

``public void write(byte[] data, int offset, int length) throws IOException``
 
``public void close() throws IOException ``

There's also one new method, `finish()`, which finishes writing the compressed data onto the underlying output stream but does not close the underlying stream. You should call `finish()` instead of `close()` if there are multiple filters chained to the stream: 
``public void finish() throws IOException ``

The `close()` method finishes writing the compressed data onto the underlying stream and then closes it: 

``public void close() throws IOException ``

The protected `deflate()` method sends the compressed data to the underlying stream. You don't invoke it directly. Subclasses that implement different compression formats may override it: 

``protected void deflate() throws IOException ``

> [**see the code** ](  https://blog.mouadoumous.online/exemple-of-using-the-deflateroutputstream )