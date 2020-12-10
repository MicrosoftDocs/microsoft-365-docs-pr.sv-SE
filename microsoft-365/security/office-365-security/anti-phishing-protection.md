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
ms.service: O365-seccomp
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
description: Administratörer kan lära sig mer om skydd mot nätfiske-funktioner i Exchange Online Protection (EOP) och Microsoft Defender för Office 365.
ms.openlocfilehash: 5b175a252f95c62a40348a78e694628ee58488bd
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615003"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Skydd mot nätfiske i Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


*Nätfiske* är ett e-postangrepp som försöker stjäla känslig information i meddelanden som verkar vara från legitima eller betrodda avsändare. Det finns särskilda typer av nät fiske. Till exempel:

- **Spear nätfiske** använder prioriterat, anpassat innehåll som är specifikt skräddarsydda för de riktade mottagarna (vanligt vis efter Reconnaissance på mottagarnas mottagare).

- **Whaling** riktar sig till chefer eller andra mål inom en organisation för maximal effekt.

- **Företags-e-postkompromisser (BEC)** använder förfalskade betrodda avsändare (finans tjänstemän, kunder, betrodda partners etc.) för att lura mottagarna att godkänna betalningar, överföra penning medel eller Visa kunddata.

- **Utpressnings tro** vara som krypterar dina data och kräver betalning för att dekryptera det nästan alltid med nät fiske meddelanden. Skydd mot nätfiske kan inte hjälpa dig att dekryptera krypterade filer, men det kan hjälpa till att identifiera de inledande nät fiske meddelandena som är kopplade till utpressnings bara kampanjen. Mer information om hur du återställer från en utpressnings tro Jan attack finns i [återställa från en utpressnings tro Jan attack i Microsoft 365](recover-from-ransomware.md).

Det är ännu svårt för utbildade användare att identifiera avancerade nät fiske meddelanden. Som tur är kan Exchange Online Protection (EOP) och ytterligare funktioner i Microsoft Defender för Office 365 hjälpa dig.

## <a name="anti-phishing-protection-in-eop"></a>Skydd mot nätfiske i EOP

EOP (det vill säga Microsoft 365-organisationer utan Microsoft Defender för Office 365) innehåller funktioner som kan skydda din organisation från nätfiske-hot:

- **Förfalskningsinformation**: granska falska meddelanden från avsändare i interna och externa domäner samt tillåt eller blockera avsändarna. Mer information finns i [Konfigurera förfalsknings information i EOP](learn-about-spoof-intelligence.md).

- **Anti-nätfiske-principer i EOP**: Aktivera eller inaktivera förfalsknings intelligens, Aktivera oautentiserad avsändare i Outlook på eller av och ange åtgärd för blockerade avsändare (flytta till mappen skräp post eller karantän). Mer information finns i [Konfigurera principer för nätfiske i EOP](configure-anti-phishing-policies-eop.md).

- **Implicit e-postauktorisering**: EOP förbättrar standardinställningarna för inkommande e-post ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)och [DMARC](use-dmarc-to-validate-email.md)) med avsändarens rykte, avsändarens historik, mottagar historik, beteende analys och andra avancerade tekniker som hjälper dig att identifiera förfalskade avsändare. Mer information finns i [E-postautentisering i Microsoft 365](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Ytterligare skydd mot nätfiske i Microsoft Defender för Office 365

Microsoft Defender för Office 365 innehåller fler och fler avancerade nät fiske funktioner:

- **Skydd mot nätfiske i Microsoft Defender för Office 365**: skapa nya anpassade principer, konfigurera inställningar för skydd mot obehörig person (skydda användare och domäner från personifiering), inställningar för post lådor och justerbara avancerade nät fiske trösklar. Mer information finns i [Konfigurera anti-nätfiske-principer i Microsoft Defender för Office 365](configure-atp-anti-phishing-policies.md). Mer information om skillnaderna mellan anti-nätfiske-principer i EOP och anti-nätfiske-principer i Defender för Office 365 finns i [principer för nätfiske i Microsoft 365](set-up-anti-phishing-policies.md).

- **Kampanjmallar**: maskin inlärning och andra heuristik identifierar och analyserar meddelanden som ingår i koordinerade nätfiske-attacker mot hela tjänsten och din organisation. Mer information finns i [vyn kampanjer i Microsoft Defender för Office 365](campaigns.md).

- **Angrepps Simulator**: administratörer kan skapa falska nät fiske meddelanden och skicka dem till interna användare som utbildnings verktyg. Mer information finns i [angrepps Simulator i Microsoft Defender för Office 365](attack-simulator.md).

## <a name="other-anti-phishing-resources"></a>Andra AntiPhishing-resurser

- För slutanvändare: [skydda dig från nätfiske och andra former av bedrägerier online](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).

- [Hur Microsoft 365 verifierar från-adressen för att förhindra nätfiske](how-office-365-validates-the-from-address.md).
