# Image-Analysis-and-Compression-
    Tema 2 - Metode numerice

Task1

    Functia task1 primeste o imagine de intrare photo si un numar intreg k
    (numarul de valori singulare) si efectuează urmatorii pasi:
        - Convertse imaginea de intrare photo la tipul de date double pentru precizie 
        numerica in timpul calculelor.
        - Aplica algoritmul de Decompunerein Valori Singulare (SVD) matricei photo. 
        Acest lucru decompune matriceain trei matrici separate: U, S si V.
        - Calculeaza matricile reduse U_r, S_r si V_r selectand primele k coloane din U, 
        primele k randuri si coloane din S si primele k coloane din V, respectiv.
        - Calculeaza matricea de aproximare new_X a matricei initiale photo prin 
        inmultirea matricilor U_r, S_r si transpusa lui V_r.
        - Convertse matricea new_X la tipul de date uint8 pentru a obtine o reprezentare 
        validă a imaginii.
    Returneaz matricea rezultata de aproximare new_X ca rezultat al functiei.



Task2

    Functia task2 primeste doua argumente: photo - o matrice reprezentand o imagine 
    si pcs - un numarintreg reprezentand numarul de componente principale 
    pe care dorim sa le pastram.
    Scopul functiei este sa aproximeze matricea initiala photo folosind analiza 
    valorilor singulare si sa returneze o noua matrice new_X care reprezinta imaginea 
    aproximata.
    Functia realizeaza urmatorii pasi:
        - Obtine dimensiunea matricei photo si se stochează in variabilele m si n.
        - Initializează matricea new_X cu zerouri avand aceeaai dimensiune ca photo.
        - Matricea photo este convertitain tipul de date double.
        - Normalizeaza matricea photo prin scaderea mediei fiecarui rand.
        - Calculeaza media pentru fiecare rand al matricei photo si se stocheaza 
        in vectorul row_means.
        - Construieste o matrice row_means_matrix prin repetarea mediei fiecarui element 
        pentru a obtine o matrice de aceeasi dimensiune cu photo.
        - Actualizează vectorii din new_X prin scaderea mediei corespunzatoare.
        - Construieste matricea Z ca fiind transpusa matricei new_X impartita la 
        radical din n - 1.
        - Aplica descompunerea valorilor singulare (SVD) matricei Z si se obtin 
        matricile U, S si V.
        - Construieste matricea W din primele pcs coloane ale matricei V.
        - Calculeaza matricea Y ca fiind produsul dintre transpusa matricei W si 
        matricea new_X.
        - Aproximeaza matricea initiala photo utilizând matricile W, Y si row_means_matrix.
        - Matricea rezultata approx_photo este convertit in tipul de date uint8 pentru a 
        reprezenta o imagine valid.
    Noua matrice new_X este returnata ca rezultat al functiei.
    In final, functia returneaza o imagine aproximata folosind analiza valorilor singulare 
    si reducerea dimensionalitatii la primele pcs componente principale.



Task 3

    Functia task3 primeste doua argumente: photo - o matrice reprezentand o 
    imagine si pcs - un numar intreg reprezentand numarul de componente 
    principale. 
    Scopul functiei este sa aproximeze matricea initiala photo folosind analiza 
    valorilor proprii si sa returneze o noua matrice new_X care reprezinta imaginea 
    aproximata.
    Functia realizeaza urmatorii pasi:
        - Obtine dimensiunea matricei photo si se stocheaza in variabilele m si n.
        - Initializeaza matricea new_X cu zerouri avand aceeasi dimensiune ca photo.
        - Matricea photo este convertit  in tipul de date double.
        - Calculeaza media fiecarui rand al matricei photo si se stocheaza in 
        vectorul row_means.
        - Normalizeaza matricea photo prin scaderea mediei fiecarui rand.
        - Construieste o matrice row_means_matrix prin repetarea mediei fiecarui 
        element pentru a obtine o matrice de aceeasi dimensiune cu photo.
        - Actualizeaza vectorii din new_X prin scaderea mediei corespunzatoare.
        - Calculeaza matricea de covarianta Z folosind formula (new_X * new_X') / (n - 1).
        - Calculeaza vectorii si valorile proprii ale matricei de covarianta Z 
        folosind functia eig.
        - Vectorii proprii sunt stocati in matricea V, iar valorile proprii in matricea 
        diagonala S.
        - Ordonează descrescator valorile proprii si se reordoneaza vectorii proprii in 
        matricea V corespunzatoare.
        - Pastreaza doar primele pcs coloane din matricea V, care reprezinta componentele 
        principale.
        - Construieste matricea Y prin schimbarea bazei matricei new_X folosind matricea W.
        - Calculeaza matricea approx_photo, care reprezinta o aproximare a matricei 
        initiale photo.
        - Inmulteste matricea W cu matricea Y si se adauga inapoi media randurilor 
        scazuta anterior.
        - Matricea rezultata approx_photo este convertita in tipul de date uint8 pentru a 
        reprezenta o imagine valida.
    Noua matrice new_X este returnata ca rezultat al functiei.
    In final, functia realizeaza o aproximare a matricei initiale folosind analiza valorilor 
    proprii si reducerea dimensionalitatii la primele pcs componente principale.



Task 4

    visualise_image :
        Aceasta functie, visualise_image, primeste o matrice de antrenament train_mat si un
        numar number si returneaza o imagine reprezentata ca o matrice.
        In functie de number, se citeste o linie specifica din matricea de antrenament. Aceasta 
        linie reprezinta valorile pixelilor imaginii pe care dorim să o vizualizam.
        Linia citita este apoi transformata intr-o matrice de dimensiune 28x28 utilizand functia 
        reshape. Deoarece imaginea este reprezentata ca un vector liniar in matricea de antrenament, 
        trebuie sa o transpunem pentru a o transformaintr-o matrice conventionala.
        Matricea rezultata este convertitain tipul de date uint8 pentru a fi considerata o 
        imagine validă. Astfel, functia visualise_image ne permite sa extragem si sa 
        vizualizam o imagine specifica din matricea de antrenament.

    prepare_data :
        Aceasta functie, prepare_data, primeste un nume de fisier name si numarul de imagini 
        de antrenament no_train_images si returneaza matricea de antrenament train_mat si 
        vectorul de etichete train_val.
        In functie de name, functia incarca datele din fisierul specificat utilizand functia load. 
        Aceste date sunt stocate intr-o variabila d.
        Matricea train_mat este initializata ca o matrice de dimensiune no_train_images x 784 (28x28),
        in care vor fi stocate imaginile de antrenament.
        Vectorul train_val este initializat ca un vector de dimensiune 1 x no_train_images,
        in care vor fi stocate etichetele corespunzatoare imaginilor de antrenament.
        Apoi, primele no_train_images linii din matricea de imagini de antrenament incarcata sunt 
        salvate in train_mat, iar primele no_train_images valori din vectorul de etichete sunt salvate
        in train_val.
        Astfel, functia prepare_data ne permite sa incarcam datele de antrenament si sa le pregatim 
        pentru utilizarea ulterioara in algoritmi de invatare automata.

    magic_with_pca :
        Aceasta functie, magic_with_pca, primeste o matrice de antrenament train_mat si numarul 
        de componente principale pcs si returneaza rezultatele algoritmului PCA aplicat pe matricea 
        de antrenament.
        Matricea train este initializa ca o copie a matricei de antrenament.
        Vectorul miu este initializat ca un vector de medii al fiecarei coloane din matricea 
        de antrenament.
        Matricea Y este initializa ca o matrice de dimensiune m x pcs (numarul de imagini de 
        antrenament x numarul de componente principale), in care vor fi stocate proiectiile imaginilor 
        de antrenament pe componentele principale.
        Matricea Vk este initializa ca o matrice de dimensiune n x pcs (dimensiunea fiecărei imagini 
        x numarul de componente principale), in care vor fi stocate vectorii proprii corespunzatori 
        celor mai mari valori proprii.
        In continuare, se efectuează următoarele operatii:
            - Matricea de antrenament train_mat este convertita in tipul de date double.
            - Calculeaza media fiecarei coloane a matricii de antrenament si se stocheaza in miu.
            - Scade media miu din matricea de antrenament pentru a o normaliza.
            - Calculeaza matricea de covarianta a matricii de antrenament normalizate.
            - Calculeaza vectorii si valorile proprii ale matricei de covarianta utilizand functia eig.
            - Valorile proprii sunt sortate descrescator, iar vectorii proprii corespunzatori sunt 
            reordonate in consecinta.
            - Selectează primele pcs coloane din matricea de vectori proprii si se stocheaza in Vk.
            - Matricea Y este obtinut prin proiecTia matricii de antrenament normalizate pe baza 
            vectorilor proprii din Vk.
            - Matricea de antrenament finala train este obtinuta prin aproximarea matricii de 
            antrenament normalizate utiliznd matricea Vk.
        Astfel, functia magic_with_pca aplica algoritmul PCA asupra matricii de antrenament si returneaz 
        rezultatele obținute: matricea de antrenament finala train, media coloanelor miu, matricea de 
        proiectii Y si matricea de vectori proprii Vk.

    prepare_photo :
        Aceasta functie, prepare_photo, primeste o imagine im si o transforma intr-un sir de pixeli 
        pentru a fi usor de utilizatin procesul de predictie.
        Sirul rezultat sir este initializat ca un sir de zerouri de dimensiune 1x784.
        In continuare, se efectuează urmatoarele operatii:
            - Inverseaza pixelii imaginii im prin scaderea fiecarui pixel de la valoarea maxima posibila
            - Transpune imaginea pentru a avea pixelii dispusi intr-o forma liniara.
            - Imaginea transpusa este transformata intr-un vector linie utilizand functia reshape.
            - Vectorul rezultat este salvat in sir.
        Astfel, functia prepare_photo inverseaza culorile imaginii si o transforma intr-un sir de pixeli 
        care poate fi utilizat in procesul de predictie.

    KNN :
        Aceasta functie, KNN, implementeaza algoritmul k-nearest neighbors pentru a realiza o predictie pe 
        baza imaginilor din setul de antrenament.
        Parametrii de intrare sunt:
            labels: etichetele corespunzatoare imaginilor din setul de antrenament.
            Y: matricea setului de antrenament cu imagini transformate in spatiul componentelor principale.
            test: imaginea de test pentru care se doreste o predictie.
            k: numarul de vecini apropiati de luat in considerare.
        Functia incepe prin initializarea predictiei cu o valoare negativa.
        Se initializeaza vectorul distance de dimensiune m cu zerouri. Se parcurge fiecare rand din matricea 
        Y si se calculeaza distanta euclidiana intre randul respectiv si vectorul de test. Distantele 
        sunt salvatein vectorul distance. Apoi, distantele sunt ordonate crescator si se pastreaza primele k 
        valori care corespund imaginilor cele mai apropiate. Etichetele acestor imagini sunt salvate in vectorul 
        k_nearest_labels.
        In final, predictia este calculata ca mediana valorilor din k_nearest_labels, oferind astfel o predictie 
        bazata pe votul majoritatii celor mai apropiati k vecini.
        Astfel, functia KNN implementeaza algoritmul KNN pentru a realiza o predictie pe baza vecinilor apropiati 
        din setul de antrenament.

    classifyImage :
        Aceasta functie, classifyImage, combina functiile anterioare pentru a face o predictie pe baza imaginii 
        de test.
        Parametrii de intrare sunt:
            im: imaginea de test.
            train_mat: matricea setului de antrenament cu imagini.
            train_val: etichetele corespunzatoare imaginilor din setul de antrenament.
            pcs: numarul de componente principale pentru analiza PCA.
        Functia incepe prin initializarea predictiei cu o valoare negativa. Imaginea im este convertita la tipul 
        double pentru a se potrivi cu prelucrarea ulterioara.Aplicam functia magic_with_pca pe setul de date 
        de antrenament train_mat pentru a obtine matricea train de antrenament, media miu, matricea Yin spatiul 
        componentelor principale si matricea Vk cu vectorii proprii ai matricei de covarianta. Media fiecarei 
        coloane a imaginii im este scazuta din vectorul imagine, pentru a realiza normalizarea. Matricea im este 
        transformata in noul spatiu de baza prin inmultirea cu matricea Vk.
        In final, predictia este calculata folosind metoda k-nearest neighbors cu k = 5, pe baza etichetelor de 
        antrenament train_val, matricei de antrenament transformate Y si imaginei de test im.
        Astfel, functia classifyImage realizeaza o predictie pe baza imaginii de test utilizand analiza PCA si 
        algoritmul KNN.
