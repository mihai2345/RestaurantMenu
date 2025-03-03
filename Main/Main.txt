import random
import time
y=1
print("Bine ati venit ")
def afiseaza_meniu():
   if y==1:
    time.sleep(3)
    print("Meniu:")
    time.sleep(2)
    print("1.Autentificare")
    time.sleep(2)
    print("2.Booking")
    time.sleep(2)
    print("3.Relatii clienti")
    time.sleep(2)
    print("4.Meniu restaurant")
    time.sleep(2)
    print("5.Contact")
    time.sleep(2)
    print("6.Iesire din meniu ")
    time.sleep(2)
   else:
    print("Meniu:")
    print("1.Autentificare cont client")
    print("2.Informatii camere si rezervare")
    print("3.Relatii clienti")
    print("4.Meniu restaurant si plasare comanda")
    print("5.Contact")
    print("6.Mentenanta") 
    print("7.Iesire din meniu ")
def optiune_1():
    print("Ati selectat Autentificarea\n")
def optiune_2():
    print("Ați selectat Informatii Clienti\n")
    time.sleep(2)
    print("Optiunile de la Informatii clienti sunt:")
    time.sleep(2)
    print("1.Inchiriere")
    print("2.Disponibilitate camere")
    print("3.Tipuri camere")
    print("4.Verificare status rezervare")
    k=input(print("Alegeti o categorie din cele de mai sus:"))
    nrdisponibil=100
    nrintrodus=1
    nume=[]
    prenume=[]
    datainceput=[]
    datafinal=[]
    telefon=[]
    persoane=[]
    adresa=[]
    if k==str(1):
        print("Bine ati venit la meniul de inchiriere")
        time.sleep(2)
        nume.append(input("Numele dvs. este: "))
        time.sleep(1)
        prenume.append(input("Prenumele dvs. este: "))
        time.sleep(1)
        datainceput.append(input("Data de inceput a vacantei dvs este: "))
        time.sleep(1)
        datafinal.append(input("Data de final a vacantei dvs. este: "))
        time.sleep(1)
        telefon.append(input("Numarul dvs. de telefon este: "))
        time.sleep(1)
        persoane.append(input("Numarul de persoane este: "))
        adresa.append(input("Adresa dumneavoastra este: "))
        time.sleep(2)
        print("Rezervarea a fost finalizata cu succes")
        time.sleep(1)
        print("Pentru a vedea statusul rezervarii mergeti la verificare status rezervare")
        time.sleep(2)
      
  #  if k==str(2):
    if k==str(3):
        despre_camere()
  #  if k==str(4):
def despre_camere():
    print("Ati ales categoria Tipuri camere")
    print("Alegeti din categoria urmatoare de camere,camera dorita:")
    time.sleep(2)
    print("1.Camera single")
    print("2.Camera double")
    print("3.Camera triple")
    print("4.Apartament")
    print("5.Inapoi")
    alegere = input("Introduceți numărul opțiunii dumnevoastara ")
    while int(alegere)>0 and int(alegere)<6:
        if alegere==str(1):
            print("\nCamera Single")
            print("Descriere: Camera pentru o persoană")
            print("Preț/noapte: $100")
            break
        elif alegere==str(2):
            print("\nCamera Double")
            print("Descriere: Camera pentru două persoane")
            print("Preț/noapte: $150")
            break
        elif alegere==str(3):
            print("\nCamera Triple")
            print("Descriere: Camera pentru trei persoane")
            print("Preț/noapte: $200")
            break
        elif alegere==str(4):
            print("\nApartament")
            print("Descriere: Apartament de lux")
            print("Preț/noapte: $300")
            break
        elif alegere==str(5):
            print("Revenire la meniu principal...")
            optiune_2()
            break
    else:
            print("Opțiune invalidă. Vă rugăm să introduceți o opțiune validă.")
            print("Transfer automat la categoria Tipuri de camera")
            time.sleep(4)
            despre_camere()
def optiune_3():
    print("Ați selectat Relatii Clienti\n")
    time.sleep(2)
    print("Subcategoriile disponibile sunt:")
    time.sleep(2)
    print("1.Reclamatii")
    time.sleep(2)
    print("2.Sugestii")
    time.sleep(2)
    print("3.Informatii refeeritoare la facilitati")
    time.sleep(2)
    a=input("Alegeti subcategoria din cele de mai sus")
    if a==str(1):
        print("Ati ales sectiunea de Reclematii")
        time.sleep(1)
        j=input("Ce reclamatie aveti sa ne comunicati?")
        print("Multumim pentru interesul acordat in a ne ajuta sa ne dam seama ce merge gresit")
        time.sleep(2)
        t =time.localtime()
        current_time = time.strftime("%H:%M:%S", t)
        f = open("reclamatii.txt", "a")
        f.write("Reclamatia cu codul "+str(random.randint(200000000000000000, 400000000000000000000000000))+", primita la ora: "+str(current_time)+" care spune :"+j)
        f.write("\n")
        f.close()
    elif a==str(2):
        print("Ati ales sectiunea de Sugestii")
        time.sleep(2)
        j=input("Ce sugestie aveti sa ne comunicati?")
        print("Multumim pentru interesul acordat in a ne ajuta sa ne inbunatatim servicile")
        time.sleep(2)
        t =time.localtime()
        current_time = time.strftime("%H:%M:%S", t)
        f = open("sugestie.txt", "a")
        f.write("Sugestia cu codul "+str(random.randint(200000000000000000, 400000000000000000000000000))+", primita la ora: "+str(current_time)+" care spune :"+j)
        f.write("\n")
        f.close()
    elif a==str(3):
        print("Ati ales sectiunea de informatii despre facilitati")
        time.sleep(3)
        print("Hotelul nostru se bucura de multe facilitati,insa cele mai importante 40 sunt:")
        time.sleep(3)
        nume_fisier = "facilitati.txt"
        try:
         with open(nume_fisier, "r") as file:
          continut_fisier = file.read()
          print("Conținutul fișierului 'facilitati.txt':\n")
          print(continut_fisier)
        except FileNotFoundError:
          print(f"Fișierul '{nume_fisier}' nu a fost găsit.")
        except Exception as e:
          print(f"A intervenit o eroare: {e}")
        time.sleep(2)
def optiune_4():
    print("Ati selectat Meniu Restaurant")
   # time.sleep(3)
    print("Bine ati venit la meniul Restaurantului nostru")
    print("Va rugam sa alegeti o optiune din cele de mai jos:")
  #  time.sleep(3)
    meniu_restaurant()
    
def meniu_restaurant():
    print("1.Meniu paste")
    print("2.Meniu salate")
    print("3.Meniu carne") 
    print("4.Meniu peste")
    print("5.Meniu deserturi")
    print("6.Meniu racoritoare")
  #  time.sleep(2)
    x=input("Ce optiune alegeti de mai sus?")
    if x=="1":
       meniu1()
    if x=="2":
        meniu2()
    if x=="3":
        meniu3()
    if x=="4":
        meniu4()
    if x=="5":
        meniu5()
    if x=="6":
        meniu6()
def meniu1():
 print("Ati selectat Meniu paste\n")
 print("Meniul de paste este:")
 print("1. Spaghetti Carbonara ")
 print("2. Penne all'Arrabbiata ")
 print("3. Fettuccine Alfredo ")
 print("4. Linguine Frutti di Mare")
 print("5. Lasagna Bolognese ")
 print("6. Ravioli al Tartufo ")
 print("7. Gnocchi alla Sorrentina")
 print("8. Tagliatelle Pesto ")
 print("9. Canneloni Ricotta ")
 print("10. Farfalle Primavera ")
 print("11. Orecchiette con Cime di Rapa")
 print("12. Tortellini alla Panna ")
 print("13. Pappardelle alla Boscaiola ")
 print("14. Rigatoni Amatriciana ")
 print("15. Orzo con Verdure ")
 print("16. Pici Cacio e Pepe ")
 print("17. Agnolotti al Tartufo ")
 print("18. Fusilli alla Puttanesca ")
 print("19. Tortellini in Brodo ")
 print("20. Strozzapreti ai Funghi ")
 print("21. Cavatappi alla Vodka ")
 print("22. Reginette con Salmone ")
 print("23. Mezze Maniche alla Siciliana ")
 print("24. Conchiglie con Zucchine ")
 print("25. Agnolotti al Burro e Salvia ")
 print("26. Pizzoccheri della Valtellina ")
 print("27. Paccheri con Melanzane ")
 print("28. Trofie al Pesto Genovese ")
 print("29. Campanelle al Limone ")
 print("30. Stelline alla Campidanese ")
 print("31. Paste personalizate")
 print("32. Inapoi")
# time.sleep(3)
 a=str(input("Pentru a afla pretul produselor sau pentru a va personaliza pastele introduceti numarul produsuli:"))
 if a>str(0) and a<str(31):
     print("pretul este:"+str(random.randint(20, 40)))
     print("Mulțumim pentru comanda dvs. și vă așteptăm să savurați!")
     t = time.localtime()
     current_time = time.strftime("%H:%M:%S", t)
     f = open("restaurant.txt", "a")
     f.write("Comanda cu codul "+str(random.randint(200000000000000000, 400000000000000000000000000))+", primita la ora: "+str(current_time))
     f.write("\n")
     f.close()
 if a==str(31):
     print("Bine ati venit la meniu de personalizare a pastelor dumneavostra")
     print("Alegeți din următoarele opțiuni pentru a vă construi propria porție de paste:")
     paste = ["Spaghetti", "Penne", "Fettuccine", "Linguine", "Farfalle", "Tortellini", "Rigatoni", "Tagliatelle"]
     sosuri = ["Carbonara", "Arrabbiata", "Alfredo", "Frutti di Mare", "Bolognese", "Pesto", "Aglio e Olio", "Puttanesca"]
     ingrediente_suplimentare = ["Bucățele de pui", "Fructe de mare", "Ciuperci", "Broccoli", "Sunca", "Usturoi", "Parmezan", "Roșii Uscate"]
     print("Tipuri de paste:")
     for i, tip in enumerate(paste, 1):
       print(f"{i}. {tip}")
     alegere_paste = int(input("Selectați numărul corespunzător tipului de paste: "))
     print("Sosuri disponibile:")
     for i, sos in enumerate(sosuri, 1):
        print(f"{i}. {sos}")
     alegere_sos = int(input("Selectați numărul corespunzător sosului: "))
     print("Ingrediente suplimentare:")
     for i, ingredient in enumerate(ingrediente_suplimentare, 1):
       print(f"{i}. {ingredient}")
     alegere_ingredient = input("Selectați numerele corespunzătoare ingredientelor suplimentare (separate prin spațiu): ")
     pret_paste = 10
     pret_sos = 5
     pret_ingredient_suplimentar = 3
     cost_total = pret_paste + pret_sos
     alegere_ingredient = alegere_ingredient.split()
     for alegere in alegere_ingredient:
       cost_total += pret_ingredient_suplimentar
     print("\nComanda dvs. este următoarea:")
     print(f"Paste: {paste[alegere_paste - 1]}")
     print(f"Sos: {sosuri[alegere_sos - 1]}")
     print("Ingrediente suplimentare:")
     for alegere in alegere_ingredient:
       print(ingrediente_suplimentare[int(alegere) - 1])
     print(f"Preț total: {cost_total} lei")
     print("Mulțumim pentru comanda dvs. și vă așteptăm să savurați!")
     t = time.localtime()
     current_time = time.strftime("%H:%M:%S", t)
     f = open("restaurant.txt", "a")
     f.write("Comanda cu codul "+str(random.randint(200000000000000000, 400000000000000000000000000))+", primita la ora: "+str(current_time))
     f.write("\n")
     f.close()
 elif a==str(32):
         meniu_restaurant()
 elif a>str(32) or a<str(1):
       print("Optiune invalida.Reintoarcere automata la meniul principal de paste.")
       time.sleep(3)
       meniu1()
 g=input("Mai aveti nevoie de ceva de la meniul restaurnatului?")
 if g.lower() == 'da':
        print("Ati ales sa reveniti la meniul principal al restaurantului\n")
        meniu_restaurant()
def meniu2():
    print("Ati selectat Meniu salate\n")
    print("Meniul de salate este:")
    print("1. Salata Caesar")
    print("2. Salata Caprese")
    print("3. Salata Nicoise")
    print("4. Salata Waldorf")
    print("5. Salata Greek")
    print("6. Salata Cobb")
    print("7. Salata Orientala")
    print("8. Salata de legume proaspete")
    print("9. Salata de fructe de mare")
    print("10. Salata de pui cu avocado")
    print("11. Salata vegana")
    print("12. Salata de quinoa")
    print("13. Salata de spanac cu portocale")
    print("14. Salata de linte cu morcovi")
    print("15. Salata de broccoli cu bacon")
    print("16. Salata de cartofi")
    print("17. Salata de somon cu dill")
    print("18. Salata de ton cu fasole")
    print("19. Salata de avocado cu creveti")
    print("20. Salata Waldorf cu pui")
    print("21. Salata de primavara")
    print("22. Salata de macrou")
    print("23. Salata cu piept de pui si portocale")
    print("24. Salata de cartofi cu castraveti")
    print("25. Salata cu andive si nuci")
    print("26. Salata de vinete")
    print("27. Salata cu quinoa si avocado")
    print("28. Salata de spanac cu feta")
    print("29. Salata cu rosii cherry")
    print("30. Salata personalizata")
    print("31. Inapoi")
    a = input("Pentru a afla pretul produselor sau pentru a va personaliza salata introduceti numarul produsului: ")
    if a.isnumeric() and 1 <= int(a) <= 29:
        print(f"Pretul este: {random.randint(15, 35)} lei")
        print("Mulțumim pentru comanda dvs. și vă așteptăm să savurați!")
        t = time.localtime()
        current_time = time.strftime("%H:%M:%S", t)
        f = open("restaurant.txt", "a")
        f.write("Comanda cu codul "+str(random.randint(200000000000000000, 400000000000000000000000000))+", primita la ora: "+str(current_time))
        f.write("\n")
        f.close()
    if a == '30':
        print("Bine ati venit la meniu de personalizare a salatelor dumneavoastra")
        print("Alegeți din următoarele opțiuni pentru a vă construi propria salata:")
        ingrediente_salata = [
            "Salata verde", "Rosii", "Castraveti", "Ceapa rosie", "Masline", "Ardei gras", "Branza feta", 
            "Nuci", "Avocado", "Somon afumat", "Piept de pui", "Creveți", "Dressing Caesar", "Dressing Ranch", 
            "Dressing Balsamic", "Dressing de lamaie", "Dressing de iaurt"
        ]
        
        print("Ingrediente disponibile:")
        for i, ingredient in enumerate(ingrediente_salata, 1):
            print(f"{i}. {ingredient}")
        
        alegere_ingredient = input("Selectați numerele corespunzătoare ingredientelor (separate prin spațiu): ")
        pret_ingredient_suplimentar = 3
        cost_total = 10  
        alegere_ingredient = alegere_ingredient.split()
        for alegere in alegere_ingredient:
            cost_total += pret_ingredient_suplimentar
        print("\nComanda dvs. este următoarea:")
        print("Ingrediente:")
        for alegere in alegere_ingredient:
            print(ingrediente_salata[int(alegere) - 1])
        print(f"Preț total: {cost_total} lei")
        print("Mulțumim pentru comanda dvs. și vă așteptăm să savurați!")
        t = time.localtime()
        current_time = time.strftime("%H:%M:%S", t)
        f = open("restaurant.txt", "a")
        f.write("Comanda cu codul "+str(random.randint(200000000000000000, 400000000000000000000000000))+", primita la ora: "+str(current_time))
        f.write("\n")
        f.close()
    elif a==str(31):
         meniu_restaurant()
    elif a>str(31) or a<str(1):
        print("Optiune invalida.Reintoarcere automata la meniul principal de ssalate.")
        time.sleep(3)
        meniu2()
    g=input("Mai aveti nevoie de ceva de la meniul restaurnatului?")
    if g.lower() == 'da':
        print("Ati ales sa reveniti la meniul principal al restaurantului\n")
        meniu_restaurant()
def meniu3():
    print("Ati selectat Meniu cu preparate de carne\n")
    print("Meniul de carne este:")
    print("1. Biftec cu cartofi prajiti")
    print("2. Pui la gratar cu legume")
    print("3. Costita la cuptor cu cartofi")
    print("4. Miel la gratar cu salata")
    print("5. Porc cu ciuperci si sos")
    print("6. Rasol de vita cu sos de vin")
    print("7. Friptura de pui cu sos de smantana")
    print("8. Hamburger cu cartofi wedges")
    print("9. Chateaubriand cu sos bearnaise")
    print("10. Sarmale cu mamaliguta")
    print("11. Frigarui de porc cu legume")
    print("12. Pui Kung Pao")
    print("13. Cotlet de porc cu mere si telina")
    print("14. Picanha la gratar")
    print("15. Tocana de miel cu mamaliguta")
    print("16. Pulpe de pui crocante")
    print("17. Shaorma de pui")
    print("18. Carnati de casa cu mustar")
    print("19. Pui cu sos de arahide")
    print("20. Ribeye cu ciuperci si cartofi")
    print("21. Carne de vita cu legume si sos de soia")
    print("22. Tocana de pui cu ciuperci")
    print("23. Frigarui de vita cu cartofi")
    print("24. Iepure la cuptor cu legume")
    print("25. Carnati cu varza calita")
    print("26. Piept de pui umplut cu spanac si branza")
    print("27. Carne tocata cu cartofi prajiti")
    print("28. Ribs cu cartofi copti")
    print("29. Tocana de miel cu vin si rozmarin")
    print("30. Preparat de carne personalizat")
    print("31. Inapoi")
    a = input("Pentru a afla pretul produselor sau pentru a va personaliza preparatul de carne introduceti numarul produsului: ")
    if a.isnumeric() and 1 <= int(a) <= 29:
        print(f"Pretul este: {random.randint(25, 45)} lei")
        print("Mulțumim pentru comanda dvs. și vă așteptăm să savurați!")
        t = time.localtime()
        current_time = time.strftime("%H:%M:%S", t)
        f = open("restaurant.txt", "a")
        f.write("Comanda cu codul "+str(random.randint(200000000000000000, 400000000000000000000000000))+", primita la ora: "+str(current_time))
        f.write("\n")
        f.close()
    if a == '30':
        print("Bine ati venit la meniu de personalizare a preparatelor de carne dumneavoastra")
        print("Alegeți din următoarele opțiuni pentru a vă construi propriul preparat de carne:")
        ingrediente_carne = [
            "Biftec", "Pui", "Costita de porc", "Miel", "Porc", "Vita", "Piept de pui", "Carne tocata",
            "Iepure", "Carnati", "Shaorma", "Ribeye", "Piept de vita", "Iepure", "Carne de vita"
        ]
        sosuri_carne = [
            "Sos de vin", "Sos de smantana", "Sos bearnaise", "Sos de arahide", "Sos de soia", "Sos de rosii", 
            "Sos de mustar", "Sos de ciuperci", "Sos de lamaie"
        ]
        garnituri_carne = [
            "Cartofi prajiti", "Legume", "Salata", "Sos de mămăliguță", "Cartofi wedges", "Mere si telina",
            "Mamaliguta", "Legume si sos", "Cartofi copti", "Rozmarin"
        ]
        print("Ingrediente disponibile:")
        for i, ingredient in enumerate(ingrediente_carne, 1):
            print(f"{i}. {ingredient}")
        print("Sosuri disponibile:")
        for i, sos in enumerate(sosuri_carne, 1):
            print(f"{i}. {sos}")
        print("Garnituri disponibile:")
        for i, garnitura in enumerate(garnituri_carne, 1):
            print(f"{i}. {garnitura}")
        alegere_ingredient = input("Selectați numerele corespunzătoare ingredientelor, sosurilor, si garniturilor (separate prin spațiu): ")
        pret_ingredient_suplimentar = 5
        cost_total = 20  
        alegere_ingredient = alegere_ingredient.split()
        for alegere in alegere_ingredient:
            cost_total += pret_ingredient_suplimentar
        print("\nComanda dvs. este următoarea:")
        print("Ingrediente:")
        for alegere in alegere_ingredient:
            if int(alegere) <= len(ingrediente_carne):
                print(ingrediente_carne[int(alegere) - 1])
            elif int(alegere) <= len(ingrediente_carne) + len(sosuri_carne):
                print(sosuri_carne[int(alegere) - len(ingrediente_carne) - 1])
            else:
                print(garnituri_carne[int(alegere) - len(ingrediente_carne) - len(sosuri_carne) - 1])
        
        print(f"Preț total: {cost_total} lei")
        print("Mulțumim pentru comanda dvs. și vă așteptăm să savurați!")
        t = time.localtime()
        current_time = time.strftime("%H:%M:%S", t)
        f = open("restaurant.txt", "a")
        f.write("Comanda cu numarul "+str(random.randint(200000000000000000, 400000000000000000000000000))+", primita la ora: "+str(current_time))
        f.write("\n")
        f.close()
    elif a==str(31):
         meniu_restaurant()
    elif a>str(31) or a<str(1):
        print("Optiune invalida.Reintoarcere automata la meniul principal de carne.")
        time.sleep(3)
        meniu3()
    g=input("Mai aveti nevoie de ceva de la meniul restaurnatului?")
    if g.lower() == 'da':
        print("Ati ales sa reveniti la meniul principal al restaurantului\n")
        meniu_restaurant()
def meniu4():
    print("Ati selectat Meniu cu preparate de peste si fructe de mare\n")
    print("Meniul de peste si fructe de mare este:")
    print("1. Somon la gratar cu legume")
    print("2. Calamari prajiti")
    print("3. Paella cu fructe de mare")
    print("4. Creveți cu usturoi și unt")
    print("5. File de cod cu sos de lamaie")
    print("6. Supa de fructe de mare")
    print("7. Ton la gratar cu salata")
    print("8. Frigarui de creveți cu cartofi")
    print("9. Midii in sos de vin alb")
    print("10. Peste la cuptor cu legume")
    print("11. File de tilapia cu sos de capere")
    print("12. Sardele cu legume la gratar")
    print("13. Peste cu sos de smantana")
    print("14. Sushi mix")
    print("15. Fructe de mare la tigaie cu usturoi")
    print("16. Supa crema de peste")
    print("17. Tarta cu fructe de mare")
    print("18. Caracatita la gratar cu salata")
    print("19. Creveti cu paste si sos de rosii")
    print("20. Peste cu garnitura de orez")
    print("21. Fructe de mare cu sos picant")
    print("22. File de somon cu pesto")
    print("23. Peste cu ciuperci si sos de vin")
    print("24. Pastrav cu cartofi si lamaie")
    print("25. Supa de creveți")
    print("26. Midii in sos de curry")
    print("27. Sushi de ton")
    print("28. Creveți cu orez si legume")
    print("29. Tarta cu ton")
    print("30. Preparat de peste sau fructe de mare personalizat")
    print("31. Inapoi")
    a = input("Pentru a afla pretul produselor sau pentru a va personaliza preparatul de peste introduceti numarul produsului: ")
    if a.isnumeric() and 1 <= int(a) <= 29:
        print(f"Pretul este: {random.randint(30, 50)} lei")
        print("Mulțumim pentru comanda dvs. și vă așteptăm să savurați!")
        t = time.localtime()
        current_time = time.strftime("%H:%M:%S", t)
        f = open("restaurant.txt", "a")
        f.write("Comanda cu numarul "+str(random.randint(200000000000000000, 400000000000000000000000000))+", primita la ora: "+str(current_time))
        f.write("\n")
        f.close()
    if a == '30':
        print("Bine ati venit la meniu de personalizare a preparatelor de peste sau fructe de mare dumneavoastra")
        print("Alegeți din următoarele opțiuni pentru a vă construi propriul preparat de peste sau fructe de mare:")
        ingrediente_peste = [
            "Somon", "Calamari", "Creveți", "Cod", "Ton", "Tilapia", "Sardele", "Caracatita", "Pastrav",
            "Tara", "Sushi", "Fructe de mare", "Sardele", "Pastrav", "Creveți", "Tarta de ton"
        ]
        sosuri_peste = [
            "Sos de lamaie", "Sos de vin", "Sos de usturoi si unt", "Sos de capere", "Sos de smantana",
            "Sos picant", "Sos pesto", "Sos de ciuperci", "Sos de rosii", "Sos de curry"
        ]
        garnituri_peste = [
            "Legume", "Cartofi", "Salata", "Orez", "Paste", "Mamaliga"
        ]
        print("Ingrediente disponibile:")
        for i, ingredient in enumerate(ingrediente_peste, 1):
            print(f"{i}. {ingredient}")
        print("Sosuri disponibile:")
        for i, sos in enumerate(sosuri_peste, 1):
            print(f"{i}. {sos}")
        print("Garnituri disponibile:")
        for i, garnitura in enumerate(garnituri_peste, 1):
            print(f"{i}. {garnitura}")
        alegere_ingredient = input("Selectați numerele corespunzătoare ingredientelor, sosurilor, si garniturilor (separate prin spațiu): ")
        pret_ingredient_suplimentar = 6
        cost_total = 25  
        alegere_ingredient = alegere_ingredient.split()
        for alegere in alegere_ingredient:
            cost_total += pret_ingredient_suplimentar
        print("\nComanda dvs. este următoarea:")
        print("Ingrediente:")
        for alegere in alegere_ingredient:
            if int(alegere) <= len(ingrediente_peste):
                print(ingrediente_peste[int(alegere) - 1])
            elif int(alegere) <= len(ingrediente_peste) + len(sosuri_peste):
                print(sosuri_peste[int(alegere) - len(ingrediente_peste) - 1])
            else:
                print(garnituri_peste[int(alegere) - len(ingrediente_peste) - len(sosuri_peste) - 1])
        print(f"Preț total: {cost_total} lei")
        print("Mulțumim pentru comanda dvs. și vă așteptăm să savurați!")
        t = time.localtime()
        current_time = time.strftime("%H:%M:%S", t)
        f = open("restaurant.txt", "a")
        f.write("Comanda cu numarul "+str(random.randint(200000000000000000, 400000000000000000000000000))+", primita la ora: "+str(current_time))
        f.write("\n")
        f.close()
    elif a==str(31):
         meniu_restaurant()
    elif a>str(31) or a<str(1):
        print("Optiune invalida.Reintoarcere automata la meniul principal de peste.")
        time.sleep(3)
        meniu4()
    g=input("Mai aveti nevoie de ceva de la meniul restaurnatului?")
    if g.lower() == 'da':
        print("Ati ales sa reveniti la meniul principal al restaurantului\n")
        meniu_restaurant()
def meniu5():
    print("Ati selectat Meniu cu deserturi\n")
    print("Meniul de deserturi este:")
    print("1. Tort de ciocolata")
    print("2. Tiramisu")
    print("3. Panna Cotta")
    print("4. Clatite cu inghetata")
    print("5. Cheesecake cu fructe")
    print("6. Profiterol cu ciocolata calda")
    print("7. Salam de biscuiti")
    print("8. Crema de zahar ars")
    print("9. Mousse de ciocolata")
    print("10. Fructe proaspete cu inghetata")
    print("11. Brownie cu nuci si inghetata")
    print("12. Eclere cu crema de vanilie")
    print("13. Parfait cu fructe")
    print("14. Crem Brulee")
    print("15. Bezele cu fructe")
    print("16. Tort de fructe")
    print("17. Budinca de paine cu vanilie")
    print("18. Bomboane de ciocolata")
    print("19. Cirese negre cu smantana")
    print("20. Desert personalizat")
    print("21. Inapoi")
    a = input("Pentru a afla pretul deserturilor sau pentru a va personaliza desertul introduceti numarul desertului: ")
    if a.isnumeric() and 1 <= int(a) <= 19:
        print(f"Pretul este: {random.randint(10, 20)} lei")
        print("Mulțumim pentru comanda dvs. și vă așteptăm să savurați!")
        t = time.localtime()
        current_time = time.strftime("%H:%M:%S", t)
        f = open("restaurant.txt", "a")
        f.write("Comanda cu numarul "+str(random.randint(200000000000000000, 400000000000000000000000000))+", primita la ora: "+str(current_time))
        f.write("\n")
        f.close()
    if a == '20':
        print("Bine ati venit la meniu de personalizare a deserturilor dumneavoastra")
        print("Alegeți din următoarele opțiuni pentru a vă construi propriul desert:")
        
        ingrediente_dessert = [
            "Ciocolata", "Biscuiti", "Vanilie", "Fructe", "Nuci", "Crema", "Cirese", "Bezele", "Budinca",
            "Caramel", "Bomboane", "Inghetata"
        ]
        topping_dessert = [
            "Ciocolata calda", "Fructe proaspete", "Smantana"
        ]
        print("Ingrediente disponibile:")
        for i, ingredient in enumerate(ingrediente_dessert, 1):
            print(f"{i}. {ingredient}")
        
        print("Topping disponibile:")
        for i, topping in enumerate(topping_dessert, 1):
            print(f"{i}. {topping}")
        alegere_ingredient = input("Selectați numerele corespunzătoare ingredientelor și topping-urilor (separate prin spațiu): ")
        pret_ingredient_suplimentar = 4
        cost_total = 15  
        alegere_ingredient = alegere_ingredient.split()
        for alegere in alegere_ingredient:
            cost_total += pret_ingredient_suplimentar
        
        print("\nComanda dvs. este următoarea:")
        print("Ingrediente:")
        for alegere in alegere_ingredient:
            if int(alegere) <= len(ingrediente_dessert):
                print(ingrediente_dessert[int(alegere) - 1])
            else:
                print(topping_dessert[int(alegere) - len(ingrediente_dessert) - 1])
        print(f"Preț total: {cost_total} lei")
        print("Mulțumim pentru comanda dvs. și vă așteptăm să savurați!")
        t = time.localtime()
        current_time = time.strftime("%H:%M:%S", t)
        f = open("restaurant.txt", "a")
        f.write("Comanda cu numarul "+str(random.randint(200000000000000000, 400000000000000000000000000))+", primita la ora: "+str(current_time))
        f.write("\n")
        f.close()
    elif a==str(21):
         meniu_restaurant()
    elif a>str(21) or a<str(1):
        print("Optiune invalida.Reintoarcere automata la meniul principal de deserturi.")
        time.sleep(3)
        meniu5()
    g=input("Mai aveti nevoie de ceva de la meniul restaurnatului?")
    if g.lower() == 'da':
        print("Ati ales sa reveniti la meniul principal al restaurantului\n")
        meniu_restaurant()
def meniu6():
    print("Ati selectat Meniu cu bauturi racoritoare\n")
    print("Meniul de bauturi racoritoare este:")
    print("1. Apa minerala")
    print("2. Apa plata")
    print("3. Suc de portocale")
    print("4. Cola")
    print("5. Limonada")
    print("6. Ceai verde")
    print("7. Ceai negru")
    print("8. Cafea")
    print("9. Suc de mere")
    print("10. Suc de piersici")
    print("11. Suc de ananas")
    print("12. Suc de mango")
    print("13. Suc de capsuni")
    print("14. Suc de grepfrut")
    print("15. Iced tea")
    print("16. Smoothie de fructe")
    print("17. Frappe")
    print("18. Cola Light")
    print("19. Cola Zero")
    print("20. Bautura energizanta")
    print("21. Bautura de fructe")
    print("22. Mocktail")
    print("23. Cappuccino")
    print("24. Latte")
    print("25. Ciocolata calda")
    print("26. Apa plata cu lamaie")
    print("27. Apa plata cu castraveti")
    print("28. Apa minerala cu lamaie")
    print("29. Apa minerala cu portocale")
    print("30. Bautura personalizata")
    print("31. Inapoi")
    a = input("Pentru a afla pretul bauturilor sau pentru a va personaliza bautura introduceti numarul bauturii: ")
    if a.isnumeric() and 1 <= int(a) <= 29:
        print(f"Pretul este: {random.randint(5, 10)} lei")
        print("Mulțumim pentru comanda dvs. și vă așteptăm să savurați!")
        t = time.localtime()
        current_time = time.strftime("%H:%M:%S", t)
        f = open("restaurant.txt", "a")
        f.write("Comanda cu numarul "+str(random.randint(200000000000000000, 400000000000000000000000000))+", primita la ora: "+str(current_time))
        f.write("\n")
        f.close()
    elif a == '30':
        print("Bine ati venit la meniu de personalizare a bauturilor dumneavoastra")
        print("Alegeți din următoarele opțiuni pentru a vă construi propria bautura:")
        ingrediente_bautura = [
            "Soda", "Sirop de fructe", "Lamaie", "Menta", "Zahar", "Gheata", "Cafea", "Lapte", "Frappe",
            "Grepfrut", "Portocale", "Piersici", "Ananas", "Mango", "Capsuni", "Limonada", "Ceai", "Cappuccino",
            "Latte", "Ciocolata", "Bomboane", "Lichior", "Vodka", "Rum", "Gin", "Tequila", "Whiskey"
        ]
        topping_bautura = [
            "Cacao", "Inghetata", "Frisca", "Frappe", "Gheata", "Vanilie", "Frisca", "Coaja de lamaie", "Felii de portocale",
            "Felii de lamaie", "Felii de lime", "Felii de castraveti", "Felii de pepene", "Cuburi de gheata"
        ]
        print("Ingrediente disponibile:")
        for i, ingredient in enumerate(ingrediente_bautura, 1):
            print(f"{i}. {ingredient}")
        print("Topping disponibile:")
        for i, topping in enumerate(topping_bautura, 1):
            print(f"{i}. {topping}")
        alegere_ingredient = input("Selectați numerele corespunzătoare ingredientelor și topping-urilor (separate prin spațiu): ")
        pret_ingredient_suplimentar = 2
        cost_total = 8  
        alegere_ingredient = alegere_ingredient.split()
        for alegere in alegere_ingredient:
            cost_total += pret_ingredient_suplimentar
        
        print("\nComanda dvs. este următoarea:")
        print("Ingrediente:")
        for alegere in alegere_ingredient:
            if int(alegere) <= len(ingrediente_bautura):
                print(ingrediente_bautura[int(alegere) - 1])
            else:
                print(topping_bautura[int(alegere) - len(ingrediente_bautura) - 1])
        print(f"Preț total: {cost_total} lei")
        print("Mulțumim pentru comanda dvs. și vă așteptăm să savurați!")
        t = time.localtime()
        current_time = time.strftime("%H:%M:%S", t)
        f = open("restaurant.txt", "a")
        f.write("Comanda cu numarul "+str(random.randint(200000000000000000, 400000000000000000000000000))+", primita la ora: "+str(current_time))
        f.write("\n")
        f.close()
    elif a==str(31):
         meniu_restaurant()
    elif a>str(31) or a<str(1):
        print("Optiune invalida.Reintoarcere automata la meniul principal de racoritoare.")
        time.sleep(3)
        meniu6()
    g=input("Mai aveti nevoie de ceva de la meniul restaurnatului?")
    if g.lower() == 'da':
        print("Ati ales sa reveniti la meniul principal al restaurantului\n")
        meniu_restaurant()
def optiune_5():
    print("Ati selectat Contact")
    time.sleep(2)
    print("1.Locatie")
    print("2.Calculator distanta")
    print("3.Istoric restaurant")
    print("4.Program restaurant")
    y=input("Alegeti din meniul de mai sus categoria dorita")
    if y=="1":
        time.sleep(2)
        print("Subcategoriile sunt:")
        time.sleep(2)
        print("1.Adresa ")
        print("2.Atractii turistice din jur")
        print("3.Indicatii pentru a ajunge la adresa")
        time.sleep(2)
        c=input("Subcategoria aleasa este:")
        if c=="1":
            time.sleep(2)
            print("Locatia restaurantului este:")
            print("Adresa: Str. Eusebiu Andries nr. 123, Cluj-Napoca, Romania")
        if c=="2":
            tme.sleep(2)
            print("Atractiile turstice din jurul restaurantului sunt:")
            time.sleep(2)
            print("Gradina zoologica la 300m")
            print("Primaria orasului Cluj-Napoca la 100m")
            print("Muzeul Ianos Vastij la 250m")
            print("Muzeul de arta contemporana la 150m")
            print("Teatrul Micul Print la 350m")
            print("Podul Marea Speranta la 200m")
            print("Biserica Buna speranta la 150m")
            print("Catedrala Arhangelul Andrei la 400m")
            print("Piata Iancu de Hunedoara la 235m")
        if c=="3":
            time.sleep(2)
            print("Pentru indicatii depinde daca folosim autobuzul sau tramvai")
            time.sleep(2)
            print("1.Autobuz")
            print("2.Tramvai")
            d=input("Alegere dintre autobuz si tramvai")
            if d=="1":
                print("Autobuzele care ajung la hotel sunt 456,678,987 si statile de unde pot fi luate sunt:Mihai Vitezul,Alexandru cel Bun si Diamant")
            if d=="2":
                print("Tramvaiele care ajung pana la hotel sunt 45,34,12,67 si pot fi luate de la statile:Bucuresti,Tudor Vianu,Europa si Bistrita-Nasaud")
    if y=="2":
       
        distanta_hotel = {
         "bucuresti": 50,
         "cluj-Napoca": 300,
         "timisoara": 450,
         "iasi": 350,
         "constanta": 100,
         "brasov": 150,
         "sibiu": 400,
         "galati": 300,
         "craiova": 200,
         "oradea": 500,
         "targoviste":600,
         "sinaia":350,
         "calimanesti":678,
         "petrosani":456,
         "mangalia":234,
         "braila":434,
         "mircesti":334,
         "neptun":560,
         "navodari":348
        }


        oras_input = input("Introduceți orașul: ").lower()


        if oras_input in distanta_hotel:
    
         distante = [distanta_hotel[oras_input]]
    
   
         print(f"Distanța de la hotel la {oras_input} este {distante[0]} km.")
        else:
          print("Orașul introdus nu este înregistrat.")
def optiune_6():
    print("Ati selectat iesire din meniu")
x=input("Vrei sa continui spre meniu?\n")
while x=='Da' or x=='da':
    afiseaza_meniu()
    optiune = input("Selectați o opțiune: \n")
    if optiune == "1":
        optiune_1()
        x=input("Doriti sa va intoarceti la meniul principal al hotelului?\n")
        while x != 'da' and x != 'Da':
            print("Multumim ca ne-ati vizitat siteul")
            break
    elif optiune == "2":
        optiune_2()
        x=input("Doriti sa va intoarceti la meniul principal al hotelului?\n")
        while x != 'da' and x != 'Da':
            print("Multumim ca ne-ati vizitat siteul")
            break
    elif optiune == "3":
        optiune_3()
        x=input("Doriti sa va intoarceti la meniul principal al hotelului?\n")
        while x != 'da' and x != 'Da':
            print("Multumim ca ne-ati vizitat siteul")
            break
    elif optiune == "4":
        optiune_4()
        x=input("Doriti sa va intoarceti la meniul principal al hotelului?\n")
        while x != 'da' and x != 'Da':
            print("Multumim ca ne-ati vizitat siteul")
            break
    elif optiune == "5":
        optiune_5()
        x=input("Doriti sa va intoarceti la meniul principal al hotelului?\n")
        while x != 'da' and x != 'Da':
            print("Multumim ca ne-ati vizitat siteul")
            break
    elif optiune == "6":
        optiune_6()
        x=input("Sunteti sigur ca nu mai doriti nimic?\n")
        while x=='da' or x=='Da':
            print("Multumim ca ne-ati vizitat siteul")
            break
    else:
        print("Opțiune invalidă. Vă rugăm să selectați o opțiune validă.\n")
print("Ne pare rau ca vizita dumneavoastra a fost asa de scurta")
