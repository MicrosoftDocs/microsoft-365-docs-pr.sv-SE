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
ms.openlocfilehash: 9a57929e42f08db8abda170c889441d3a50ade72
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209253"
---
# <a name="turn-on-microsoft-threat-protection"></a>Aktivera Microsoft Hotskydd

**Gäller:**
- Microsoft Hotskydd

Microsoft Threat Protection förenar din incidentsvarsprocess genom att integrera nyckelfunktioner i Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security och Azure ATP. Den här enhetliga upplevelsen ger dig kraftfulla funktioner som du kan komma åt i Microsoft 365-säkerhetscentret.

För att få bästa möjliga skydd och optimera Microsofts hotskydd rekommenderar vi att du distribuerar alla tillämpliga tjänster som stöds i nätverket. Mer information [finns i om hur du distribuerar tjänster som stöds](deploy-supported-services.md).

## <a name="check-license-eligibility-and-required-permissions"></a>Kontrollera behörighet för licenser och nödvändiga behörigheter
En Microsoft 365 E5-, E5 Security-, A5- eller A5-säkerhetslicens eller en giltig kombination av licenser ger åtkomst till tjänster som stöds och ger dig rätt att använda Microsoft Threat Protection i Microsoft 365-säkerhetscenter utan ytterligare licenskostnader.

Detaljerad licensinformation [finns i licenskraven](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Kontrollera din roll
Du måste vara **global administratör** eller **säkerhetsadministratör** i Azure Active Directory för att kunna aktivera Microsoft Threat Protection. [Visa dina roller i Azure AD](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a>Börja använda tjänsten

>[!IMPORTANT]
>Från och med den 12 maj 2020 kommer Microsoft gradvis att lansera nya, optimerade upplevelser kring [licenskrav](prerequisites.md#licensing-requirements) och aktivera Microsoft Threat Protection. Under flera veckor under denna period kommer vissa kunder att börja se ändringar i sina portalupplevelser. Information om de nya upplevelserna markeras **Ny upplevelse** i den här artikeln.

Microsoft Threat Protection sammanställer data från de olika integrerade tjänsterna. Det kommer att bearbeta och lagra data centralt för att identifiera nya insikter och göra centraliserade svarsarbetsflöden möjliga. Det gör detta utan att påverka befintliga distributioner, inställningar eller data som är associerade med de integrerade tjänsterna.

Innan du aktiverar tjänsten visar Microsoft 365-säkerhetscentret ([security.microsoft.com](https://security.microsoft.com)) välkomstsidan för Microsoft Threat Protection när du väljer **Incidenter,** **Åtgärdscenter**eller **Jakt** i navigeringsfönstret. Dessa navigeringsalternativ visas inte om du inte kan använda Microsoft Threat Protection.

![Bild av välkomstsidan för Microsoft Threat Protection som visas om Microsoft Threat Protection inte har aktiverats på ](../../media/mtp-welcome.png)
 *välkomstsidan för Microsoft Threat Protection i Microsoft 365-säkerhetscenter*

Om du vill aktivera Microsoft Threat Protection slutför du helt enkelt processen från välkomstsidan. Du kan också aktivera Microsoft Threat Protection genom att komma åt **Inställningar** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) i navigeringsfönstret och välja **Microsoft Threat Protection**.

>[!NOTE]
>Om du inte ser **Inställningar** i navigeringsfönstret eller inte kunde komma åt sidan kontrollerar du dina behörigheter och licenser.

### <a name="select-data-center-location"></a>Välj datacenterplats
Om Microsoft Defender ATP har etablerats för din organisation lagras och bearbetas data på samma datacenterplats som du har valt för [microsoft Defender ATP-data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). Om du inte har Microsoft Defender ATP blir du ombedd att välja en ny datacenterplats specifikt för Microsoft Threat Protection. 
 
Du måste ge ditt samtycke innan data delas mellan tjänster och aggregeras.

**Ny erfarenhet:** Från och med den 12 maj 2020 kommer kunderna gradvis att få ändringar i den här upplevelsen. För dem med den nya upplevelsen väljer tjänsten automatiskt den optimala datacenterplatsen för dina aggregerade data baserat på dina befintliga Microsoft 365-säkerhetstjänster. Den valda datacenterplatsen visas på skärmen.

### <a name="confirm-that-the-service-is-on"></a>Bekräfta att tjänsten är aktiverad
När tjänsten har etablerats läggs följande till:

- [Hantering av incidenter](incidents-overview.md)
- Ett åtgärdscenter för hantering av [automatisk undersökning och svar](mtp-autoir.md)
- [Avancerad jaktkapacitet](advanced-hunting-overview.md)

![Bild av navigeringsfönstret i Microsoft 365 security center med Microsoft Threat Protection-funktioner ](../../media/mtp-on.png)
 *i Microsoft 365-säkerhetscenter med incidenthantering och andra funktioner för Microsoft Threat Protection*

### <a name="getting-azure-atp-data"></a>Hämta Azure ATP-data
Om du vill dela Azure ATP-data med Microsoft Threat Protection kontrollerar du att Microsoft Cloud App Security och Azure ATP-integrering är aktiverat. [Läs mer om den här integrationen](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>Inaktivera Microsoft Threat Protection
Om du vill sluta använda Microsoft Threat Protection går du till **Inställningar**  >  **microsoft threat protection**  >  **opt-in / opt-out** i Microsoft 365 security center. Avmarkera **Aktivera Microsoft Threat Protection** och spara ändringarna.

Motsvarande funktioner tas bort från Microsoft 365-säkerhetscentret.

## <a name="get-assistance"></a>Få hjälp

Microsofts supportpersonal kan hjälpa till att etablera eller avetablera tjänsten och relaterade resurser på din klientorganisation. Om du behöver hjälp väljer du **Behöver du hjälp?** NÃ¤s ã¤nder du support nÃ¤nder du Microsoft Threat Protection.

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över Microsofts hotskydd](microsoft-threat-protection.md)
- [Licenskrav och andra förutsättningar](prerequisites.md)
- [Distribuera tjänster som stöds](deploy-supported-services.md)
- [Översikt över Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Översikt över Office 365 ATP](../office-365-security/office-365-atp.md)
- [Översikt över Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Översikt över Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender ATP-datalagring](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)