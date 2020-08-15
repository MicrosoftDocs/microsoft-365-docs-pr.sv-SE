---
title: Metod tips för att använda Office 365 på en långsam nätverks
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
description: I den här artikeln får du hjälp med de bästa metoderna för att använda Office 365 i ett långsamt nätverk.
ms.openlocfilehash: a0a15191fa0240f24cecc5e595de9a259cacc9f9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694730"
---
# <a name="best-practices-for-using-office-365-on-a-slow-network"></a>Metod tips för att använda Office 365 på en långsam nätverks

Vore det inte bra om din Internet anslutning alltid är snabb och aldrig upphörde? Kanske kommer den att komma. Under tiden finns det praktiska saker du kan göra för att arbeta i ett balky nätverk och ändå få det dagliga arbetet. Även om Office 365 är en molnbaserad tjänst finns det också på många sätt att arbeta med innehållet offline och för att det ska bli lättare att synkronisera dina ändringar. Dessutom är det ibland mer effektivt att arbeta med innehållet offline bara för att programmen körs snabbare och användar gränssnittet svarar mer. Nu är det här: Office 365 ger dig det bästa av två världar. Så här drar du nytta av det. 
  
> [!TIP]
> Vill du se hur långsamt (eller fast) din nätverks anslutning är? Prova [ OOKLA ](https://www.speedtest.net/) eller testa [nätverks hastigheten](https://www.windowsphone.com/store/app/network-speed-test/9b9ae06b-2961-41ef-987d-b09567cffe70). 

## <a name="why-is-my-network-so-slow"></a>Varför är mitt nätverk så långsamt?

Även om du inte har kontroll över nätverkets prestanda kan du förstå vad som händer bakom kulisserna. Internet är mycket komplicerat, men det finns några koncept som kan hjälpa dig att förstå situationen bättre. Med de bästa metoderna i den här artikeln kan du undvika prestanda problem och minska godheten.
  
**Viktiga faktorer som påverkar nätverks prestanda**

![Prestanda faktorer för nätverk](../media/62a94322-3f1a-4d2d-bbdc-2aa0722d2d96.png)
  
 **Bandbredd och svars tid** De två viktigaste måtten för nätverks prestanda är bandbredd och svars tid: 
  
- Bandbredd är överföringshastigheten mätt i bitar per sekund. Större är bättre. Bandbredden är som en vatten pipe. Ju större rör desto mer vatten kan du lägga på den.

- Fördröjning är den tid det tar för innehållet att komma från en server eller tjänst till din enhet och mäts i millisekunder. Snabbare är bättre. Fördröjningen kan orsakas av olika faktorer, till exempel dålig bandbredd, en sparse-anslutning eller överförings tid.

 **Vanliga problem** Utöver bandbredd och svars tid kan andra problem påverka nätverkets prestanda och är ofta oförutsägbart. Nätverks prestanda kan variera beroende på tiden på dagen eller din fysiska plats. Nätverket kan bli tilltäppt när vissa händelser uppstår som tar hänsyn till användningen av Internet, till exempel en natur katastrof eller en allmän offentlig händelse. Storleken på och komplexiteten hos den sida som laddas och antalet filer som överförs har en direkt påverkan på prestanda. En WiFi-anslutning kan tillfälligt sänkas: till exempel avsöker du ett stort konferens möte med tusentals samtal genom att begära alla till tweet samtidigt. 
  
 **Överväganden för ett satellit nätverk** Ett satellit nät är användbart när ett land nät inte är genomförbart, till exempel ett bakre land, ett surfat fartyg eller ett vetenskapligt avancerat område. Dessa nätverk förlitar sig på satelliter som är placerade i en mitt synkrona bana 22 000 mil ovanför likställaren. Överföringen tar emellertid faktiskt ca 90 000 miles och så att ett satellit nät har en långsam fördröjning (500 ms eller mer) än ett land nät (20 till 50ms). Under de bästa förhållandena är det möjligt att du inte märker denna svars tid, men för att ladda ned stora filer, direktuppspelade videoklipp och spel spelas antagligen det. Ett annat problem är "regn toning" där tunga väder, till exempel thunderstorms och Blizzards, kan avbryta satellit sändningen tillfälligt.
  
## <a name="are-you-sure-its-the-network"></a>Är du säker på att det är nätverket?

När du får prestanda problem bör du först kontrol lera att din enhet inte orsakar problemet. Det finns två saker du kan göra för att göra en större förbättring:
  
- Kontrol lera att din enhet är igång och att det inte finns någon skadlig program vara på datorn.

- Köp om möjligt mer minne. Att lägga till minne är det enklaste och mest effektiva sättet att förbättra datorns prestanda. Det är särskilt användbart när du arbetar med stora filer och videor.

Mer information finns i [ Windows-prestanda och-underhåll ](https://windows.microsoft.com/windows/performance-maintenance-help#performance-maintenance-help) och [tips för att förbättra datorns prestanda i Windows 10](https://support.microsoft.com/en-za/help/4002019/windows-10-improve-pc-performance).

## <a name="best-practices-for-using-your-browser"></a>Metod tips för att använda webbläsaren

Webbläsaren är din gateway för Office 365, så att den kan påverka prestanda, särskilt med den tid det tar att läsa in en sida och hur ofta du ska resa till Office 365-tjänsten.
  
 **Webbläsare allmänt**
  
Här är några förslag för webbläsare i allmänhet:
  
- Inaktivera tilläggs komponenter som kan påverka prestanda eller som du inte behöver.

- Öka cachestorleken för dina tillfälliga Internet-filer.

- När du har loggat in på ditt arbets-eller skol konto håller du webbläsarfönstret öppet under hela dagen. Du kan öppna andra flikar och fönster utan att logga in igen. Om du behöver logga in på ett annat konto kan du använda privat surfning. 

- När alla sidor har laddats ned och öppnats behåller du dem öppna med flikar. Det är enkelt att navigera mellan flikar och att använda sidan senare på dagen. Uppdatera endast en sida om du vill ha den senaste informationen på den sidan.

- Om det tar för lång tid att öppna en sida stoppar du sid nedladdningen (tryck på ESC) och uppdaterar sidan (tryck på F5). 

-  Minska rund resan till Office 365 när det är möjligt. I stället för att bläddra igenom listor eller bibliotek kan du till exempel söka efter filer i ett stort bibliotek och filtrera i en lista för att få fram de resultat du vill. Du kan dessutom skapa vyer som minimerar sid inläsnings tid. Mer information finns i [hantera stora listor och bibliotek i Office 365](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784#BKMK_PAGES).

- Om video prestanda är dåligt kan du kanske Ladda ner videon och titta på den på enheten. En nedladdnings länk kan vara tillgänglig, eller så kan du högerklicka på video länken och välja **Spara mål som**.

 **Webbläsarbaserad**
  
Här är några förslag för din specifika webbläsare:
  
- **Internet Explorer** Uppgradera till Internet Explorer version 11 eller senare för att få avsevärda förbättringar av prestandan jämfört med tidigare versioner. Mer information finns i [fel söknings guide för Internet Explorer](https://support.microsoft.com/help/2437121/troubleshooting-guide-for-internet-explorer-when-you-access-office-365).

- **Firefox** Mer information finns i så här [fungerar Firefox långsamt eller slutar fungera](https://support.mozilla.org/products/firefox/fix-problems/slowness-or-hanging).

- **Safari** Mer information finns i [Apple-Safari](https://www.apple.com/safari/).

- **Chrome** Mer information finns i [Hjälp för Chrome](https://support.google.com/chrome/?hl=en).
  
## <a name="best-practices-for-using-outlook-and-outlook-web-app"></a>Metod tips för att använda Outlook och Outlook Web App

Att läsa, skriva och ordna e-post är en stor del av alla dagar. Både Outlook och Outlook Web App (OWA) ger stöd för offline-support. Att använda ett e-postprogram på din mobil telefon är ett annat användbart alternativ. Använd följande alternativ som bäst passar dina behov:
  
- Uppgradera till den senaste versionen av Outlook för att få avsevärda prestanda förbättringar jämfört med tidigare versioner. 

-  Med Outlook Web App kan du skapa offline-meddelanden, kontakter och Kalender händelser som laddas upp när OWA kan ansluta till Office 365. Mer information om hur du konfigurerar och använder OWA i offlineläge finns i [använda Outlook Web App offline](https://support.office.com/article/3214839c-0604-4162-8a97-6856b4c27b36).

- I Outlook kan du arbeta i cachelagrat läge där det automatiskt ansluter när så är möjligt. Du kan låta Outlook Ladda ner hela post lådan eller bara en del av den. Mer information finns i [Aktivera cachelagrat Exchange-läge](https://support.office.com/article/7885af08-9a60-4ec3-850a-e221c1ed0c1c) och [arbeta offline i Outlook](https://support.office.com/article/f3a1251c-6dd5-4208-aef9-7c8c9522d633).

- Outlook erbjuder också ett offline-läge. För att använda detta måste du först aktivera cachelagrat läge så att informationen från ditt konto kopieras till datorn. I offline-läge försöker Outlook ansluta med inställningarna för skicka och ta emot, eller när du har angett att det ska fungera online. Mer information finns i [arbeta offline för att undvika data anslutnings avgifter](https://support.office.com/article/827fe51f-5609-4062-82b4-3578057f9282), [ändra inställningar för skicka och ta emot när du arbetar offline](https://support.office.com/article/f681ec10-cb14-40cb-8709-1909a13c304a)och [Växla från att arbeta offline till online](https://support.office.com/article/2460e4a8-16c7-47fc-b204-b1549275aac9).

- Om du har en mobil telefon kan du använda den för att postsortering din e-post och kalender över operatörens nätverk.

> [!NOTE]
> Här är några råd om när du ska använda Outlook eller OWA. Om det inte finns något problem på din enhet finns det en fullständig uppsättning funktioner och det passar bäst för dig. Om disk utrymmet är ett problem på din enhet bör du överväga att använda OWA som har en delmängd funktioner men fungerar bäst på ett online-läge. Du kan naturligtvis använda det på grund av att de fungerar bra tillsammans.
  
## <a name="best-practices-for-using-onedrive-for-business"></a>Metod tips för att använda OneDrive för företag

OneDrive för företag är utformat för att arbeta med dina filer online och offline. När du har konfigurerat det sker synkronisering av ändringar automatiskt och tillförlitligt var och när du gör dem. Om nätverket är långsamt kan du arbeta med offline-versionen av filerna.
  
Synkroniseringsprogrammet för OneDrive för företag innehåller en SharePoint Online-eller Office 365 Business-prenumeration, eller så kan du [Ladda ner](https://support.microsoft.com/kb/2903984) OneDrive för företag-synkroniseringsprogrammet gratis. Det här programmet är också snabbare än att använda kommandona **Öppna i Utforskaren** och **Ladda upp** . Mer information finns i [Konfigurera datorn för att synkronisera dina OneDrive för företag-filer i Office 365](https://support.office.com/article/23e1f12b-d896-4cb1-a238-f91d19827a16).
  
Här är några ytterligare vägledningar för att använda synkroniseringsprogrammet för OneDrive för företag:
  
- Om du synkroniserar ett stort bibliotek för första gången ska du börja synkronisera under tiden, till exempel över natten.

- Du kan använda funktionen [stoppa synkronisering av ett bibliotek med appen OneDrive för företag](https://support.office.com/article/a7e41f1f-3a98-4ca7-9443-f10250688330) för att tillfälligt stoppa synkroniseringen av uppdateringar. Men Använd den här funktionen för korta perioder, till exempel ett par timmar i taget, för att undvika ett stort antal uppdateringar och för att minimera risken att slå samman konflikter om flera personer arbetar med samma dokument.
  
## <a name="best-practices-for-using-onenote"></a>Metod tips för att använda OneNote

Alla SharePoint-gruppwebbplatser har en inbyggd OneNote-anteckningsbok och du kan enkelt skapa din egen. OneNote är ett bra sätt att samla in information som du behöver varje dag för att få uppgifter gjorda. Många team använder till exempel OneNote som en samlings plats för vecko möten, projekt anteckningar, idéer, planer och status rapporter. Du kan strukturera denna information med hjälp av sidor, avsnitt och flikar.
  
Det fina med OneNote är att du kan komma åt innehållet från i stort sett vilken enhet som helst, oavsett om det är ett skriv bord, en bärbar dator, en surfplatta eller en mobil telefon. Men du behöver inte oroa dig för att spara eller synkronisera eftersom OneNote gör det åt dig.
  
Mer information finns i [Microsoft OneNote](https://office.microsoft.com/onenote).

## <a name="best-practices-for-using-skype-for-business-and-lync-online"></a>Metod tips för Skype för företag och Lync Online

Här följer allmänna rikt linjer för hur du använder Skype för företag eller Lync Online när nätverket är långsamt:

- Använd snabb meddelanden när du kan på ett långsamt nätverk.

- Undvik att ringa telefonsamtal via virtuella privata nätverk (VPN) eller RAS-anslutningar (fjärråtkomst).

- Kontrol lera att din ljuden het är godkänd. Mer information finns i [telefoner och enheter som är kvalificerade för Microsoft Lync](https://docs.microsoft.com/skypeforbusiness/lync-cert/ip-phones).

- När du använder PowerPoint i en onlinepresentation kan du minska storleken och komplexiteten för bilderna. Mer information finns i [tips om hur du förbättrar presentationens prestanda](https://support.office.com/article/34c82835-5f23-4bf0-98cc-72235bbd2949).

- Video prestanda är beroende av nätverks prestanda. Undvik att använda video om nätverket är långsamt.

Mer information finns i [dålig ljud-eller video kvalitet i Lync Online](https://support.microsoft.com/kb/2386655)eller så här [felsöker du anslutnings problem i Skype för företag](https://support.office.com/article/troubleshoot-connection-issues-in-skype-for-business-ca302828-783f-425c-bbe2-356348583771).
  
## <a name="best-practices-for-using-sharepoint-lists"></a>Metod tips för att använda SharePoint-listor

Att arbeta med listdata offline för att "svepa in", analysera eller rapportera data är ett bra sätt att minimera påverkan på långsamma nätverk. Du kan läsa och skriva de flesta listor från Microsoft Access 2019 och Microsoft Access 2016 genom att länka till dem. Du kan också exportera en lista till en Excel-tabell, som skapar en enkelriktad data anslutning mellan Excel-tabellen och listan. Lär dig hur du [arbetar offline med tabeller som är länkade till SharePoint-listor](https://support.office.com/article/work-offline-with-tables-that-are-linked-to-sharepoint-lists-5d66594a-6176-4a25-a198-320f13ccf41e).
  
Mer information finns i avsnittet "mer om hur du hanterar stora listor" i [hantera stora listor och bibliotek i Office 365](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784).
  
## <a name="best-practices-for-customizing-web-pages"></a>Metod tips för att anpassa webb sidor

När du anpassar en webb sida kan du oavsiktligt orsaka dålig prestanda på sidan. Ett antal faktorer kan påverka storleken på sidan, till exempel hur många webb delar som läggs till, hur många listor eller biblioteks objekt som visas först och hur du kodar sidan.
  
Mer information finns i [Justera SharePoint Online-prestanda](tune-sharepoint-online-performance.md).
  
## <a name="best-practices-for-using-project-online"></a>Metod tips för att använda Project Online

Följande rikt linjer kan förbättra nätverks prestanda.
  
- Project Online och SharePoint Online kräver synkronisering, vilket kan vara tidsödande. Om dina projekt grupper har en liten omsättning kan du inaktivera synkronisering av projekt webbplats för att förbättra prestandan för projekt publicering och projekt information. Begränsa Active Directory-synkronisering till grupper av resurser som faktiskt behöver använda systemet och övervaka eventuella eventuella behörighets problem efter synkroniseringen av stora grupper.

- Om din organisation använder Project-webbplatser kan du skapa dem på begäran istället för automatiskt. Detta påskyndar den första publicerings upplevelsen och undviker onödiga webbplatser och innehåll.

- Med projekt informations sidor (PDP) kan du utlösa en omberäkning av hela projektet och genomföra arbets flödes åtgärder, som båda kan vara prestanda intensiva. Undvik att utlösa två uppdaterings processer samtidigt på samma PDP genom att inte uppdatera kalender fälten (start datum, slutdatum, rapport datum och aktuellt datum) och icke-schemalagda fält (projekt namn, beskrivning och ägare).

- Minska antalet webb delar och anpassade fält som visas i varje PDP. Skapa en dedikerad PDP med bara fält som kräver uppdatering för att förbättra belastningen och spara tid.

- När du använder OData för rapportering kan du begränsa mängden data du frågar efter genom att använda Server filter.

Mer information finns i [Justera Project Online-prestanda](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c).
  
## <a name="whats-the-best-way-to-report-problems"></a>Vilket är det bästa sättet att rapportera problem?

Microsoft förbättrar kontinuerligt den allmänna prestandan hos Office 365 genom att övervaka nätverket, mäta bandbredd och fördröjning, öka sid inläsnings tiden, minska disk-I/O-omdesigna sidor för att använda minimal nedladdnings strategi, lägga till maskin vara i Data Center och lägga till fler data Center. Mer information om hur du kontrollerar aktuella status-och rapporterings problem finns i [så här kontrollerar du Office 365-tjänstens hälsa](view-service-health.md).
  
## <a name="see-also"></a>Se även

[Network planning and performance tuning for Office 365](network-planning-and-performance.md)
  
[Principer för nätverks anslutning för Office 365](microsoft-365-network-connectivity-principles.md)
  
[Hantera slut punkter för Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Vanliga frågor om Office 365-slut punkter](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
 
