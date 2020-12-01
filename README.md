# proiect-SCCV

1)Modulul pentru_verificari:
-cu ajutorul modulului dlib se detecteaza fata pe care 
o voi cropa 
- se parcurge folderul cu imagini care are path ul folder gt_db/folder cu fiecare personaj/imagine
-se apeleaza lbp7X7 si histograma 7x7
-se creaza vectorul de trasaturi(scoate din histograma 7x7) si se salveaza ca fisier txt.

2) Modulul face_utils este un modul care ajuta la dectarea fetei

3)lbp_7x7 - se creaza blocuri de 7x7 pixeli din imagine
se va lua pixelul din mijloc si va fi comparat cu vecinii sai
daca valoarea din mijloc este mai mare sau egal decat un pixel de langa el
atunci acel pixel devine 1, daca este mai mic acel pixel devine 0

Dupa ce pixelii din jurul celui din mijloc au fost comparati se alege 
o directie si se formeaza un numar binar care va fi transformat intr-un numar zecimal
Acel numar zecimal este noua valoarea a pixelului din mijloc

Se repeta pentru fiecare pixel in parte

4)calc_hist_7x7
Se calculeaza histograma pentru imaginea nou creata.Pentru fiecare bucata de 7x7 va exista cate o histograma
asta inseamna ca pentru o imagine vom avea 49 de histograme care 
vor descrie fata unei persoane.

5)Random forest

-practic in acest modul nu vom mai folosi random forest
dar se pregatesc datele pentru antrenare si testare

- se alege un numar pentru a imparti baza de date in testare si antrenare
- se parcurg fisierele text unde avem histogramele salvate care ne descriu fata
- se eticheteaza fiecare imagine cu un numar pentru simplitate adica persoana1 va avea 15 etichete de 1 pentru ca avem 15 imagini cu acea persoana
- dupa ce se creaza lista cu toate etichetele si toate valorile se imparte random cu acel numar in lista de antrenare si ce ramane se duce in lista de testare
- pentru comoditate valorile din liste trebuie schimbate float si numpy array