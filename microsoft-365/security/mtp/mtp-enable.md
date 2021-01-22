---
title: Aktivera Microsoft 365 Defender i Säkerhetscenter för Microsoft 365
description: Lär dig hur du aktiverar Microsoft 365 Defender och börjar integrera säkerhetshändelsen och svaret.
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 19f035a271626077911b05082a4aba6d67355cdb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930228"
---
# <a name="turn-on-microsoft-365-defender"></a>Aktivera Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-threat-protection.md) ger en enhetlig svarsprocess för incidenter genom att integrera nyckelfunktioner i Microsoft Defender för Endpoint, Microsoft Defender för Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet. Den här enhetliga upplevelsen ger kraftfulla funktioner som du kan komma åt i Säkerhetscenter för Microsoft 365.

Microsoft 365 Defender aktiveras automatiskt när berättigade kunder med rätt behörighet besöker Microsoft 365 säkerhetscenter. Läs den här artikeln för att förstå olika krav och hur Microsoft 365 Defender etableras.

## <a name="check-license-eligibility-and-required-permissions"></a>Kontrollera behörigheten för licensen och de behörigheter som krävs

En licens till en Microsoft 365-säkerhetsprodukt ger vanligtvis dig rätt att använda Microsoft 365 Defender i Microsoft 365 säkerhetscenter utan ytterligare licenskostnad. Vi rekommenderar att du skaffar en Microsoft 365 E5-, E5-säkerhets-, A5- eller A5-säkerhetslicens eller en giltig kombination av licenser som ger tillgång till alla tjänster som stöds.

Om du vill ha detaljerad [licensinformation läser du licenskraven.](prerequisites.md#licensing-requirements)

### <a name="check-your-role"></a>Kontrollera din roll

Du måste vara **global administratör eller** **säkerhetsadministratör i** Azure Active Directory för att kunna aktivera Microsoft 365 Defender. [Visa dina roller i Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Tjänster som stöds

Microsoft 365 Defender sammanställer data från de olika tjänster som stöds och som du redan har distribuerat. Den kommer att bearbeta och lagra data centralt för att identifiera nya insikter och göra centraliserade svarsarbetsflöden möjliga. Det gör detta utan att påverka befintliga distributioner, inställningar eller data som är kopplade till de integrerade tjänsterna.

För att få bästa skydd och optimera Microsoft 365 Defender rekommenderar vi att du distribuerar alla tillämpliga tjänster som stöds i nätverket. Mer information finns i [om hur du distribuerar tjänster som stöds.](deploy-supported-services.md)

## <a name="before-starting-the-service"></a>Innan tjänsten startas

Innan du aktiverar tjänsten visas inställningssidan i Microsoft 365 Säkerhetscenter[(security.microsoft.com)](https://security.microsoft.com)i Microsoft 365 Defender  när du väljer Incidenter, Åtgärdscenter eller Jagning i navigeringsfönstret.  De här navigeringsobjekten visas inte om du inte är berättigad att använda Microsoft 365 Defender.

![Bild på inställningssidan för Microsoft 365 Defender som visas om Microsoft 365 Defender inte har aktiverats i inställningarna för ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft 365 Defender i Säkerhetscenter för Microsoft 365*

## <a name="starting-the-service"></a>Starta tjänsten

Om du vill aktivera Microsoft 365 Defender väljer du **Aktivera Microsoft 365 Defender** och tillämpa ändringen. Du kan också öppna  det här alternativet genom att välja Inställningar [(security.microsoft.com/settings)](https://security.microsoft.com/settings)i navigeringsfönstret och sedan **välja Microsoft 365 Defender.**

> [!NOTE]
> Om du inte ser Inställningar **i** navigeringsfönstret eller inte kunde komma åt sidan kontrollerar du dina behörigheter och licenser.

### <a name="data-center-location"></a>Datacenterplats

Microsoft 365 Defender lagrar och bearbetar data på samma plats som [används av Microsoft Defender för Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) Om du inte har Microsoft Defender för Slutpunkt väljs en ny datacenterplats automatiskt utifrån var aktiva Microsoft 365-säkerhetstjänster finns. Den valda platsen för datacentret visas på skärmen.

Välj **Behöver du hjälp?** i Säkerhetscenter för Microsoft 365 om du vill kontakta Microsofts support om etablering av Microsoft 365 Defender på en annan datacenterplats.

> [!NOTE]
> Microsoft Defender för Slutpunkt tillhandahåller automatiskt datacenter i Europeiska unionen (EU) när det aktiveras via Azure Defender. Microsoft 365 Defender etablerar automatiskt i samma DATACENTER i EU för kunder som har etablerat Defender för Endpoint på det här sättet.

### <a name="confirm-that-the-service-is-on"></a>Bekräfta att tjänsten är på

När tjänsten har etablerats lägger den till:

- [Incidenthantering](incidents-overview.md)
- Ett åtgärdscenter för hantering [av automatiserad undersökning och svar](mtp-autoir.md)
- [Avancerade sökfunktioner](advanced-hunting-overview.md)

![Bild av navigeringsfönstret i Microsoft 365 Säkerhetscenter med Microsoft 365 Defender-funktionerna i Microsoft 365 Säkerhetscenter med incidenthantering och andra ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 Defender-funktioner*

### <a name="getting-microsoft-defender-for-identity-data"></a>Hämta Microsoft Defender för identitetsdata

Om du vill dela Microsoft Defender för identitetsdata med Microsoft 365 Defender ska du se till att Microsoft Cloud App Security och Microsoft Defender för identitetsintegrering är aktiverat. [Läs mer om den här integreringen.](https://docs.microsoft.com/cloud-app-security/mdi-integration)

## <a name="get-assistance"></a>Få hjälp

Läs vanliga frågor och svar om hur du använder Microsoft 365 [Defender.](mtp-enable-faq.md)

Microsofts supportpersonal kan hjälpa till att tillhandahålla eller återkalla tjänsten och relaterade resurser i klientorganisationen. Behöver du hjälp väljer **du Behöver du hjälp?** i Säkerhetscenter för Microsoft 365. När du kontaktar supporten kan du nämna Microsoft 365 Defender.

## <a name="related-topics"></a>Relaterade ämnen

- [Vanliga frågor och svar](mtp-enable-faq.md)
- [Licenskrav och andra förutsättningar](prerequisites.md)
- [Distribuera tjänster som stöds](deploy-supported-services.md)
- [Översikt över Microsoft 365 Defender](microsoft-threat-protection.md)
- [Översikt över Microsoft Defender för slutpunkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Översikt över Defender för Office 365](../office-365-security/office-365-atp.md)
- [Översikt över säkerhet i Microsoft Cloud App](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Översikt över Microsoft Defender för identitet](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender för lagring av slutpunktsdata](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
