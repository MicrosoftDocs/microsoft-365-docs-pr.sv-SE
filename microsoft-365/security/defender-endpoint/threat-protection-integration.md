---
title: Integrera Microsoft Defender för Endpoint med andra Microsoft-lösningar
description: Läs om hur Microsoft Defender för Endpoint integreras med andra Microsoft-lösningar, bland annat Microsoft Defender för identitet och Azure Säkerhetscenter.
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: microsoft 365 defender, villkorsstyrd åtkomst, office, avancerat skydd mot hot, microsoft defender för identitet, microsoft defender för office, azure säkerhetscenter, microsoft cloud app security, azure sentinel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 287ad9adeccd527b756bdd5304d3c89fc1b2d789
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076490"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a>Microsoft Defender för Endpoint och andra Microsoft-lösningar

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a>Integrera med andra Microsoft-lösningar

Microsoft Defender för Endpoint är direkt integrerat med olika Microsoft-lösningar.

### <a name="azure-security-center"></a>Azure Security Center
Microsoft Defender för Endpoint tillhandahåller en omfattande lösning för serverskydd, inklusive funktioner för identifiering av slutpunkt och svar (EDR) på Windows-servrar.

### <a name="azure-sentinel"></a>Azure Sentinel
Med Microsoft Defender för slutpunktskopplingen kan du strömma aviseringar från Microsoft Defender för Slutpunkt till Azure Sentinel. På så sätt kan du mer omfattande analysera säkerhetshändelser i organisationen och skapa spelböcker för effektiva och omedelbart svar.

### <a name="azure-information-protection"></a>Azure Information Protection
Skydda känsliga data samtidigt som du aktiverar produktiviteten på arbetsplatsen genom dataidentifiering och dataskydd.

### <a name="conditional-access"></a>Med villkorsstyrd åtkomst
Microsoft Defender för Endpoints riskpoäng för dynamiska enheter integreras i utvärderingen av villkorsstyrd åtkomst och säkerställer att endast säkra enheter har åtkomst till resurser. 

### <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security
Microsoft Cloud App Security utnyttjar Microsoft Defender för Slutpunktsslutpunktssignaler för att tillåta direkt insyn i användning av molnprogram, inklusive användning av molntjänster som inte stöds (skugg-IT) från alla Microsoft Defender för övervakade slutpunktsenheter.

### <a name="microsoft-defender-for-identity"></a>Microsoft Defender for Identity
Misstänkta aktiviteter körs under ett användarsammanhang. Integreringen mellan Microsoft Defender för Endpoint och Azure ATP ger flexibiliteten att genomföra undersökning av cybersäkerhet för aktiviteter och identiteter.

### <a name="microsoft-defender-for-office"></a>Microsoft Defender för Office
[Defender för Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) skyddar organisationen mot skadlig programvara i e-postmeddelanden och filer via ATP – säkra länkar, ATP – säkra bifogade filer, avancerade skydd mot nätfiske och förfalskningsfunktioner. Integreringen mellan Office 365 ATP och Microsoft Defender för Endpoint gör att säkerhetsanalytiker är bättre på att undersöka startpunkten för en attack. Genom delning av hotinformation kan attacker finnas och blockeras. 

>[!NOTE]
> Defender för Office 365-data visas för händelser under de senaste 30 dagarna. För aviseringar visas Defender för Office 365-data baserat på första aktivitetstiden. Därefter är data inte längre tillgängliga i Defender för Office 365.

### <a name="skype-for-business"></a>Skype för företag
Integreringen av Skype för företag är ett sätt för analytiker att kommunicera med en potentiellt komprometterad användare eller enhetsägare via en enkel knapp från portalen.

## <a name="microsoft-365-defender"></a>Microsoft 365 Defender
Med Microsoft 365 Defender utgör Microsoft Defender för Endpoint och olika Microsoft-säkerhetslösningar en enhetlig företagssäkerhetssvit före och efter intrång som integrerar inbyggt i slutpunkt, identitet, e-post och program för att identifiera, förhindra, undersöka och automatiskt svara på avancerade attacker. 
 
[Läs mer om Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)


## <a name="related-topics"></a>Relaterade ämnen
- [Konfigurera integrering och andra avancerade funktioner](advanced-features.md)
- [Översikt över Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)
- [Aktivera Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/mtp-enable)
- [Skydda användare, data och enheter med villkorsstyrd åtkomst](conditional-access.md)
