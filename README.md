# Sprint4
1. Veiksmas
Paskelbiu du kintamuosius per input ir button id
Sekančią Const paskelbsiu per class (kad pasigilinti)nors galėčiau ir per Id.
2. Veiksmas
Paskelbiu funkciją konstruktorių, kad inicijuoti, kada užbaigtas Task(-užduotis) kada ne.
Funkcija apibudinam -"Description"(tai tas apibudinimas, kuris pareis iš inputo.
Kai Task susikuria  numatyta reikšmė bus false.
3. Veiksmas
Nuspaudus  addTaskBtn, description, turės fiksuotis objekte, kurį siusime į masyvą,ir kas kart naujai sukurtas Task keliaus kaip naujas objektas į masyvo galą , 

Kad sukurta objekta, galėtume siusti į masyvą, tam sukuriame kintamaji, kuriam pradžiai suteikiame reikšmę tuščio masyvo. Veliau tai keisim.  

Nuspaudus  addTaskBtn pirmiausia išklausysime renginį-event('click'-paspaudimas) po ko vidinėje funkcijoje, kuri bus iššaukiama paspaudus addTaskBtn, objektą, kuri sukursime konstruktoriumi(description), siūsime į let kintamuoju sukurtą tuščią masyvą "tasks" 

Masyvui tasks priskiriame metodą push, metodas push siunčia i masyvo galą objektą.
Kurdami naują objektą su funkcija new Task
Perduodame jai pradžioje sukurto kintamojo mazgą , inputo'description-task' su numatyta verte value

4. Veiksmas
tasks masyvą siūsiu į Local Storage ir paskui iš ten imsime reikiamus objektus
Kiek aukščiau pateiksime funkciją, kuri mums būs reikalinga ir kituose dalyse.

Kreipiames i globaline mums prieinamą localStorage,  su metodu setItem kuriuo(viduje) perduodame dvi prasmes (key: string, value: string) key- pervadinsime į mūsu uždavinį('tasks'), (antrają reikšmę reiktu paduoti JSON formatu. Todėl masyvą tasks  turime perfarmatuoti į JSON ir tik tada nusiūsti į  Local Storage
updateLocal iššaukiam būten tada kai suveikia tasks.push

Patikriname serveryje(Application =>Local Storage
https://github.com/Vizijant/Sprint4/blob/main/img/Fiksavimas.PNG

5. Local Storage Array Fill
Kreipiuosi į Local Storage ir tikrinu ar pas mane yra kas Local Storage kad reikšmes siūsti į lokalų masyvą o jei nieko ten nerasime tai task  bus tuščas, ir tada mes užpildisime jį, o iš jo pildysis masyvas- Local Storage. Suksim ratu.
let tasks;      !localStorage.tasks ? tasks = [] : tasks = JSON.parse(localStorage.getItem('tasks'));

6. Added features to make  "tasks" appear on the page

Jeigu local Storage yra reikšmių "!localStorage.tasks" tada jos  siunčiamos į tasks. Per funkcija  "fillHtmlList()" kreipiames į tasks, tada metodas "forEach()" vieną kartą vykdo pateiktą funkciją kiekvienam masyvo elementui.  Tada, per sukurtą funkcija, "createTemplate(item, index) "formuojasi šablonas, kuris siunčiamas į "todos-wrapper", kad pasiektu galutinį tikslą -pasirodytu ekrane.

7. Added task tagging features

Kad įgalinti  migtuką "btn-complete" (jį nuspaudus, ekranas išduotu užduoties "task"  įvykdymo faktą). 
1) Kreipsiuos į masyvą "tasks", kad surasti tą elementą , kuris buvo paveiktas paspaudimu, 
2) Iššaukti funkciją complete.Task priimant reikšmę index, Po ko kreipsiuos į masyvą, kad pakeisti reikšmes, ir kreipsiuos localStorage, kad localStorage per "updateLocal" funkciją atnaujintu reikšmes orientuodamasis į masyvą "tasks".


8. Deleting tasks

Kad  ištrinti užduotis masyve, o duomenys  atsinaujintu localStorage, kreipiuosi į tasks ir su metodu 
Splice trinsiu vieną pasirinktą index, po ko iššauksiu () kad atnaujintu localStorage, tada  su () fillHtmlList
 pasiektiu galutinį tikslą -  paspaudus delete migtuką, užduotis ekrane pradingsta.
