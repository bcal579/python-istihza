Numpy
=====

NumPy, Python programlama dilinde bilimsel hesaplamalar için kullanılan bir kütüphanedir. "Numerical Python" ifadesinin kısaltmasıdır. NumPy, büyük, çok boyutlu diziler ve matrisler oluşturmayı ve bu diziler üzerinde yüksek performanslı matematiksel işlemler yapmayı sağlar.

NumPy, klasik Python'dan daha hızlıdır çünkü:

1. **Düşük Seviye Optimizasyon**:
   NumPy, C ve Fortran gibi düşük seviyeli dillerde yazılmıştır. Bu, hesaplamaların daha verimli bir şekilde gerçekleştirilmesini sağlar.
   
2. **Vektörleştirme**:
   NumPy, döngüleri ve tekrarlayan işlemleri vektörleştirerek toplu işlemler yapar. Bu, işlemlerin daha hızlı ve daha az bellek kullanarak gerçekleştirilmesine olanak tanır.
   
3. **Sabit Boyutlu Diziler**:
   NumPy dizileri (ndarray), sabit boyutlu ve homojen veri tiplerine sahiptir. Bu, bellek yönetimini optimize eder ve işlem hızını artırır.
   
4. **Daha Az Python Overhead'i**:
   NumPy, Python'un dinamik tip sisteminin getirdiği ek yükü azaltarak daha hızlı çalışır. Python'da her bir öğe için tip kontrolü yapılırken, NumPy'de bu işlem daha az sıklıkla gerçekleşir.

Bu nedenlerle, büyük veri setleri ve matematiksel hesaplamalarla çalışırken NumPy kullanmak, performans açısından büyük avantajlar sağlar.

NDArray Oluşturmak - Upcasting
-------------------------------

NDArray = N-dimensional array = Çok boyutlu dizi

1. **Çok Boyutluluk**: `ndarray`, 1D (tek boyutlu), 2D (iki boyutlu), 3D (üç boyutlu) ve daha yüksek boyutlu dizileri temsil edebilir. Örneğin, bir 2D `ndarray`, matris olarak düşünülebilir.
   
2. **Homojen Veri Tipi**: Tüm elemanlar aynı veri tipine sahiptir. Bu, dizinin bellekte daha verimli bir şekilde saklanmasını sağlar.
   
3. **Hız ve Verimlilik**: NumPy, C dilinde yazıldığı için, `ndarray` üzerinde yapılan işlemler genellikle Python'un yerel veri yapılarıyla yapılan işlemlerden çok daha hızlıdır.
   
4. **Matematiksel İşlemler**: `ndarray`, vektör ve matris işlemleri gibi matematiksel işlemleri kolayca yapmanıza olanak tanır.

Upcasting = Daha düşük olan bir verinin daha yükseğe çıkarılması. Örneğin int32'nin float64'e çıkarılması.

.. code-block:: python

   import numpy as np

   # 1D ndarray oluşturma
   arr_1d = np.array([1, 2, 3, 4, 5])
   print("1D Dizi:", arr_1d)

   # 2D ndarray (matris) oluşturma
   arr_2d = np.array([[1, 2, 3], [4, 5, 6]])
   print("2D Dizi:\n", arr_2d)

   # Dizi boyutunu öğrenme
   print("Dizi Boyutu:", arr_2d.shape)

   # Dizi elemanlarına erişim
   print("İlk Eleman:", arr_1d[0])
   print("İkinci Satır, Üçüncü Sütun Elemanı:", arr_2d[1, 2])

   # Dizi üzerinde matematiksel işlemler
   arr_squared = arr_1d ** 2
   print("Kareleri:", arr_squared)

   # 2 katman, 2 satır ve 3 sütundan oluşan 3D dizi oluştur
   arr_3d = np.array([[[1, 2, 3], [4, 5, 6]],  # 1. katman
                      [[7, 8, 9], [10, 11, 12]]])  # 2. katman

   # Dizi özelliklerini yazdır
   print("Dizi Şekli (Shape):", arr_3d.shape)  # (2, 2, 3) - 2 katman, 2 satır, 3 sütun
   print("Dizi Boyutu (Size):", arr_3d.size)   # 12 - Toplam 12 eleman
   print("Dizi Veri Tipi (Dtype):", arr_3d.dtype)  # int64 - Elemanların veri tipi
   print("Dizi Boyut Sayısı (Ndim):", arr_3d.ndim)  # 3 - Dizi 3 boyutlu
   print("Eleman Boyutu (Itemsize):", arr_3d.itemsize)  # 8 - Her bir int64 elemanı 8 byte
   # Shape: #(2, 2, 3) - Dizi 2 katman, 2 satır ve 3 sütun içerir.

Çıktımız
--------

.. code-block:: python

   1D Dizi: [1 2 3 4 5]
   2D Dizi:
   [[1 2 3]
    [4 5 6]]
   Dizi Boyutu: (2, 3)
   İlk Eleman: 1
   İkinci Satır, Üçüncü Sütun Elemanı: 6
   Kareleri: [ 1  4  9 16 25]

.. code-block:: python
   import numpy as np  # NumPy kütüphanesini içe aktar

   # 2x3 boyutunda bir NumPy dizisi oluştur
   arr = np.array([[1, 2, 3], [4, 5, 6]])

   # Dizi şekli (boyutları)
   print("Dizi Şekli (Shape):", arr.shape)  # Çıktı: (2, 3) - 2 satır, 3 sütun

   # Dizi boyutu (toplam eleman sayısı)
   print("Dizi Boyutu (Size):", arr.size)  # Çıktı: 6 - Toplam 6 eleman var

   # Dizi veri tipi
   print("Dizi Veri Tipi (Dtype):", arr.dtype)  # Çıktı: int64 - Elemanların veri tipi

   # Dizi boyut sayısı (kaç boyutlu)
   print("Dizi Boyut Sayısı (Ndim):", arr.ndim)  # Çıktı: 2 - Dizi 2 boyutlu

   # Her bir elemanın byte cinsinden boyutu
   print("Eleman Boyutu (Itemsize):", arr.itemsize)  # Çıktı: 8 - Her bir int64 elemanı 8 byte

Veri Tipleri
============

- **Veri Tipleri**: NumPy, çeşitli veri tiplerini destekler (int, float, complex, bool, str).

Veri tipleri ile alakalı dönüşümler:

.. code-block:: python

   import numpy as np

   # 1. NumPy kütüphanesini içe aktarıyoruz.

   # 2. Bir NumPy dizisi oluşturuyoruz.
   y = np.array([3, 4, 5], dtype=np.float)  # [3.0, 4.0, 5.0] şeklinde bir dizi oluşturur.

   # 3. Dizi elemanlarının veri tipini karmaşık sayılara dönüştürüyoruz.
   y = y.astype(np.complex)  # Dizi elemanları artık karmaşık sayılar olarak kabul edilir. 
   # Örneğin: [3.0 + 0.0j, 4.0 + 0.0j, 5.0 + 0.0j]

Bazı matematiksel işlemler:

.. code-block:: python

   # 1. Dizi elemanlarının karekökünü alıyoruz.
   karekök = np.sqrt(y)  # Her bir elemanın karekökünü alır. 
   # Sonuç: [1.732 + 0.0j, 2.0 + 0.0j, 2.236 + 0.0j]

   # 2. Karmaşık bir sayı oluşturuyoruz.
   z = np.complex(3, 4)  # 3 + 4i şeklinde bir karmaşık sayı oluşturur. 
   # NumPy'de karmaşık sayılar genellikle 'j' ile gösterilir, yani 3 + 4j.

   # 3. Reel ve sanal kısımları alıyoruz.
   reel_kisim = z.real  # Karmaşık sayının reel kısmını alır. Sonuç: 3.0
   sanal_kisim = z.imag  # Karmaşık sayının sanal kısmını alır. Sonuç: 4.0

   # 4. Sonuçları yazdırıyoruz.
   print("Karmaşık sayı:", z)          # Çıktı: (3+4j)
   print("Reel kısım:", reel_kisim)    # Çıktı: 3.0
   print("Sanal kısım:", sanal_kisim)  # Çıktı: 4.0


Save Load
=========

- **Diziyi Kaydetme**: `np.save('dosya_adı.npy', dizi)` ile diziyi kaydedebilirsiniz.
- **Diziyi Yükleme**: `np.load('dosya_adı.npy')` ile kaydedilen diziyi yükleyebilirsiniz.

.. code-block:: python

   # Bir NumPy dizisi oluşturma
   dizi = np.array([1, 2, 3, 4, 5])

   # Diziyi kaydetme
   np.save('dizi.npy', dizi)  # 'dizi.npy' adında bir dosya oluşturur.

   # Diziyi metin dosyası olarak kaydetme
   np.savetxt('dizi.txt', dizi, fmt='%d')  # 'dizi.txt' adında bir dosya oluşturur.

   '''
   # 1. Tam Sayı Formatları
   # %d: Tam sayıları kaydetmek için.

   # 2. Ondalık Sayı Formatları
   # %.nf: n ondalık basamakla ondalıklı sayıları kaydetmek için.
   # Örnek: %.2f (2 ondalık basamak)
   # Örnek: %.3f (3 ondalık basamak)

   # 3. Bilimsel Notasyon Formatları
   # %e: Sayıları bilimsel notasyonla kaydetmek için.
   # %g: Sayıları en uygun formatta (tam sayı, ondalıklı veya bilimsel notasyon) kaydetmek için.

   # 4. Diğer Formatlar
   # %s: String (metin) verileri kaydetmek için.
   # %o: Sayıları sekizli (octal) sistemde kaydetmek için.
   # %x: Sayıları onaltılı (hexadecimal) sistemde kaydetmek için.
   '''

   yuklenen_dizi = np.load('dizi.npy')  # 'dizi.npy' dosyasından diziyi yükler.

   yuklenen_dizi_txt = np.loadtxt('dizi.txt', dtype=int)  # 'dizi.txt' dosyasından diziyi yükler.

Fonksiyonlar
============

### Ones, Zero

### Kullanım Amaçları

1. **Başlangıç Değerleri**: Sıfır veya bir değerleri, genellikle bir algoritmanın başlangıç aşamasında başlangıç değerleri olarak kullanılır. Örneğin, bir matrisin veya vektörün başlangıç değerlerini belirlemek için kullanılabilir.
   
2. **Dizi Oluşturma**: Belirli boyutlarda ve belirli değerlerle (sıfır veya bir) diziler oluşturmak için kullanılır. Bu, daha sonra bu diziler üzerinde matematiksel işlemler yaparken veya veri analizi yaparken faydalıdır.
   
3. **Yer Tutucu Olarak Kullanma**: Sıfır veya bir değerleri, daha sonra doldurulacak yer tutucular olarak kullanılabilir. Örneğin, bir modelin çıktısını saklamak için bir dizi oluşturulabilir.
   
4. **Matematiksel İşlemler**: Bazı matematiksel işlemler veya algoritmalar, sıfır veya bir değerleri ile başlamak için gereklidir. Örneğin, bir matris çarpımı veya toplama işlemi yaparken başlangıç değerleri olarak kullanılabilir.

### Örnek Kullanım Alanları

1. **Makine Öğrenimi**: Modelin ağırlıklarını başlatmak için sıfır veya bir dizileri kullanılabilir. Örneğin, bir sinir ağı modelinin ağırlıklarını başlatmak için `np.zeros` veya `np.ones` kullanılabilir.
   
2. **Veri Analizi**: Veri analizi sırasında, belirli bir boyutta sıfır veya bir dizisi oluşturmak, veri toplama veya istatistiksel hesaplamalar için faydalı olabilir.
   
3. **Simülasyonlar**: Fiziksel veya matematiksel simülasyonlarda, başlangıç koşullarını belirlemek için sıfır veya bir dizileri kullanılabilir.
   
4. **Görüntü İşleme**: Görüntü işleme uygulamalarında, belirli bir boyutta boş (sıfır) bir görüntü oluşturmak için kullanılabilir.

.. code-block:: python

   # Birinci parametre satır, ikincisi sütun.

   # 2x3 boyutunda sıfırlardan oluşan bir dizi oluşturma
   zero_array = np.zeros((2, 3))

   '''
   [[0. 0. 0.]
    [0. 0. 0.]]
   '''

   ones_array = np.ones((2, 3))

   '''
   [[1. 1. 1.]
    [1. 1. 1.]]
   '''

   # 2 tane 3x4 dizi oluşturma. Bu kod iki katmanlı bir çıktır verir.
   zero_array = np.zeros((2, 3, 4))

   '''
   [[[0. 0. 0. 0.]
     [0. 0. 0. 0.]
     [0. 0. 0. 0.]]

    [[0. 0. 0. 0.]
     [0. 0. 0. 0.]
     [0. 0. 0. 0.]]]
   '''

Full
====

### Kullanım Alanları

- **Başlangıç Değerleri**: Belirli bir değeri başlangıç değeri olarak kullanmak istediğiniz durumlarda.
- **Yer Tutucu Olarak Kullanma**: Daha sonra doldurulacak bir dizi oluşturmak için.
- **Matematiksel İşlemler**: Belirli bir değeri kullanarak matematiksel işlemler yapmak için.

.. code-block:: python

   numpy.full(shape, fill_value, dtype=None)

   # shape: Oluşturulacak dizinin boyutunu belirten bir tuple. Örneğin, (2, 3) ifadesi 2 satır ve 3 sütundan oluşan bir dizi oluşturur.
   # fill_value: Dizinin tüm elemanlarını doldurmak için kullanılacak değer.
   # dtype: (isteğe bağlı) Dizinin veri tipini belirler. Örneğin, dtype=int ile tam sayılardan oluşan bir dizi oluşturabilirsiniz.

   # 2x3 boyutunda 7 ile doldurulmuş bir dizi oluşturma
   full_array = np.full((2, 3), 7)
   print(full_array)

Empty, Fill
===========

empty fonksiyonu rastgele değerler verir.

.. code-block:: python

   x = np.empty((2, 2))  # 2 satır 2 sütundan oluşur, rastgele veriler kullanır.

   x.fill(3)  # Tüm diziyi 3 ile doldurur.

Empty, Fill
===========

empty fonksiyonu rastgele değerler verir.

.. code-block:: python

   x = np.empty((2, 2))  # 2 satır 2 sütundan oluşur, rastgele veriler kullanır.

   x.fill(3)  # Tüm diziyi 3 ile doldurur.

Eye
====

### Kullanım Alanları

`numpy.eye`, birim matris oluşturmak için kullanılan bir fonksiyondur. Kare veya dikdörtgen boyutlarda birim matrisler oluşturabilir ve köşegenin konumunu belirlemek için çeşitli parametreler alır. Bu fonksiyon, lineer cebir ve matris hesaplamalarında önemli bir araçtır.

- **Lineer Cebir**: Birim matris, matris çarpımında etkisiz eleman olarak kullanılır. Yani, herhangi bir matris ile birim matris çarpıldığında, sonuç orijinal matris olur.
- **Matris Hesaplamaları**: Çeşitli matematiksel ve istatistiksel hesaplamalarda birim matris kullanılır.
- **Algoritmalar**: Bazı algoritmalar, başlangıç koşulları olarak birim matris kullanabilir.

.. code-block:: python

   numpy.eye(N, M=None, k=0, dtype=float)

   '''
   N: Matrisin satır sayısı.
   M: (isteğe bağlı) Matrisin sütun sayısı. Eğer belirtilmezse, M değeri N olarak varsayılır ve kare bir matris oluşturulur.
   k: (isteğe bağlı) Köşegenin konumunu belirler. k=0 ana köşegeni (sol üstten sağ alta), k>0 üst köşegenleri, k<0 ise alt köşegenleri ifade eder.
   dtype: (isteğe bağlı) Matrisin veri tipini belirler. Varsayılan olarak float türündedir.
   '''

   lower_diagonal_matrix = np.eye(4)

   print(lower_diagonal_matrix)

   '''
   [[1. 0. 0. 0.]
    [0. 1. 0. 0.]
    [0. 0. 1. 0.]
    [0. 0. 0. 1.]]
   '''

`numpy.eye` fonksiyonundaki `k` parametresi, oluşturulan birim matrisin köşegeninin konumunu belirlemek için kullanılır. Bu parametre, matrisin ana köşegeninin (sol üstten sağ alta) üstünde veya altında yer alan köşegenleri ifade eder.

### `k` Parametresinin Anlamı

- `k` parametresi, `numpy.eye` fonksiyonunda köşegenin konumunu belirler.
- `k = 0` ana köşegeni, `k > 0` üst köşegenleri, `k < 0` ise alt köşegenleri ifade eder.
- Bu parametre, birim matrisin yapısını özelleştirmek için kullanılır ve matris hesaplamalarında esneklik sağlar.

- **`k = 0`**: Ana köşegen. Bu durumda, matrisin köşegenindeki elemanlar 1 olur ve diğer tüm elemanlar 0 olur.
- **`k > 0`**: Üst köşegenler. `k` değeri pozitif olduğunda, köşegen, ana köşegenin üstünde yer alır. Örneğin, `k = 1` ana köşegenin hemen üstündeki köşegeni ifade eder.
- **`k < 0`**: Alt köşegenler. `k` değeri negatif olduğunda, köşegen, ana köşegenin altında yer alır. Örneğin, `k = -1` ana köşegenin hemen altındaki köşegeni ifade eder.

.. code-block:: python

   import numpy as np

   # Ana köşegen (k=0)
   identity_matrix = np.eye(3, k=0)
   print("Ana Köşegen (k=0):")
   print(identity_matrix)
   # Çıktı: 
   # [[1. 0. 0.]
   #  [0. 1. 0.]
   #  [0. 0. 1.]]
   # Açıklama: 3x3 boyutunda birim matris. Ana köşegen (k=0) elemanları 1, diğerleri 0.

   print()

      # Üst köşegen (k=1)
   upper_diagonal_matrix = np.eye(4, k=1)
   print("Üst Köşegen (k=1):")
   print(upper_diagonal_matrix)
   # Çıktı: 
   # [[0. 1. 0. 0.]
   #  [0. 0. 1. 0.]
   #  [0. 0. 0. 1.]
   #  [0. 0. 0. 0.]]
   # Açıklama: 4x4 boyutunda matris. Ana köşegenin hemen üstündeki köşegen (k=1) elemanları 1, diğerleri 0.

   print()

   # Alt köşegen (k=-1)
   lower_diagonal_matrix = np.eye(4, k=-1)
   print("Alt Köşegen (k=-1):")
   print(lower_diagonal_matrix)
   # Çıktı: 
   # [[0. 0. 0. 1.]
   #  [0. 0. 1. 0.]
   #  [0. 1. 0. 0.]
   #  [1. 0. 0. 0.]]
   # Açıklama: 4x4 boyutunda matris. Ana köşegenin hemen altındaki köşegen (k=-1) elemanları 1, diğerleri 0.

   print()

   # Üst köşegen (k=2)
   upper_diagonal_matrix_k2 = np.eye(4, k=2)
   print("Üst Köşegen (k=2):")
   print(upper_diagonal_matrix_k2)
   # Çıktı: 
   # [[0. 0. 1. 0.]
   #  [0. 0. 0. 1.]
   #  [0. 0. 0. 0.]
   #  [0. 0. 0. 0.]]
   # Açıklama: 4x4 boyutunda matris. Ana köşegenin iki üstündeki köşegen (k=2) elemanları 1, diğerleri 0.

   print()

   # Alt köşegen (k=-2)
   lower_diagonal_matrix_k_neg2 = np.eye(4, k=-2)
   print("Alt Köşegen (k=-2):")
   print(lower_diagonal_matrix_k_neg2)
   # Çıktı: 
   # [[0. 0. 0. 1.]
   #  [0. 0. 0. 0.]
   #  [0. 0. 0. 0.]
   #  [0. 0. 0. 0.]]
   # Açıklama: 4x4 boyutunda matris. Ana köşegenin iki altındaki köşegen (k=-2) elemanları 1, diğerleri 0.

Alternatif yöntem
=================

.. code-block:: python

   numpy.identity(n)

Köşegen üzerindeki sayıları kontrol etmek:
-------------------------------------------

.. code-block:: python

   x = np.diag([4, 7, 11, 3])


Arrange
=======

`numpy.arange` fonksiyonu, belirli bir başlangıç değeri, bitiş değeri ve adım boyutu ile bir dizi oluşturur.

.. code-block:: python

   numpy.arange(start, stop, step)

   - **start**: (isteğe bağlı) Diziye dahil edilecek başlangıç değeri. Varsayılan değer 0'dır.
   - **stop**: Diziye dahil edilmeyecek bitiş değeri.
   - **step**: (isteğe bağlı) Aradaki adım boyutu. Varsayılan değer 1'dir.

.. code-block:: python

   import numpy as np  # NumPy kütüphanesini içe aktar

   # 1. Adım: Başlangıç, bitiş ve adım değerlerini belirle
   start = 0  # Başlangıç değeri
   stop = 10  # Bitiş değeri
   step = 2   # Adım boyutu

   # 2. Adım: arange fonksiyonunu kullanarak dizi oluştur
   # arange(start, stop, step) -> start ile stop arasında step kadar artan değerler döner
   values = np.arange(start, stop, step)

   # 3. Adım: Oluşturulan değerleri yazdır
   print("Dizi:", values)

   '''
   Dizi: [0 2 4 6 8]
   '''

`numpy.linspace` ise belirli bir aralıkta belirli sayıda eşit aralıklı değerler oluşturur.

.. code-block:: python

   import numpy as np  # NumPy kütüphanesini içe aktar

   # 1. Adım: Başlangıç ve bitiş değerlerini belirle
   start = 0  # Başlangıç değeri
   end = 10   # Bitiş değeri
   num_points = 5  # Oluşturulacak nokta sayısı

   # 2. Adım: linspace fonksiyonunu kullanarak eşit aralıklı sayılar oluştur
   # linspace(start, stop, num) -> start ile stop arasında num kadar eşit aralıklı değer döner
   values = np.linspace(start, end, num_points)

   # 3. Adım: Oluşturulan değerleri yazdır
   print("Eşit aralıklı değerler:", values)

   '''
   Eşit aralıklı değerler: [ 0.   2.5  5.   7.5 10. ]
   '''

Reshape
=======

`numpy.reshape`, NumPy kütüphanesinde bulunan bir fonksiyondur ve bir dizinin boyutunu değiştirmek için kullanılır. Bu fonksiyon, mevcut bir diziyi farklı bir şekle (boyuta) dönüştürmenizi sağlar. Örneğin, bir 1D diziyi 2D veya 3D diziye dönüştürebilirsiniz.

.. code-block:: python

   numpy.reshape(a, newshape, order='C')

Parametreler
============

- **a**: (array_like) Yeniden şekillendirilmek istenen dizi.
- **newshape**: (int veya tuple) Yeni şekil. Dizi boyutlarını belirtir. Dizi elemanlarının toplamı, yeni şeklin eleman sayısına eşit olmalıdır.
- **order**: (str, isteğe bağlı) Dizi elemanlarının yeniden şekillendirilme sırasını belirler. 'C' (satır-major) veya 'F' (sütun-major) olarak ayarlanabilir. Varsayılan değer 'C'dir.

.. code-block:: python

   import numpy as np  # NumPy kütüphanesini içe aktar

   # 1. Adım: Bir dizi oluştur
   original_array = np.arange(12)  # 0'dan 11'e kadar olan sayılardan oluşan bir dizi

   print("Orijinal Dizi:", original_array)

   # 2. Adım: Dizi boyutunu değiştirmek için reshape fonksiyonunu kullan
   reshaped_array = np.reshape(original_array, (3, 4))  # 3 satır ve 4 sütunlu bir diziye dönüştür

   print("Yeniden Şekillendirilmiş Dizi:\n", reshaped_array)

   '''
   Orijinal Dizi: [ 0  1  2  3  4  5  6  7  8  9 10 11]

   Yeniden Şekillendirilmiş Dizi:

   [[ 0  1  2  3]
    [ 4  5  6  7]
    [ 8  9 10 11]]
   '''

Random
=======

.. code-block:: python

   import numpy as np  # NumPy kütüphanesini içe aktar

   # 1. Rastgele ondalık sayılar oluştur (0 ile 1 arasında)
   random_array = np.random.random(size=(3, 4))  # 3x4 boyutunda rastgele sayılar
   print("Rastgele Ondalık Sayılar (0-1):\n", random_array)

   # 2. Rastgele tam sayılar oluştur (0 ile 10 arasında)
   random_int_array = np.random.randint(low=0, high=10, size=(3, 4))  # 3x4 boyutunda tam sayılar
   print("Rastgele Tam Sayılar (0-10):\n", random_int_array)


NdArray Değiştirmek (Insert, Append, Stack, Delete)
===================================================

.. code-block:: python

   import numpy as np

   # Örnek bir dizi oluşturma
   x = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

   # İlk elemanı yazdırma
   print(x[0])  # İlk satır: [1 2 3]

   # Son elemanı yazdırma
   print(x[-1])  # Sondan geriye doğru -1, -2 diye gider; Son satır: [7 8 9]

   # 3. elemanı 200 ile güncelleme
   x[2] = 200  # 3. satırı 200 ile günceller
   print(x)

   # 0. satır ve 2. sütundaki elemanı yazdırma
   print(x[0, 2])  # 0. satır, 2. sütun: 3

   # 1. satır ve 2. sütundaki elemanı 100 ile güncelleme
   x[1, 2] = 100
   print(x)

   # Belirli satırları silme
   y = np.delete(x, [0, 1], axis=0)  # 0. ve 1. satırları siler
   print(y)

   # 1. satırı silme
   y = np.delete(x, 1, axis=0)  # 1. satırı siler
   print(y)

   # 0. ve 2. satırları silme
   y = np.delete(x, [0, 2], axis=0)  # 0. ve 2. satırları siler
   print(y)

   # Diziye eleman ekleme
   x = np.append(x, 100)  # 100'ü diziye ekler
   print(x)

   # Birden fazla eleman ekleme
   x = np.append(x, [200, 300])  # 200 ve 300'ü diziye ekler
   print(x)

   # Belirli bir eksende eleman ekleme
   x = np.append(x, [[200], [300]], axis=0)  # 200 ve 300'ü yeni satırlar olarak ekler
   print(x)

   # 2D diziye yeni sütun ekleme
   x = np.append(x, [[400], [500]], axis=1)  # 400 ve 500'ü yeni sütun olarak ekler
   print(x)

   # Belirli bir konuma eleman ekleme
   x = np.insert(x, 1, 10)  # 1. indekse 10 ekler
   print(x)

   # Dikey olarak yığma
   z = np.vstack((x, y))  # x ve y dizilerini dikey olarak birleştirir
   print(z)

   # Yatay olarak yığma
   z = np.hstack((x, y))  # x ve y dizilerini yatay olarak birleştirir
   print(z)

   # Yatay yığma, iki veya daha fazla diziyi yan yana birleştirir. Bu işlem, dizilerin sütun sayılarının eşit olması gerektiği anlamına gelir.
   # Örnek 1: Yatay Yığma

   # İki 2D dizi oluşturma
   a = np.array([[1, 2], [3, 4]])
   b = np.array([[5, 6], [7, 8]])

   # Yatay yığma
   c = np.hstack((a, b))
   print("Yatay Yığma Sonucu:\n", c)

   '''
   Çıktı:

   Yatay Yığma Sonucu:

   [[1 2 5 6]
    [3 4 7 8]]

   Açıklama: a ve b dizileri yan yana birleştirilmiştir. Sonuçta, her iki dizinin satırları korunarak sütunlar birleştirilmiştir.
   Örnek 2: Yatay Yığma ile Farklı Boyutlar
   '''

   # Farklı boyutlarda diziler
   d = np.array([[9], [10]])

   # Yatay yığma
   e = np.hstack((a, d))

   print("Yatay Yığma Sonucu (Farklı Boyutlar):\n", e)

      '''
   Çıktı:

   Yatay Yığma Sonucu (Farklı Boyutlar):

   [[ 1  2  9]
    [ 3  4 10]]

   Açıklama: d dizisi, a dizisinin sütun sayısına uyacak şekilde yığılmıştır. Bu, farklı boyutlardaki dizileri birleştirmenin bir yoludur.
   Dikey Yığma (np.vstack)

   Dikey yığma, iki veya daha fazla diziyi üst üste birleştirir. Bu işlem, dizilerin sütun sayılarının eşit olması gerektiği anlamına gelir.
   Örnek 1: Dikey Yığma
   '''

   # İki 2D dizi oluşturma
   f = np.array([[1, 2]])
   g = np.array([[3, 4]])

   # Dikey yığma
   h = np.vstack((f, g))

   print("Dikey Yığma Sonucu:\n", h)

   '''
   Çıktı:

   Dikey Yığma Sonucu:

   [[1 2]
    [3 4]]

   Açıklama: f ve g dizileri üst üste birleştirilmiştir. Sonuçta, her iki dizinin sütunları korunarak satırlar birleştirilmiştir.
   Örnek 2: Dikey Yığma ile Farklı Boyutlar
   '''

   # Farklı boyutlarda diziler
   i = np.array([[5], [6]])

   # Dikey yığma
   j = np.vstack((f, i))

   print("Dikey Yığma Sonucu (Farklı Boyutlar):\n", j)

   '''
   Çıktı:

   Dikey Yığma Sonucu (Farklı Boyutlar):

   [[1 2]
    [5 6]]

   Açıklama: i dizisi, f dizisinin sütun sayısına uyacak şekilde yığılmıştır. Bu, farklı boyutlardaki dizileri birleştirmenin bir yoludur.
   '''

Slicing
=======

.. code-block:: python

   import numpy as np

   # ndarray[start:end], ndarray[start:], ve ndarray[:end]

   # Örnek bir 2D NumPy dizisi oluşturma
   x = np.array([[1, 2, 3, 4],
                 [5, 6, 7, 8],
                 [9, 10, 11, 12],
                 [13, 14, 15, 16]])

   # 1. Örnek: ndarray[start:end]
   # 0. ve 1. satırları ve 1. ve 2. sütunları alma
   dilim1 = x[0:2, 1:3]  # 0. ve 1. satır, 1. ve 2. sütun
   print("Dilim 1:\n", dilim1)  # Çıktı: [[2 3], [6 7]]

   # 2. Örnek: ndarray[start:]
   # 1. satırdan itibaren tüm sütunları alma
   dilim2 = x[1, :]  # 1. satır
   print("Dilim 2:\n", dilim2)  # Çıktı: [5 6 7 8]

   # 3. Örnek: ndarray[:end]
   # İlk 3 satırı alma
   dilim3 = x[:3, :]  # İlk 3 satır
   print("Dilim 3:\n", dilim3)  # Çıktı: [[ 1  2  3  4], [ 5  6  7  8], [ 9 10 11 12]]

   # 4. Örnek: Sadece belirli bir sütunu alma
   # Tüm satırlardan 2. sütunu alma
   dilim4 = x[:, 2]  # 2. sütun
   print("Dilim 4:\n", dilim4)  # Çıktı: [ 3  7 11 15]

   # 5. Örnek: Negatif indeksleme ile dilimleme
   # Son 2 satırı alma
   dilim5 = x[-2:, :]  # Son 2 satır
   print("Dilim 5:\n", dilim5)  # Çıktı: [[ 9 10 11 12], [13 14 15 16]]

   # 6. Örnek: Copy ile dilimleme
   # İlk 3 satır ve 1. ve 2. sütunları kopyalama
   y = np.copy(x[0:3, 1:3])  # 0, 1, 2. satırlar ve 1, 2. sütunlar
   print("Kopyalanan Dilim (y):\n", y)  # Çıktı: [[ 2  3], [ 6  7], [10 11]]

   # 7. Örnek: Adım kullanarak dilimleme
   # Her 2. satırı alma
   dilim6 = x[::2, :]  # Her 2. satır
   print("Dilim 6:\n", dilim6)  # Çıktı: [[ 1  2  3  4], [ 9 10 11 12]]

   # 8. Örnek: Çok boyutlu dizilerde dilimleme
   # 1. satırdan 2. sütunu alma
   dilim7 = x[1:3, 1:3]  # 1. ve 2. satır, 1. ve 2. sütun
   print("Dilim 7:\n", dilim7)  # Çıktı: [[ 6  7], [10 11]]

   # 9. Örnek: Tüm diziyi ters çevirme
   # Tüm diziyi ters çevirme
   dilim8 = x[::-1, ::-1]  # Tüm satırları ve sütunları ters çevirir
   print("Dilim 8 (Ters Çevirme):\n", dilim8)  # Çıktı: [[16 15 14 13], [12 11 10 9], [8 7 6 5], [4 3 2 1]]

      # 10. Örnek: Belirli bir aralıkta dilimleme
   # 1. ve 2. satırlardan 0. ve 1. sütunları alma
   dilim9 = x[1:3, 0:2]  # 1. ve 2. satır, 0. ve 1. sütun
   print("Dilim 9:\n", dilim9)  # Çıktı: [[ 5  6], [ 9 10]]

   # 11. Örnek: Slicing ile belirli bir elemanı güncelleme
   # 0. satır ve 1. sütundaki elemanı güncelleme
   x[0, 1] = 20  # 0. satır, 1. sütun
   print("Güncellenmiş Dizi:\n", x)  # Çıktı: [[ 1 20  3  4], [ 5  6  7  8], [ 9 10 11 12], [13 14 15 16]]

   # 12. Örnek: Slicing ile belirli bir sütunu güncelleme
   # 2. sütundaki tüm elemanları 100 ile güncelleme
   x[:, 2] = 100  # Tüm satırlardaki 2. sütun
   print("Güncellenmiş Dizi (2. Sütun):\n", x)  # Çıktı: [[  1  20 100  4], [  5  6 100  8], [  9 10 100 12], [13 14 100 16]]

   # 13. Örnek: Slicing ile belirli bir satırı güncelleme
   # 3. satırı [99, 98, 97, 96] ile güncelleme
   x[3, :] = [99, 98, 97, 96]  # 3. satır
   print("Güncellenmiş Dizi (3. Satır):\n", x)  # Çıktı: [[  1  20 100  4], [  5  6 100  8], [  9 10 100 12], [99 98 97 96]]

   # 14. Örnek: Slicing ile belirli bir aralıkta elemanları alma
   # 0. ve 1. satırlardan 1. sütunu alma
   dilim10 = x[0:2, 1]  # 0. ve 1. satır, 1. sütun
   print("Dilim 10:\n", dilim10)  # Çıktı: [20  6]

   # 15. Örnek: Slicing ile belirli bir aralıkta elemanları alma
   # 2. ve 3. satırlardan 0. sütunu alma
   dilim11 = x[2:4, 0]  # 2. ve 3. satır, 0. sütun
   print("Dilim 11:\n", dilim11)  # Çıktı: [ 9 99]

   # 16. Örnek: Slicing ile belirli bir aralıkta elemanları alma
   # 1. ve 2. satırlardan 0. ve 3. sütunları alma
   dilim12 = x[1:3, [0, 3]]  # 1. ve 2. satır, 0. ve 3. sütun
   print("Dilim 12:\n", dilim12)  # Çıktı: [[ 5  8], [ 9 12]]

   # 17. Örnek: Slicing ile belirli bir aralıkta elemanları alma
   # 0. ve 3. satırlardan tüm sütunları alma
   dilim13 = x[[0, 3], :]  # 0. ve 3. satır
   print("Dilim 13:\n", dilim13)  # Çıktı: [[  1  20 100  4], [99 98 97 96]]

   # 18. Örnek: Slicing ile belirli bir aralıkta elemanları alma
   # 1. ve 2. satırlardan 0. ve 3. sütunları alma
   dilim14 = x[1:3, [0, 3]]  # 1. ve 2. satır, 0. ve 3. sütun
   print("Dilim 14:\n", dilim14)  # Çıktı: [[ 5  8], [ 9 12]]

   # 19. Örnek: Slicing ile belirli bir aralıkta elemanları alma
   # 0. ve 3. satırlardan tüm sütunları alma
   dilim15 = x[[0, 3], :]  # 0. ve 3. satır
   print("Dilim 15:\n", dilim15)  # Çıktı: [[  1  20 100  4], [99 98 97 96]]

   # 20. Örnek: Slicing ile belirli bir aralıkta elemanları alma
   # 1. ve 2. satırlardan 1. sütunu alma
   dilim16 = x[1:3, 1]  # 1. ve 2. satır, 1. sütun
   print("Dilim 16:\n", dilim16)  # Çıktı: [6 10]

   # 21. Örnek: Slicing ile belirli bir aralıkta elemanları alma
   # 0. ve 1. satırlardan 2. sütunu alma
   dilim17 = x[0:2, 2]  # 0. ve 1. satır, 2. sütun
   print("Dilim 17:\n", dilim17)  # Çıktı: [100  7]


Fancy, Boolean Indexing
========================

Fancy indexing, bir dizinin belirli elemanlarını seçmek için bir dizi veya liste kullanmanıza olanak tanır. Bu, dizinin belirli indekslerini seçmek için kullanılır.

.. code-block:: python

   import numpy as np

   # Örnek bir NumPy dizisi oluşturma
   x = np.array([[1, 2, 3, 4],
                 [5, 6, 7, 8],
                 [9, 10, 11, 12],
                 [13, 14, 15, 16]])

   # Fancy indexing ile belirli elemanları alma
   # 0. satırdan 1. ve 3. sütunları, 2. satırdan 1. ve 3. sütunları alma
   satirlar = np.array([0, 2])  # Seçilecek satır indeksleri
   sutunlar = np.array([1, 3])  # Seçilecek sütun indeksleri

   # Fancy indexing ile elemanları alma
   dilim_fancy = x[satirlar[:, np.newaxis], sutunlar]  # Satır ve sütunları birleştirerek seçim yapma
   print("Fancy Indexing Sonucu:\n", dilim_fancy)
   # Çıktı:
   # [[ 2  4]
   #  [10 12]]

Boolean indexing, bir dizinin elemanlarını seçmek için bir boolean (True/False) dizisi kullanmanıza olanak tanır. Bu, belirli bir koşulu sağlayan elemanları seçmek için kullanılır.

.. code-block:: python

   # Örnek bir NumPy dizisi oluşturma
   y = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])

   # Boolean indexing ile belirli koşulu sağlayan elemanları alma
   # 5'ten büyük olan elemanları seçme
   kosul = y > 5  # Boolean dizisi
   print("Boolean Indexing Sonucu:\n", y[kosul])  # Kosulu sağlayan elemanları alma
   # Çıktı: [ 6  7  8  9 10]

   # Boolean indexing ile başka bir örnek
   # 3 ile 7 arasındaki elemanları seçme
   kosul2 = (y >= 3) & (y <= 7)  # Boolean dizisi
   print("3 ile 7 arasındaki elemanlar:\n", y[kosul2])  # Kosulu sağlayan elemanları alma
   # Çıktı: [3 4 5 6 7]

   print(x[(x % 2 == 0)])

   print(np.all(x > y))  # x'in her değeri y'den büyükse.
   print(np.any(x > y))  # x'in herhangi bir değeri y'den büyükse.

   mask = (x % 2 == 0)
   print(type(mask))  # True veya False değeri döndürür.
   x[mask] = -3  # True değeri olan hepsine -3 değeri verir.

Fancy ve Boolean Indexing'in Kullanım Alanları
-----------------------------------------------

1. **Veri Analizi**: Belirli koşullara göre veri setlerinden alt küme almak için kullanılır.
2. **Veri Manipülasyonu**: Diziler üzerinde belirli elemanları güncellemek veya değiştirmek için kullanılır.
3. **Görselleştirme**: Belirli koşullara göre verileri seçerek daha anlamlı grafikler oluşturmak için kullanılır.

Grup İşlemleri ve Sıralama
==========================

.. code-block:: python

   import numpy as np

   # İki örnek dizi oluşturma
   a = np.array([1, 2, 3, 4, 5])
   b = np.array([4, 5, 6, 7, 8])

   # 1. Örnek: intersect1d
   # İki dizi arasındaki kesişimi bulma
   kesisim = np.intersect1d(a, b)  # a ve b dizilerinin kesişimi
   print("Kesişim (intersect1d):", kesisim)  # Çıktı: [4 5]

   # 2. Örnek: setdiff1d
   # a dizisinde olup b dizisinde olmayan elemanları bulma
   fark_a_b = np.setdiff1d(a, b)  # a dizisinde olup b dizisinde olmayan elemanlar
   print("a'da olup b'de olmayan (setdiff1d):", fark_a_b)  # Çıktı: [1 2 3]

   # 3. Örnek: setdiff1d
   # b dizisinde olup a dizisinde olmayan elemanları bulma
   fark_b_a = np.setdiff1d(b, a)  # b dizisinde olup a dizisinde olmayan elemanlar
   print("b'de olup a'da olmayan (setdiff1d):", fark_b_a)  # Çıktı: [6 7 8]

   # 4. Örnek: union1d
   # İki dizi arasındaki birleşimi bulma
   birlesim = np.union1d(a, b)  # a ve b dizilerinin birleşimi
   print("Birleşim (union1d):", birlesim)  # Çıktı: [1 2 3 4 5 6 7 8]

   # 5. Örnek: unique
   # Tekrar eden elemanları kaldırarak benzersiz elemanları bulma
   c = np.array([1, 2, 2, 3, 4, 4, 5])
   benzersiz = np.unique(c)  # c dizisindeki benzersiz elemanlar
   print("Benzersiz Elemanlar (unique):", benzersiz)  # Çıktı: [1 2 3 4 5]

   # 6. Örnek: in1d
   # a dizisinin elemanlarının b dizisinde bulunup bulunmadığını kontrol etme
   bulundu_mu = np.in1d(a, b)  # a dizisindeki her elemanın b dizisinde olup olmadığını kontrol et
   print("a dizisinin elemanları b dizisinde bulunuyor mu?:", bulundu_mu)  # Çıktı: [False False False  True  True]

   # 7. Örnek: in1d ile boolean dizisi kullanma
   # Boolean dizisini kullanarak a dizisinden b dizisinde bulunan elemanları alma
   a_bulunan = a[bulundu_mu]  # a dizisindeki bulunan elemanları seçme
   print("b dizisinde bulunan a dizisinin elemanları:", a_bulunan)  # Çıktı: [4 5]


.. code-block:: python

   import numpy as np

   # Örnek bir dizi oluşturma
   dizi = np.array([3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5])

   # 1. Örnek: np.sort
   # Diziyi sıralama ve yeni bir sıralı dizi döndürme
   sirali_dizi = np.sort(dizi)  # Sıralanmış yeni bir dizi döndürür
   print("Sıralı Dizi (np.sort):", sirali_dizi)  # Çıktı: [1 1 2 3 3 4 5 5 5 6 9]

   # 2. Örnek: np.argsort
   # Dizinin sıralı indekslerini alma
   sirali_indeksler = np.argsort(dizi)  # Sıralı indeksleri döndürür
   print("Sıralı İndeksler (np.argsort):", sirali_indeksler)  # Çıktı: [1 3 4 0 5 2 8 6 9 7 10]

   # 3. Örnek: np.ndarray.sort
   # Diziyi yerinde sıralama (in-place sorting)
   dizi_yerinde = np.array([3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5])  # Yeni bir dizi oluşturma
   dizi_yerinde.sort()  # Diziyi yerinde sıralar
   print("Yerinde Sıralı Dizi (ndarray.sort):", dizi_yerinde)  # Çıktı: [1 1 2 3 3 4 5 5 5 6 9]

   # 4. Örnek: Sıralama ile çok boyutlu dizi
   # Çok boyutlu bir dizi oluşturma
   cok_boyutlu_dizi = np.array([[3, 1, 4],
                                 [1, 5, 9],
                                 [2, 6, 5]])

   # 4.1. Örnek: np.sort ile satır bazında sıralama
   sirali_cok_boyutlu = np.sort(cok_boyutlu_dizi, axis=1)  # Her satırı sıralar
   print("Satır Bazında Sıralı Dizi (np.sort):\n", sirali_cok_boyutlu)
   # Çıktı:
   # [[1 3 4]
   #  [1 5 9]
   #  [2 5 6]]

   # 4.2. Örnek: np.sort ile sütun bazında sıralama
   sirali_cok_boyutlu_sutun = np.sort(cok_boyutlu_dizi, axis=0)  # Her sütunu sıralar
   print("Sütun Bazında Sıralı Dizi (np.sort):\n", sirali_cok_boyutlu_sutun)
   # Çıktı:
   # [[1 1 4]
   #  [2 5 5]
   #  [3 6 9]]

   # 5. Örnek: np.lexsort
   # Birden fazla diziyi sıralamak için kullanılır
   # İki dizi oluşturma
   dizi1 = np.array(['b', 'a', 'c'])
   dizi2 = np.array([3, 1, 2])

   # İki diziye göre sıralama
   sirali_indeksler_lex = np.lexsort((dizi2, dizi1))  # dizi2'ye göre önce, dizi1'e göre sonra sıralar
   print("Lexicographic Sıralı İndeksler (np.lexsort):", sirali_indeksler_lex)  # Çıktı: [1 2 0]

   # Sıralı diziyi elde etme
   sirali_dizi_lex = dizi1[sirali_indeksler_lex]
   print("Lexicographically Sıralı Dizi:", sirali_dizi_lex)  # Çıktı: ['a' 'c' 'b']

Matematiksel İşlemler
=====================

.. code-block:: python

   import numpy as np

   # İki örnek dizi oluşturma
   a = np.array([1, 2, 3, 4])
   b = np.array([5, 6, 7, 8])

   # Toplama
   toplama = a + b
   print("Toplama:", toplama)  # Çıktı: [ 6  8 10 12]

   # Çıkarma
   cikarma = a - b
   print("Çıkarma:", cikarma)  # Çıktı: [-4 -4 -4 -4]

   # Çarpma
   carpma = a * b
   print("Çarpma:", carpma)  # Çıktı: [ 5 12 21 32]

   # Bölme
   bolme = a / b
   print("Bölme:", bolme)  # Çıktı: [0.2        0.33333333 0.42857143 0.5       ]

Matematiksel Fonksiyonlar
==========================

.. code-block:: python

   # Örnek bir dizi oluşturma
   x = np.array([0, np.pi/2, np.pi])

   # Sinüs hesaplama
   sinus = np.sin(x)
   print("Sinüs:", sinus)  # Çıktı: [0. 1. 0.]

   # Kosinüs hesaplama
   kosinus = np.cos(x)
   print("Kosinüs:", kosinus)  # Çıktı: [ 1. 0. -1.]

   # Logaritma hesaplama
   y = np.array([1, 10, 100])
   logaritma = np.log10(y)
   print("Logaritma (base 10):", logaritma)  # Çıktı: [0. 1. 2.]

İstatiksel İşlemler
===================

.. code-block:: python

   # Örnek bir dizi oluşturma
   data = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])

   # Ortalama hesaplama
   ortalama = np.mean(data)
   print("Ortalama:", ortalama)  # Çıktı: 5.5

   # Medyan hesaplama
   medyan = np.median(data)
   print("Medyan:", medyan)  # Çıktı: 5.5

   # Standart sapma hesaplama
   std_sapma = np.std(data)
   print("Standart Sapma:", std_sapma)  # Çıktı: 2.8722813232690143

Matris İşlemleri
================

Matris, sayılardan veya matematiksel nesnelerden (örneğin, değişkenler veya semboller) oluşan dikdörtgen biçiminde bir düzenlemedir. Matematikte ve istatistikte yaygın olarak kullanılan matrisler, genellikle sayıları düzenlemek, hesaplamalar yapmak ve sistemleri temsil etmek için kullanılır. Matrisler, satırlar ve sütunlar halinde düzenlenmiş elemanlardan oluşur.

- **Tanım**: Sayılardan veya matematiksel nesnelerden oluşan dikdörtgen biçiminde bir düzenleme.
- **Boyutlar**: Matrisin boyutları, satır sayısı (m) ve sütun sayısı (n) ile tanımlanır (örneğin, (m × n)).

Matris Türleri:
----------------

1. **Kare Matris**: Satır ve sütun sayısı eşit olan matrislerdir.
2. **Sıfır Matris**: Tüm elemanları sıfır olan matrislerdir.
3. **Birim Matris**: Ana köşegen üzerindeki elemanları 1, diğerleri 0 olan kare matrislerdir.
4. **Transpoze Matris**: Bir matrisin satır ve sütunlarının yer değiştirmesiyle elde edilen matristir; bu işlem, matrisin boyutunu değiştirir.

.. code-block:: python

   # İki matris oluşturma
   A = np.array([[1, 2], [3, 4]])
   B = np.array([[5, 6], [7, 8]])

   # Matris çarpımı
   matris_carpimi = np.dot(A, B)  # veya A @ B
   print("Matris Çarpımı:\n", matris_carpimi)
   # Çıktı:
   # [[19 22]
   #  [43 50]]

   # Matrisin transpozu
   transpoze = A.T
   print("Transpoze:\n", transpoze)
   # Çıktı:
   # [[1 3]
   #  [2 4]]