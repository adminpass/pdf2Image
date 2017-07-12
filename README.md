# pdf2Image
PDF转图片DEMO,可实现超大PDF在线懒加载预览
PDF的在线预览可是用pdf.js等前端工具，也可使用以下
### XDOC:
http://xdocin.com/
### office online：
http://preview.tita.com/op/generate.aspx

对比多种方案，最终选择Apache的pdfbox，转换清晰，效率也不错
主要用到的jar包：
- pdfbox-2.0.6.jar
- fontbox-2.0.6.jar
- bcprov-jdk15on-157.jar
- commons-logging-1.2.jar（依赖）



### 注：部分pdf转换会有以下错误，请加入bcprov-jdk15on-157.jar
    Exception in thread "main" java.lang.NoClassDefFoundError: org/bouncycastle/jce/provider/BouncyCastleProvider
    	at org.apache.pdfbox.pdmodel.encryption.PDEncryption.<init>(PDEncryption.java:96)
    	at org.apache.pdfbox.pdfparser.PDFParser.prepareDecryption(PDFParser.java:310)
    	at org.apache.pdfbox.pdfparser.PDFParser.initialParse(PDFParser.java:225)
    	at org.apache.pdfbox.pdfparser.PDFParser.parse(PDFParser.java:276)
    	at org.apache.pdfbox.pdmodel.PDDocument.load(PDDocument.java:1000)
    	at org.apache.pdfbox.pdmodel.PDDocument.load(PDDocument.java:956)
    	at org.apache.pdfbox.pdmodel.PDDocument.load(PDDocument.java:904)
    	at com.pdf.PdfReader.parsePdf(PdfReader.java:26)
    	at com.pdf.PdfReader.main(PdfReader.java:19)
    Caused by: java.lang.ClassNotFoundException: org.bouncycastle.jce.provider.BouncyCastleProvider
    	at java.net.URLClassLoader.findClass(Unknown Source)
    	at java.lang.ClassLoader.loadClass(Unknown Source)
    	at sun.misc.Launcher$AppClassLoader.loadClass(Unknown Source)
    	at java.lang.ClassLoader.loadClass(Unknown Source)
    	... 9 more
