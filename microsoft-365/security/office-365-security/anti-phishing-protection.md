---
title: Skydd mot nätfiske
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: Administratörer kan läsa mer om funktionerna för skydd mot nätfiske i Exchange Online Protection (EOP) och Microsoft Defender för Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 290f5f7797d987fb65a99e3f9e656bfec4cf83f3
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538345"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Skydd mot nätfiske i Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*Nätfiske* är en e-postattack som försöker stjäla känslig information i meddelanden som verkar vara från legitima eller betrodda avsändare. Det finns särskilda kategorier av nätfiske. Till exempel:

- **Nätfiske** används med fokuserat, anpassat innehåll som är specifikt anpassat efter de riktade mottagarna (vanligtvis efter efterkontroll på mottagarna av attackeret).

- **Whaling** riktar sig till chefer eller andra högvärdesmålen i en organisation för maximal effekt.

- **BEC (Business Email Compromise)** använder förfalskade betrodda avsändare (finansansvariga, kunder, betrodda partner osv.) för att lura mottagare att godkänna betalningar, överföra pengar eller visa kunddata. Lär dig mer genom att titta på [den här videon](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2).

- **Utpressningstrojaner** som krypterar dina data och kräver betalning för att dekryptera dem börjar nästan alltid med nätfiskemeddelanden. Skydd mot nätfiske kan inte hjälpa dig att dekryptera krypterade filer, men det kan hjälpa dig att identifiera de första nätfiskemeddelanden som är kopplade till utpressningstrojankampanjen. Mer information om hur du återställer från en utpressningstrojanattack finns i [Återskapa från en utpressningstrojanattack i Microsoft 365](recover-from-ransomware.md).

Med den växande komplexiteten på attacker är det ännu svårt för användare med utbildning att identifiera avancerade nätfiskemeddelanden. Som tur är kan Exchange Online Protection (EOP) och de extra funktionerna i Microsoft Defender för Office 365 vara till hjälp.

## <a name="anti-phishing-protection-in-eop"></a>Skydd mot nätfiske i EOP

EOP (d.v.s. Microsoft 365 organisationer utan Microsoft Defender för Office 365) innehåller funktioner som kan skydda organisationen mot nätfiskehot:

- **Förfalskningsinformation:** Använd förfalskningsinformation för att granska identifierade förfalskningsavsändare i meddelanden från externa och interna domäner, och tillåt eller blockera manuellt de identifierade avsändarna. Mer information finns i [Insikt om förfalskningsinformation i EOP](learn-about-spoof-intelligence.md).

- Principer för skydd mot nätfiske i **EOP:** Aktivera eller inaktivera förfalskningsinformation, aktivera eller inaktivera oauthticerad avsändaridentifiering i Outlook samt ange åtgärder för spärrade avsändare. Mer information finns i Konfigurera [principer för skydd mot nätfiske i EOP.](configure-anti-phishing-policies-eop.md)

- **Tillåt eller blockera falska avsändare i Tillåten av klient/blockeringslista**: När du åsidosätter domen i Insikt om förfalskningsinformation blir den falska avsändaren en manuell tillåtelse eller blockera posten som bara visas på fliken **Falska** i Tillåten av klient/blockeringslistan. Du kan också skapa tillåtna eller blockera poster manuellt för falska avsändare innan de upptäcks av förfalskningsinformation. För mer information se [Hantera Tillåten av klient/blockeringslista i EOP](tenant-allow-block-list.md).

- **Implicit** e-postautentisering: EOP förbättrar vanliga e-postautentiseringskontroller för inkommande e-post [(SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)och [DMARC)](use-dmarc-to-validate-email.md)med avsändarens rykte, avsändarhistorik, mottagarhistorik, beteendeanalys och andra avancerade tekniker som hjälper till att identifiera förfalskade avsändare. Mer information finns i [E-postautentisering i Microsoft 365](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Ytterligare skydd mot nätfiske i Microsoft Defender för Office 365

Microsoft Defender för Office 365 innehåller ytterligare och mer avancerade funktioner mot nätfiske:

- Principer för skydd mot nätfiske i **Microsoft Defender för Office 365:** Konfigurera inställningar för personifieringsskydd för specifika meddelandeavsändare och avsändardomäner, postlådeintelligensinställningar och justerbara avancerade tröskelvärden för nätfiske. Mer information finns i Konfigurera [principer för skydd mot nätfiske i Microsoft Defender för Office 365.](configure-atp-anti-phishing-policies.md) Mer information om skillnaderna mellan principer för skydd mot nätfiske i EOP och principer för skydd mot nätfiske i Defender för Office 365 finns i Principer för skydd mot [nätfiske i Microsoft 365.](set-up-anti-phishing-policies.md)

- **Kampanjvyer:** Maskininlärning och annan heuristik identifierar och analyserar meddelanden som är inblandade i koordinerade nätfiskeattacker mot hela tjänsten och organisationen. Mer information finns i [Kampanjvyer i Microsoft Defender för Office 365](campaigns.md).

- **Attackattack**: Administratörer kan skapa falska nätfiskemeddelanden och skicka dem till interna användare som ett utbildningsverktyg. Mer information finns i [Attack Defender i Microsoft Defender för Office 365](attack-simulator.md).

## <a name="other-anti-phishing-resources"></a>Andra resurser mot nätfiske

- För slutanvändare: Skydda [dig mot nätfiskeförsök och andra former av onlinebedrägerier.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)

- [Hur Microsoft 365 verifierar Från-adressen för att förhindra nätfiske](how-office-365-validates-the-from-address.md).
