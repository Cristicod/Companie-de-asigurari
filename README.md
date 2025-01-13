# Companie-de-asigurari
# Proiect-POO TEMA 12
## Titlul proiectului:Companie de asigurări – gestionarea diferitelor categorii de polițe de asigurare(auto, de viață,...)
Descriere generală:
Acest proiect reprezintă o aplicație care permite gestionarea polițelor de asigurare pentru o companie de asigurări. Polițele sunt organizate pe categorii distincte (auto, de viață, de călătorie), fiecare cu detalii specifice. Toate informațiile despre polițe sunt salvate într-un fișier text pentru persistență între sesiuni.

Funcționalități principale:
- Gestionarea informațiilor despre polițe (adăugare, vizualizare).
- Stocarea și încărcarea datelor din fișiere.
-Calcule automate pentru prețurile polițelor și clasele bonus-malus.
Structura aplicației:
Aplicația este compusă din următoarele clase:

1. Clasa Polita (abstractă)
Reprezintă baza pentru toate tipurile de polițe.
Atribute:
- numeClient – Numele clientului.
- prenumeClient – Prenumele clientului.
- varsta – Vârsta clientului.
Metode:
- afiseazaDetalii() (virtuală, pură) – Afisează detalii despre poliță.
- serializeaza() (virtuală, pură) – Serializează datele poliței pentru stocare în fișier.
2. Clasa PolitaAuto
- Derivată din clasa Polita, gestionează polițele de asigurare auto.
- Atribute suplimentare:
- marcaMasina – Marca mașinii asigurate.
- kilometri – Kilometrajul mașinii.
- capacitateCilindrica – Capacitatea cilindrică a mașinii.
- vechimeSofer – Vechimea permisului șoferului.
- AAvutAccidente – Dacă șoferul a avut accidente (true/false).
- clasaBonusMalus – Clasa bonus-malus a poliței.
- pret – Costul poliței.
Funcționalități:
- Calcul automat al clasei bonus-malus în funcție de vechimea șoferului și accidente.
- Calculul prețului poliței în funcție de datele mașinii și clasa bonus-malus.
3. Clasa PolitaViata
- Derivată din clasa Polita, gestionează polițele de asigurare de viață.
Atribute suplimentare:
- sumaAsigurata – Suma totală asigurată.
- sanatos – Starea de sănătate a clientului (true/false).
- pret – Costul poliței.
Funcționalități:
Calculul prețului bazat pe suma asigurată, cu penalizări pentru starea nesănătoasă.
4. Clasa PolitaCalatorie
Derivată din clasa Polita, gestionează polițele de asigurare pentru călătorii.
Atribute suplimentare:
- taraDestinatie – Țara de destinație.
- sporturiExtreme – Dacă include sporturi extreme (true/false).
- durata – Durata călătoriei (în zile).
- pret – Costul poliței.
Funcționalități:
Calculul prețului bazat pe durata călătoriei și penalizări pentru sporturi extreme.
5. Clasa GestionarePolite
Gestionează toate polițele din aplicație.
Atribute:
- polite – Vector de pointeri la obiecte de tip Polita.
- numeFisier – Numele fișierului de stocare.
Funcționalități:
- incarcaPoliteDinFisier() – Încarcă polițele din fișier la pornirea aplicației.
- salveazaPoliteInFisier() – Salvează polițele în fișier la ieșirea din aplicație.
- adaugaPolita(Polita* polita) – Adaugă o poliță în vector.
- afiseazaToatePolitele() – Afișează toate polițele din vector.
Funcționalități implementate în meniu:
Adăugarea unei polițe auto, de viață sau de călătorie.
Vizualizarea tuturor polițelor.
Salvarea datelor la ieșire.
Funcționare:
Pornire aplicație:

Aplicația încarcă polițele existente din fișierul polite.txt.
Navigare în meniu:

Utilizatorul poate adăuga o poliță (auto, de viață, de călătorie) furnizând detalii prin consola interactivă.
Toate polițele adăugate sunt afișate prin comanda specifică din meniu.
Închidere aplicație:

Toate polițele din sesiunea curentă sunt salvate în fișierul polite.txt.
Exemple de utilizare:
- Adăugare poliță auto:
- Client: Mihai Popescu
- Vârsta: 35
- Mașină: Dacia Logan
- Kilometri: 150,000
- Capacitate cilindrică: 1400
- Vechime permis: 5 ani
- Fără accidente
Rezultat:
- Bonus-Malus: B5
- Preț: Calculat automat și afișat în consolă.kk