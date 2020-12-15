---
title: Komma igång med att använda en ämnes upplevelse (för hands version)
description: Lär dig hur du gör för att få en ämnes upplevelse i din organisation.
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX
ms.openlocfilehash: 9709bec9b6e59ef05903f9c04909c796eb4127f4
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683467"
---
# <a name="get-started-driving-adoption-of-topic-experiences-preview"></a>Komma igång med att använda en ämnes upplevelse (för hands version)

> [!Note]
> Innehållet i den här artikeln gäller för projekt cortex privat för hands version. [Läs mer om Project Cortex](https://aka.ms/projectcortex).

Innan du börjar med att börja använda måste du förstå de koncept som ingår i kunskaps hantering och ämnen. Följande diagram visar vad som händer under identifiering och undersökning av ämnen:

![Ämnets arkitektur](../media/knowledge-management/topic-management-architecture.png)

- **Identifiering**: användarna kan upptäcka kunskaper i de program de använder varje dag genom ämnes kort – de kan också upptäcka ämnen i Microsoft Search.
- Undervisar **: ämnes** experter (SMF) förfina ämnen via ämnes sidor och AI får från deras inmatning. Ämnes Center innehåller ämnes sidor som användare kan utforska och experter kan hantera.
- **Identifiering**: med kunskap och personer i Microsoft Graph och artificiell intelligens (ämnen, färdigheter, så vidare) identifieras och ordnas automatiskt i närliggande ämnen. SharePoint-innehållet indexeras med säkerhets innehåll.
- **Tillägg**: med Microsoft Graph-innehåll (kommer snart) kan du skriva ut kunskap från externa tjänster och data databaser.

Om du vill ha mer information kan du läsa [översikten](knowledge-management-overview.md) för en introduktion.

Tänk på följande:

- Identifiering av avsnitt förbättras när det finns mer innehåll.
- Säkerhet, sekretess och plats för dina data bevaras även om informationen visas i en ny upplevelse.
- Användare behöver en licens för att kunna visa avsnitts upplevelser.
- Identifiering är inlednings vis på Engelskt språk innehåll.

För att förbereda dig kan du tänka igenom de här frågorna:

- Vilket innehåll ska användas för avsnitts identifiering?
- Vem ska hantera ämnen?
- Vem kommer att se ämnen och markeringar?
- Vilka ämnen förväntas?

Kontrol lera den här listan över förutsättningar för att få ut det mesta möjliga av ämnena:

|Produkt eller funktion |Beskrivning |
|:-------|:--------|
|SharePoint Online med moderna SharePoint-sidor |Avsnitts utvinning inkluderar bara innehåll på SharePoint-webbplatser, och ämnes kort kan bara visas på moderna sidor.|
|Microsoft Graph |Du kan styra om ämnen ska ingå eller uteslutas från sökning eller Delve med Microsoft Graph-inställningarna. |

## <a name="plan-for-adoption"></a>Abonnemang för antagande

För att planera för införande av avsnitts upplevelser måste du:

![Steg för att planera för antagandet](../media/knowledge-management/km-adoption-plan-adoption.png)

1. Planera tillvägagångs sätt och mål scenarier:
    - Tänk på hur du definierar och prioriterar [scenarier](#target-scenarios).
    - Tänk på vilka [intressenter](#identify-stakeholders) och projekt medlemmar du måste ha inblandade.  
    - Ta reda på vilken rörelse påverkan du vill ha och hur du kommer att [mäta framgång](#create-a-success-plan).

2. Engagera organisationen:
    - Identifiera de företags grupper och affärs team som måste vara inblandade och få justering av dem och de scenarier som du planerar.
    - Börja tänka på hur vissa tidiga antaganden kommer att få kritiskt, snabb feedback så att du kan iterera för att få den bästa lösningen.
    - Börja bygga gemenskapen och Tänk på hur olika ämnen kan användas i organisationen i de här grupperna.

3. Utbilda din organisation: de flesta kan förstå konceptet med ämnen och hur ämnes kort sammanfattar relevant information och förstå och se värdet. Men du kanske vill skapa utbildning som är skräddarsydda efter din egen kultur och organisation för att visa hur du vill att olika ämnen ska användas i organisationen. Några utbildnings resurser:
    - [Resurs Center för projekt cortex](https://aka.ms/projectcortex). Inkluderar översikter och funktions information, inspelade Office timme-videor och-presentationer samt information om partners och deras möjligheter.
    - Kommer snart, utbildnings video och hjälp till slutanvändare.

4. [Skapa ett mästare nätverk](#build-a-champion-network):
    - Du kanske har en community med olika övnings-eller mästare-nätverk. Det här är bra sätt att Socialize och evangelize och få kollegor att hjälpa dig. Och de kan dela med dig av framgång berättelser som kan vara mycket värdefulla. De kan ge råd och generera spänningen.

### <a name="target-scenarios"></a>Mål scenarier

Anledningen hjälper dig att avgöra vilken modell som behövs och hur du strukturerar din organisation baserat på var modellen ska användas. Här är några scenarier där kunskaps hanteringen kan hjälpa din organisation:

- Roll registrering & utbildning: det är viktigt att förstå en ny organisations terminologi, viktiga projekt och kulturen. Enkel identifiering av ämnen kan hjälpa nya anställda att komma igång snabbt med nya jobb, roller och projekt.
- Expertis och informations delning: när ämnen hanteras och delas kan folk i dina organisationer lättare hitta information och experter för att under lätta arbetet.
- Expanderat beslut som gör och förbättrar tiden för att marknadsföra: när det är lätt att nå information och experter kan du snabbt och Shave tid på projekt.

Här är ett scenario för roll registrering:

- En anställd (Jordanien) tar en ny roll eller har nyanställd och börjar med en roll. Jordanien vill vara inblandade och produktiva så snabbt som möjligt. Men Jordanien behöver också hjälp med att hitta en start plats.
- En kollega (Kim) som fanns i rollen innan ämnes sidorna i Jordanien har kunnat hjälpa nya anställda och alla andra som letar efter den informationen.
- Kim var ett litet företag och hade behörighet att titta på obekräftade ämnes sidor. Obekräftade ämnes sidor är fantastiska start punkter för vad AI har upptäckt och skapats och Kim kunde redigera dem för att lägga till expert resurser, definitioner och fästa andra resurser.
- När Jordanien läser genom ett nytt inlägg i SharePoint, ser Jordanien ett ämne med fokus och hovra över det för att snabbt få en definition av termen och vem du ska kontakta med fler frågor. Tidigare kan du ha varit tvungen att hitta dessa uppgifter och kontakta kollegor för att se vem du ska fråga om något.
- Att visa den här informationen genom avsnitts upplevelser kan vara kraftfullt, eftersom även om den här informationen kan vara tillgänglig förut kan den vara silod och svår att hitta. Att placera in det i de program som används av Jordanien och att hjälpa till att få dessa experter att hålla en uppfattning om engagemang och community. Det kan också hjälpa Jordanien att känna sig bättre när den nya rollen behandlas.

När du har identifierat dina scenarier kan du prioritera scenariot:

Ett sätt att prioritera det är att illustrera dina scenarier i ett rutnät som visar effekten jämfört med. Leta efter scenarier som har både hög effekt och är lätta att implementera. Gör dem till din högsta prioritet. Den låga effekten och svåra att implementera scenarier är din lägsta prioritet. När du har en snabb chans som är lätt att implementera är det enklare att genomföra scenariot, det hjälper folk att få glädje och se möjligheterna att använda ämnen.

![Hög påverkan, det är lätt att implementera scenarier med hög prioritet](../media/knowledge-management/topics-prioritize-scenarios.png)

Välj ett par viktiga scenarier att fokusera på från början, samar beta med dina tidiga efterföljare för att få lite feedback och sedan delta i faserna. På det sättet kan du iterera, göra förbättringar och få feedback så att du kan öka tiden. 

### <a name="identify-stakeholders"></a>Identifiera intressenter

Identifiera intressenterna för projektet. Viktiga roller är direktör, slutägare och representanter.

|Roll |Uppgifter |Department |
|:-------|:-------|:--------|
| Direktör (er)   | Kommunicerar visioner och-värden till företaget   |  Ledarskaps chef   |
| Projektets leads | Övervaka hela kör-och start processen | Projektledning |
| Kunskaps administratörer| Konfigurera och konfigurera avsnitts upplevelser | IT-avdelning |
| Kunskaps chefer | Hantera ämnen och övervaka taxonomin | Alla avdelningar |
| Kategoriserings chefer | Övervaka taxonomin | Alla avdelningar |
| Ämnes experter och ämnes deltagare | Skapa eller läsa ämnen och beskrivningar | Alla avdelningar |
| Representanter | Hjälp evangelize och hantering av objekt hantering | Alla avdelningar (personal) |
| Klient organisations administratör | Konfigurera inställningar för klient organisations nivå | IT-avdelning |
| Power Platform-administratör| Konfigurera gemensam data tjänst miljö | IT-avdelning |
| Sök efter administratör eller chef | Konfigurera Sök inställningar | IT-avdelning |

I en större organisation kanske du också har flera personer i de här rollerna, och du behöver driva en samordning mellan dem. I ett mindre företag kan en person utföra flera av dessa roller. Olika roller kanske är mer inblandade i de olika faserna i projektet. Vissa personer är bland annat inblandade i att konfigurera funktionerna (klient administratörer), medan andra inte är med i din början med att definiera ämnen malm kan delta i över gång (ämnes experter och representanter).
 
Även om vi rekommenderar att du har var och en av de här rollerna, kanske du inte behöver allt för att komma igång med din lösning.

### <a name="create-a-success-plan"></a>Skapa en lyckad plan

Använd dessa indikatorer för att mäta framgångar i din organisation. Titta på:

1. Ämnes användning:
      - Ämnena exponeringar
      - Antal ämnen – både bekräftade och obekräftade i den granskade ämnes listan.
      - Antal publicerade avsnitts sidor.
1. Slutanvändarens feedback från ämnes kort.
1. Gör enkäterna för anställda. Ämnena bör förbättra personalens förmåga att hitta information, så Sök efter olika sätt att samla in sina uppgifter och synpunkter.
1. Positiv effekt för Sök analys. Eftersom ämnena visas i Sök upplevelsen kan det vara enklare att hitta avbrutna sökningar eftersom det är lättare för fler än en sökning. 

### <a name="build-a-champion-network"></a>Skapa ett mästare nätverk

Skapa ett mästare nätverk i din organisation. Representanter är viktiga eftersom de kan:

- Skapa en cirkel av påverkan bland deras team
- Hantera hanteringen & underhåll

Du kan rekrytera representanter från olika roller – kunskaps chefer och experter.

Massor av mästare-nätverk använder Yammer som sin plattform. I Yammer kan folk posta frågor och få svar och dela med dig av framgång. Det är svårt att få ord ut fristående, så du kan lita på att ett nätverk i hela företaget ger råd om sina kollegor och visar hur deras team använder ämnen så att andra team kan tänka på sina egna scenarier.

I vissa organisationer används hackathons (formell eller informell, virtuell eller person) för att samla grupper av personer att arbeta med ett visst projekt. Du kan till exempel samla dina ämnes experter och låta dem samar beta för att granska en uppsättning ämnes sidor.

Tänk på hur du känner igen ditt representanter. Belöna sina aktiviteter, ge dem en viss igenkänning och skapa en synlig community-känsla så att de känner till att de är intressanta för något och att de också kommer tillbaka från det.

Nu när du är redo att sätta igång kan du se till att du håller på att främja pågående engagemang.

- Underhåll aktiva Yammer-grupper för din representanter.
- Dela med dig av framgång.
- Håll periodiska ytterligare åtagande händelser för att dela med dig av berättelser eller introducera nya funktioner.
- Ställ in utmaningar för folk och kör tävlingar.

## <a name="next-steps"></a>Nästa steg

När du är redo att ta del av ämnen måste du skaffa personer.

- Börja presentera funktionerna och få dem att tänka på deras scenarier.
- Samla intressenterna och skapa scenarier.
- Kör gemenskapen och Tänk igenom hur du ska delta.
- Slutför sedan förberedelse stegen. Vissa kan vara tekniska kunskaper och en del av företagets beredskap.
- Socialize och Höj dig.
