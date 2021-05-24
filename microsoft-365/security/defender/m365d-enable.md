---
title: Aktivera Microsoft 365 Defender i Microsoft 365 säkerhetscenter
description: Lär dig hur du aktiverar Microsoft 365 Defender och börjar integrera säkerhetstillbud och -svar.
keywords: komma igång, aktivera Microsoft 365 Defender, Microsoft 365 Defender, M365, säkerhet, dataplats, nödvändiga behörigheter, licensberättigande, inställningssidan
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
ms.openlocfilehash: 3d7564b5d509190c8c8e799c541bb0ca583097f1
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636236"
---
# <a name="turn-on-microsoft-365-defender"></a>Aktivera Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-365-defender.md) enhetligt din svarsprocess för incidenter genom att integrera nyckelfunktioner i Microsoft Defender för Slutpunkt, Microsoft Defender för Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet. Den här enhetliga upplevelsen lägger till kraftfulla funktioner som du kan komma åt Microsoft 365 säkerhetscenter.

Microsoft 365 Defender aktiveras automatiskt när berättigade kunder med den behörighet som krävs går till Microsoft 365 säkerhetscenter. Läs den här artikeln för att förstå olika krav och hur Microsoft 365 Defender etableras.

## <a name="check-license-eligibility-and-required-permissions"></a>Kontrollera behörigheten för licensen och vilka behörigheter som krävs

En licens till en Microsoft 365-säkerhetsprodukt ger vanligtvis dig rätt att använda Microsoft 365 Defender i Microsoft 365 säkerhetscenter utan ytterligare licenskostnad. Vi rekommenderar att du skaffar en Microsoft 365 E5, E5-säkerhet, A5- eller A5-säkerhetslicens eller en giltig kombination av licenser som ger åtkomst till alla tjänster som stöds.

Mer detaljerad licensinformation finns [i licenskraven.](prerequisites.md#licensing-requirements)

### <a name="check-your-role"></a>Kontrollera din roll

Du måste vara **global administratör eller** **säkerhetsadministratör i Azure Active Directory** kunna aktivera Microsoft 365 Defender. [Visa dina roller i Azure AD](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Tjänster som stöds

Microsoft 365 Defender sammanställer data från de olika tjänster som stöds och som du redan har distribuerat. Den bearbetar och lagrar data centralt för att identifiera nya insikter och göra centraliserade svarsarbetsflöden möjliga. Det gör detta utan att befintliga distributioner, inställningar eller data som är kopplade till de integrerade tjänsterna påverkas.

För att få bästa skydd och optimera Microsoft 365 Defender rekommenderar vi att du distribuerar alla tillämpliga tjänster som stöds i nätverket. Mer information finns [i distribuera tjänster som stöds.](deploy-supported-services.md)

## <a name="onboard-to-the-service"></a>Introducera till tjänsten
Det är enkelt att komma Microsoft 365 i Defender. I navigeringsmenyn väljer du valfri Microsoft 365 Defender-objekt, till exempel Incidenter, Ärenden, Åtgärdscenter eller Hotanalys för att påbörja onboarding-processen. 

### <a name="data-center-location"></a>Datacenterplats

Microsoft 365 Defender lagrar och bearbetar data på samma [plats som används av Microsoft Defender för Slutpunkt](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). Om du inte har Microsoft Defender för Endpoint väljs en ny datacenterplats automatiskt baserat på platsen för aktiva Microsoft 365 säkerhetstjänster. Den valda platsen för datacenter visas på skärmen.

Välj **Behöver du hjälp?** på Microsoft 365 om du vill kontakta Microsoft Support om etablering Microsoft 365 Defender på en annan datacenterplats.

> [!NOTE]
> Microsoft Defender för Slutpunkt tillhandahåller automatiskt datacenter i Europeiska unionen (EU) när det aktiveras via Azure Defender. Microsoft 365 Defender etablerar automatiskt i samma datacenter i EU för kunder som har etablerat Defender för Slutpunkt på det här sättet.

### <a name="confirm-that-the-service-is-on"></a>Bekräfta att tjänsten är på

När tjänsten har etablerats läggs följande till:

- [Incidenthantering](incidents-overview.md)
- [Varningskö](investigate-alerts.md)
- Ett åtgärdscenter för hantering [av automatiserad undersökning och svar](m365d-autoir.md)
- [Avancerade sökfunktioner](advanced-hunting-overview.md)
- Analys av hot

![Bild av Microsoft 365 säkerhetscenter-navigeringsfönstret med Microsoft 365 Defender Microsoft 365 säkerhetscenter med incidenthantering och andra ](../../media/overview-incident.png)
 *Microsoft 365 Defender-funktioner*

### <a name="getting-microsoft-defender-for-identity-data"></a>Hämta Microsoft Defender för identitetsdata 
Om du vill aktivera Microsoft Cloud App Security måste du logga in på Microsoft Cloud App Security minst en gång.

## <a name="get-assistance"></a>Få hjälp

Läs vanliga frågor om hur du slår på Microsoft 365 Defender i Vanliga frågor [och svar.](m365d-enable-faq.md)

Microsofts supportpersonal kan hjälpa dig med att tillhandahålla eller återkalla tjänsten och relaterade resurser i klientorganisationen. Om du behöver hjälp väljer du Behöver du **hjälp?** Microsoft 365 säkerhetscenter. När du kontaktar supporten kan du Microsoft 365 Defender.

## <a name="related-topics"></a>Relaterade ämnen

- [Vanliga frågor och svar](m365d-enable-faq.md)
- [Licenskrav och andra krav](prerequisites.md)
- [Distribuera tjänster som stöds](deploy-supported-services.md)
- [Microsoft 365 Defender-översikt](microsoft-365-defender.md)
- [Översikt över Microsoft Defender för slutpunkt](../defender-endpoint/microsoft-defender-endpoint.md)
- [Översikt över Office 365 Defender](../office-365-security/defender-for-office-365.md)
- [Microsoft Cloud App Security översikt](/cloud-app-security/what-is-cloud-app-security)
- [Översikt över Microsoft Defender för identitet](/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender för slutpunktsdatalagring](../defender-endpoint/data-storage-privacy.md)
