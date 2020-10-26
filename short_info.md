# Kisa Bilgiler : 

#### Buffer nedir ? 

Buffer (tampon saha), verilerin IO işlemlerinden sonra belleğe yazılmadan önce uğradıkları bir sahadır. Bufferlar IO işlemi sırasında kullanıcının beklemesini engellemek için kullanılırlar.

Bilgisayar sistemlerinde dosya okuma, dosya yazma ve ağlar arası iletişim ikili sayı tabanına göre yapılır. JavaScript, unicode ile barışık olmasına rağmen, ikili (binary) veriyi işlemekte çok iyi özellikler göstermez.

Node.js'te buffer bir tamsayı dizisi gibi çalışır; ancak yeniden boyut verilemez. Buffer sınıfı, globaldir; ikili (binary) veriyi doğrudan işleme olanağı sağlar.


#### Bufferda yazma işlemi : 

buf.write() metodu, buffer'a bir string yazmak için kullanılır

`
var buf = new Buffer(12); 

buf.write(" harikadir",10,"utf8");

`

#### Buffer'dan Okuma İşlemi 

buf.toString([kodlama], [başlangıç], [son])

buf.toString() metodu, ikili olarak kodlanmış veriyi çözer ve buffer'daki veriyi okuyarak bir stringe yükler.

`
var buf = new Buffer(15);

buf.write("TURKIYE","utf8");
buf.toString("utf8",0,4); 

//çıktı TURK olur
`

#### Bir Stringin Gerçek Uzunluğu 

Buffer.byteLength(string, [kodlama]) metodu, verilen bir kodlama sistemine göre saklandığında, string'in alacağı gerçek uzunluk miktarını verir.


```javascript
var sar="Turkcell Gelecegi Yazanlar";

console.log(Buffer.byteLength(sar,"utf8")); // utf-8 türündeki uzunluğunu verir 
console.log(Buffer.byteLength(sar,"base64"));// base64 türündeki uzunluğunu verir 

```


#### İki Buffer'ı Birbirine Ekleme

Buffer.concat() metodu, iki ya da daha fazla buffer'ı ya da string'i birbirine eklemek için kullanılır.

```javascript
var a = new Buffer("merhaba");
var b = new Buffer(" istanbul");
var c = Buffer.concat([a,b],16);
c.toString();

```

