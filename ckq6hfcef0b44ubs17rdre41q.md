## Decompressing data in Java using Inflater input Stream

The `InflaterInputStream` class is a filter stream that inflates data while reading it from the underlying stream. 

``public class InflaterInputStream extends FilterInputStream ``

Each inflater input stream uses a protected Inflater object called inf to decompress data that is stored in a protected internal byte array called buf. There's also a protected int field called *len* that (unreliably) stores the number of bytes currently in the buffer, as opposed to the length of the buffer itself. 
``protected Inflater inf;`` 
``protected byte[] buf; ``
``protected int len; ``
The same Inflater object must not be used in multiple streams at the same time. 
The underlying input stream from which deflated data is read, the Inflater object inf, and the length of the byte array buf are all set by one of the three `InflaterInputStream()`constructors: 

``public InflaterInputStream(InputStream in, Inflater inf, int bufferLength) ``

``public InflaterInputStream(InputStream in, Inflater inf)`` 

``public InflaterInputStream(InputStream in) ``

The underlying input stream must be specified, while the buffer length defaults to 512 bytes, 
and the Inflater defaults to an inflater for deflated streams (as opposed to zipped or gzipped 
streams). Of course, the `InflaterInputStream` has all the usual input stream methods like 
`read()`, `available()`, and `close()`. It overrides the following three methods: 

`public int read() throws IOException` 

`public int read(byte[] data, int offset, int length) throws IOException `

`public long skip(long n) throws IOException `

For the most part, you use these the same way you'd use any read() or skip() method. However, it's occasionally useful to know that the read method throws a new subclass of IOException, `java.util.zip.ZipException`, if the problem is that the data doesn't adhere to the expected format. You should also know that `read()`, `skip()`, and all other input stream methods count the uncompressed bytes, not the compressed raw bytes that were actually read. 
There's also one new protected method, `fill()`, which reads compressed data from the 
underlying input stream into buf, sets len to the number of bytes read, and then sets inf's input to the appropriate subarray of buf: 

`protected void fill() throws IOException `


> [ **See the code** ]( https://blog.mouadoumous.online/exemple-code-for-inflater-input-stream )