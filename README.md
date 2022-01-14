# interpolation-search
interpolation search
Interpolation Search algoritmasına, Binary Search algoritmasının modifiye edilmiş halidir diyebiliriz. Binary Search, aranan değeri bulmak için, arama yapılan listeyi her adımda iki parçaya bölerek ilerler. Ama her zaman veri kümesinin ortasından başlamak mantıklı değildir. Bunun yerine, aramamız gereken öğeye bağlı olarak aramamıza her seferinde farklı bir konumdan da başlayabiliriz.
Interpolation Search’ te Binary Search’teki gibi her zaman dizinin ortasından başlamak yerine, arama işlemini başlatacağımız dizini hesaplamak için aşağıdaki denklem kullanır. Bu işlemle daha az adımda aranan değeri bulmak hedeflenir. 
Bu yöntem, dizinin öğelerinin eşit olarak dağıldığı durumlarda ikili aramayı geride bırakabilir.

mid = left+ ((key-array[left]) * (right– left) ) / ( array[right] – array[left])

left, right = arama yapılan listenin başlangıç
ve bitiş indisleridir. 
key = aranan değer

dizi    : [2 3 6 8 10 13 16 18] 
indisler:  0 1 2 3  4   5    6    7  
13’ü aradığımızı düşünelim. 
key = 13, 
left = 0,  
right = 7, 
array[left] = 2, 
array[right] = 18 

mid = 0 + ((13-2) * (7-0) / (18-2)) = 4.8125 ~ 4 olarak bulunur. (Sonuç yuvarlanır.) 
array[4] =  10 aranan değer değildir. 
array[4] deki eleman 13'ten küçük olduğu için
sol yarıyı yok sayar ve sağ yarıda tekrar deneriz.

2 3 6 8 10 13 16 18  
key =13, 
left = 5 ,  
right =7, 
array[left] = 13, 
array[right] = 18 

mid = 5 + ((13-13) * (7-5) / (18-13)) = 5
array[5] = 13 aranan değer bulunur.

Aslında mid değerini hesaplandıktan sonra, sürecin geri
kalanı Binary Search ile aynıdır. array[mid] değerini key ile
karşılaştırırız.
array[mid] değeri, key’den küçükse key daha sağda olduğu için mid, sol olarak kabul edilip işlem tekrarlanır.
array[mid] değeri , key’den büyükse key daha solda olduğu için mid, sağ olarak kabul edilip işlem tekrarlanır.   
array[mid] = key olduğunda işlem tamamlanır.

Time Complexity

İnterpolation Search için best case, bulunan mid değeri key’ e eşit olduğunda gerçekleşir. Bu, en iyi durum zaman karmaşıklığının O(1) olmasını sağlar.
Worst case de, dizideki tüm öğeleri çarprazlamak gerekir ve bu da O(n) zaman karmaşıklığına neden olacaktır.
Avarange case ise O(loglogn) kadar küçüktür.

İnterpolasyon Aramasını kullanmak için temel gereksinim, veri kümesinin sıralanması ve  düzgün bir şekilde dağıtılmasıdır.
Fakat verilerin gerçekte oldukça rastgele olduğu düşürsek gerçek hayatta çok sınırlı sayıda uygulaması vardır.
Bununla birlikte, eğer veriler gerçekten düzgün bir şekilde dağılmışsa, aşağıdaki görüntüden deanlaşılacağı gibi, İnterpolasyon Search, Binary Search’ten çok daha iyi performans gösterir.

![image](https://user-images.githubusercontent.com/16039532/149589403-1b3d2090-c7e4-4d27-b7c5-c3efa149b713.png)




