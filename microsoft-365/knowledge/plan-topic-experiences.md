---
title: Planera ämnen i Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig hur du planerar för avsnitts upplevelser i Microsoft 365
ms.openlocfilehash: 153937cf6bc4a12f0a27866204b2286c343ddf55
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668338"
---
# <a name="plan-topic-experiences-in-microsoft-365"></a>Planera ämnen i Microsoft 365

Du har kontroll över hur ämnen finns i organisationen. Dina planerings beslut för avsnitts upplevelser säkerställer att de högkvalitativ avsnitten visas för användarna och att de har rätt behörighet att använda och bidra med kunskapen.

I den här artikeln ska vi undersöka dessa planerings beslut:

- Vilka SharePoint-webbplatser du vill crawla för avsnitt.
- Vilka ämnen, om det finns något, som du vill undanta från avsnitts upplevelser
- Vilka användare du vill göra ämnen synliga för.
- Vilka användare som du vill ge behörighet att hantera ämnen i ämnes centret.
- Vilka användare som du vill ge behörighet att skapa eller redigera ämnen i ämnes centret.
- Vilket namn du vill ge ditt ämnes Center.

Säkerhet och sekretess för dina data respekteras och ämnen som inte har rätt att få åtkomst till filer behålls inte. Vi rekommenderar också att du läser [avsnittet om säkerhet och sekretess](topic-experiences-security-privacy.md) i olika delar av planerings processen.

## <a name="requirements"></a>Krav

Du måste vara global administratör eller SharePoint-administratör för att få åtkomst till administrations centret för Microsoft 365 och konfigurera ämnen.

Alla användare som ska använda ämnes upplevelser kräver en licens för **ämnes upplevelser** . Att tilldela licenser beskrivs i [avsnittet Konfigurera ämnen](set-up-topic-experiences.md).

## <a name="topic-discovery"></a>Avsnitts identifiering

Identifieringen av ämnen anger vilka SharePoint-webbplatser som används som källor för avsnitt. Du kan välja att inkludera alla SharePoint-webbplatser, en specifik lista över webbplatser eller inga webbplatser. Vi rekommenderar att du väljer alla webbplatser så att ämnena kan upptäcka ett stort antal bra ämnen för dina användare.

När du ställer in ämnen kan du välja bland följande alternativ:

- **Alla webbplatser**: alla SharePoint-webbplatser i organisationen. Detta inkluderar aktuella och framtida webbplatser.
- **Alla, förutom utvalda webbplatser**: alla webbplatser förutom de som du anger. Webbplatser som skapats i framtiden tas med i källor för avsnitts identifiering. 
- **Endast valda webbplatser**: bara de webbplatser som du anger. Webbplatser som skapats i framtiden kommer inte att ingå som källor för identifiering av ämnen.
- **Inga webbplatser**: det finns inga SharePoint-webbplatser.

Om du väljer antingen **alla, förutom markerade webbplatser** eller **bara valda webbplatser**, kan du ladda upp en CSV-fil med en lista med webbplatser. Dessa alternativ är användbara om du utför en pilot och vill inkludera ett begränsat antal webbplatser att starta.

Du kan kopiera CSV-mallen nedan:

``` csv
Site name,URL
```

Vi rekommenderar inte att du väljer **några webbplatser** eftersom den förhindrar att ämnen skapas eller uppdateras automatiskt. Men du kan välja det här alternativet om du vill konfigurera ämnen och sedan lägga till webbplatser senare.

Vi rekommenderar att du skapar en process för användare eller kunskaps chefer för att begära att enskilda webbplatser tas bort från avsnitts identifiering om de behövs i organisationen.

## <a name="user-permissions"></a>Användar behörigheter

De användar behörigheter du anger avgör vilka personer i organisationen som interagerar med ämnen och vad de kan göra.

*Hantera ämnen*

Kunskaps cheferna övervakar informationen, hur de struktureras och andra metod tips i organisationen. De kan bekräfta och avvisa ämnen.

Du kan ange enskilda ämnes hanterare, men vi rekommenderar att du skapar en säkerhets grupp (eller använder en befintlig) som innehåller de personer som du vill ska vara kunskaps chefer. Du kan ange denna säkerhets grupp under inställnings processen.

*Skapa och redigera ämnen*

Ämnes deltagare är representanter och ämne experter i din organisation. De kan skapa och redigera ämnen. 

Vi rekommenderar att du gör det möjligt för alla i organisationen att skapa och redigera ämnen eftersom ämnet fungerar bäst när alla användare kan dela information.

Om du vill begränsa skapandet av och redigera ämnen för vissa personer eller grupper kan du skapa en säkerhets grupp för dem och ange den under konfigurations processen.

Du kan välja att inte tillåta att vem som helst bidrar till ämnen, men detta rekommenderas inte. Kunskaps cheferna kan fortfarande redigera och skapa avsnitt.

*Visnings program*

Avsnitts visnings program kan se information på ämnes sidor, i Sök Resultat och när ämnen markeras i innehållet som SharePoint-sidor. Användare kan bara se upptäckta ämnen när de har åtkomst till de filer och sidor som avsnittet upptäcktes i.

När du konfigurerar visnings program kan du välja mellan:

- **Alla i organisationen**
- **Endast valda personer eller säkerhets grupper**
- **Ingen**

Vi rekommenderar **alla i organisationen**, men om du gör en pilot kanske du vill välja bara utvalda personer eller säkerhets grupper. Du kan också välja **Nej** om du vill konfigurera ämnen, men inte tillåta att andra kan se ämnen ännu. (Kunskaps ansvariga har fortfarande åtkomst att tillåta att de kan läsa ämnen och hjälp med beslutet att göra avsnitts upplevelser mer tillgängliga.)

## <a name="knowledge-rules"></a>Kunskaps regler

Som administratör kan du exkludera vissa ämnen från ämnen. Det här är praktiskt om du vill förhindra att känsliga data visas i avsnitt. Även om kunskaps cheferna kan utesluta ämnen i ämnes centret är de avsnitt som inte är undantagna av administratören inte ens synliga för kunskaps cheferna. (Kunskaps chefer kan också ta bort ämnen i ämnes Center efter identifiering.)

Om du vill undanta ämnen på administratörs nivå måste du lägga till dem i en. csv-fil och ladda upp filen. Du kan göra det under installationen eller senare.

CSV-filen måste innehålla följande parametrar:

- **Namn**: Skriv namnet på det ämne som du vill undanta. Du kan göra det på två sätt:
- **MatchType-exakt/delvis**: Skriv om det namn du angav är en *exakt* eller *delvis* matchnings typ.
    - Exakt träff: du kan ange exakt namn eller akronym (till exempel *contoso* eller *ATL*).
    - Ofullständig matchning: du kan exkludera alla ämnen som har ett visst ord i det.  Till exempel kommer *bågen* att exkludera alla ämnen med ord *båge* i det, till exempel *båge cirkel*, *plasma båge svets* eller *tränings båge*. Observera att den inte utesluter ämnen där texten är inkluderad som en del av ett ord, till exempel *arkitekturen*.
- **Står för (valfritt)**: (kallas även för att *utöka*) om du vill undanta en akronym skriver du in de ord som akronym står för.

    ![Uteslut avsnitt i en CSV-mall](../media/exclude-topics-csv.png) 

Du kan kopiera CSV-mallen nedan:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a>Administration

När du ställer in ämnen som en del av inställningen skapas ett avsnitts Center automatiskt. Tänk på vad du vill namnge ämnes centret och vad du vill att URL-adressen ska vara. Du kan ange både namn och URL som en del av konfigurations processen och du kan ändra namnet (men inte URL) senare i administrations centret för Microsoft 365. Du kan bara ha ett ämnes Center.

## <a name="setup-checklist"></a>Check lista för inställningar

När du konfigurerar ämnen måste du ha följande objekt i installations guiden:

> [!div class="checklist"]
> * Lista över webbplatser att inkludera eller exkludera om de inte innehåller alla webbplatser för avsnitts identifiering
> * Säkerhets grupp för avsnitts läsare om du inte vill att alla användare ska kunna se ämnen
> * Säkerhets grupp för ämne deltagare om de inte tillåter alla användare att skapa och redigera ämnen
> * Säkerhets grupp för kunskaps chefer om du inte vill att alla användare ska kunna hantera ämnen
> * Lista över känsliga ämnen som ska undantas från identifiering av avsnitt
> * Ett namn på webbplatsen för ämnes Center

## <a name="see-also"></a>Se även

[Konfigurera ämnen](set-up-topic-experiences.md)

[Hantera identifiering av avsnitt i Microsoft 365](topic-experiences-discovery.md)

[Hantera ämnets synlighet i Microsoft 365](topic-experiences-knowledge-rules.md)

[Hantera behörigheter för ämne i Microsoft 365](topic-experiences-user-permissions.md)

[Ändra namnet på ämnes centret i Microsoft 365](topic-experiences-administration.md)
