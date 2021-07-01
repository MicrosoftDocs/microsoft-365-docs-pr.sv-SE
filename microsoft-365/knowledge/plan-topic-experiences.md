---
title: Planera för Microsoft Viva Topics
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Lär dig planera för Abonnemang på Microsoft Viva Topics
ms.openlocfilehash: a407fd6e6919c3b85235e317e5ed3ff103607700
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229545"
---
# <a name="plan-for-microsoft-viva-topics"></a>Planera för Microsoft Viva Topics

Du har kontroll över hur ämnen upplevs i organisationen. Dina planeringsbeslut för ämnen säkerställer att ämnen av hög kvalitet visas för användarna och att de har rätt behörighet att använda och bidra med kunskap.

I den här artikeln kommer vi att undersöka följande planeringsbeslut:

- Vilka SharePoint webbplatser du vill crawla efter ämnen
- Vilka ämnen, om det finns några, som du vill utesluta från ämnesupplevelser
- Vilka användare vill du göra ämnen synliga för
- Vilka användare som du vill ge behörighet att hantera ämnen i ämnescentret
- Vilka användare som du vill ge behörighet att skapa eller redigera ämnen i ämnescentret
- Vilket namn vill du ge ditt ämnescenter?

Säkerhet och sekretess för dina data respekteras och ämnesupplevelsen ger inte användarna ytterligare åtkomst till filer som de inte har rättigheter till. Vi rekommenderar att du även läser [Säkerhet och sekretess för Microsoft Viva Topics](topic-experiences-security-privacy.md) som en del av planeringsprocessen.

Mer information om AI-tekniken bakom Viva Topics finns [i Alexandria i Microsoft Viva Ämnen: från stora data till stora kunskaper](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge).

## <a name="requirements"></a>Krav

Du måste prenumerera [på Viva Topics](https://www.microsoft.com/microsoft-viva/topics) och vara global administratör SharePoint administratör för att få åtkomst Administrationscenter för Microsoft 365 och konfigurera Ämnen.

Alla användare som ska använda Ämnen kräver en **licens för ämnesupplevelser.** Tilldelning av licenser omfattas av [Konfigurera Microsoft Viva-ämnen.](set-up-topic-experiences.md)

## <a name="topic-discovery"></a>Upptäckt av ämne

Inställningarna för identifiering av ämne anger vilka SharePoint som används som källor för ämnen. Det inkluderar både klassiska och moderna webbplatser samt webbplatser som är associerade med Microsoft Teams och Microsoft 365 Groups. OneDrive-webbplatserna inte ingår.

Du kan välja att inkludera SharePoint webbplatser, en viss lista med webbplatser eller inga webbplatser. Vi rekommenderar att du väljer alla webbplatser så att ämnesupplevelsen kan upptäcka ett stort antal bra ämnen för användarna.

När du konfigurerade ämnen kan du välja bland följande alternativ:

- **Alla webbplatser:** alla SharePoint webbplatser i organisationen. Det omfattar nuvarande och framtida webbplatser.
- **Alla, förutom valda webbplatser:** Alla webbplatser utom de du anger. Webbplatser som skapas i framtiden kommer att ingå som källor för upptäckt av ämnen. 
- **Endast markerade webbplatser**: Endast de webbplatser som du anger. Webbplatser som skapas i framtiden inkluderas inte som källor för ämnesidentifiering.
- **Inga webbplatser**: Inkludera inte några SharePoint webbplatser.

Om du väljer **Alla, förutom valda webbplatser** eller Endast valda **webbplatser,** kan du ladda upp .csv en fil med en lista över webbplatser. De här alternativen är användbara om du kör ett pilottest och vill ta med ett begränsat antal webbplatser att börja med.

Du kan kopiera .csv nedan:

``` csv
Site name,URL
```

Vi rekommenderar inte att du väljer **Inga webbplatser eftersom** det förhindrar att ämnen skapas eller uppdateras automatiskt. Du kan dock välja det här alternativet om du vill konfigurera Ämnen och sedan lägga till webbplatser senare.

Vi rekommenderar att du skapar en process som användare eller kunskapshanterare kan begära att enskilda webbplatser tas bort från ämnesidentifiering om det behövs i organisationen.

### <a name="multi-geo"></a>Multi-geo

Om din organisation har [distribuerat Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)är ämnescentret etablerat på den centrala platsen och endast SharePoint-webbplatser på den centrala platsen är tillgängliga för användning som källor för ämnen. (Om du väljer **Alla webbplatser** används alla webbplatser i Viva Topics på den centrala platsen.)

All bearbetning och lagring av innehåll utförs på den centrala platsen.

## <a name="user-permissions"></a>Användarbehörigheter

De användarbehörigheter som du anger avgör vilka personer i organisationen som interagerar med ämnen och vad de kan göra.

> [!Note] 
> För stunden har Viva Topics inte stöd för att tillhandahålla licenser eller användarbehörigheter för gästanvändare (externa). 

*Hantera ämnen*

Kunskapschefer övervakar kvaliteten på informationen, hur den strukturerade och andra metodtips i din organisation. De kan bekräfta och avvisa ämnen.

Du kan ange enskilda ämneshanterare, men vi rekommenderar att du skapar en säkerhetsgrupp (eller använder en befintlig) som innehåller de personer som du vill ska vara kunskapshanterare. Du kan ange den här säkerhetsgruppen under installationen.

*Skapa och redigera ämnen*

Ämnesdeltagare är mästare och ämnesexperter i organisationen. De kan skapa och redigera ämnen. 

Vi rekommenderar att du låter alla i organisationen skapa och redigera ämnen eftersom ämnesupplevelsen fungerar bäst när alla användare kan dela information.

Om du vill begränsa skapandet och redigeringen av ämnen till specifika personer eller grupper, skapar du en säkerhetsgrupp för dem och anger den under installationen.

Du kan välja att inte tillåta någon att bidra till ämnen, men detta rekommenderas inte. Kunskapschefer kommer fortfarande att kunna redigera och skapa ämnen om du väljer det här alternativet.

*Ämnes läsare*

Ämneslyssarna kan se information på ämnessidor, i sökresultat och när ämnen markeras i innehållet SharePoint sidor. Användare kan bara se upptäckta ämnen när de har åtkomst till filer och sidor som ämnet identifierats i.

När du ställer in ämnes läsare kan du välja bland:

- **Alla i min organisation**
- **Endast valda personer eller säkerhetsgrupper**
- **Ingen**

Vi rekommenderar **Alla i min organisation,** men om du kör ett pilottest kan det vara bra att välja endast valda personer eller säkerhetsgrupper. Du kan också välja **Ingen om** du vill konfigurera Ämnen, men inte tillåta att andra ser ämnen ännu. (Knowledge Managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)

## <a name="knowledge-rules"></a>Kunskapsregler

Som administratör kan du utesluta vissa ämnen från olika ämnesupplevelser. Det här är användbart om du vill se till att känsliga data inte visas i avsnitt. Knowledge Managers kan utesluta ämnen i ämnescentret, men ämnen som utesluts av administratören är inte ens synliga för kunskapschefer. (Knowledge managers can also remove topics in the topic center after discovery.)

Om du vill utesluta ämnen på administratörsnivå måste du lägga till dem i .csv filen och ladda upp filen. Du kan göra detta under installationen eller senare.

Filen .csv måste innehålla följande parametrar:

- **Namn**: Skriv namnet på det ämne som du vill utesluta. Du kan göra det på två sätt:
- **MatchType-Exact/Partial**: Ange om namnet du angav var en *exakt eller* *delvis* matchningstyp.
    - Exakt matchning: Du kan ta med det exakta namnet eller förkortningen (till exempel *Contoso* eller *ATL*).
    - Delvis matchning: Du kan utesluta alla avsnitt som innehåller ett visst ord.  En båge *utesluter* till exempel  alla ämnen som innehåller ordet båge, t.ex. arcuscirkel,  *Arcus* arcus- eller *utbildningsbåge.* Observera att den inte exkluderar ämnen där texten ingår i ett ord, till exempel *Arkitektur.*
- **Står för (valfritt)**: (kallas även *expansion*) Om du vill utesluta en förkortning skriver du orden förkortningen står för.

    ![Utesluta ämnen i CSV-mallen](../media/exclude-topics-csv.png) 

Du kan kopiera CSV-mallen nedan:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a>Administration

När du ställer in Ämnen skapas ett ämnescenter automatiskt som en del av installationen. Fundera på vad du vill ge ämnescentret ett namn och vad du vill att URL-adressen ska vara. Du kan ange både namn och URL-adress som en del av installationsprocessen och du kan ändra namnet (men inte URL:en) senare i Administrationscenter för Microsoft 365. Du kan bara ha ett ämnescenter.

## <a name="setup-checklist"></a>Checklista för konfiguration

När du skapar ämnesupplevelser behöver du följande när du går igenom installationsguiden:

> [!div class="checklist"]
> * Lista över webbplatser som ska inkluderas eller uteslutas om de inte omfattar alla webbplatser för ämnesidentifiering
> * Säkerhetsgrupp för ämnesvyer om inte alla användare kan visa ämnen
> * Säkerhetsgrupp för ämnesdeltagare om inte alla användare kan skapa och redigera ämnen
> * Säkerhetsgrupp för ämneshanterare om inte alla användare får hantera ämnen
> * Lista över känsliga ämnen som ska undantas från ämnesidentifiering
> * Ett namn på webbplatsen för ämnescentret

## <a name="see-also"></a>Se även

[Konfigurera ämnesupplevelser](set-up-topic-experiences.md)

[Hantera ämnesidentifiering i Microsoft 365](topic-experiences-discovery.md)

[Hantera synligheten för ämnen i Microsoft 365](topic-experiences-knowledge-rules.md)

[Hantera ämnesbehörigheter i Microsoft 365](topic-experiences-user-permissions.md)

[Ändra namnet på ämnescentret i Microsoft 365](topic-experiences-administration.md)
