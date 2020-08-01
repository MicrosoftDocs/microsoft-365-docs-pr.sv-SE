---
title: Undantag från tjänstplanen
description: ''
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 826710bf59acd88494adf1f154e5657d1e039af7
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529941"
---
# <a name="exceptions-to-the-service-plan"></a>Undantag från tjänstplanen

Microsoft Managed Desktop tillhandahåller en lista över kurerade enheter, [standardenhetsinställningar,](device-policies.md)programkrav och vissa [konfigurerbara inställningar](../working-with-managed-desktop/config-setting-overview.md), som alla är utformade för att ge slutanvändare en säker, produktiv och trevlig upplevelse. Det är bäst att alltid stanna med den service som tillhandahålls. Vi inser dock att vissa detaljer i tjänsten kanske inte passar exakt med organisationens behov. Om du känner att du behöver ändra tjänsten på något sätt är det viktigt att du följer följande processer för att begära dessa ändringar.
 
## <a name="types-of-exceptions"></a>Typer av undantag

Ett undantag är ett tillägg eller en ändring av microsofts baskonfiguration för hanterade skrivbord. exempel sträcker sig från USB-portars konfiguration till att distribuera en ny drivrutin. Vi grupperar olika undantag enligt följande:

|Type (Typ)  |Beskrivning  |
|---------|---------|
|Produktivitetsprogram     |  Förgrundsprogram som behövs av slutanvändare, begränsad av [applikationskraven](mmd-app-requirements.md)       |
|Säkerhetsagenter & VPN     |  Programvara som används för att skydda, övervaka eller ändra enhetens eller nätverkets beteende       |
|Övervakning av digital erfarenhet     |  Programvara som används för att spåra data på en användares enhet för att rapportera till IT       |
|Drivrutiner för maskinvara eller programvara     |   Drivrutiner, begränsade av [applikationskraven](mmd-app-requirements.md)      |
|Politik     | Windows 10- eller Microsoft 365 Apps för företagsinställningar på en hanterad enhet        |
|Enheter     | Enheter som inte finns med i [listan över](device-list.md) hanterade skrivbord i Microsoft        |
|Annat     |  Allt som inte omfattas av de andra områdena       |
 
## <a name="request-an-exception"></a>Begär ett undantag

Skicka begäranden via Microsoft Managed Desktop Admin-portalen genom att skapa en ändringsbegäran. Var noga med att inkludera dessa uppgifter:

-   Undantagstyp: Vilken kategori av undantag är det? (se föregående tabell)
-   Krav: Vad är det specifika affärskravet för undantaget?
-   Förslag: Vilken lösning begär ditt företag?
-   Tidslinje: Hur länge vill du att undantaget ska vara? 

## <a name="how-we-assess-an-exception-request"></a>Hur vi bedömer en undantagsbegäran

När vi granskar undantagsförfrågningar bedömer vi dessa faktorer i den här ordningen:
 
1.  Vissa program och principer som Microsoft Managed Desktop distribuerar till alla enheter är inte förhandlingsbara, så din begäran får inte påverka dem. Mer information finns i [Enhetskonfiguration.](device-policies.md)
2.  Begränsad produktivitet programvara som krävs av en slutanvändare att göra sitt jobb kommer sannolikt att godkännas. 
3.  Om vi kan uppfylla dina krav med hjälp av Microsoft-teknik godkänner vi troligen din begäran om en undantagsmigreringsperiod på tre till tolv månader (beroende på projektets omfattning).
4.  Om vi inte kan uppfylla dina krav med hjälp av Microsoft-teknik godkänner vi sannolikt din begäran om den inte bryter mot något av villkoren nedan.  

Dessa principer säkerställer att Microsoft Managed Desktop alltid kan uppfylla dina behov samtidigt som du spårar avvikelser från vår standardmall. 

## <a name="key-conditions"></a>Viktiga villkor

Vi granskar undantag för att säkerställa att de inte bryter mot något av dessa villkor:

-   Ett undantag får inte påverka systemsäkerheten negativt. 
-   Om du underhåller undantaget får det inte medföra någon betydande kostnad för antingen Microsoft Managed Desktop-åtgärder eller support.
-   Ett undantag får inte påverka systemets stabilitet, till exempel genom att orsaka att kernel-läge kraschar eller hängs.
-   Ändringen får inte hindra oss från att använda tjänsten eller stå i konflikt med microsofts kärnteknik för hanterade datorer.

Dessa villkor kan förändras i framtiden. Om vi gör sådana ändringar kommer vi att ge 30 dagars varsel innan dessa villkor träder i kraft.  Om Microsoft Managed Desktop tillhandahåller ett alternativt sätt att uppfylla ett godkänt undantag meddelar Microsoft Managed Desktop kunden om Microsoft Managed Desktop ändrar vägen för att stödja undantaget. 

## <a name="revoking-approval-for-an-exception"></a>Återkalla godkännande för ett undantag

När ett begärt undantag har godkänts och distribuerats är det möjligt att vi kan upptäcka problem som bryter mot de viktiga villkoren som inte var uppenbara när vi godkände ändringen från början. I det här fallet kan vi behöva återkalla godkännande för undantaget.
 
Om detta inträffar meddelar vi dig med hjälp av administrationsportalen för Hanterade skrivbord. Från första gången vi meddelar dig har du 90 dagar på dig att ta bort undantaget innan enheterna med undantag inte längre är bundna av Microsoft Managed Desktop-servicenivåavtal. Vi skickar flera meddelanden till dig enligt en strikt tidslinje – men en allvarlig incident eller ett allvarligt hot kan kräva att vi ändrar tidslinjen eller våra beslut om ett undantag. Vi tar inte *bort* ett undantag utan ditt medgivande, men alla enheter med återkallat undantag är inte längre bundna av vårt servicenivåavtal. Här är tidslinjen för meddelanden som vi kommer att skicka dig:

- **Första meddelandet:** Vi tillhandahåller det första meddelandet om vårt beslut att återkalla godkännandet, inklusive information om varför vi återkallar det, de åtgärder vi råder dig att vidta, tidsfristen för dessa åtgärder och åtgärder att följa om du vill överklaga beslutet. Detta är 90 dagar i förväg innan undantaget måste tas bort från alla enheter. 
- **Andra varsel (30 dagar senare):** Vi lämnar ett andra meddelande, inklusive samma information som lämnas i det första meddelandet. 
- **Tredje varsel (60 dagar efter det första meddelandet):** Vi lämnar ett tredje meddelande, inklusive samma information som lämnas i det första meddelandet. 
- **Slutligt meddelande (1 vecka före tidsfristen på 90 dagar):** Vi lämnar ett fjärde meddelande, inklusive samma information som lämnas i det första meddelandet.
- **90 dagar efter första varsel:** Servicenivåavtal för Microsoft Managed Desktop gäller inte längre för alla enheter som har det återkallade undantaget. Du kan när som helst överklaga beslutet och tillhandahålla ytterligare information för övervägande, inklusive uppgradering, konfigurationsändringar eller ändring av programvara. 


