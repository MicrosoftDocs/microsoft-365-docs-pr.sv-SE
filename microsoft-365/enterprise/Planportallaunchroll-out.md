---
title: Planera hur portalen ska lanseras i SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: I den här artikeln beskrivs hur du kan planera din portal start i SharePoint Online och vilka åtgärder som ska vidtas för en lyckad start
ms.openlocfilehash: e22fa4d9cbfed79841d844f111e3eb91a708512e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694901"
---
# <a name="planning-your-portal-launch-roll-out-plan-in-sharepoint-online"></a>Planera hur portalen ska lanseras i SharePoint Online

En portal är en SharePoint-webbplats på ditt intranät som har ett stort antal webbplats läsare som använder innehåll på webbplatsen. I stora organisationer kan det finnas flera av dessa; till exempel en företags Portal och en HR-Portal. Vanligt vis har portarna relativt par personer som skapar och redigerar webbplatsen och dess innehåll. De flesta besökare på portalen läser och konsumerar bara innehållet.

I den här artikeln beskrivs hur du planerar distributionen och distributions planen till SharePoint Online. Det finns också tillvägagångs sätt för att följa traditionella inläsnings testning för SharePoint Online. SharePoint Online är en moln tjänst och lastens kapacitet, hälsa och total belastning i tjänsten hanteras av Microsoft.

Om du vill ha hjälp med att skapa en lyckad Portal följer du de grundläggande principerna, metoderna och rekommendationerna i [skapa, lansera och underhålla en felfri Portal](https://go.microsoft.com/fwlink/?linkid=2105838) 

Distributions tillvägagångs sätt är markerat nedan.

## <a name="overview-of-capacity-planning-in-sharepoint-online"></a>Översikt över kapacitets planering i SharePoint Online
För att effektivt utnyttja kapaciteten och för att hantera oväntad tillväxt är vi automatiserade och kan spåra vissa användnings scenarier i alla grupper. När exakt tillväxt inte är oförutsägbart för någon klient organisation i en Server grupp, är det förutsägbart att en sammanlagd summa begärs över tiden. Genom att identifiera tillväxt trenderna i SharePoint Online kan vi planera för framtida utbyggnad. Mer information om [kapacitets planering och belastnings testning av SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md).

En viktig del av en lyckad start är "Wave" eller "stegvis Sammanfattning"-metoden. 

## <a name="can-i-load-test-sharepoint-online"></a>Kan jag ladda testa SharePoint Online?
SharePoint Online är en delad miljö med flera innehavare som är bal anse rad mellan anläggningar och skala, och den behandlas fort löp ande. Ladda test en miljö, till exempel SharePoint Online, vars skalnings ändringar kontinuerligt ger ett oväntat resultat, men det är inte tillåtet. 

Läs mer:  [kapacitets planering och belastnings testning av SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)

## <a name="optimize-pages-by-following-recommended-guidelines"></a>Optimera sidor genom att följa rekommenderade rikt linjer
Sidor från en lokal distribution bör inte bara flyttas när de är på SharePoint Online utan att granska dem mot rekommenderade regler för SharePoint Online. Det bästa är att alltid optimera start sidan för alla webbplatser eller portaler i SharePoint, eftersom det är den plats där de flesta användare i organisationen kommer att komma åt som start punkt för webbplatsen.

Några grundläggande faktorer bör övervägas:
- Lokala installationer kan utnyttjas på traditionella serverbaserade cacheminnen, till exempel objektcache, utdatacache och BLOB-cachen. Med skillnader i miljön i molnet är de här alternativen inte nödvändigt vis tillgängliga som skir-skillnader gör dem mindre förmånliga.
- Alla sidor/funktioner/anpassningar som används för moln förbrukning bör optimeras för högre latens och andra användares fördelade enheter, så att användare i olika områden eller regioner har en mer enhetlig upplevelse. Cloud erbjuder optimeringar som innehålls leverans nätverk (CDN) för att optimera för en distribuerad användar bas samt för moderna SharePoint-användning används av våra LKG-webbdelar (OOTB).

### <a name="what-to-do"></a>Vad kan jag göra:
 - För alla webbplats sidor i SharePoint Online används [verktyget Nätverksdiagnostik](https://aka.ms/perftool), som är ett krom tillägg som hjälper dig att analysera och tillhandahålla vägledning. Den kan användas av webbplats ägare, redigerare, administratörer och utvecklare eftersom den är utformad för att vara en utgångs punkt för analys och optimering.
 - Utvecklare bör också använda utvecklingsverktyg som F12-verktyg för utvecklare och CTRL-F12 i webbläsaren på moderna sidor. [/Fiddler-loggar](https://www.telerik.com/download/fiddler) kan också användas för att granska storleks vikten (hur stor sidan är i MB) på sidan och antalet samtal och element som påverkar den övergripande sid inläsningen. 

Det här avsnittet var en kort sammanfattning av hur du optimerar sidor.  Mer information finns i:  [skapa, starta och underhålla en felfri Portal](https://go.microsoft.com/fwlink/?linkid=2105838).

## <a name="follow-a-wave--phased-roll-out-approach"></a>Följ en nedrullningsbar metod med våg-och mellanliggande ljud
Den traditionella omfattande utrops-metoden för webbplats lanseringar tillåter inte verifiering att anpassningar, externa källor, tjänster eller processer har testats på rätt sätt. Det innebär inte att det tar några månader att starta, men det rekommenderas till minst flera dagar beroende på organisationens storlek. Om du följer ett abonnemang för en våg kan du välja att pausa och lösa problem innan du fortsätter med nästa fas och därmed sänka det potentiella antalet användare som påverkas av eventuella problem. SharePoint som tjänst förlänger din kapacitet baserat på användning och förväntad användning och vi behöver inte meddela oss om din start, följ rikt linjerna för att säkerställa framgång.
  
Som du ser i följande bild är antalet inbjudna användare betydligt högre än de som faktiskt använder webbplatsen. Den här bilden visar en strategi för hur du ska lansera en version. Med den här metoden kan du identifiera olika sätt att förbättra SharePoint-webbplatsen innan de flesta användare ser den.
  
![Diagram som visar inbjudna och aktiva användare](../media/0bc14a20-9420-4986-b9b9-fbcd2c6e0fb9.png)
  
I pilot fasen är det bra att få feedback från användare om att organisationen litar på och vet att det kommer att vara. På det sättet är det möjligt att mäta hur systemet används, samt hur det fungerar.
  
Under varje vågor kan du samla in feedback om användare kring funktionerna samt prestanda under varje enskild installation. Det här är fördelen med att vi saktar fram systemet och gör förbättringar när systemet får mer användning. Det gör det också möjligt för oss att reagera på den ökade belastningen när webbplatsen är uppkopplad till fler och fler användare och kombinerat med hjälp av rikt linjerna för sid optimering säkerställer en positiv upplevelse för dina användare.

### <a name="what-to-do"></a>Vad kan jag göra:
- Bestäm tiden för varje fas och kontrol lera att du har en beredskaps-eller paus möjlighet, om du behöver göra ändringar innan du fortsätter
- Planera den första gruppen av användare som du vill aktivera för att se till att du får feedback som du måste gå vidare. Det innebär att om möjligt kan du välja en aktiv grupp med användare som ska ge feedback i tid
- När du planerar varje våg kan du pröva och börja med en liten användar bas (färre än 5000 användare) och sedan öka grupp storleken allteftersom du fortsätter med varje våg. Det gör att du kan skapa en successiv metod och gör det enklare att pausa möjligheter.
