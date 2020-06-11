---
title: Använda identitets-, enhets- och hotskydd för dataskyddsreglering
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
- M365solutions
ms.custom: ''
description: Förhindra personuppgiftsbrott med microsoft 365-tjänster för personuppgiftsskydd och hotskydd.
ms.openlocfilehash: 74894037ef2fe56aeb5bc44340cd8a946863baff
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695085"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Använda identitets-, enhets- och hotskydd för dataskyddsreglering

Microsoft 365 tillhandahåller ett antal funktioner för identitets-, enhets- och hotskydd som organisationer kan använda för att följa reglerna för datasekretessrelaterad efterlevnad. I den här artikeln beskrivs vad de datasekretessregler som krävs i dessa områden och en lista över relaterade Funktioner och tjänster från Microsoft 365 med länkar till mer information som hjälper dig att hantera implementeringskrav.

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>Hur identitet, enhet och hotskydd relaterar till datasekretessreglering

Även om bestämmelserna om datasekretess varierar i fråga om deras specificitet, ingår kärnan i vad de kräver i GDPR:s artikel 5.1 f, där det anges att 

- Personuppgifter ska behandlas på ett sätt som säkerställer lämplig säkerhet för personuppgifterna, inklusive skydd mot obehörig eller olaglig behandling och mot oavsiktlig förlust, förstörelse eller skada, med hjälp av lämpliga tekniska eller organisatoriska åtgärder ("integritet och sekretess").

Eftersom personuppgiftsbrott ofta orsakas av kompromettering av administrativa konton eller slutanvändarkonto och åtkomst till skadligt system. Till exempel, en admin konto hacka kan resultera i exfiltration av kundens kreditkortsnummer eller annan personlig information. Alla allmänt tillrådliga identitets-, enhets- och hotskydd som är tillgängliga med Microsoft 365 bör implementeras, vilket återspeglas i din efterlevnadspoäng.

## <a name="using-the-results-of-your-assessment-work-and-compliance-score"></a>Använda resultaten av ditt bedömningsarbete och efterlevnadspoäng

Efterlevnadspoängen omfattar identitets-, enhets- och hotskydd med hjälp av följande kategorier:

- Identiteten motsvarar kategorin **Kontrollåtkomst**
- Enheten motsvarar kategorin **Hantera enheter**
- Skydd mot hot motsvarar kategorin **Skydda mot hot**
 
Om dessa väljs ut i vår urvalsuppsättning med fyra huvudregler för datasekretess anger efterlevnadspoäng 90 förbättringsåtgärder, varav de flesta har fått ett "27". Eftersom ett så stort antal kallas ut av efterlevnadspoäng för dessa kategorier, listas några av de vanligaste här, som referens.

Använd [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) för identitet och kategorin Control **Access,** med vilken du kan:

- Implementera reprisresistent autentisering (för att förhindra "Man in the middle"-attacker)
- Blockera äldre autentisering.
- Konfigurera användarrisk- och användaråtkomstriskprinciper.
- Aktivera villkorlig åtkomst och MFA (Multi Factor Authentication) för administratörer och icke-administratörer.
- Konfigurera och tillämpa lösenordsprinciper.
- Begränsa åtkomsten till privilegierade konton med Azure AD Privileged Identity Management.
- Inaktivera åtkomst vid uppsägning.
- Granska användarkonton och statusändringar.
- Granska rollgrupp och administrativa ändringar.

Använd [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) för enheter och kategorin Hantera **enheter,** med vilken du kan:

- Blockera fängelse trasiga och rotade mobila enheter.
- Konfigurera Intune för hantering av mobila enheter.
- Skapa efterlevnadsprinciper för Android-, iOS-, macOS- och Windows-enheter.
- Skapa en enhetskonfigurationsprofil för Android-, iOS-, macOS- och Windows-enheter.
- Skapa principer för appskydd för iOS och Windows.
- Dölj information med låsskärmen.
- Implementera lösenordsprinciper för mobila enheter.
- Kräv att mobila enheter låser in vid inaktivitet.
- Kräv att mobila enheter rensar vid flera inloggningsfel.

Använd [Exchange Online Protection och Office 365 Advanced Threat Protection (ATP)](../security/office-365-security/office-365-atp.md) för kategorin Skydda mot **hot,** med vilken du kan:

- Aktivera avsändareautentisering (SPF, DMARC och DKIM).
- Konfigurera ATP-principer (Advanced Threat Protection) (Office 365 Advanced Threat Protection).
- Implementera ATP-säkra bilagor.
- Implementera ATP Safe Links.
- Implementera principer för identifiering och svar av skadlig kod.
- Implementera principer för skräppost för utgående och inkommande.

### <a name="references"></a>Referenser:

- [Vanliga principer för identitets- och enhetsåtkomst](../enterprise/identity-access-policies.md)
- [Skydda mot hot i Office 365](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [ATP säkra bilagor](../security/office-365-security/atp-safe-attachments.md)
- [Säkra ATP-länkar](../security/office-365-security/atp-safe-links.md)
- [ATP Säkra dokument](../security/office-365-security/safe-docs.md)
