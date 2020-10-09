---
title: Använd identitets-, enhets-och hot skydd för data integritets förordning
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Förhindra person uppgifter om identitets-, enhets-och hot skydd i Microsoft 365.
ms.openlocfilehash: e084036860f5d15a14ca6c75305583b86a5fc53f
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48398697"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Använd identitets-, enhets-och hot skydd för data integritets förordning

Microsoft 365 tillhandahåller ett antal funktioner för identitets-, enhets-och hot skydd som organisationer kan använda för att uppfylla data integritets regler. I den här artikeln beskrivs vad data integritets reglerna kräver i dessa områden och en lista över relaterade funktioner och tjänster i Microsoft 365 med länkar till mer information som hjälper dig att hantera implementerings kraven.

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>Så här skyddar identitet, enhet och hot mot data integritets reglering

Även om data integritets reglerna varierar beroende på deras betydelse, är syftet med vad de kan prata med i GDPR i paragraf 5.1 (f), som visar att: 

- Person uppgifter ska behandlas på ett sätt som säkerställer lämplig säkerhet för person uppgifter, inklusive skydd mot obehörig eller olaglig behandling samt mot oavsiktlig förlust, destruktion eller skada, med lämpliga tekniska eller organisatoriska åtgärder ("integritet och konfidentialitet").

Eftersom person data brott ofta orsakas av administratörs-eller slutanvändarens problem med intrång i systemet. Ett administratörs konto Hacker kan till exempel ge exfiltration kreditkorts nummer eller annan personlig information. Allt allmänt tillrådligt krypterings-, enhets-och hot-skydd som är tillgängligt med Microsoft 365 kan komma att implementeras, som kommer att återspeglas i din uppkopplings poäng, i Compliance Manager.

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a>Använda resultaten av din bedömnings arbete och kompatibilitetskontrollen

Efterföljandekrav inkluderar identitets-, enhets-och hot skydd med dessa kategorier:

- Identiteten motsvarar kategorin för **kontroll åtkomst**
- Enheten motsvarar kategorin **Hantera enheter**
- Hotet skyddas **mot kategorin skydda mot hot**
 
Om dessa är markerade i vårt exempel med fyra viktiga data integritets regler anger överensstämmelse hanteraren 90 förbättrings åtgärder, de flesta av dessa betyg är "27". Eftersom ett sådant stort nummer besvaras av Compliance Manager för dessa kategorier, är några av de vanligaste fälten listade som referens.

Använd [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) för identitet och **kontroll åtkomst** kategori, med vilken du kan:

- Implementera Replay-motstånd (för att förhindra "man i mitten")
- Blockera bakåtkompatibel-verifikation.
- Konfigurera principer för användar risker och användar inloggnings risker.
- Aktivera villkorsstyrd åtkomst och multifaktorautentisering för administratörer och icke-administratörer.
- Konfigurera och tillämpa lösen ords principer.
- Begränsa åtkomsten till behöriga konton med Azure AD restrict Identity Management.
- Inaktivera åtkomst vid uppsägning.
- Granska användar konton och status ändringar.
- Granska roll grupper och administrativa ändringar.

Använd [Microsoft slut punkts hanteraren](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) för enheter och kategorin **Hantera enheter** , med vilken du kan:

- Blockera Jail trasiga och rotade mobila enheter.
- Konfigurera Intune för hantering av mobila enheter.
- Skapa efterlevnadsprinciper för Android, iOS, macOS och Windows-enheter.
- Skapa en konfigurations profil för Android, iOS, macOS och Windows.
- Skapa program skydds principer för iOS och Windows.
- Dölja information med lås skärmen.
- Implementera principer för lösen ord för mobila enheter.
- Kräv att mobila enheter låses vid inaktivitet.
- Kräv att mobila enheter rensas på flera inloggnings problem.

Använd [Exchange Online Protection och Office 365 Avancerat skydd (ATP)](../security/office-365-security/office-365-atp.md) för kategorin **skydda mot hot** :

- Aktivera avsändare (SPF, DMARC och DKIM).
- Konfigurera Office 365 skydd mot nätfiske (avancerat skydd).
- Implementera säkra filer för ATP.
- Implementera säkra ATP-länkar.
- Implementera identifierings-och svars principer för skadlig kod.
- Implementera principer för utgående och inkommande skräp post.

### <a name="references"></a>Innehåller

- [Vanliga principer för identitets- och enhetsåtkomst](../security/office-365-security/identity-access-policies.md)
- [Skydda mot hot i Office 365](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [Säkra filer för ATP](../security/office-365-security/atp-safe-attachments.md)
- [Säkra ATP-länkar](../security/office-365-security/atp-safe-links.md)
- [ATP Säkra dokument](../security/office-365-security/safe-docs.md)
