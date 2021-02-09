---
title: Planera för Microsoft Viva-ämnen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Läs om hur du planerar för Microsoft Viva-ämnen
ms.openlocfilehash: 2f7b85399f0b1f49e25aae1f1d4627413594f618
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150484"
---
# <a name="plan-for-microsoft-viva-topics"></a>Planera för Microsoft Viva-ämnen

Du har kontroll över hur ämnen upplevs i organisationen. Ditt planeringsbeslut för ämnen säkerställer att ämnen av hög kvalitet visas för användarna och att de har rätt behörighet att använda och bidra med kunskap.

I den här artikeln undersöker vi de här planeringsbesluten:

- Vilka SharePoint-webbplatser du vill crawla för ämnen
- Vilka ämnen, om det finns några, som du vill utesluta från ämnesupplevelser
- Vilka användare vill du göra ämnen synliga för
- Vilka användare som du vill ge behörighet till att hantera ämnen i ämnescentret
- Vilka användare som du vill ge behörighet att skapa eller redigera ämnen i ämnescentret
- Vilket namn vill du ge ämnescentret?

Säkerheten och sekretessen för dina data respekteras och ämnesupplevelsen ger inte användarna ytterligare åtkomst till filer som de inte har rättigheter till. Vi rekommenderar att du även läser [säkerhet och sekretess i Microsoft Viva Topics som](topic-experiences-security-privacy.md) en del av planeringsprocessen.

## <a name="requirements"></a>Krav

Du måste prenumerera [på Viva Topics](https://www.microsoft.com/microsoft-viva/topics) och vara global administratör eller SharePoint-administratör för att få åtkomst till administrationscentret för Microsoft 365 och konfigurera ämnen.

Alla användare som kommer att använda Ämnen kräver en **licens för ämnesupplevelser.** Tilldelning av licenser omfattas av [Konfigurera Microsoft Viva-ämnen.](set-up-topic-experiences.md)

## <a name="topic-discovery"></a>Upptäckt av ämne

I inställningarna för identifiering av ämnen anges vilka SharePoint-webbplatser som används som källor för ämnen. Du kan välja att ta med alla SharePoint-webbplatser, en specifik lista med webbplatser eller inga webbplatser. Vi rekommenderar att du väljer alla webbplatser så att ämnesupplevelsen kan upptäcka ett stort antal bra ämnen för användarna.

När du ställer in ämnen kan du välja bland följande alternativ:

- **Alla webbplatser:** Alla SharePoint-webbplatser i organisationen. Det omfattar aktuella och framtida webbplatser.
- **Alla, förutom valda webbplatser:** Alla webbplatser utom de du anger. Webbplatser som skapas i framtiden kommer att ingå som källor för ämnesidentifiering. 
- **Endast valda webbplatser**: Endast de webbplatser som du anger. Webbplatser som skapas i framtiden kommer inte att inkluderas som källor för identifiering av ämnen.
- **Inga webbplatser:** Inkludera inte några SharePoint-webbplatser.

Om du väljer **Alla, förutom valda webbplatser** **eller** Endast valda webbplatser, kan du ladda upp en CSV-fil med en lista över webbplatser. De här alternativen är användbara om du kör en pilot och vill ta med ett begränsat antal webbplatser att börja med.

Du kan kopiera CSV-mallen nedan:

``` csv
Site name,URL
```

Vi rekommenderar inte att du väljer **Inga webbplatser eftersom** det förhindrar att ämnen skapas eller uppdateras automatiskt. Du kan dock välja det här alternativet om du vill konfigurera Ämnen och sedan lägga till webbplatser senare.

Vi rekommenderar att du skapar en process som användare eller kunskapshanterare kan begära att enskilda webbplatser tas bort från ämnesidentifiering om det behövs i organisationen.

## <a name="user-permissions"></a>Användarbehörigheter

De användarbehörigheter som du anger avgör vilka personer i organisationen som interagerar med ämnen och vad de kan göra.

*Hantera ämnen*

Kunskapshanterare övervakar kvaliteten på informationen, hur den är strukturerad och andra metodtips i organisationen. De kan bekräfta och avvisa ämnen.

Du kan ange enskilda ämneshanterare, men vi rekommenderar att du skapar en säkerhetsgrupp (eller använder en befintlig) som innehåller de personer som du vill ska vara kunskapshanterare. Du kan ange den här säkerhetsgruppen under installationen.

*Skapa och redigera ämnen*

Ämnesdeltagare är mästare och ämnesexperter i organisationen. De kan skapa och redigera ämnen. 

Vi rekommenderar att du låter alla i organisationen skapa och redigera ämnen eftersom ämnesupplevelsen fungerar bäst när alla användare kan dela information.

Om du vill begränsa skapandet och redigeringen av ämnen till specifika personer eller grupper, skapar du en säkerhetsgrupp för dem och anger den under installationen.

Du kan välja att inte tillåta att någon bidrar till ämnen, men det rekommenderas inte. Kunskapschefer kommer fortfarande att kunna redigera och skapa ämnen om du väljer det här alternativet.

*Ämnes läsare*

Ämnes läsare kan se information på ämnessidor, i sökresultat och när ämnen markeras i innehåll som SharePoint-sidor. Användare kan bara se upptäckta ämnen när de har åtkomst till filer och sidor som ämnet identifierats i.

När du inställningar för ämnes läsare kan du välja bland:

- **Alla i min organisation**
- **Endast valda personer eller säkerhetsgrupper**
- **Ingen**

Vi rekommenderar **Alla i min organisation,** men om du kör ett pilottest kanske du bara vill välja valda personer eller säkerhetsgrupper. Du kan också välja **Ingen om** du vill konfigurera Ämnen, men inte tillåta att andra ser ämnen ännu. (Kunskapshanterare har fortfarande åtkomst till att visa ämnen och hjälpa till med beslutet att göra ämnen allmänt tillgängliga.)

## <a name="knowledge-rules"></a>Kunskapsregler

Som administratör kan du utesluta vissa ämnen från ämnesupplevelser. Det är användbart om du vill se till att känsliga data inte visas i avsnitten. Knowledge Managers kan utesluta ämnen i ämnescentret, men ämnen som utesluts av administratören är inte ens synliga för kunskapschefer. (Knowledge Managers kan också ta bort ämnen i ämnescentret efter upptäckten.)

Om du vill utesluta ämnen på administratörsnivå måste du lägga till dem i en CSV-fil och ladda upp filen. Det kan du göra under installationen eller senare.

CSV-filen måste innehålla följande parametrar:

- **Namn:** Skriv namnet på det ämne som du vill utesluta. Du kan göra det på två sätt:
- **MatchType-Exact/Partial:** Ange om namnet du angav var en *exakt eller* *delvis* matchningstyp.
    - Exakt matchning: Du kan ta med det exakta namnet eller förkortningen (till exempel *Contoso* eller *ATL).*
    - Delvis matchning: Du kan utesluta alla ämnen som innehåller ett visst ord.  En båge *utesluter* till exempel  alla ämnen där ordet båge finns, t.ex. arcuscirkel, arcus-arcus- eller *utbildningsbåge.*  Observera att den inte exkluderar ämnen där texten ingår som en del av ett ord, till exempel *arkitektur.*
- **Står för (valfritt)**: (Kallas även *expansion)* Om du vill utesluta en förkortning skriver du orden som förkortningen står för.

    ![Utesluta ämnen i CSV-mall](../media/exclude-topics-csv.png) 

Du kan kopiera CSV-mallen nedan:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a>Administration

När du ställer in ämnen, som en del av installationsprocessen, skapas ett ämnescenter automatiskt. Fundera på vad du vill ge ämnescentret och vad du vill att URL-adressen ska vara. Du kan ange både namn och URL som en del av installationsprocessen och du kan ändra namn (men inte URL) senare i administrationscentret för Microsoft 365. Du kan bara ha ett ämnescenter.

## <a name="setup-checklist"></a>Checklista för installation

När du skapar ämnesupplevelser behöver du följande när du går igenom installationsguiden:

> [!div class="checklist"]
> * Lista över webbplatser som ska inkluderas eller undantas om de inte inkluderar alla webbplatser för identifiering av ämnen
> * Säkerhetsgrupp för ämnesvisningsprogram om inte alla användare kan visa ämnen
> * Säkerhetsgrupp för ämnesdeltagare om inte alla användare kan skapa och redigera ämnen
> * Säkerhetsgrupp för ämneskunskapershanterare om de inte tillåter att alla användare hanterar ämnen
> * Lista över känsliga ämnen som inte ska upptäckas
> * Ett namn på ämnescenterwebbplatsen

## <a name="see-also"></a>Se även

[Konfigurera ämnesupplevelser](set-up-topic-experiences.md)

[Hantera identifiering av ämnen i Microsoft 365](topic-experiences-discovery.md)

[Hantera synlighet för ämnen i Microsoft 365](topic-experiences-knowledge-rules.md)

[Hantera ämnesbehörigheter i Microsoft 365](topic-experiences-user-permissions.md)

[Ändra namnet på ämnescentret i Microsoft 365](topic-experiences-administration.md)
