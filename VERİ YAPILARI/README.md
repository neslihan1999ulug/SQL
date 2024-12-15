# PROJE -1  CEVAPLARI 
INSERTION SORT
[22,27,16,2,18,6] -> Insertion Sort
Yukarı verilen dizinin sort türüne göre aşamalarını yazınız.

dizi = {22,27,16,2,18,6}  
İlk:
Mevcut eleman 22
Dizideki ilk elemanın sıralı olduğu varsayılır.
0. indekse kadar sıralanmış kısım şudur: [22]

İlk Geçiş:
27'yi 22 ile karşılaştır (sıralanmış kısmı olan geçerli eleman).
27 büyük olduğundan 23'ten sonra kalmalı .
1. indekse kadar sıralanmış kısım : [22, 27]

İkinci Geçiş:
16' yı 22 ve 27 ile karşılaştır (sıralanmış kısmı olan geçerli eleman).
16 sayısı 22'den ve 23'ten küçük olduğundan 22 ile 27'nin önüne gelmektedir. 
2. indekse kadar sıralanmış kısım : [16, 22, 27]

Üçüncü Geçiş:
2'yi 16 , 22 ve 27 ile karşılaştır (sıralanmış kısmı olan geçerli öğe).
2 , 16'dan küçük olduğundan , 16'dan önce 2 eklenir.
3. indekse kadar sıralanmış kısım : [2, 16, 22, 27]

Dördüncü Geçiş:
18'i 2, 16, 22 ve 27 ile karşılaştır (sıralanmış kısmı olan geçerli öğe).
18, 16'dan büyük ve 22'den küçük olduğundan 16 ile 22 arasına 18'i yerleştiriyoruz .
4. indekse kadar sıralanmış kısım : [2, 16, 18, 22, 27]

Beşinci Geçiş:
6'yı 2, 16, 18, 22 ve 27 ile karşılaştır.
6, 2'den büyük 16'dan küçük olduğu için 2 ile 16 arasına 6 yerleştiriyoruz.
5. indekse kadar sıralanmış kısım : [2, 6, 16, 18, 22, 27] 
Son Dizi: 

Sıralanmış dizi şudur: [2, 6, 16, 18, 22, 27]

Big-O gösterimini yazınız.
Time Complexity of Insertion Sort
Best case: O(n) , = O(6)
Average case: O(n²) , O(6²)
Worst case: O(n²) ,   O(6²)

Time Complexity: Dizi sıralandıktan sonra 18 sayısı aşağıdaki case'lerden hangisinin kapsamına girer? Yazınız
Avarage Case girmektedir.
Average case: Aradığımız sayının ortada olması


SELECTION SORT 
[7,3,5,8,2,9,4,15,6] dizisinin Selection Sort'a göre ilk 4 adımını yazınız.
İlk:
Dizideki ilk eleman dizi içerisindeki en küçük eleman kontrol edilerek seçilir.
0. indekse kadar sıralanmış kısım şudur: [2]

İlk Geçiş:
ilk eleman seçildikten sonra geriye kalan elamanlar arasında en küçük eleman 2. eleman olarak sıralanır.
Geriye kalan elemanlarda en küçüğü 3'dür
1. indekse kadar sıralanmış kısım : [2, 3]

İkinci Geçiş:
 2. eleman seçildikten sonra geriye kalan elamanlar arasında en küçük eleman 3. eleman olarak sıralanır.
2. indekse kadar sıralanmış kısım : [2, 3, 4]

Üçüncü Geçiş:
 3. eleman seçildikten sonra geriye kalan elamanlar arasında en küçük eleman 4. eleman olarak sıralanır.
3. indekse kadar sıralanmış kısım : [2, 3, 4, 5]

İlk 4 adıma kadar olan sıralanmış dizi şudur: [2, 3, 4, 5]

# PROJE -2  CEVAPLARI
MERGE SORT
[16,21,11,8,12,22] -> Merge Sort

Yukarıdaki dizinin sort türüne göre aşamalarını yazınız.
         [16,21,11,8,12,22]
[16,21,11]----------------[8,12,22]
[16,21]-[11]------------[8,12]-[22]
[16]-[21]-[11]--------[8]-[12]-[22]
[16,21]-[11]------------[8,12]-[22]
[11,16,21]----------------[8,12,22]
         [8,11,12,16,21,22]
Big-O gösterimini yazınız.
O(nlogn)-->O(6log6) 

# PROJE -3  CEVAPLARI
BINARY SEARCH TREE
[7, 5, 1, 8, 3, 6, 0, 9, 4, 2] dizisinin Binary-Search-Tree aşamalarını yazınız.

Binary Search Treede en üstte bulunan node Root = 6 olarak alıyorum.
 Root = [6]
Root’tan küçük değere sahip olan node’lar Root’un sol tarafında yer alacak.
Root’tan büyük değere sahip olan node’lar Root’un sağ tarafında yer alacak.

 Sorgu root 6'dır. root'un sağında 7 bulunur. Solunda 5 bulunur 
                   [6]
              [5]        [7]
          [4]     [1]        [8]
      [3]            [0]         [9]
  [2]
Binary Serch Tree yukarıdaki gibidir.