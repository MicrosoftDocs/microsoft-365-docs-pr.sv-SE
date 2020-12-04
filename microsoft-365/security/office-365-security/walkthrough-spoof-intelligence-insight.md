---
title: Genom gång – Insight-inblick
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur inblicken med förfalsknings information fungerar. De kan snabbt avgöra vilka avsändare som skickar e-post till sina organisationer från domäner som inte klarar e-postauktorisering (SPF, DKIM eller DMARC).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6f5ebd0fd42d17354eeb1e03c946ac5446c3667c
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572747"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>Genom gång-inblick i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I Microsoft 365-organisationer med Defender för Office 365 kan du använda falsk IT-insyn för att snabbt avgöra vilka avsändare som skickar e-postautentisering på ett legitimt sätt.

Genom att tillåta att kända avsändare skickar falska meddelanden från kända platser kan du minska falska positiva (god e-post som är markerad som dålig). Genom att övervaka tillåtna avsändare tillhandahåller du ett ytterligare säkerhets skikt för att förhindra att osäkra meddelanden kommer in i organisationen.

Mer information om rapporter och insikter finns i [rapporter och insikter i avsnittet om säkerhets & efterlevnad](reports-and-insights-in-security-and-compliance.md).

Den här genom gången är en av flera för säkerhets & Compliance Center. Information om hur du navigerar i rapporter och insikter finns i avsnittet [Närliggande information](#related-topics) .

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. För att gå direkt till sidan **säkerhets instrument panel** <https://protection.office.com/searchandinvestigation/dashboard> .

  Du kan visa inblick från fler än en instrument panel i säkerhets & Compliance Center. Oavsett vilken instrument panel du tittar på, ger inblicken samma uppgifter och gör att du snabbt kan utföra samma uppgifter.

- Du måste tilldelas behörigheter i säkerhets & Compliance Center innan du kan göra det i den här artikeln:
  - **Organisationshantering**
  - **Säkerhets administratör**
  - **Säkerhets läsare**
  - **Global läsare**

  **Obs!** när du lägger till användare i motsvarande Azure Active Directory-roll i Microsoft 365 Admin Center får användarna den behörighet som krävs för säkerhets & efterlevnad Center _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

- Du aktiverar och inaktiverar förfalsknings intelligens i policy mot nätfiske i Microsoft Defender för Office 365. Mer information finns i [Konfigurera anti-nätfiske-principer i Microsoft Defender för Office 365](configure-atp-anti-phishing-policies.md).

- Information om hur du använder falsk intelligens för att övervaka och hantera avsändare som skickar dig overifierade meddelanden finns i [Konfigurera förfalsknings intelligens i Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Öppna inblicken för falsk identitet i säkerhets & efterlevnad

1. Gå till instrument panelen **Threat Management** i säkerhets & efterlevnad \> **.**

2. Leta efter något av följande i raden **insikter** :

   - **Förfalsknings intelligens är aktiverat**: inblicken heter **falska domäner som inte kunde verifieras av de senaste 30 dagarna**. Det här är standardinställningen.
   - **Förfalsknings intelligens är inaktiverat**: inblicken i namngivna **Aktivera förfalsknings skydd** och när du klickar på den kan du aktivera förfalsknings intelligens.

3. Inblicken på instrument panelen visar information så här:

   ![Skärm bild av inblick i Spoof intelligens](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Denna inblick har två lägen:

   - **Insight-läge**: om förfalsknings intelligens är aktiverat visar insikt dig hur många meddelanden som har påverkats av våra förfalsknings funktioner under de senaste 30 dagarna.

   - **Vad händer om-läge**: om förfalsknings intelligens är inaktiverat visar insikten dig hur *många meddelanden som* har påverkats av våra förfalsknings uppgifter under de senaste 30 dagarna.

   Oavsett vilket är de falska domänerna som visas i inblicken indelade i två kategorier: **misstänkta domän par** och **icke misstänkt domän par**. Dessa kategorier är indelade i tre olika buckets för att du ska kunna granska.

   Ett **domän par** är en kombination av från-adressen och den sändande infrastrukturen:

   - Från-adressen är avsändarens e-postadress som visas i rutan från i e-postklienter. Denna adress kallas också `5322.From` adress.

   - Den sändande infrastrukturen, eller avsändaren, är domän domänen för omvänd DNS-sökning (PTR-post) för den sändande IP-adressen. Om den sändande IP-adressen inte har någon PTR-post identifieras avsändaren av den sändande undernätet med den 255.255.255.0 nät masken i CIDR-notation (/24). Om IP-adressen till exempel är 192.168.100.100 är avsändarens fullständiga IP-adress 192.168.100.100/24.

   **Misstänkta domän par** är:

   - **Falska användare med hög exakthet**: baserat på de historiska sändnings-och ryktes poängen för domänerna, är det mycket säkert att domänerna är falska och att meddelanden från dessa domäner är mer troligt att de är skadliga.

   - **Falska säkerhets** problem: baserat på historiska sändnings mönster och ryktes poängen för domänerna, är det ganska säkert att domänerna är falska och att meddelanden som skickas från dessa domäner är giltiga. Falsk positiv identitet är mer sannolik i den här kategorin än högkonfidens.

   - **Icke misstänkt domän par** (inklusive **räddad förfalskning**): domänen misslyckades explicit kontroller för e-postauktorisering [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)och [DMARC](use-dmarc-to-validate-email.md)). Domänen godkände emellertid vår implicita kontroll för e-postverifikationer ([sammansatt verifikation](email-validation-and-authentication.md#composite-authentication)). Därför har ingen åtgärd mot förfalskning gjorts för meddelandet.

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>Visa detaljerad information om misstänkta domän par från inblicken för falska uppgifter

1. Klicka på något av de här domän paren (High, måttlig eller räddat) i den här funktionen.

   Sidan för att **Insight-information** visas. På sidan visas en lista med avsändare som skickar overifierad e-post till din organisation.

   Med den här informationen kan du avgöra om falska meddelanden är godkända eller om du behöver vidta ytterligare åtgärder.

   Du kan sortera informationen efter antal meddelanden, det datum då datafilen senast upptäcktes och mer.

2. Välj ett objekt i tabellen för att öppna en informations ruta som innehåller information om domän paret. Informationen inkluderar:
   - Varför vi fångade det här.
   - Det här behöver du göra.
   - En domän Sammanfattning.
   - WhoIs data om avsändaren.
   - Liknande meddelanden som vi har sett i klient organisationen från samma avsändare.

   Härifrån kan du också välja att lägga till eller ta bort domän paret från **AllowedToSpoof** Safe delistion.

   ![Skärm bild av en domän i informations fönstret för förfalsknings information](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-list"></a>Lägga till eller ta bort en domän från AllowedToSpoof-listan

Du lägger till eller tar bort en domän från listan AllowedToSpoof (Safe-avsändare) i informations fönstret i den falska informationen om ett domän par. Ställ in växlings knappen på motsvarande sätt.

Om du bara tillåter ett domän par kan kombinationen av den nekade domänen *och* den sändande infrastrukturen. Den tillåter inte e-post från den nekade domänen från någon källa eller tillåter inte e-post från den sändande infrastrukturen för någon domän.

Du tillåter till exempel följande domän par för att skicka falska meddelanden till din organisation:

- *Falsk domän*: Gmail.com "
- *Skickar infrastruktur* `tms.mx.com` :

Endast e-post från det domän paret kommer att tillåtas för falska identiteter. Andra avsändare som försöker falska gmail.com är inte tillåtna. Meddelanden i andra domäner från tms.mx.com kontrol leras av förfalsknings intelligens.

## <a name="related-topics"></a>Relaterade ämnen

[Skydd mot förfalskning i Microsoft 365](anti-spoofing-protection.md)
