---
title: Aktivera Microsoft 365 Defender i Säkerhetscenter för Microsoft 365
description: Lär dig hur du aktiverar Microsoft 365 Defender och börjar integrera dina säkerhetstillbud och -svar.
keywords: komma igång, aktivera MTP, Microsoft Threat Protection, M365, säkerhet, dataplats, nödvändiga behörigheter, licensberättigande, inställningssidan
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: bf8fdb2a8a42ef7b70b744cbbb5663e6afe51989
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764392"
---
# <a name="turn-on-microsoft-365-defender"></a>Aktivera Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-365-defender.md) ger en enhetlig svarsprocess för incidenter genom att integrera nyckelfunktioner i Microsoft Defender för slutpunkt, Microsoft Defender för Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet. I den här enhetliga upplevelsen läggs kraftfulla funktioner som du kan komma åt i Säkerhetscenter för Microsoft 365.

Microsoft 365 Defender aktiveras automatiskt när berättigade kunder med behörighet besöker Säkerhetscenter för Microsoft 365. Läs den här artikeln om du vill förstå olika krav och hur Microsoft 365 Defender är etablerat.

## <a name="check-license-eligibility-and-required-permissions"></a>Kontrollera behörigheten för licensen och vilka behörigheter som krävs

En licens till en Microsoft 365-säkerhetsprodukt ger vanligtvis dig rätt att använda Microsoft 365 Defender i Microsoft 365 säkerhetscenter utan ytterligare licenskostnad. Vi rekommenderar att du skaffar en Microsoft 365 E5-, E5-säkerhetslicens, A5- eller A5-säkerhetslicens eller en giltig kombination av licenser som ger åtkomst till alla tjänster som stöds.

Mer detaljerad licensinformation finns [i licenskraven.](prerequisites.md#licensing-requirements)

### <a name="check-your-role"></a>Kontrollera din roll

Du måste vara **global administratör eller** **säkerhetsadministratör i** Azure Active Directory för att kunna aktivera Microsoft 365 Defender. [Visa dina roller i Azure AD](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Tjänster som stöds

Microsoft 365 Defender sammanställer data från de olika tjänster som stöds och som du redan har distribuerat. Den bearbetar och lagrar data centralt för att identifiera nya insikter och göra centraliserade svarsarbetsflöden möjliga. Det gör detta utan att befintliga distributioner, inställningar eller data som är kopplade till de integrerade tjänsterna påverkas.

För att få bästa skydd och optimera Microsoft 365 Defender rekommenderar vi att du distribuerar alla tillämpliga tjänster som stöds i nätverket. Mer information finns [i distribuera tjänster som stöds.](deploy-supported-services.md)

## <a name="onboard-to-the-service"></a>Introducera till tjänsten
Det är enkelt att komma igång med Microsoft 365 Defender. I navigeringsmenyn väljer du ett objekt under avsnittet Slutpunkter, till exempel Incidenter, Ärenden, Säkerhetscenter eller Hotanalys för att påbörja onboarding-processen. 

### <a name="data-center-location"></a>Datacenterplats

Microsoft 365 Defender lagrar och bearbetar data på samma [plats som används av Microsoft Defender för slutpunkt.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) Om du inte har Microsoft Defender för Endpoint väljs en ny datacenterplats automatiskt baserat på platsen för aktiva Microsoft 365-säkerhetstjänster. Den valda platsen för datacenter visas på skärmen.

Välj **Behöver du hjälp?** på Säkerhetscenter i Microsoft 365 om du vill kontakta Microsoft Support om etableringen av Microsoft 365 Defender på en annan datacenterplats.

> [!NOTE]
> Microsoft Defender för Slutpunkt tillhandahåller automatiskt datacenter i Europeiska unionen (EU) när det aktiveras via Azure Defender. Microsoft 365 Defender etablerar automatiskt i samma datacenter i EU för kunder som har etablerat Defender för Slutpunkt på det här sättet.

### <a name="confirm-that-the-service-is-on"></a>Bekräfta att tjänsten är på

När tjänsten har etablerats läggs följande till:

- [Incidenthantering](incidents-overview.md)
- [Varningskö](investigate-alerts.md)
- Ett åtgärdscenter för hantering [av automatiserad undersökning och svar](m365d-autoir.md)
- [Avancerade sökfunktioner](advanced-hunting-overview.md)
- Analys av hot

![Bild av navigeringsfönstret i Microsoft 365 Säkerhetscenter med Microsoft 365 Defender-funktioner Microsoft 365 Säkerhetscenter med incidenthantering och andra ](../../media/overview-incident.png)
 *Microsoft 365 Defender-funktioner*

### <a name="getting-microsoft-defender-for-identity-data"></a>Hämta Microsoft Defender för identitetsdata 
Om du vill aktivera integrering med Microsoft Cloud App Security måste du logga in på Microsoft Cloud App Security minst en gång.

## <a name="get-assistance"></a>Få hjälp

Läs vanliga frågor om hur du använder Microsoft 365 Defender i Vanliga frågor och svar om hur du får svar på de vanligaste frågorna om hur du använder Microsoft 365 [Defender.](m365d-enable-faq.md)

Microsofts supportpersonal kan hjälpa dig med att tillhandahålla eller återkalla tjänsten och relaterade resurser i klientorganisationen. Om du behöver hjälp väljer du Behöver du **hjälp?** i Säkerhetscenter för Microsoft 365. När du kontaktar supporten nämner du Microsoft 365 Defender.

## <a name="related-topics"></a>Relaterade ämnen

- [Vanliga frågor och svar](m365d-enable-faq.md)
- [Licenskrav och andra krav](prerequisites.md)
- [Distribuera tjänster som stöds](deploy-supported-services.md)
- [Översikt över Microsoft 365 Defender](microsoft-365-defender.md)
- [Översikt över Microsoft Defender för slutpunkt](../defender-endpoint/microsoft-defender-endpoint.md)
- [Översikt över Defender för Office 365](../office-365-security/defender-for-office-365.md)
- [Översikt över säkerhet i Microsoft Cloud App](/cloud-app-security/what-is-cloud-app-security)
- [Översikt över Microsoft Defender för identitet](/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender för slutpunktsdatalagring](../defender-endpoint/data-storage-privacy.md)
