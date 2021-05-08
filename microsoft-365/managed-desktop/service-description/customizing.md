---
title: Undantag från tjänstplanen
description: Så här begär du undantag från standardtjänstplanen
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 59a2b8227eb7e410ecf8506ce288978213537edc
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245522"
---
# <a name="exceptions-to-the-service-plan"></a>Undantag från tjänstplanen

Microsoft Hanterat skrivbord finns en anpassad enhetslista, [standardinställningar](device-policies.md)för enheter, [](../working-with-managed-desktop/config-setting-overview.md)programkrav och vissa konfigurerbara inställningar , allt utformat för att ge användarna en säker, produktiv och trevlig upplevelse. Det är bäst att alltid ha kvar tjänsten som den tillhandahålls. Men vi känner igen att viss information om tjänsten kanske inte exakt passar organisationens behov. Om du anser att du behöver ändra tjänsten på något sätt är det viktigt att du följer följande processer för att begära dessa ändringar.
 
## <a name="types-of-exceptions"></a>Typer av undantag

Ett undantag är alla tillägg eller ändringar i Microsoft Hanterat skrivbord baskonfiguration. Exempel kan vara allt från KONFIGURATION av USB-portar till distribution av en ny drivrutin. Vi grupperar olika undantag enligt följande:

|Typ  |Beskrivning  |
|---------|---------|
|Produktivitetsprogram     |  Förgrundsprogramvara som användare behöver, begränsad enligt [programkraven](mmd-app-requirements.md)       |
|Säkerhetsagenter & VPN     |  Programvara som används för att skydda, övervaka eller ändra enhetens eller nätverkets beteende       |
|Övervakning av digital upplevelse     |  Programvara som används för att spåra data på en användares enhet för att rapportera till IT       |
|Maskinvaru- eller programvarudrivrutiner     |   Drivrutiner, som begränsas av [programkraven](mmd-app-requirements.md)      |
|Principer     | Windows 10 eller Microsoft 365-appar för företag på en hanterad enhet        |
|Enheter     | Enheter som inte finns på [Microsoft Hanterat skrivbord-enhet](device-list.md)        |
|Annat     |  Allt som inte omfattas av andra områden       |
 
## <a name="request-an-exception"></a>Begära ett undantag

Skicka förfrågningar via Microsoft Hanterat skrivbord-administrationsportalen genom att skapa en ändringsförfrågan. Se till att ange följande information:

- Undantagstyp: Vilken undantagskategori är den? (se föregående tabell)
- Krav: Vad är det specifika affärskravet för undantaget?
- Förslag: Vilken lösning begär ditt företag?
- Tidslinje: Hur länge vill du att undantaget ska pågå? 

## <a name="how-we-assess-an-exception-request"></a>Så här gör vi för att bedöma en begäran om undantag

När vi granskar begäran om undantag bedömer vi dessa faktorer i följande ordning:
 
1. Vissa program och principer Microsoft Hanterat skrivbord distribuerar till alla enheter är inte negobara, så din begäran får inte påverka dem. Mer information [finns](device-policies.md) i Enhetskonfiguration.
2. Begränsad produktivitetsprogram som en användare behöver för att göra sitt jobb kommer sannolikt att godkännas. 
3. Om vi kan uppfylla dina krav med hjälp av Microsoft-teknik godkänner vi antagligen din begäran om en undantagsmigreringsperiod på tre till 12 månader (beroende på projektets omfattning).
4. Om vi inte uppfyller dina krav med hjälp av Microsoft-teknik godkänner vi din begäran såvida den inte strider mot något av villkoren nedan.  

De här principerna säkerställer Microsoft Hanterat skrivbord alltid kan uppfylla dina behov samtidigt som du spårar avvikelser från vår standardmall. 

## <a name="key-conditions"></a>Nyckelvillkor

Vi granskar undantag för att säkerställa att de inte bryter mot något av dessa villkor:

- Ett undantag får inte påverka systemsäkerhet negativt. 
- Att underhålla undantaget får inte medför en betydande kostnad för Microsoft Hanterat skrivbord åtgärder eller support.
- Ett undantag får inte påverka systemstabiliteten, till exempel genom att kernelläget kraschar eller hänger sig.
- Ändringen får inte hindra oss från att använda tjänsten eller vara i konflikt med Microsoft Hanterat skrivbord teknik.

Dessa villkor kan komma att ändras i framtiden. Om vi gör sådana ändringar kommer vi att tillhandahålla 30 dagars förvarning innan dessa villkor börjar gälla.  Om Microsoft Hanterat skrivbord levererar ett alternativt sätt att uppfylla ett godkänt undantag meddelar Microsoft Hanterat skrivbord kunden bör Microsoft Hanterat skrivbord på vilket sätt som stöd för undantaget ska användas. 

## <a name="revoking-approval-for-an-exception"></a>Återkalla godkännande av undantag

När ett begärt undantag har godkänts och distribuerats är det möjligt att vi kan upptäcka problem som bryter mot de nyckelvillkor som inte blev tydligt när vi godkänt ändringen från början. I det här fallet kan vi behöva återkalla godkännandet av undantaget.
 
Om det händer meddelar vi dig via administrationsportalen Microsoft Hanterat skrivbord. Första gången du meddelas har du 90 dagar på dig att ta bort undantaget innan enheterna med undantaget inte längre är bundna Microsoft Hanterat skrivbord av serviceavtal. Vi skickar flera meddelanden enligt en strikt tidslinje – men ett allvarligt incident eller hot kan innebära att vi måste ändra tidslinjen eller våra beslut om ett undantag. Vi tar inte bort *ett* undantag utan ditt medgivande, men alla enheter med ett återkallat undantag är inte längre bundna av vårt servicenivåavtal. Här är tidslinjen för meddelanden som vi skickar till dig:

- **Första meddelandet:** Vi lämnar ett första meddelande om vårt beslut att återkalla godkännandet, inklusive information om varför vi återkallar det, de åtgärder vi rekommenderar att du ska vidta, tidsgränsen för dessa åtgärder och åtgärder att följa om du vill tilltala beslutet. Det här meddelandet inträffar 90 dagar i förväg innan undantaget måste tas bort från alla enheter. 
- **Andra meddelandet (30 dagar senare):** Vi tillhandahåller ett andra meddelande, inklusive samma information som angavs i det första meddelandet. 
- **Tredje meddelandet (60 dagar efter det första meddelandet):** Vi tillhandahåller ett tredje meddelande, inklusive samma information som angavs i det första meddelandet. 
- **Sista meddelandet (en vecka före deadlinen på 90 dagar):** Vi tillhandahåller ett fjärde meddelande, inklusive samma information som angavs i det första meddelandet.
- **90 dagar efter det första meddelandet:** Microsoft Hanterat skrivbord servicenivåavtal gäller inte längre för enheter som har det återkallade undantaget. Du kan när som helst utmaninga beslutet och lämna ytterligare information för överväganden, inklusive uppgradering, konfigurationsändringar eller ändring av programvara. 


