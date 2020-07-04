# A brief intro to the syntax of JavaScript
In this little introduction I want to tell you about 5 concepts:

* white space

* case sensitivity

* literals

* identifiers

* comments



## JavaScript sentaksına(söz dizimine) kısa bir giriş
Bu kısacık girişte sizlere beş konu hakkında bir şeyler söyleyeceğim:

* Boşluk(White space)

* Büyük-küçük harf ayrımı

* Yazım

* Tanımlayıcılar(identifiers)

* Yorum
  
## ----------

### White space

 JavaScript does not consider white space meaningful. Spaces and line breaks can be added in any fashion you might like, at least in theory.

In practice, you will most likely keep a well defined style and adhere to what people commonly use, and enforce this using a linter or a style tool such as Prettier.

For example, I always use 2 space characters for each indentation.



### Boşluk (White Space)

 JavaScript bırakılan boşluğu anlamlandırmaz. Boşluklar ve satır geçişleri, teoride, istediğiniz tarzda eklenebilir.

Pratikte, büyük ihtimalle iyi derlenmiş bir stil tutturacaksınız ve insanlar çoğunlukla ne kullanıyorsa ona bağlı olacaksınız. Bu kullanım sizi Prettier gibi bir stil aracı kullanımına sizi itecektir.

## ----------

### Case sensitive
JavaScript is case sensitive. A variable named `something` is different than `Something`.

The same goes for any identifier.



### Büyük-küçük harf ayrımı
 JavaScript büyük-küçük harf ayrımına duyarlıdır. `something` diye yazacağınız şey `Something` 'den farklı olacaktır.

 Aynısı herhangi bir tanımlayıcı(identifier) için de geçerlidir.

## ----------

### Literals
We define literal as a value that is written in the source code, for example, a number, a string, a boolean or also more advanced constructs, like Object Literals or Array Literals:

```javascript
5
'Test'
true
['a', 'b']
{color: 'red', shape: 'Rectangle'}

```



## Yazım

Yazımı kaynak kodda yazılmış bir değer olarak tanımlarız. Örneğin bir sayı(number), string, boolean ya da Nesne(Object) yazımı veya Dizi(Array) yazımı gibi daha ileri constructlar(yapılar).

```javascript
5
'Test'
true
['a', 'b']
{color: 'red'; shape:'Rectangle'}

```

## ----------

### Identifiers
An identifier is a sequence of characters that can be used to identify a variable, a function, or an object. It can start with a letter, the dollar sign $ or an underscore _, and it can contain digits. Using Unicode, a letter can be any allowed character, for example, an emoji 😄.

```javascript
Test
test
TEST
_test
Test1
$test

```
The dollar sign is commonly used to reference DOM elements.

Some names are reserved for JavaScript internal use, and we can't use them as identifiers.


### Tanımlayıcılar
Tanımlayıcı(identifier) bir değişkeni, bir fonksiyonu ya da bir objeyi tanımlamak için kullanılan karakter aralığı olarak adlandırılabilir. Bir harfle, dolar($) işaretiyle, alt çizgi(_) de başlayabilir ya da basamaklar(digits) içerebilir. Unicode(Evrensel kod) kullanarak bir harf, izin verilen herhangi bir karakter olabilir, mesela bir emoji(😄).

```javascript
Test
test
TEST
_test
Test1
$test

```

Dolar işareti DOM(Data Object Model) elementlerine referans için kullanılır.

Bazı adlar JavaScript dahili kullanımı için rezerve edilmiştir; bunları tanımlayıcı olarak kullanamayız.

## ----------


### Comments
Comments are one of the most important parts of any program, in any programming language. They are important because they let us annotate the code and add important information that otherwise would not be available to other people (or ourselves) reading the code.

In JavaScript, we can write a comment on a single line using `//`. Everything after `//` is not considered as code by the JavaScript interpreter.

Like this:

```javascript
// a comment
true //another comment

```
Another type of comment is a multi-line comment. It starts with `/*` and ends with `*/.`

Everything in between is not considered as code:

```javascript
/* some kind
of 
comment 

*/
```



### Yorumlar
Yorumlar bir programın ya da programlama dilinin en önemli parçalarıdır. Önemli olmalarının sebebi kodu okurken kendimiz için ya da okuyacak başka birisi için kod hakkında detaylı açıklamalar yapmamızı ve önemli bilgileri eklememizi sağlamasıdır.

JavaScript'te tek satırlık yorumları `//` ile yaparız. Bu aralıkta yazılanlar kod olarak değerlendirilmez.

```javascript
// Bir Yorum
true //Başka bir yorum

```

Bir diğer yorum ise çoklu satırlardaki yorumdur. `/*` ile başlar ve `*/` ile biter.

Bu aralıktakiler kod olarak değerlendirilmez.

```javascript
/* some kind
of
comment

*/
```