This is a database dump of the data which was used for the EmmisionQuality API, which was available on Trafiklab up to 2019.

Den miljödatabas som Viktoriainstitutet tillhandahåller under travelhack och därefter är enkel och ger en miljöpåverkansbild för ett antal vanliga transportslag (bil, buss, spårvagn, tåg). För samtliga transportslag är det bara energin för framdrivningen som omfattas i denna miljöpåverkansbeskrivning, och inte andra aspekter som t.ex. buller, markanvändningsbehov och partikelspridning från lednings-, asfalts-, hjul-, däck- och rälsförslitning. För att göra miljöpåverkan jämförbar mellan de olika transportslagen omfattas energiförbrukningens alla miljöpåverkande steg, hela vägen från oljekälla/vattenkraftverk/kärnkraftverk etc. till ’avgasrör’.

Man kan använda denna databas för att ge en siffra på den relativa miljöpåverkan i den transportlösning man väljer. Förr närma sig hållbar utveckling bör målet vara att använda så lite energi som möjligt, att den energi som används är förnybar, att göra så lite utsläpp som möjligt där de inte stör människor eller natur och att ändå transportera människor på bästa sätt.

I korthet

    Emissionerna som anges är resultatet av förbränning av kolväte, som olja, diesel, bensin, etanol, metangas
    Koldioxid antas leda till växthuseffekt om det ger ett nettobidrag till atmosfären.   
    Övriga utsläpp och deras miljömässiga innebörd beskrivs kort nedan.
    MJ förnybar, MJ fossil och MJ kärnkraft indikerar olika miljörelaterade aspekter om vart energin kommer ifrån för att tillgängliggöra energin för framdrivningen av transporten (MJ = Megajoule). Förnybart betyder att det troligen växer monokulturell skog eller åker någonstans. Fossilt innebär att man tar upp olja eller gas eller bryter kol. Kärnkraft innebär att energin kommer från kärnkraft, alltså ett energislag med mycket gruvbrytning och stora avfallssvårigheter.  

Ingående substanser

En lista av följande substansdata, med mätetal och enhet och följande tolkning ges som svar på API-anropen:

    CO2(total) : Den totala mängden CO2-utsläpp för bränsle/energiförbrukningen för valt transportslag, alltså både den andel som bidrar till växthuseffekt och den som ingår i en kortare koldioxidcykel med som växtmaterial i skog och annat.
    CO2(fossil) : Den totala mängden CO2-utsläpp som är tillförd till atmosfären, alltså den andel av CO2(total) som antas bidra till växthuseffekt. Dessa två CO2-tal ska alltså INTE summeras!
    NOX: Kväveoxider, ämnen som leder till hälsoproblem i stadsluften och försurningsproblem I skog mark och kustområden.
    HC: Kolväten, leder till hälsoproblem i stadsluften
    CH4: Metangas, en mycket kraftigare klimatgas än CO2, men oftast släppts de tut mindre CH4 än CO2.
    CO: Kolmonoxid, en giftig gas.
    PM: Partiklar, hälsofarliga I stadsmiljön. Har samband med en lång rad olika sjukdomar.
    SO2: Svaveldioxid, leder till hälsoproblem i stadsluften och försurningsproblem I skog mark och kustområden.
    MJ(förnybar): Mängd förnybara energislag som utnyttjats under bränslets livscykel.
    MJ(fossil) : Mängd icke förnybara kolbaserade energislag som utnyttjats under bränslets livscykel.
    MJ(kärnkraft) : Mängd kärnkraftsenergi som utnyttjats under bränslets livscykel.

Notera: CO2-utsläppsdata i denna databas kan ’konkurrera’ med CommuteGreeners CO2 Emission, vilket kan leda till förvirring. För sammanhanget Travel Hack kan man välja vilken som helst av dessa två datakällor om man endast vill beskriva CO2-utsläpp (Dubbelkolla dock först om CommuteGreener ger totalt utsläpp eller fossilt utsläpp.) 

API:t ger transportmiljödata från huvudsakligen NTMs databas (NTM = Nätverket för transporter och Miljö www.ntmcalc.org) för fordonsemissioner. Relationsdatabasen bakom detta API är däremot helt egenutvecklad för detta projekt, ISET, för att klara att söka transporter med fler olika kategoriseringar. Databasen innehåller också  egna tillägg av transportmiljödata.  För ändamålet har vi valt att ha en så enkel frågestruktur som möjligt, för att göra det lätt för mjukvaruutvecklare som inte är kunniga inom miljöområdet att att ställa meningsfulla frågor till databasen och att tolka svaren.