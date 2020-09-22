---
title: Aktivera skydd mot Microsoft Threat i säkerhets Center för Microsoft 365
description: Lär dig hur du aktiverar skydd mot Microsoft Threats och hur du integrerar dina säkerhets tillbud och svar.
keywords: komma igång, aktivera MTP, Microsoft Threat Protection, M365, säkerhet, data plats, behörigheter, licens kvalificering, sidan Inställningar
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 65e3a2609bc41ddeda95134874e5873e184a2a54
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201165"
---
# <a name="turn-on-microsoft-threat-protection"></a>Aktivera Microsoft Hotskydd

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Hotskydd

[Skydd mot Microsoft-hotet](microsoft-threat-protection.md) interagerar med att integrera viktiga funktioner i Microsoft Defender Avancerat skydd (ATP), Office 365 ATP, Microsoft Cloud App Security och Azure ATP. Denna enhetliga upplevelse lägger till kraftfulla funktioner som du kan komma åt i Microsoft 365 Security Center.

Skydd mot Microsoft Threat aktive ras automatiskt när berättigade kunder med nödvändig behörighet gå till Microsoft 365 säkerhets Center. Läs den här artikeln för att förstå olika förutsättningar och hur Microsoft Threat Protection etableras.

## <a name="check-license-eligibility-and-required-permissions"></a>Kontrol lera licens krav och nödvändiga behörigheter
En licens till en Microsoft 365-säkerhetsprodukt ger generellt rätt att använda Microsoft Threat Protection i Microsoft 365 säkerhets Center utan extra licens kostnad. Vi rekommenderar att få en Microsoft 365 E5-, E5-säkerhet, A5-eller A5-säkerhetslicens eller en giltig kombination av licenser som ger till gång till alla tjänster som stöds.

Mer detaljerad information om licensiering finns [i licens kraven](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Kontrol lera din roll
Du måste vara **Global administratör** eller **säkerhets administratör** i Azure Active Directory för att aktivera skydd mot Microsoft Threat. [Visa dina roller i Azure AD](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Tjänster som stöds
Microsoft Threat Protection samlar data från olika tjänster som du redan har distribuerat. Den bearbetar och lagrar data centralt för att identifiera nya insikter och göra centraliserade arbets flöden möjligt. Det gör det utan att befintliga distributioner, inställningar eller data som är kopplade till de integrerade tjänsterna påverkas.

För att få bästa möjliga skydd och optimera Microsoft Threat Protection rekommenderar vi att du distribuerar alla tillämpliga tjänster som stöds på ditt nätverk. Mer information finns i [om att distribuera tjänster som stöds](deploy-supported-services.md).

## <a name="before-starting-the-service"></a>Innan tjänsten startas
Innan du aktiverar tjänsten visar Microsoft 365 säkerhets Center ([Security.Microsoft.com](https://security.microsoft.com)) Sidan skydds inställningar för Microsoft Threat när du väljer **händelser**, **Åtgärds Center**eller **jakt** från navigerings fönstret. Dessa navigerings objekt visas inte om du inte är behörig att använda skydd mot Microsoft Threat.

![Bild av sidan Microsoft Threat Protection Settings som visas om Microsoft Threat Protection inte har Aktiver ATS för ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft Threat Protection-inställningar i Microsoft 365 Security Center*

## <a name="starting-the-service"></a>Startar tjänsten
Om du vill aktivera skyddet mot Microsoft Threats väljer du **aktivera Microsoft Threat Protection** och tillämpa ändringen. Du kan också komma åt det här alternativet genom att välja **Inställningar** ([Security.Microsoft.com/settings](https://security.microsoft.com/settings)) i navigerings fönstret och sedan välja **Microsoft Threat Protection**.

>[!NOTE]
>Om du inte ser **Inställningar** i navigerings fönstret eller inte har åtkomst till sidan kontrollerar du dina behörigheter och licenser.

### <a name="data-center-location"></a>Plats för data Center
Microsoft Threat Protection lagrar och bearbetar data på [samma plats som Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). Om du inte har Microsoft Defender ATP, väljs automatiskt en ny data Center plats som baseras på platsen för den aktiva Microsoft 365-säkerhetstjänsten. Den valda data Center platsen visas på skärmen. 

Välj **behöver du hjälp?** i Microsoft 365 säkerhets Center kan du kontakta Microsoft support om att tillhandahålla Microsoft Threat Protection på en annan plats i data centret. 

>[!NOTE]
>Microsoft Defender ATP tillhandahåller automatiskt bestämmelser i EU-datacenter när de aktive ras via Azure Security Center. Microsoft Threat Protection tillhandahåller automatiskt samma EU-datacenter för kunder som har etablerat Microsoft Defender ATP på det här sättet. 

### <a name="confirm-that-the-service-is-on"></a>Kontrol lera att tjänsten är på
När tjänsten har etablerats lägger den till:

- [Hantering av incidenter](incidents-overview.md)
- Ett åtgärds Center för att hantera [Automatisk undersökning och svar](mtp-autoir.md)
- [Avancerade jakt](advanced-hunting-overview.md) funktioner

![Bild av navigerings fönstret i Microsoft 365 säkerhets Center med Microsoft Threat Protection ](../../media/mtp-enable/mtp-on.png)
 *, Microsoft 365 säkerhets Center med problem hantering och andra hot Protection-funktioner från Microsoft*

### <a name="getting-azure-atp-data"></a>Hämta data för Azure ATP
Om du vill dela Azure ATP-data med Microsoft Threat Protection kontrollerar du att Microsoft Cloud App Security och Azure ATP-integreringen är aktiverat. [Läs mer om denna integrering](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>Inaktivera skydd mot Microsoft Threat
Om du vill sluta använda skydd mot Microsoft kan du gå till **Inställningar**  >  **Microsoft Threat Protection**  >  **och välja bort** Microsoft 365 säkerhets Center. Avmarkera **aktivera Microsoft Threat Protection** och tillämpa ändringarna.

Motsvarande funktioner tas bort från Microsoft 365 säkerhets Center.

## <a name="get-assistance"></a>Få hjälp

Om du vill få svar på de vanligaste frågorna om att aktivera skydd mot Microsoft Threat kan du [läsa vanliga frågor och svar](mtp-enable-faq.md).

Microsofts support personal kan tillhandahålla eller avetablera tjänsten och relaterade resurser för din klient organisation. För mer information, Välj **behöver du hjälp?** i Microsoft 365 Security Center. När du kontaktar supporten kan du nämna Microsoft Threat Protection.

## <a name="related-topics"></a>Relaterade ämnen

- [Vanliga frågor och svar](mtp-enable-faq.md)
- [Licens krav och andra förutsättningar](prerequisites.md)
- [Distribuera tjänster som stöds](deploy-supported-services.md)
- [Microsoft Threat Protection-översikt](microsoft-threat-protection.md)
- [Översikt över Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Office 365 ATP-översikt](../office-365-security/office-365-atp.md)
- [Säkerhets översikt för Microsoft Cloud App](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Översikt över Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender ATP-data lagring](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
