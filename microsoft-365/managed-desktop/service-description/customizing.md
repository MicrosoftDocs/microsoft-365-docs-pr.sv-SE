---
title: Undantag från serviceplanen
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: aca3bb6413aaab7620b1e1277c821a79dba4bb2f
ms.sourcegitcommit: 9083036e787cf997fbceb19c66af594d0fa81d0f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/13/2019
ms.locfileid: "42811496"
---
# <a name="exceptions-to-the-service-plan"></a>Undantag från serviceplanen

Microsoft Managed Desktop tillhandahåller en kurerad enhetslista, [standardenhetsinställningar,](device-policies.md)programkrav och vissa [konfigurerbara inställningar](../working-with-managed-desktop/config-setting-overview.md), alla utformade för att ge en säker, produktiv och trevlig upplevelse för slutanvändare. Det är bäst att alltid stanna med tjänsten som tillhandahålls. Vi inser dock att vissa detaljer om tjänsten kanske inte passar exakt med din organisations behov. Om du känner att du behöver ändra tjänsten på något sätt är det viktigt att du följer följande processer för att begära dessa ändringar.
 
## <a name="types-of-exceptions"></a>Typer av undantag

Ett undantag är ett tillägg eller en ändring av microsoft-baskonfigurationen för hanterade skrivbord. exempel sträcker sig från KONFIGURATION AV USB-portar till distribution av en ny drivrutin. Vi grupperar olika undantag enligt följande:

|Type (Typ)  |Beskrivning  |
|---------|---------|
|Programvara för produktivitet     |  Förgrundsprogram som behövs av slutanvändare, begränsas av [applikationskraven](mmd-app-requirements.md)       |
|Säkerhetsagenter & VPN     |  Programvara som används för att skydda, övervaka eller ändra enhetens eller nätverkets beteende       |
|Övervakning av digital erfarenhet     |  Programvara som används för att spåra data på en användares enhet för att rapportera till IT       |
|Drivrutiner för maskinvara eller programvara     |   Drivrutiner, begränsas av [programkraven](mmd-app-requirements.md)      |
|Politik     | Windows 10- eller Office 365 ProPlus-inställningar på en hanterad enhet        |
|Enheter     | Enheter som inte finns i [enhetslistan](device-list.md) för Microsoft Managed Desktop        |
|Andra     |  Allt som inte omfattas av de andra områdena       |
 
## <a name="request-an-exception"></a>Begär ett undantag

Skicka förfrågningar via Microsoft Managed Desktop Admin portalen genom att skapa en ändringsbegäran. Var noga med att inkludera dessa uppgifter:

-   Undantagstyp: Vilken kategori av undantag är det? (se föregående tabell)
-   Krav: Vad är det specifika affärskravet för undantaget?
-   Förslag: Vilken lösning är ditt företag begär?
-   Tidslinje: Hur länge vill du att det här undantaget ska pågå? 

## <a name="how-we-assess-an-exception-request"></a>Hur vi bedömer en undantagsbegäran

När vi granskar undantagsförfrågningar bedömer vi dessa faktorer i den här ordningen:
 
1.  Vissa program och principer som Microsoft Managed Desktop distribuerar till alla enheter kan inte överlåts, så din begäran får inte påverka dem. Mer information finns i [Enhetskonfiguration.](device-policies.md)
2.  Begränsad produktivitet programvara som krävs av en slutanvändare att göra sitt jobb kommer sannolikt att godkännas. 
3.  Om vi kan uppfylla dina krav med hjälp av Microsoft-teknik godkänner vi troligen din begäran om en undantagsmigremigningsperiod på tre till tolv månader (beroende på projektets omfattning).
4.  Om vi inte kan uppfylla dina krav med hjälp av Microsoft-teknik godkänner vi troligen din begäran om den inte bryter mot något av villkoren nedan.  

Dessa principer säkerställer att Microsoft Managed Desktop alltid kan uppfylla dina behov samtidigt som avvikelser från vår standardmall spåras. 

## <a name="key-conditions"></a>Viktiga villkor

Vi granskar undantag för att säkerställa att de inte bryter mot något av dessa villkor:

-   Ett undantag får inte påverka systemsäkerheten negativt. 
-   Om du behåller undantaget får det inte medföra någon betydande kostnad för antingen Microsoft Managed Desktop-åtgärder eller support.
-   Ett undantag får inte påverka systemstabiliteten, till exempel genom att orsaka att kernel-läge kraschar eller låser sig.
-   Ändringen får inte hindra oss från att driva tjänsten eller stå i konflikt med microsofts kärnteknik.

Dessa villkor kan komma att ändras i framtiden. Om vi gör sådana ändringar, kommer vi att ge 30 dagars varsel innan dessa villkor träder i kraft.  Om Microsoft Managed Desktop levererar ett alternativt sätt att uppfylla ett godkänt undantag meddelar Microsoft Managed Desktop kunden om Microsoft Managed Desktop ändrar sättet att stödja undantaget. 

## <a name="revoking-approval-for-an-exception"></a>Återkalla godkännande för ett undantag

När ett begärt undantag har godkänts och distribuerats är det möjligt att vi kan upptäcka problem som bryter mot de viktigaste villkoren som inte var uppenbara när vi godkände ändringen i första hand. I den här situationen kan vi behöva återkalla godkännandet för undantaget.
 
Om detta inträffar meddelar vi dig med hjälp av administratörsportalen för Microsoft Managed Desktop. Från första gången vi meddelar dig har du 90 dagar på dig att ta bort undantaget innan enheterna med undantaget inte längre är bundna av servicenivåavtal på Microsoft Managed Desktop. Vi skickar flera meddelanden enligt en strikt tidslinje , men en allvarlig incident eller ett allvarligt hot kan kräva att vi ändrar tidslinjen eller våra beslut om ett undantag. Vi tar inte *bort* ett undantag utan ditt medgivande, men alla enheter med återkallat undantag kommer inte längre att vara bundna av vårt servicenivåavtal. Här är tidslinjen för meddelanden som vi skickar dig:

- **Första meddelandet:** Vi meddelar det första meddelandet om vårt beslut att återkalla godkännandet, inklusive information om varför vi återkallar det, de åtgärder vi råder dig att vidta, tidsfristen för dessa åtgärder och åtgärder att följa om du vill överklaga beslutet. Detta är 90 dagar i förväg innan undantaget måste tas bort från alla enheter. 
- **Andra varsel (30 dagar senare):** Vi meddelar ett andra meddelande, inklusive samma information som finns i det första meddelandet. 
- **Tredje meddelandet (60 dagar efter det första meddelandet):** Vi lämnar ett tredje meddelande, inklusive samma information som lämnas i det första meddelandet. 
- **Slutligt meddelande (1 vecka före tidsfristen på 90 dagar):** Vi lämnar ett fjärde meddelande, inklusive samma information som lämnas i det första meddelandet.
- **90 dagar efter första varsel:** Microsoft Managed Desktop-servicenivåavtal gäller inte längre för alla enheter som har det återkallade undantaget. När som helst kan du bestrida beslutet och tillhandahålla ytterligare information för övervägande, inklusive uppgradering, konfigurationsändringar eller ändring av programvara. 


