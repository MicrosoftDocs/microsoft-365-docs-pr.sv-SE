---
title: Använda identitets-, enhets- och hotskydd för dataskyddsförordningen
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
description: Förhindra personliga databrott med tjänster för identitet, enhet och hotskydd i Microsoft 365.
ms.openlocfilehash: 145b8a59f7eafb95adf71dc24613ee15ef1c2cca
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052356"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Använda identitets-, enhets- och hotskydd för dataskyddsförordningen

Microsoft 365 tillhandahåller ett antal funktioner för identitet, enheter och hotskydd som organisationer kan använda för att hjälpa till att uppfylla sekretessrelaterade bestämmelser om datasekretess. I den här artikeln beskrivs vad datasekretessbestämmelser kräver på dessa områden och en lista med relaterade Microsoft 365-funktioner och -tjänster med länkar till mer information som hjälper dig att uppfylla implementeringskraven.

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>Hur identitets-, enhets- och hotskydd relaterar till dataskyddsförordningen

Även om datasekretessreglerna varierar beroende på deras specifika natur är det viktigaste för det de kallar i GDPR:s artikel 5(1)(f), där det står att:

- Personuppgifter ska bearbetas på ett sätt som säkerställer tillräcklig säkerhet för personuppgifter, inklusive skydd mot obehörig eller olaglig bearbetning och mot oavsiktlig förlust, intrång eller skada genom att använda lämpliga tekniska åtgärder eller organisationsåtgärder (integritet och konfidentialitet).

Eftersom personliga databrott ofta orsakas av administrativa intrång eller slutanvändarkontointrång och skadlig systemåtkomst. Till exempel kan en hack för ett administratörskonto resultera i att kundkortsnummer eller annan personlig information förs över. Alla vi rekommenderar att du använder identitets-, enhets- och hotskydd tillsammans med Microsoft 365 bör potentiellt implementeras, vilket återspeglas i efterlevnadsresultatet i Efterlevnadshanteraren.

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a>Använda resultaten från ditt utvärderingsarbete och Efterlevnadshanteraren

Efterlevnadshanteraren innehåller identitets-, enhets- och hotskydd med följande kategorier:

- Identiteten motsvarar **kategorin Kontrollåtkomst**
- Enheten motsvarar kategorin **Hantera** enheter
- Hotskydd motsvarar **kategorin Skydda mot** hot
 
Om dessa väljs i vår exempeluppsättning med fyra huvudregler för datasekretess anger Efterlevnadshanteraren 90 förbättringsåtgärder, varav de flesta har poänget "27". Eftersom Ett så stort antal anges av Efterlevnadshanteraren för dessa kategorier anges några av de vanligaste här, som referens.

Använd [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) för identitet och kategorin **Kontrollåtkomst,** som du kan med:

- Implementera replay-authentication (för att förhindra "man i mitten"-attacker)
- Blockera äldre autentisering.
- Konfigurera principer för användarrisk och användar inloggningsrisk.
- Aktivera villkorlig åtkomst och multifaktorautentisering (MFA) för administratörer och icke-administratörer.
- Konfigurera och tillämpa lösenordsprinciper.
- Begränsa åtkomst till konton med behörighet med identitetshantering med Azure AD-behörighet.
- Inaktivera åtkomst vid uppsägning.
- Granska användarkonton och statusändringar.
- Granska rollgrupper och administrativa ändringar.

Använd [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) för enheter och kategorin **Hantera** enheter med vilka du kan:

- Blockera jail broken and rooted mobile devices.
- Konfigurera Intune för hantering av mobila enheter.
- Skapa efterlevnadsprinciper för Android-, iOS-, macOS- och Windows-enheter.
- Skapa en profil för enhetskonfiguration för Android-, iOS-, macOS- och Windows-enheter.
- Skapa principer för appskydd för iOS och Windows.
- Dölj information med låsskärmen.
- Implementera lösenordsprinciper för mobila enheter.
- Kräv att mobila enheter låser sig vid inaktivitet.
- Kräva att mobila enheter rensar vid flera inloggningsfel.

Använd [Exchange Online Protection och Microsoft Defender för Office 365](../security/defender-365-security/defender-for-office-365.md) **för** kategorin Skydda mot hot med vilka du kan:

- Aktivera avsändarautentisering (SPF, DMARC och DKIM).
- Konfigurera Microsoft Defender för Office 365 mot nätfiske.
- Implementera säkra bifogade filer.
- Implementera säkra länkar.
- Implementera principer för identifiering av skadlig programvara och svar.
- Implementera principer för utgående och inkommande skräppost.

### <a name="references"></a>Referenser:

- [Vanliga principer för identitets- och enhetsåtkomst](../security/defender-365-security/identity-access-policies.md)
- [Skydda mot hot i Office 365](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [Säkra bifogade filer](../security/defender-365-security/safe-attachments.md)
- [Säkra länkar](../security/defender-365-security/safe-links.md)
- [Säkra dokument](../security/defender-365-security/safe-docs.md)
