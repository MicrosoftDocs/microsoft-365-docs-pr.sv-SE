---
title: Aktivera Microsoft Threat Protection i Microsoft 365-säkerhetscentret
description: Läs om hur du aktiverar Microsoft Threat Protection och börjar integrera säkerhetsincidenten och säkerhetssvaret.
keywords: komma igång, aktivera MTP, Microsoft Threat Protection, M365, säkerhet, dataplats, obligatoriska behörigheter, licensbehörighet, inställningssida
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
ms.openlocfilehash: fa970b28939ad43bf6a2717e603013277bc9130f
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42806482"
---
# <a name="turn-on-microsoft-threat-protection"></a>Aktivera Microsoft Threat Protection

**Gäller:**
- Skydd av Hot mot Microsoft

Microsoft Threat Protection förenar din incidentsvarsprocess genom att integrera nyckelfunktioner i Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security och Azure ATP. Den här enhetliga upplevelsen lägger till kraftfulla funktioner som du kan komma åt i Säkerhetscentret för Microsoft 365.

För att få bästa möjliga skydd och optimera Microsoft Threat Protection rekommenderar vi att du distribuerar alla tillämpliga tjänster som stöds i nätverket. Mer information [finns i om hur du distribuerar tjänster som stöds](deploy-supported-services.md).

## <a name="check-license-eligibility-and-required-permissions"></a>Kontrollera licensbehörighet och obligatoriska behörigheter
En Microsoft 365 E5-, E5-säkerhets- eller A5-licens eller en giltig kombination av licenser ger åtkomst till tjänster som stöds och ger dig rätt att använda Microsoft Threat Protection i Microsoft 365 security center.

För detaljerad [licensinformation, läs licenskraven](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Kontrollera din roll
Du måste vara en **global administratör** eller **säkerhetsadministratör** i Azure Active Directory för att aktivera Microsoft Threat Protection. [Visa dina roller i Azure AD](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a>Börja använda tjänsten
Microsoft Threat Protection sammanställer data från de olika integrerade tjänsterna. Det kommer att bearbeta och lagra data centralt för att identifiera nya insikter och göra centraliserade svararbetsflöden möjliga.

Innan du aktiverar tjänsten visas välkomstsidan för Microsoft 365[(security.microsoft.com](https://security.microsoft.com)) välkomstsidan för Microsoft Threat Protection när du väljer **Incidenter,** **Åtgärdscenter**eller **Jakt** från navigeringsfönstret. Dessa navigeringsalternativ visas inte om du inte är berättigad att använda Microsoft Threat Protection.

![Bild på välkomstsidan för Microsoft Threat Protection som visas](../../media/mtp-welcome.png)
om Microsoft Threat Protection inte har aktiverats på välkomstsidan för*Microsoft Threat Protection i Microsoft 365 security center*

Om du vill aktivera Microsoft Threat Protection slutför du bara processen från välkomstsidan. Du kan också aktivera Microsoft Threat Protection genom att komma åt **Inställningar** [(security.microsoft.com/settings)](https://security.microsoft.com/settings)i navigeringsfönstret och välja **Microsoft Threat Protection**.

>[!NOTE]
>Om du inte ser **Inställningar** i navigeringsfönstret eller inte kunde komma åt sidan kontrollerar du dina behörigheter och licenser.

### <a name="select-data-center-location"></a>Välj datacenterplats
Om Microsoft Defender ATP har etablerats för din organisation lagras och bearbetas data på samma datacenterplats som du har valt för [dina Microsoft Defender ATP-data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). Om du inte har Microsoft Defender ATP blir du ombedd att välja en ny datacenterplats specifikt för Microsoft Threat Protection. 

Du måste ge samtycke innan data delas mellan tjänster och aggregeras.

### <a name="confirm-that-the-service-is-on"></a>Bekräfta att tjänsten är på
När tjänsten har etablerats, lägger den till:

- [Hantering av incidenter](incidents-overview.md)
- Ett åtgärdscenter för hantering av [automatiserad utredning och svar](mtp-autoir.md)
- [Avancerad jaktkapacitet](advanced-hunting-overview.md)

![Bild av navigeringsfönstret i Microsoft 365](../../media/mtp-on.png)
security center med Microsoft Threat Protection har*Microsoft 365 security center med incidenthantering och andra Funktioner för Microsoft Threat Protection*

### <a name="getting-azure-atp-data"></a>Hämta Azure ATP-data
Om du vill dela Azure ATP-data med Microsoft Threat Protection kontrollerar du att Microsoft Cloud App Security och Azure ATP-integrering är aktiverat. [Läs mer om den här integrationen](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>Inaktivera Microsoft threat protection
Om du vill sluta använda Microsoft Threat Protection går du till **Inställningar** > **Microsoft Threat Protection** > **Opt-in / Opt-out** i Microsoft 365 security center. Avmarkera **Aktivera Microsoft Threat Protection** och spara ändringarna.

Motsvarande funktioner tas bort från Microsoft 365 security center.

## <a name="get-assistance"></a>Få hjälp

Microsofts supportpersonal kan hjälpa till att etablera eller avetablera tjänsten och relaterade resurser på din klientorganisation. Om du vill ha hjälp väljer du **Behöver du hjälp?** När du kontaktar supporten bör du nämna Microsoft Threat Protection.

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över Microsoft Threat Protection](microsoft-threat-protection.md)
- [Licenskrav och andra förutsättningar](prerequisites.md)
- [Distribuera tjänster som stöds](deploy-supported-services.md)
- [Översikt över Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Översikt över Office 365 ATP](../office-365-security/office-365-atp.md)
- [Översikt över Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Azure ATP-översikt](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender ATP-datalagring](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
