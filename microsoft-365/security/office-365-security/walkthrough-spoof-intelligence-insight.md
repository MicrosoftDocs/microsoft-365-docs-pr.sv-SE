---
title: Genomgång av insikt om förfalskningsinformation
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Administratörer kan ta reda på hur förfalskningsinformation fungerar. De kan snabbt avgöra vilka avsändare som legitimt skickar e-post till sina organisationer från domäner som inte klarar e-postautentiseringskontroller (SPF, DKIM eller DMARC).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8ca40e2cde08e5ea213d4c19366f038f1da19fa7
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407222"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>Genomgång – förfalskningsinformation i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

I Microsoft 365-organisationer med Defender för Office 365 kan du använda Spoof Intelligence-insikt för att snabbt avgöra vilka externa avsändare som legitimt skickar oautisk e-post (meddelanden från domäner som inte klarar SPF-, DKIM- eller DMARC-kontroller).

Genom att tillåta att kända externa avsändare skickar falska meddelanden från kända platser kan du minska antalet falska positiva meddelanden (bra e-postmeddelande markeras som dåligt). Genom att övervaka tillåtna förfalskningsavsändare får du ytterligare en säkerhetsnivå för att förhindra att osäkra meddelanden kommer till organisationen.

Mer information om rapporter och insikter finns i Rapporter och insikter i Säkerhets- & [Efterlevnadscenter.](reports-and-insights-in-security-and-compliance.md)

Den här genomgången är en av flera för Säkerhets- & Efterlevnadscenter. Mer information om hur du navigerar i rapporter och insikter finns i genomgångarna [i avsnittet Relaterade](#related-topics) ämnen.

> [!NOTE]
> Förfalskningsinformation visar data från de senaste 7 dagarna. [Förfalskningsprincipen och](learn-about-spoof-intelligence.md) motsvarande [Get-PhishFilterPolicy-cmdlet](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy) i Exchange Online PowerShell visar data från de senaste 30 dagarna. [Get-SpoofMailReport visar](https://docs.microsoft.com/powershell/module/exchange/get-spoofmailreport) data i upp till 90 dagar.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till **sidan för instrumentpanelen för** säkerhet använder du <https://protection.office.com/searchandinvestigation/dashboard> .

  Du kan visa förfalskningsinformationsinsikter från mer än en instrumentpanel i Säkerhets- & Efterlevnadscenter. Oavsett vilken instrumentpanel du tittar på ger insikten samma information och gör att du snabbt kan utföra samma uppgifter.

- Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:
  - **Organisationshantering**
  - **Säkerhetsadministratör**
  - **Säkerhetsläsare**
  - **Global Reader**

  Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

  **Obs!** Om du lägger till användare till motsvarande Azure Active Directory-roll i administrationscentret för Microsoft  365 får användarna de behörigheter som krävs i säkerhets- och efterlevnadscentret för & och behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).

- Du aktiverar och inaktiverar förfalskningsinformation i principer för skydd mot nätfiske i Microsoft Defender för Office 365. Spoof intelligence är aktiverat som standard. Mer information finns i Konfigurera [principer för nätfiske i Microsoft Defender för Office 365.](configure-atp-anti-phishing-policies.md)

- Information om hur du använder förfalskningsinformation för att övervaka och hantera avsändare som skickar icke-godkända meddelanden till dig finns i Konfigurera förfalskningsinformation i [Microsoft 365.](learn-about-spoof-intelligence.md)

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Öppna förfalskningsinformationsinsikten i Säkerhets- & Efterlevnadscenter

1. Gå till instrumentpanelen för & säkerhets- och  \> **efterlevnadscenter.**

2. Leta efter **något** av följande på raden Insikter:

   - **Troliga förfalskningsdomäner under** de senaste sju dagarna: Den här insikten anger att förfalskningsinformation är aktiverad (det är aktiverat som standard).
   - **Aktivera spoofskydd:** Den här insikten anger att förfalskningsskydd är inaktiverat och om du klickar på insikten kan du aktivera förfalskningsinformation.

3. Insikten på instrumentpanelen visar dig information så här:

   ![Skärmbild av förfalskningsinformation](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Den här insikten har två lägen:

   - **Insiktsläge:** Om förfalskningsinformation har aktiverats visar insikten hur många meddelanden som har påverkats av våra förfalskningsfunktioner under de senaste sju dagarna.
   - **Vad händer** om-läge: Om förfalskningsinformation är inaktiverad  visar insikten hur många meddelanden som skulle ha påverkats av våra förfalskningsfunktioner under de senaste sju dagarna.

   Oavsett vilket så är de förfalskningsdomäner som visas i insikten uppdelade i två **kategorier:** Misstänkta domäner och **icke-misstänkta domäner.**

   - **Exempel på misstänkta** domäner:

     - Betrodd förfalskning: Baserat på de historiska avsändarmönster och ryktesresultatet för domänerna är vi mycket säkra på att domänerna är förfalskning och meddelanden från dessa domäner är mer troliga att de är skadliga.

     - Måttlig konfidensförfalskning: Baserat på historiska sändningsmönster och ryktesresultatet för domänerna är vi ganska säkra på att domänerna är förfalskning och att meddelanden som skickas från dessa domäner är legitima. Falska positiva resultat är mer troliga i den här kategorin än förfalskning med hög konfidens.

   **Icke-misstänkta domäner:** Domänen misslyckades med explicit e-postautentisering kontrollerar [SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)och [DMARC).](use-dmarc-to-validate-email.md) Men domänen har passerat vår implicita e-postautentiseringskontroller[(sammansatt autentisering).](email-validation-and-authentication.md#composite-authentication) Därför vidtogs ingen förfalskningsåtgärd för meddelandet.

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a>Visa detaljerad information om misstänkta domäner från förfalskningsinformation

1. Klicka på misstänkta domäner eller **icke-misstänkta** domäner **på** spoofinsikter om du vill gå till sidan **Med** säkerhetsinformation. På **sidan Spoof Intelligence finns** följande information:

   - **Spoofed domain:** The domain of the poofed user that's displayed in the **From box** in email clients. Den här adressen kallas även `5322.From` för adressen.
   - **Infrastruktur:** Kallas även den _avsändande infrastrukturen._ Domänen finns i en omvänd DNS-sökning (PTR-post) för käll-e-postserverns IP-adress. Om käll-IP-adressen inte har någon PTR-post identifieras den avsändande infrastrukturen som \<source IP\> /24 (t.ex. 192.168.100.100/24).
   - **Antal meddelanden:** Antalet meddelanden från den avsändande infrastrukturen till organisationen som innehåller den angivna förfalskningsdomänen under de senaste 7 dagarna.
   - **Sågs** senast: Det senaste datumet då ett meddelande togs emot från den avsändande infrastrukturen som innehåller den falska domänen.
   - **Förfalskningstyp: Det** här värdet är **Externt.**
   - **Tillåtet att kapa?**: Värdena som visas här är:
     - **Ja:** Meddelanden från en kombination av en förfalskningsanvändares domän och infrastruktur för att skicka meddelanden tillåts och hanteras inte som falska e-postmeddelanden.
     - **Nej:** Meddelanden från en kombination av en förfalskningsanvändares domän och infrastrukturen för sändning markeras som falska. Åtgärden styrs av standardprincipen för skydd mot nätfiske eller anpassade principer för nätfiske (standardvärdet är Flytta meddelandet till mappen **Skräppost).**

     Mer information finns i Konfigurera [principer för nätfiske i Microsoft Defender för Office 365.](configure-atp-anti-phishing-policies.md)

2. Markera ett objekt i listan om du vill visa information om domänen/skicka infrastrukturpar i en utfällsida. Informationen omfattar:
   - Därför har vi fångat detta.
   - Det här behöver du göra.
   - En domänsammanfattning.
   - WhoIs data about the sender.
   - Liknande meddelanden som vi har sett i klientorganisationen från samma avsändare.

   Härifrån kan du också välja att lägga till eller ta bort domän/skicka infrastrukturpar från listan Tillåt förfalskning **av** avsändare. Ställ bara in växlingsknappen i enlighet med detta.

   ![Skärmbild av en domän i informationsfönstret om förfalskningsinformation](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a>Lägga till en domän i listan Med tillåtna förfalskning

Om du lägger till en domän i listan Tillåts i förfalskning från förfalskningsinformationsinsikter, tillåts bara kombinationen av den falska domänen och den avsändande infrastrukturen.  E-post från den falska domänen från någon källa tillåts inte heller e-post från den avsändande infrastrukturen för någon domän.

Du tillåter till exempel följande domän till listan Tillåt förfalskning:

- **Domän:** gmail.com
- **Infrastruktur:** tms.mx.com

Endast e-post från den domänen/det avsändande infrastrukturparet får förfalskning. Andra avsändare som försöker gmail.com är inte tillåtna. Meddelanden i andra domäner från tms.mx.com kontrolleras med förfalskningsinformation.

## <a name="related-topics"></a>Relaterade ämnen

[Skydd mot förfalskning i Microsoft 365](anti-spoofing-protection.md)
