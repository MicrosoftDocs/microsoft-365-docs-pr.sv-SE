---
title: Aktivera Microsoft 365 Defender i Microsoft 365 säkerhets Center
description: Lär dig hur du aktiverar Microsoft 365 Defender och hur du integrerar dina säkerhets tillbud och svar.
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
ms.openlocfilehash: c5b8cae9e4eabcb2b3c6a7eb76971784193a221d
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920508"
---
# <a name="turn-on-microsoft-365-defender"></a>Aktivera Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Med [microsoft 365 Defender](microsoft-threat-protection.md) interagerar samtals processen med att integrera viktiga funktioner i Microsoft Defender för slut punkt, Microsoft Defender för Office 365, Microsoft Cloud App Security och Microsoft Defender för identiteten. Denna enhetliga upplevelse lägger till kraftfulla funktioner som du kan komma åt i Microsoft 365 Security Center.

Microsoft 365 Defender aktive ras automatiskt när berättigade kunder med nödvändig behörighet gå till Microsoft 365 säkerhets Center. Läs den här artikeln för att förstå olika förutsättningar och hur Microsoft 365 Defender etableras.

## <a name="check-license-eligibility-and-required-permissions"></a>Kontrol lera licens krav och nödvändiga behörigheter
Med en licens till en Microsoft 365-säkerhetsprodukt får du i allmänhet rätt att använda Microsoft 365 Defender i Microsoft 365 säkerhets Center utan extra licens kostnad. Vi rekommenderar att få en Microsoft 365 E5-, E5-säkerhet, A5-eller A5-säkerhetslicens eller en giltig kombination av licenser som ger till gång till alla tjänster som stöds.

Mer detaljerad information om licensiering finns [i licens kraven](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Kontrol lera din roll
Du måste vara **Global administratör** eller **säkerhets administratör** i Azure Active Directory för att aktivera Microsoft 365 Defender. [Visa dina roller i Azure AD](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Tjänster som stöds
Microsoft 365 Defender sammanställer data från de tjänster som du redan har distribuerat. Den bearbetar och lagrar data centralt för att identifiera nya insikter och göra centraliserade arbets flöden möjligt. Det gör det utan att befintliga distributioner, inställningar eller data som är kopplade till de integrerade tjänsterna påverkas.

För att få bästa möjliga skydd och optimera Microsoft 365 Defender rekommenderar vi att du distribuerar alla tillämpliga tjänster som stöds i ditt nätverk. Mer information finns i [om att distribuera tjänster som stöds](deploy-supported-services.md).

## <a name="before-starting-the-service"></a>Innan tjänsten startas
Innan du aktiverar tjänsten visar Microsoft 365 säkerhets Center ( [Security.Microsoft.com](https://security.microsoft.com)) sidan Microsoft 365 Defender-inställningar när du väljer **händelser** , **Åtgärds Center** eller **jakt** från navigerings fönstret. Dessa navigerings objekt visas inte om du inte är berättigad att använda Microsoft 365 Defender.

![Bild av sidan Microsoft 365 Defender-inställningar som visas om Microsoft 365 Defender inte har Aktiver ATS på ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft 365 Defender-inställningar i Microsoft 365 säkerhets Center*

## <a name="starting-the-service"></a>Startar tjänsten
För att aktivera Microsoft 365 Defender väljer du **Aktivera microsoft 365 Defender** och gör ändringarna. Du kan också komma åt det här alternativet genom att välja **Inställningar** ( [Security.Microsoft.com/settings](https://security.microsoft.com/settings)) i navigerings fönstret och sedan välja **Microsoft 365 Defender**.

>[!NOTE]
>Om du inte ser **Inställningar** i navigerings fönstret eller inte har åtkomst till sidan kontrollerar du dina behörigheter och licenser.

### <a name="data-center-location"></a>Plats för data Center
Microsoft 365 Defender lagrar och bearbetar data på [samma plats som Microsoft Defender för slut punkten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). Om du inte har Microsoft Defender för slut punkt väljs en ny data Center-plats automatiskt baserat på platsen för Active Microsoft 365-säkerhetstjänster. Den valda data Center platsen visas på skärmen. 

Välj **behöver du hjälp?** i Microsoft 365 Security Center kan du kontakta Microsoft support om hur du konfigurerar Microsoft 365 Defender på en annan plats i data centret. 

>[!NOTE]
>Microsoft Defender för slut punkt tillhandahåller automatiskt bestämmelser i EU-datacenter när de aktive ras via Azure Defender. Microsoft 365 Defender tillhandahåller automatiskt samma EU-datacentertjänster för kunder som har etablerat Defender för slut punkt på det här sättet. 

### <a name="confirm-that-the-service-is-on"></a>Kontrol lera att tjänsten är på
När tjänsten har etablerats lägger den till:

- [Hantering av incidenter](incidents-overview.md)
- Ett åtgärds Center för att hantera [Automatisk undersökning och svar](mtp-autoir.md)
- [Avancerade jakt](advanced-hunting-overview.md) funktioner

![Bild av navigerings fönstret i Microsoft 365 säkerhets Center med Microsoft 365 Defender funktioner ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 säkerhets Center med problem hantering och andra Microsoft 365 Defender-funktioner*

### <a name="getting-microsoft-defender-for-identity-data"></a>Microsoft Defender för identitets data
Om du vill dela Microsoft Defender för identitets data med Microsoft 365 Defender kontrollerar du att säkerhet för Microsoft Cloud App och Microsoft Defender för identitets integrering är aktiverat. [Läs mer om denna integrering](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-365-defender"></a>Inaktivera Microsoft 365 Defender
Om du vill sluta använda Microsoft 365 Defender går du till **Inställningar**  >  **Microsoft 365 Defender** och väljer att  >  **välja ut** i Microsoft 365 säkerhets Center. Avmarkera **aktivera Microsoft 365 Defender** och tillämpa ändringarna.

Motsvarande funktioner tas bort från Microsoft 365 säkerhets Center.

## <a name="get-assistance"></a>Få hjälp

Om du vill få svar på de vanligaste frågorna om att aktivera Microsoft 365 Defender [läser du vanliga frågor och svar](mtp-enable-faq.md).

Microsofts support personal kan tillhandahålla eller avetablera tjänsten och relaterade resurser för din klient organisation. För mer information, Välj **behöver du hjälp?** i Microsoft 365 Security Center. När du kontaktar supporten, omnämnande Microsoft 365 Defender.

## <a name="related-topics"></a>Relaterade ämnen

- [Vanliga frågor och svar](mtp-enable-faq.md)
- [Licens krav och andra förutsättningar](prerequisites.md)
- [Distribuera tjänster som stöds](deploy-supported-services.md)
- [Översikt över Microsoft 365 Defender](microsoft-threat-protection.md)
- [Översikt över Microsoft Defender för slut punkter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Översikt över Defender för Office 365](../office-365-security/office-365-atp.md)
- [Säkerhets översikt för Microsoft Cloud App](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Microsoft Defender för identitets översikt](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender för slut punkts data lagring](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
