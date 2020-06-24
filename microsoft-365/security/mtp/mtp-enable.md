---
title: Aktivera Microsoft Threat Protection i Microsoft 365-säkerhetscentret
description: Lär dig hur du aktiverar Microsoft Threat Protection och börjar integrera din säkerhetsincident och ditt säkerhetssvar.
keywords: komma igång, aktivera MTP, Microsoft Threat Protection, M365, säkerhet, dataplats, nödvändiga behörigheter, licensberättigande, inställningssida
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
ms.openlocfilehash: 0badae0d81b52b89c47f950b889109d4b9d35dda
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844614"
---
# <a name="turn-on-microsoft-threat-protection"></a>Aktivera Microsoft Hotskydd

**Gäller:**
- Microsoft Hotskydd

[Microsoft Threat Protection](microsoft-threat-protection.md) förenar din incidentsvarsprocess genom att integrera viktiga funktioner i Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security och Azure ATP. Den här enhetliga upplevelsen ger dig kraftfulla funktioner som du kan komma åt i Microsoft 365-säkerhetscentret.

Microsoft Threat Protection aktiveras automatiskt när berättigade kunder med de behörigheter som krävs besöker Microsoft 365-säkerhetscenter. Läs den här artikeln om du vill förstå olika förutsättningar och hur Microsoft Threat Protection etableras.

## <a name="check-license-eligibility-and-required-permissions"></a>Kontrollera behörighet för licenser och nödvändiga behörigheter
En licens till en Microsoft 365-säkerhetsprodukt ger dig i allmänhet rätt att använda Microsoft Threat Protection i Microsoft 365-säkerhetscenter utan extra licenskostnader. Vi rekommenderar att du skaffar en Microsoft 365 E5-, E5 Security-, A5- eller A5-säkerhetslicens eller en giltig kombination av licenser som ger åtkomst till alla tjänster som stöds.

Detaljerad licensinformation [finns i licenskraven](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Kontrollera din roll
Du måste vara **global administratör** eller **säkerhetsadministratör** i Azure Active Directory för att kunna aktivera Microsoft Threat Protection. [Visa dina roller i Azure AD](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Tjänster som stöds
Microsoft Threat Protection sammanställer data från de olika tjänster som stöds som du redan har distribuerat. Det kommer att bearbeta och lagra data centralt för att identifiera nya insikter och göra centraliserade svarsarbetsflöden möjliga. Det gör detta utan att påverka befintliga distributioner, inställningar eller data som är associerade med de integrerade tjänsterna.

För att få bästa möjliga skydd och optimera Microsoft Threat Protection rekommenderar vi att du distribuerar alla tillämpliga tjänster som stöds i nätverket. Mer information [finns i om hur du distribuerar tjänster som stöds](deploy-supported-services.md).

## <a name="before-starting-the-service"></a>Innan du påbörjar tjänsten
Innan du aktiverar tjänsten visar Microsoft 365-säkerhetscentret ([security.microsoft.com](https://security.microsoft.com)) sidan Microsoft Threat Protection-inställning när du väljer **Incidenter,** **Åtgärdscenter**eller **Jakt** i navigeringsfönstret. Dessa navigeringsobjekt visas inte om du inte kan använda Microsoft Threat Protection.

![Bild av inställningssidan för Microsoft Threat Protection som visas om Microsoft Threat Protection inte har aktiverats i ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft Threat Protection-inställningarna i Microsoft 365-säkerhetscenter*

## <a name="starting-the-service"></a>Starta tjänsten
Om du vill aktivera Microsoft Threat Protection väljer du Aktivera **Microsoft Threat Protection** och tillämpar ändringen. Du kan också komma åt det här alternativet genom att välja **Inställningar** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) i navigeringsfönstret och sedan välja **Microsoft Threat Protection**.

>[!NOTE]
>Om du inte ser **Inställningar** i navigeringsfönstret eller inte kunde komma åt sidan kontrollerar du dina behörigheter och licenser.

### <a name="data-center-location"></a>Plats för datacenter
Microsoft Threat Protection lagrar och bearbetar data på [samma plats som används av Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). Om du inte har Microsoft Defender ATP väljs en ny datacenterplats automatiskt baserat på platsen för aktiva Microsoft 365-säkerhetstjänster. Den valda datacenterplatsen visas på skärmen.

>[!NOTE]
>Välj **Behöver du hjälp?** i Microsoft 365-säkerhetscentret för att kontakta Microsoft-supporten om microsoft threat protection på en annan datacenterplats. 

### <a name="confirm-that-the-service-is-on"></a>Bekräfta att tjänsten är aktiverad
När tjänsten har etablerats läggs den till:

- [Hantering av incidenter](incidents-overview.md)
- Ett åtgärdscenter för hantering av [automatisk undersökning och svar](mtp-autoir.md)
- [Avancerad jaktkapacitet](advanced-hunting-overview.md)

![Bild av navigeringsfönstret i Microsoft 365 security center med Microsoft Threat Protection-funktioner ](../../media/mtp-enable/mtp-on.png)
 *i Microsoft 365-säkerhetscenter med incidenthantering och andra funktioner för Microsoft Threat Protection*

### <a name="getting-azure-atp-data"></a>Hämta Azure ATP-data
Om du vill dela Azure ATP-data med Microsoft Threat Protection kontrollerar du att Microsoft Cloud App Security och Azure ATP-integrering är aktiverat. [Läs mer om den här integrationen](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>Inaktivera Microsoft Threat Protection
Om du vill sluta använda Microsoft Threat Protection går du till **Inställningar**  >  **microsoft threat protection**  >  **opt-in / opt-out** i Microsoft 365 security center. Avmarkera **Aktivera Microsoft Threat Protection** och tillämpa ändringarna.

Motsvarande funktioner kommer att tas bort från Microsoft 365 säkerhetscenter.

## <a name="get-assistance"></a>Få hjälp

Om du vill ha svar på de vanligaste frågorna om hur du aktiverar Microsoft Threat Protection [läser du vanliga frågor och svar](mtp-enable-faq.md).

Microsofts supportpersonal kan hjälpa till att etablera eller avetablera tjänsten och relaterade resurser på din klientorganisation. Om du behöver hjälp väljer du **Behöver du hjälp?** NÃ¤s Ã¤n ã¤nder du support nÃ¤nder du Microsoft Threat Protection.

## <a name="related-topics"></a>Relaterade ämnen

- [Vanliga frågor och svar](mtp-enable-faq.md)
- [Licenskrav och andra förutsättningar](prerequisites.md)
- [Distribuera tjänster som stöds](deploy-supported-services.md)
- [Översikt över Microsoft Threat Protection](microsoft-threat-protection.md)
- [Översikt över Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Översikt över Office 365 ATP](../office-365-security/office-365-atp.md)
- [Översikt över Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Översikt över Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender ATP-datalagring](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)