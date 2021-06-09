---
title: Metodtips för att Office 365 i ett långsamt nätverk
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/29/2016
audience: End User
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
search.appverid:
- MET150
- MET150
- MOP150
- MEW150
- BCS160
ms.assetid: fd16c8d2-4799-4c39-8fd7-045f06640166
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: Den här artikeln leder dig genom de metodtips som du kan använda för Office 365 på ett långsamt nätverk.
ms.openlocfilehash: effa1038b03a9fcafc74166a1f53682186688906
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905266"
---
# <a name="best-practices-for-using-office-365-on-a-slow-network"></a>Metodtips för att Office 365 i ett långsamt nätverk

Skulle det inte vara snyggt om din Internetanslutning alltid var snabb och alltid låg? Kanske den dagen kommer. Men under tiden finns det praktiska saker du kan göra för att komma runt ett motigt nätverk och fortfarande få ditt dagliga arbete gjort. Även Office 365 är en molnbaserad tjänst erbjuder det också många sätt att arbeta med innehåll offline och smidigt hålla dina ändringar synkroniserade. Dessutom kan det ibland vara mer effektivt att arbeta med innehåll offline bara för att programmen fungerar snabbare och användargränssnittet svarar snabbare. Poängen är följande: Office 365 ger dig det bästa av båda världarna. Så här kan du dra nytta av det. 
  
> [!TIP]
> Vill du se hur långsam (eller snabb) din nätverksanslutning är? Prova [hastigheten med OOKLA eller](https://www.speedtest.net/) appen [Nätverkshastighetstest.](https://www.windowsphone.com/store/app/network-speed-test/9b9ae06b-2961-41ef-987d-b09567cffe70) 

## <a name="why-is-my-network-so-slow"></a>Varför är mitt nätverk så långsamt?

Även om du inte har kontroll över nätverkets prestanda i sig självt kan det vara bra att förstå vad som händer bakom kulisserna. Internet är enormt komplext, men det finns vissa begrepp som kan hjälpa dig att förstå situationen betydligt bättre. Genom att följa metodtipsen i den här artikeln kan du få hjälp med att lösa prestandaproblem och minska frustrationen.
  
**Viktiga faktorer som påverkar nätverkets prestanda**

![Nätverkets prestandafaktorer](../media/62a94322-3f1a-4d2d-bbdc-2aa0722d2d96.png)
  
 **Bandbredd och svarstid** De två allra viktigaste måtten på nätverkets prestanda är bandbredd och svarstid: 
  
- Bandbredden är genomflödets hastighet i bitar per sekund. Ju högre desto bättre. Bandbredden är som en vattenledning. Ju större rörledning, desto mer vatten kan "passera igenom".

- Svarstiden är den tid det tar för innehåll att komma från en server eller tjänst till din enhet och mäts i millisekunder. Ju snabbare desto bättre. Svarstiden kan orsakas av ett antal faktorer, bland annat låg bandbredd, en svag anslutning eller överföringstid.

 **Vanliga problem** Förutom bandbredd och svarstid kan andra problem påverka nätverkets prestanda, och dessa är ofta oförutsägbara. Nätverkets prestanda kan variera beroende på tid på dagen eller din fysiska plats. Nätverket kan bli tilltäppt när vissa händelser inträffar som insamling av Internet, till exempel en naturhändelse eller en större offentlig händelse. Storleken på och komplexiteten hos den sida som läses in och antalet och storleken på filer som överförs har direkt inverkan på prestandan. En WiFi-anslutning kan tillfälligt försämras. Du kan till exempel rösta på ett stort konferensmöte med tusentals personer genom att be alla twittra till samtidigt. 
  
 **Överväganden för ett satellitnätverk** Ett satellitnätverk är användbart när det inte är möjligt att ha ett marknätverk, till exempel i det land där du ligger, på ett fartyg eller i ett fjärranslutet vetenskapligt område. Satellitnätverk är beroende av satelliter som ligger i ett geosynkront kretsande 22 000 km ovanför ekvatorn. En överföring färdas dock ca 344 800 km, och därför har ett satellitnätverk långsammare svarstid (500 ms eller mer) än ett marknätverk (20 till 50 ms). När villkoren är de bästa märker du kanske inte den här fördröjningen, men när du ska ladda ned stora filer, direktuppspela videor och spela spel gör du det förmodligen. Ett annat problem är att hårt väder, till exempel åskoningar och snöstormar, tillfälligt kan avbryta satellitöverföringen.
  
## <a name="are-you-sure-its-the-network"></a>Är du säker på att det är nätverket?

När du upplever prestandaproblem kontrollerar du först att det inte är enheten som är orsaken till problemet. Det finns två saker du kan göra som kan göra en stor förbättring:
  
- Kontrollera att enheten fungerar som den ska och att det inte finns någon skadlig programvara på datorn.

- Köp mer minne om möjligt. Att lägga till minne är det enklaste och ofta mest effektiva sättet att förbättra prestandan på enheten. Det är särskilt användbart när du arbetar med stora filer och videor.

Mer information finns i Windows [Prestanda och underhåll samt Tips](https://windows.microsoft.com/windows/performance-maintenance-help#performance-maintenance-help) för att förbättra [datorns prestanda i Windows 10.](https://support.microsoft.com/en-za/help/4002019/windows-10-improve-pc-performance)

## <a name="best-practices-for-using-your-browser"></a>Metodtips för att använda webbläsaren

Din webbläsare är din gateway för Office 365, så den kan påverka prestandan, särskilt den tid det tar att läsa in en sida och hur ofta du tur och retur till Office 365-tjänsten.
  
 **Webbläsare i allmänhet**
  
Här är några förslag för webbläsare i allmänhet:
  
- Inaktivera webbläsartillägg som kan påverka prestandan eller som du inte verkligen behöver.

- Öka cachestorleken för temporära Internetfiler.

- När du har loggat in på ditt arbets- eller skolkonto behåller du webbläsarfönstret öppet hela dagen. Du kan öppna andra flikar och fönster utan att logga in igen. Om du behöver logga in på ett annat konto använder du Privat surfning. 

- När varje sida har laddats ned och öppnats kan du hålla dem öppna med hjälp av flikar. Det är enkelt att navigera mellan flikar och använda sidan senare under dagen. Uppdatera en sida endast om du behöver den senaste informationen på sidan.

- Om det tar för lång tid att öppna en sida stoppar du nedladdningen av sidan (tryck på ESC) och uppdaterar sedan sidan (tryck på F5). 

-  Dra ner på tur och returen till Office 365, om det är Office 365. I stället för att bläddra genom listor eller bibliotek kan du till exempel använda sökfunktionen för att hitta filer i ett stort bibliotek och filtrera listor så att du kommer direkt till de resultat du vill ha. Eller skapa vyer som minimerar inläsningstiden. Mer information finns i [Hantera stora listor och bibliotek i Office 365](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784#BKMK_PAGES).

- Om videoprestandan är dålig kanske du kan ladda ned videon och titta på den på din enhet. Det kan finnas en nedladdningslänk eller så kan du kanske högerklicka på videolänken och välja **Spara mål som**.

 **Specifika webbläsare**
  
Här är några förslag för just din webbläsare:
  
- **Internet Explorer** Uppgradera till Internet Explorer version 11 eller senare för att få betydande prestandaförbättringar jämfört med tidigare versioner. Mer information finns i [Felsökningsguide för Internet Explorer.](https://support.microsoft.com/help/2437121/troubleshooting-guide-for-internet-explorer-when-you-access-office-365)

- **FireFox** Mer information finns i [Firefox är långsamt eller slutar fungera.](https://support.mozilla.org/products/firefox/fix-problems/slowness-or-hanging)

- **Safari** Mer information finns i [Apple – Safari](https://www.apple.com/safari/).

- **Chrome** Mer information finns i [hjälpen till Chrome.](https://support.google.com/chrome/?hl=en)
  
## <a name="best-practices-for-using-outlook-and-outlook-web-app"></a>Metodtips för att använda Outlook och Outlook Web App

Läsa, skriva och ordna e-post uppdelar en stor del av allas dagar. Både Outlook och Outlook Web App (OWA) har stöd offline. Ett annat bra alternativ är att använda ett e-postapp på en smartphone. Använd de alternativ som passar dina behov bäst:
  
- Uppgradera till den senaste Outlook för att få betydande prestandaförbättringar jämfört med tidigare versioner. 

-  Outlook Web App kan du skapa meddelanden, kontakter och kalenderhändelser offline som sedan överförs nästa gång OWA ansluter till Office 365. Mer information om hur du inställningar och använder OWA i offlineläge finns i [Använda Outlook Web App offline.](https://support.office.com/article/3214839c-0604-4162-8a97-6856b4c27b36)

- Outlook kan arbeta i cachelagrat läge, där den automatiskt ansluts när det är möjligt. Du kan Outlook hämta hela postlådan eller bara en del av den. Mer information finns i Aktivera [cachelagrat Exchange och](https://support.office.com/article/7885af08-9a60-4ec3-850a-e221c1ed0c1c) [Arbeta offline i Outlook.](https://support.office.com/article/f3a1251c-6dd5-4208-aef9-7c8c9522d633)

- Outlook också ett offlineläge. Om du vill använda det måste du först ställa in cachelagrat läge så att information från ditt konto kopieras till datorn. I offlineläge Outlook ansluta med hjälp av inställningarna för Skicka och ta emot, eller när du manuellt ställer in det för onlinearbete. Mer information finns i Arbeta offline för att undvika [dataanslutningsavgifter](https://support.office.com/article/827fe51f-5609-4062-82b4-3578057f9282), Ändra inställningar för att skicka och ta emot när du arbetar [offline](https://support.office.com/article/f681ec10-cb14-40cb-8709-1909a13c304a)och Växla från [att arbeta offline till online.](https://support.office.com/article/2460e4a8-16c7-47fc-b204-b1549275aac9)

- Om du har en smartphone kan du använda den för att trija e-post och kalender över telefonioperatörens nätverk.

> [!NOTE]
> Här är några råd om när du kan använda Outlook eller OWA. Om diskutrymmet inte är ett problem på din enhet Outlook en fullständig uppsättning funktioner och kanske fungerar bäst för dig. Om diskutrymmet är ett problem på din enhet kan du använda OWA som har en deluppsättning funktioner, men också fungerar bäst i en onlinesituation. Du kan naturligtvis använda båda eftersom de fungerar bra tillsammans.
  
## <a name="best-practices-for-using-onedrive-for-business"></a>Metodtips för att använda OneDrive för företag

OneDrive för företag har utformats från grunden för att fungera tillsammans med dina filer online och offline. När du har ställt in det sker synkroniseringen av ändringar automatiskt och tillförlitligt var och när du än gör dem. Om nätverket är långsamt kan du arbeta med offlineversionen av filerna.
  
Appen OneDrive för företag har en prenumeration på SharePoint Online och Office 365, eller så [](https://support.microsoft.com/kb/2903984) kan du ladda ned OneDrive för företag-synkroniseringsappen kostnadsfritt. Den här appen går också snabbare än att använda **kommandona Öppna** **i Utforskaren Upload** Utforskaren. Mer information finns i [Konfigurera din dator för att synkronisera dina e OneDrive för företag filer i Office 365](https://support.office.com/article/23e1f12b-d896-4cb1-a238-f91d19827a16).
  
Här är ytterligare vägledning för hur du använder OneDrive för företag synkroniseringsapp:
  
- Om du synkroniserar ett stort bibliotek för första gången bör du starta synkroniseringen utanför arbetstid, till exempel över natten.

- Du kan använda funktionen [Sluta synkronisera ett bibliotek med OneDrive för företag för](https://support.office.com/article/a7e41f1f-3a98-4ca7-9443-f10250688330) att tillfälligt stoppa synkroniseringen av uppdateringar. Du bör emellertid bara använda den här funktionen under korta stunder, till exempel ett par timmar i taget, för att undvika köer av stora mängder uppdateringar och för att minimera risken för sammanslagningskonflikter om flera personer arbetar med samma dokument.
  
## <a name="best-practices-for-using-onenote"></a>Metodtips för att använda OneNote

Alla SharePoint-gruppwebbplatser har en inbyggd inbyggd OneNote och du kan enkelt skapa en egen. OneNote är ett bra sätt att samla information som du behöver varje dag för att få saker gjorda. Många grupper kan till exempel använda OneNote en samlingspunkt för veckomöten, projektanteckningar, idéer, planer och statusrapporter. Du kan organisera alla dessa olika information med hjälp av sidor, avsnitt och flikar.
  
Det som är OneNote är att du får tillgång till innehållet från praktiskt taget vilken enhet som helst, oavsett om det är en stationär dator, en bärbar dator, en surfplatta eller en smartphone. Och du behöver inte tänka på att spara eller synkronisera eftersom OneNote gör det åt dig.
  
Mer information finns i [Microsoft OneNote](https://office.microsoft.com/onenote).

## <a name="best-practices-for-using-skype-for-business-and-lync-online"></a>Metodtips för att använda Skype för företag och Lync Online

Här följer allmänna riktlinjer för användning Skype för företag Lync Online när nätverket är långsamt:

- Använd snabbmeddelanden när du kan eftersom det fungerar bra på ett långsamt nätverk.

- Undvik att ringa telefonsamtal via ett virtuellt privat nätverk (VPN) eller ras-anslutningar (fjärråtkomst).

- Kontrollera att ljudenheten är godkänd. Mer information finns i Telefoner [och enheter som är kvalificerade för Microsoft Lync.](/skypeforbusiness/lync-cert/ip-phones)

- När du PowerPoint i en onlinepresentation bör du minska bildernas storlek och komplexitet. Mer information finns i [Tips hur du förbättrar presentationens prestanda.](https://support.office.com/article/34c82835-5f23-4bf0-98cc-72235bbd2949)

- Videoprestandan är mycket beroende av nätverkets prestanda. Undvik att använda video om nätverket är långsamt.

Mer information finns i [Dålig ljud- eller videokvalitet i Lync Online](https://support.microsoft.com/kb/2386655)eller felsöka [anslutningsproblem i Skype för företag](https://support.office.com/article/troubleshoot-connection-issues-in-skype-for-business-ca302828-783f-425c-bbe2-356348583771).
  
## <a name="best-practices-for-using-sharepoint-lists"></a>Metodtips för att använda SharePoint listor

Att arbeta med listdata offline för att "rensa", analysera eller rapportera data är ett bra sätt att minimera påverkan på ett långsamt nätverk. Du kan läsa och skriva de flesta listor från Microsoft Access 2019 och Microsoft Access 2016 genom att länka till dem. Du kan också exportera en lista Excel tabell, vilket skapar en envägsdataanslutning mellan Excel och listan. Lär dig hur [du arbetar offline med tabeller som är länkade till SharePoint listor](https://support.office.com/article/work-offline-with-tables-that-are-linked-to-sharepoint-lists-5d66594a-6176-4a25-a198-320f13ccf41e).
  
Mer information finns i avsnittet "Mer information om hur du hanterar stora listor" i [Hantera stora listor och bibliotek i Office 365](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784).
  
## <a name="best-practices-for-customizing-web-pages"></a>Metodtips för att anpassa webbsidor

När du anpassar en webbsida kan du oavsiktligt orsaka dålig prestanda med sidan. Ett antal faktorer kan påverka, till exempel sidans komplexitet och storlek, hur många webbdelar som läggs till, hur många listor eller biblioteksobjekt som visas först och hur du kodar sidan.
  
Mer information finns i Justera [SharePoint Online-prestanda.](tune-sharepoint-online-performance.md)
  
## <a name="best-practices-for-using-project-online"></a>Metodtips för att använda Project Online

Följande riktlinjer kan förbättra nätverkets prestanda.
  
- Project Online och SharePoint online kräver synkronisering, vilket kan ta lång tid. Om dina projektteam har låg omsättning kan du inaktivera Project för att förbättra prestandan för Project Publicera Project Och Informationssidor. Begränsa Active Directory-synkroniseringen till de resursgrupper som verkligen behöver använda systemet och övervaka potentiella behörighetsproblem när stora grupper har synkroniserats.

- Om din organisation använder projektwebbplatser kan du skapa dem på begäran snarare än automatiskt. Det här gör att den första publiceringen går snabbare och att ni kan undvika att skapa webbplatser och innehåll i onödan.

- Project Detaljsidor (PDP) kan utlösa en omräkning av hela projektet och sätta igång arbetsflödesåtgärder, vilket båda kan vara prestandaintensiva åtgärder. Om du vill undvika att utlösa två uppdateringsprocesser samtidigt för samma PDP bör du undvika att uppdatera kalenderfälten (startdatum, slutdatum, rapportdatum och aktuellt datum) och fälten som inte är schemalagda (projektnamn, beskrivning och ägare).

- Minska antalet webbdelar och anpassade fält som visas på varje PDP. Skapa en dedikerad PDP med de enda fält som måste uppdateras för att förbättra inläsnings- och spartid.

- När du använder OData för rapportering kan du begränsa mängden data som du genomfrågar vid körningen med hjälp av filtrering på servern.

Mer information finns i [Justera Project Online prestanda.](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c)
  
## <a name="whats-the-best-way-to-report-problems"></a>Vilket är det bästa sättet att rapportera problem?

Microsoft förbättrar kontinuerligt den övergripande prestandan i Office 365 genom att övervaka nätverket, mäta bandbredden och svarstiden, förbättra sidinläsningstiden, minska disk-I/O, omarbeta sidor för minimal nedladdningsstrategi, lägga till maskinvara på datacenter och lägga till fler datacenter. Mer information om hur du kontrollerar din aktuella status och rapporterar problem finns [i Kontrollera Office 365 tjänstens hälsa.](view-service-health.md)
  
## <a name="see-also"></a>Se även

[Network planning and performance tuning for Office 365](network-planning-and-performance.md)
  
[Office 365 principer för nätverksanslutningar](microsoft-365-network-connectivity-principles.md)
  
[Hantera Office 365-slutpunkter](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Office 365-slutpunkter – vanliga frågor och svar](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
