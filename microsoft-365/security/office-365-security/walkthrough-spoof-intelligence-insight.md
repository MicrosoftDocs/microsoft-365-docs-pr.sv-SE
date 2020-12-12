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
ms.openlocfilehash: 665745e940ea9547d57a1d7c47ff54eaae3756b7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659696"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>Genom gång-inblick i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I Microsoft 365-organisationer med Defender för Office 365 kan du använda falsk IT-insyn för att snabbt avgöra vilka externa avsändare som skickar e-postautentisering på ett legitimt sätt.

Genom att tillåta kända externa avsändare att skicka falska meddelanden från kända platser kan du minska falska positiva (bra e-postmeddelanden). Genom att övervaka tillåtna avsändare tillhandahåller du ett ytterligare säkerhets skikt för att förhindra att osäkra meddelanden kommer in i organisationen.

Mer information om rapporter och insikter finns i [rapporter och insikter i avsnittet om säkerhets & efterlevnad](reports-and-insights-in-security-and-compliance.md).

Den här genom gången är en av flera för säkerhets & Compliance Center. Information om hur du navigerar i rapporter och insikter finns i avsnittet [Närliggande information](#related-topics) .

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. För att gå direkt till sidan **säkerhets instrument panel** <https://protection.office.com/searchandinvestigation/dashboard> .

  Du kan visa inblick från fler än en instrument panel i säkerhets & Compliance Center. Oavsett vilken instrument panel du tittar på, ger inblicken samma detaljer och gör att du snabbt kan göra samma uppgifter.

- Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:
  - **Organisationshantering**
  - **Säkerhets administratör**
  - **Säkerhets läsare**
  - **Global läsare**

  Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

  **Obs!** när du lägger till användare i motsvarande Azure Active Directory-roll i Microsoft 365 Admin Center får användarna den behörighet som krävs för säkerhets & efterlevnad Center _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

- Du aktiverar och inaktiverar förfalsknings intelligens i policy mot nätfiske i Microsoft Defender för Office 365. Förfalsknings intelligens är aktiverat som standard. Mer information finns i [Konfigurera anti-nätfiske-principer i Microsoft Defender för Office 365](configure-atp-anti-phishing-policies.md).

- Information om hur du använder falsk intelligens för att övervaka och hantera avsändare som skickar dig overifierade meddelanden finns i [Konfigurera förfalsknings intelligens i Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Öppna inblicken för falsk identitet i säkerhets & efterlevnad

1. Gå till instrument panelen **Threat Management** i säkerhets & efterlevnad \> **.**

2. Leta efter något av följande i raden **insikter** :

   - **Sannolika spoofade domäner under de senaste sju dagarna**: denna inblick visar att förfalsknings intelligens är aktiverat (det är aktiverat som standard).
   - **Aktivera förfalsknings skydd**: denna inblick visar att förfalsknings intelligens är inaktiverat och att du kan aktivera förfalsknings intelligens genom att klicka på inblicken.

3. Inblicken på instrument panelen visar information så här:

   ![Skärm bild av inblick i Spoof intelligens](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Denna inblick har två lägen:

   - **Insight-läge**: om förfalsknings intelligens är aktiverat visar insikt dig hur många meddelanden som har påverkats av våra förfalsknings funktioner under de senaste sju dagarna.
   - **Vad händer om-läge**: om förfalsknings intelligens är inaktiverat visar insikten dig hur *många meddelanden som* har påverkats av våra förfalsknings uppgifter under de senaste sju dagarna.

   Oavsett vilket är de falska domänerna som visas i inblicken indelade i två kategorier: **misstänkta domäner** och **icke misstänkt domän**.

   - **Misstänkta domäner** inkluderar:

     - Falska användare med hög exakthet: baserat på de historiska sändnings-och ryktes poängen för domänerna, är det mycket säkert att domänerna är falska och att meddelanden från dessa domäner är mer troligt att de är skadliga.

     - Falska säkerhets problem: baserat på historiska sändnings mönster och ryktes poängen för domänerna, är det ganska säkert att domänerna är falska och att meddelanden som skickas från dessa domäner är giltiga. Falsk positiv identitet är mer sannolik i den här kategorin än högkonfidens.

   **Icke misstänkt domän**: domänen kunde inte explicit e-postverifierare kontrol lera [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)och [DMARC](use-dmarc-to-validate-email.md)). Domänen godkände emellertid vår implicita kontroll för e-postverifikationer ([sammansatt verifikation](email-validation-and-authentication.md#composite-authentication)). Därför har ingen åtgärd mot förfalskning gjorts för meddelandet.

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a>Visa detaljerad information om misstänkta domäner från informationen om förfalsknings intelligens

1. Klicka på **misstänkta domäner** eller **icke misstänkt domän** för att gå till Insight-sidan för **falsk underrättelse** . Informations sidan om **falska** uppgifter innehåller följande information:

   - **Falsk domän**: domänen för den falska användare som visas i rutan **från** i e-postklienter. Denna adress kallas också `5322.From` adress.
   - **Infrastruktur**: kallas även för att _Skicka infrastrukturen_. Domänen hittades i en omvänd DNS-sökning (PTR-post) för käll-e-postserverns IP-adress. Om käll-IP-adressen inte har någon PTR-post identifieras den sändande infrastrukturen som \<source IP\> /24 (till exempel 192.168.100.100/24).
   - **Antal** meddelanden: meddelande från infrastrukturen för att skicka till din organisation som innehåller den angivna domänen under de senaste 7 dagarna.
   - **Senast sedd**: det sista datum då ett meddelande togs emot från den sändande infrastrukturen som innehåller den falska domänen.
   - **Falsk skrivning**: det här värdet är **externt**.
   - Har du **tillstånd för falska identiteter?**: de värden som visas här är:
     - **Ja**: meddelanden från en kombination av falsk användares domän och överföring av infrastrukturen tillåts och behandlas inte som falsk e-post.
     - **Nej**: meddelanden från en kombination av användarens domän och sändande infrastruktur markeras som falska. Åtgärden styrs av standard policyn för skydd mot nätfiske eller anpassade anti-phishing-principer (Standardvärdet är **Flytta meddelandet till mappen skräp post**).

     Mer information finns i [Konfigurera anti-nätfiske-principer i Microsoft Defender för Office 365](configure-atp-anti-phishing-policies.md).

2. Välj ett objekt i listan om du vill visa information om den domän/sändande infrastruktur paret i en utfällbar metod. Informationen inkluderar:
   - Varför vi fångade det här.
   - Det här behöver du göra.
   - En domän Sammanfattning.
   - WhoIs data om avsändaren.
   - Liknande meddelanden som vi har sett i klient organisationen från samma avsändare.

   Härifrån kan du också välja att lägga till eller ta bort infrastrukturen för domän/skicka från listan Tillåt nekade **avsändare** . Ställ in växlings knappen på motsvarande sätt.

   ![Skärm bild av en domän i informations fönstret för förfalsknings information](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a>Lägga till en domän i listan över bevarade

Genom att lägga till en domän i listan över tillåtna programlistor från all inblick med falsk intelligens kan bara en kombination av den falska domänen *och* den sändande infrastrukturen skickas. Den tillåter inte e-post från den nekade domänen från någon källa eller tillåter inte e-post från den sändande infrastrukturen för någon domän.

Du tillåter till exempel följande domän till listan med falska identiteter:

- **Domän**: Gmail.com
- **Infrastruktur**: TMS.MX.com

Endast e-post från den domänen/sändande infrastruktur paret kommer att få åtkomst till förfalskningar. Andra avsändare som försöker falska gmail.com är inte tillåtna. Meddelanden i andra domäner från tms.mx.com kontrol leras av förfalsknings intelligens.

## <a name="related-topics"></a>Relaterade ämnen

[Skydd mot förfalskning i Microsoft 365](anti-spoofing-protection.md)
