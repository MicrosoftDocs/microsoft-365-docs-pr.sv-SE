---
title: Skydd mot nätfiske i Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.custom: TopSMBIssues
ms.collection:
- M365-security-compliance
description: Office 365 erbjuder en mängd olika skydd mot nätfiskeattacker som standard och även via ytterligare funktioner i Office 365 Advanced Threat Protection (ATP). I det här avsnittet introduceras de onlineresurser du kan använda för att lära dig mer om och implementera alternativ och strategier mot nätfiske i Office 365.
ms.openlocfilehash: 321d983f422bf4d231a772ca445bb74a7150a56e
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537431"
---
# <a name="anti-phishing-protection-in-office-365"></a>Skydd mot nätfiske i Office 365

*Nätfiske* en e-postattack som försöker stjäla känslig information i meddelanden som verkar vara från legitima eller betrodda avsändare. Det finns specifika kategorier av nätfiske. Till exempel:

- **Spear phishing** använder mycket fokuserat och anpassat innehåll som är särskilt anpassat till de riktade mottagarna (vanligtvis efter spaning på mottagarna av angriparen).

- **Valfångst** riktas mot chefer eller andra högt värderade mål inom en organisation för maximal effekt.

- **Business email compromise (BEC)** använder förfalskade betrodda avsändare (ekonomiansvariga, kunder, betrodda partner, etc.) i ett försök att lura mottagaren att godkänna betalningar, överföra pengar eller avslöja kunddata.

- **Ransomware** som krypterar dina data och kräver betalning för att dekryptera det nästan alltid börjar i phishing-meddelanden. Skydd mot nätfiske kan inte hjälpa dig att dekryptera krypterade filer, men det kan hjälpa dig att identifiera de första nätfiskemeddelanden som är associerade med ransomware-kampanjen. Mer information om hur du återställer från en ransomware-attack finns i [Återställ från en ransomware-attack i Office 365](recover-from-ransomware.md).

Med den växande komplexiteten i attacker är det till och med svårt för utbildade användare att identifiera sofistikerade nätfiskemeddelanden. Lyckligtvis kan Exchange Online Protection (EOP) och ytterligare funktioner i Office 365 Advanced Threat Protection (ATP) hjälpa till.

## <a name="anti-phishing-protection-in-eop"></a>Skydd mot nätfiske i EOP

EOP (det vill säga Office 365-organisationer utan ATP) innehåller funktioner som kan skydda din organisation från nätfiskehot:

- **Falska underrättelser**: Granska falska meddelanden från avsändare i interna och externa domäner och tillåta eller blockera dessa avsändare. Mer information finns [i Konfigurera falska underrättelser i Office 365](learn-about-spoof-intelligence.md).

- **Standardpolicy för phishing:** Aktivera eller inaktivera falska underrättelser, aktivera eller inaktivera oautentiserade avsändande avsändare i Outlook och ange åtgärden för blockerade förfalskade avsändare (flytta till mappen Skräppost eller karantän). Mer information finns i [Konfigurera principer för nätfiske i EOP](configure-anti-phishing-policies-eop.md).

- **Implicit e-postautentisering:** EOP förbättrar standardkontroller av e-postautentisering för inkommande e-post[(SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)och [DMARC)](use-dmarc-to-validate-email.md)med avsändarens rykte, avsändarehistorik, mottagarhistorik, beteendeanalys och andra avancerade tekniker för att identifiera förfalskade avsändare. Mer information finns [i E-postautentisering i Office 365](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a>Ytterligare skydd mot nätfiske i Office 365 ATP

Office 365 ATP innehåller ytterligare och mer avancerade funktioner mot nätfiske:

- **ATP:s principer för phishing:** Skapa nya anpassade principer, konfigurera inställningar för anti-personifiering (skydda användare och domäner från personifiering), inställningar för postlådans intelligens och justerbara avancerade tröskelvärden för nätfiske. Mer information finns [i Konfigurera ATP-principer för nätfiske i Office 365](configure-atp-anti-phishing-policies.md). Mer information om skillnaderna mellan anti-phishing-principer och ATP-principer för nätfiske finns [i Principer för nätfiske mot nätfiske i Office 365](set-up-anti-phishing-policies.md).

- **Kampanjvyer**: Maskininlärning och andra heuristik identifierar och analyserar meddelanden som är involverade i samordnade nätfiskeattacker mot hela tjänsten och din organisation. Mer information finns [i Kampanjvyer i Office 365 ATP](campaigns.md).

- **Attack simulator:** Administratörer kan skapa falska nätfiskemeddelanden och skicka dem till interna användare som ett utbildningsverktyg. Mer information finns [i Attack Simulator i Office 365 ATP](attack-simulator.md).

## <a name="other-anti-phishing-resources"></a>Andra anti-phishing-resurser

- För slutanvändare: [Skydda dig mot nätfiske och andra former av onlinebedrägerier](https://support.office.com/article/f84750b4-2f2c-46c3-89f6-e65f7f8c3546).

- [Så här validerar Office 365 Från-adressen för att förhindra nätfiske](how-office-365-validates-the-from-address.md).
