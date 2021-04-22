---
title: Integrera Microsoft Defender för Endpoint med andra Microsoft-lösningar
description: Läs om hur Microsoft Defender för Endpoint integreras med andra Microsoft-lösningar, bland annat Microsoft Defender för identitet och Azure Defender.
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: microsoft 365 defender, villkorsstyrd åtkomst, office, Microsoft Defender för slutpunkt, microsoft defender för identitet, microsoft defender för office, Azure Defender, microsoft cloud app security, azure sentinel
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
ms.openlocfilehash: ce8dbef2f4fb7c3503f04f15148d2071b449b2dc
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935539"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a>Microsoft Defender för Endpoint och andra Microsoft-lösningar

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a>Integrera med andra Microsoft-lösningar

Microsoft Defender för Endpoint är direkt integrerat med olika Microsoft-lösningar.

### <a name="azure-defender"></a>Azure Defender
Microsoft Defender för Endpoint tillhandahåller en omfattande lösning för serverskydd, inklusive funktioner för identifiering av slutpunkt och svar (EDR) på Windows-servrar.

### <a name="azure-sentinel"></a>Azure Sentinel
Med Microsoft Defender för slutpunktskopplingen kan du strömma aviseringar från Microsoft Defender för Slutpunkt till Azure Sentinel. På så sätt kan du mer omfattande analysera säkerhetshändelser i organisationen och skapa spelböcker för effektiva och omedelbart svar.

### <a name="azure-information-protection"></a>Azure Information Protection
Vi tog nyligen bort Azure Information Protection-integreringen eftersom våra Endpoint DLP-funktioner införlivar en förbättrad lösning för identifiering och skydd av känsliga data som lagras på slutpunktsenheter som underlättar bättre synlighet och integrering mellan lösningar. Det här meddelades i följande [blogg](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555). Vi rekommenderar att kunder flyttar över till att använda Slutpunkt DLP.

### <a name="conditional-access"></a>Villkorsstyrd åtkomst
Microsoft Defender för Endpoints riskpoäng för dynamiska enheter integreras i utvärderingen av villkorsstyrd åtkomst och säkerställer att endast säkra enheter har åtkomst till resurser. 

### <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security
Microsoft Cloud App Security utnyttjar Microsoft Defender för Slutpunktsslutpunktssignaler för att tillåta direkt insyn i användning av molnprogram, inklusive användning av molntjänster som inte stöds (skugg-IT) från alla Microsoft Defender för övervakade slutpunktsenheter.

### <a name="microsoft-defender-for-identity"></a>Microsoft Defender for Identity
Misstänkta aktiviteter körs under ett användarsammanhang. Integreringen mellan Microsoft Defender för Endpoint och Microsoft Defender för identitet ger flexibiliteten att utföra undersökning av cybersäkerhet för alla aktiviteter och identiteter.

### <a name="microsoft-defender-for-office"></a>Microsoft Defender för Office
[Defender för Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) skyddar organisationen mot skadlig programvara i e-postmeddelanden och filer via säkra länkar, säkra bifogade filer, avancerade funktioner för nätfiske och förfalskningsinformation. Integreringen mellan Microsoft Defender för Office 365 och Microsoft Defender för Endpoint gör att säkerhetsanalytiker kan gå över till att undersöka startpunkten för en attack. Genom delning av hotinformation kan attacker finnas och blockeras. 

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
