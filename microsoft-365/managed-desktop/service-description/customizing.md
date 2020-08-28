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
ms.openlocfilehash: 0785d7ac12c7b027322338d9949a10ea30168b3b
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289067"
---
# <a name="exceptions-to-the-service-plan"></a>Undantag från tjänstplanen

Microsoft Managed Desktop tillhandahåller en granskad enhets lista, standardinställningar för [enheter](device-policies.md), program krav och vissa [konfigurerbara inställningar](../working-with-managed-desktop/config-setting-overview.md), som är utformade för att tillhandahålla en säker, produktiv och Pleasant upplevelse för användare. Det är bäst att alltid vara med tjänsten enligt anvisningarna. Vi känner inte igen att viss information om tjänsten kanske inte passar exakt med organisationens behov. Om du tror att du behöver ändra tjänsten på något sätt är det viktigt att du följer följande processer för att begära dessa ändringar.
 
## <a name="types-of-exceptions"></a>Typer av undantag

Ett undantag är ett tillägg eller ändring till Microsoft Managed desktop base-konfigurationen. exempel intervall från USB-portars konfiguration för distribution av en ny driv rutin. Det följer med följande undantag:

|Type (Typ)  |Beskrivning  |
|---------|---------|
|Produktivitets program     |  Förgrunds program som behövs av användarna, begränsade enligt [program kraven](mmd-app-requirements.md)       |
|Säkerhets agenter & VPN     |  Program vara som används för att skydda, övervaka eller ändra enhetens eller nätverkets beteende       |
|Övervakning med digital upplevelse     |  Program vara som används för att spåra data på en användares enhet för att rapportera till den       |
|Maskinvaru-eller program varu driv rutiner     |   Driv rutiner, begränsade enligt [program kraven](mmd-app-requirements.md)      |
|Principerna     | Windows 10-eller Microsoft 365-appar för företags inställningar på en hanterad enhet        |
|Anordningar     | Enheter som inte är med i [listan](device-list.md) med hanterade Station ära datorer        |
|Annat     |  Något som inte täcks av de andra områdena       |
 
## <a name="request-an-exception"></a>Begära ett undantag

Skicka förfrågningar via administrations portalen för Microsoft Managed Desktop genom att skapa en ändringsbegäran. Se till att du inkluderar dessa uppgifter:

-   Undantags typ: vilken kategorin är den? (se föregående tabell)
-   Krav: Vad är det specifika företags behovet för undantaget?
-   Förslag: vilken lösning har du för företag?
-   Tids linje: hur länge vill du att detta undantag ska göras? 

## <a name="how-we-assess-an-exception-request"></a>Hur vi utvärderar en undantags förfrågan

När vi granskar undantags förfrågningar, bedömer vi dessa faktorer i följande ordning:
 
1.  Vissa program och principer som Microsoft Managed Desktop distribueras till för alla enheter inte är överlåtbara, så din begäran får inte påverka dem. Se [enhetens konfiguration](device-policies.md) för mer information.
2.  Begränsad produktivitet program vara som krävs av en användare ska kunna göra sitt jobb godkänt. 
3.  Om vi kan uppfylla ditt krav med hjälp av Microsoft-teknik kommer vi troligen att godkänna din begäran om en tids period på tre till tolv månader (beroende på projektets omfattning).
4.  Om vi inte kan uppfylla ditt krav med hjälp av Microsoft-teknik kommer vi antagligen att godkänna din begäran såvida den inte bryter mot något av villkoren nedan.  

Dessa principer garanterar att Microsoft Managed Desktop alltid uppfyller dina behov när du spårar avvikelser från vår standardmall. 

## <a name="key-conditions"></a>Huvud villkor

Vi granskar undantag för att säkerställa att de inte bryter mot något av dessa villkor:

-   Ett undantag får inte påverka systemsäkerheten. 
-   Underhåll av undantaget får inte medföra en betydande kostnad för antingen hanterad Microsoft-dator eller support.
-   Ett undantag får inte påverka systemets stabilitet, till exempel genom att kernel-läge kraschar eller hänger sig.
-   Ändringen får inte begränsa oss från att hantera tjänsten eller konflikten med grundläggande Microsoft hanterad Skriv bords teknik.

Dessa villkor kan ändras i framtiden. Om vi gör sådana ändringar får vi 30 dagars varsel innan dessa villkor träder i kraft.  Om Microsoft Managed Desktop levererar ett alternativt sätt att möta ett godkänt undantags fel kommer Microsoft Managed Desktop att meddela kunden att Microsoft Managed Desktop förändras på det sätt som stöds. 

## <a name="revoking-approval-for-an-exception"></a>Återkalla godkännandet för ett undantag

När ett begärt undantag är godkänt och distribuerat kan vi upptäcka problem som bryter mot de viktiga förhållanden som inte var uppenbart när vi godkände ändringen. I den här situationen kanske vi måste återkalla godkännandet för undantaget.
 
Om det sker meddelar vi dig med hjälp av Microsoft Managed Desktop admin-portalen. Från första gången vi meddelar dig har du 90 dagar på dig att ta bort undantaget innan de enheter som har undantaget inte längre är bundna av Microsoft Managed Desktop Service Level-avtal. Vi skickar flera meddelanden till dig enligt en strikt tids linje – en allvarlig händelse kan kräva att vi ändrar tids linjen eller våra beslut om ett undantag. Vi *tar inte bort* ett undantag utan ditt medgivande, men alla enheter med ett återkallat undantag kommer inte längre att vara bundna av vårt service nivå avtal. Här är tids linjen för meddelanden som vi skickar till dig:

- **Första omlägget:** Vi ger det första meddelandet i vårt beslut att återkalla godkännande, inklusive information om varför vi återkallar det, de åtgärder vi rekommenderar att du vidtar, deadline för dessa åtgärder och hur du följer om du vill överklaga beslutet. Det här är 90 dagar innan undantaget måste tas bort från alla enheter. 
- **Andra Förvarningen (30 dagar senare):** Vi tillhandahåller ett andra meddelande, inklusive informationen i det första meddelandet. 
- **Tredje meddelande (60 dagar efter första Förvarningen):** Vi tillhandahåller ett tredje meddelande, inklusive informationen i det första meddelandet. 
- **Slutligt meddelande (1 vecka före tids fri sten för 90 dagar):** Vi tillhandahåller ett fjärde meddelande, inklusive informationen i det första meddelandet.
- **90 dagar efter första Förvarningen:** Det går inte längre att använda Microsoft Managed Desktop service agreement för enheter som har återkallat undantag. Du kan när som helst utmana beslutet och ge ytterligare information för övervägande, inklusive uppgradering, konfigurations ändringar eller ändring av program vara. 


