---
title: Distribuera säkerhetsfunktioner för Windows 10 Enterprise
description: Ger vägledning på hög nivå om de steg du behöver för att distribuera säkerhetsfunktioner för Windows 10 Enterprise på datorer som en del av Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-dokumentation, Windows 10 Enterprise, säkerhet
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: 5407370933c2a99781adf4ca58d3fa905328ed04
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42808978"
---
# <a name="step-5-deploy-windows-10-enterprise-security-features"></a>Steg 5: Distribuera säkerhetsfunktioner för Windows 10 Enterprise

![Fas 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Windows 10 innehåller säkerhetsfunktioner för att skydda företagsanvändare, stoppa cyberhot och förhindra dataförlust. 

Mer information om dessa tekniker finns i:

* [Identitetsskydd](https://docs.microsoft.com/windows/security/identity-protection/) – Lär dig mer om Windows Hello för företag, autentiseringsskydd och åtkomstkontroll.
* [Skydd mot hot](https://docs.microsoft.com/windows/threat-protection/) – Lär dig mer om Microsoft Defender Advanced Threat Protection, en enhetlig plattform för förebyggande skydd, identifiering efter överträdelse, automatisk undersökning och svar.
* [Informationsskydd](https://docs.microsoft.com/windows/security/information-protection/) – Lär dig mer om BitLocker, Windows Informationsskydd och andra sätt som Windows 10 hjälper till att skydda företagsdata. 

I det här steget visas hur du kan distribuera, hantera, konfigurera och felsöka med hjälp av följande säkerhetsfunktioner:

* [Antivirusprogram för Windows Defender](#windows-defender-antivirus)
* [Windows Defender Utnyttja Guard](#windows-defender-exploit-guard)
* [Avancerat hotskydd för Microsoft Defender](#windows10-sec-atp)

<a name="windows10-sec-av"></a>
## <a name="windows-defender-antivirus"></a>Antivirusprogram för Windows Defender
Windows Defender Antivirus (AV) är en lösning mot skadlig kod som är inbyggd i Windows 10. Det ger säkerhet och hantering mot skadlig kod för stationära datorer, bärbara datorer och servrar. Mer information om Windows Defender AV, minimikraven och hur du kan hantera den här funktionen finns [i Windows Defender Antivirus i Windows 10 och Windows Server 2016](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10).

Om du inte använder Windows Defender AV som primär antivirusklient, eller om du också använder Microsoft Defender ATP, finns det några hänsyn som du måste ta hänsyn till. Mer information finns i [Windows Defender AV-kompatibilitet](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility).

### <a name="deployment-and-management"></a>Distribution och hantering
Så här distribuerar och hanterar du Windows Defender AV:

* [Distribuera, hantera och rapportera om Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Referensavsnitt för hanterings- och konfigurationsverktyg](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

### <a name="configuration"></a>Konfiguration
Användare kan konfigurera ett antal funktioner. Mer information finns i följande resurser:

* [Konfigurera Windows Defender AV-funktioner](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)
* [Referensavsnitt för hanterings- och konfigurationsverktyg](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

Om du vill förstå konfigurationsalternativ läser du den här listan över alla inställningar (enligt definitionen i grupprincipkonfigurationen): [Använd grupprincipinställningar för att konfigurera och hantera Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)

Du kan använda [utvärderingsguiden för Windows Defender AV-skydd](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus) för att utvärdera skyddsnivån och effekten av Windows Defender AV i nätverket. Detta kan också vara användbart för att skapa en första konfiguration eller som en "snabbstartsguide" och uppdateras regelbundet för att ge de mest användbara rekommendationerna för att konfigurera och aktivera funktioner för att säkerställa maximalt skydd.

### <a name="reporting"></a>Rapportering
Du kan hämta rapportering med hjälp av ett konfigurationsverktyg, till exempel Microsoft Endpoint Configuration Manager eller Microsoft Intune. Du kan också få rapporter från Update Compliance (OMS) eller genom att använda Windows-händelseloggar i din SIEM. Om du har en licens för Microsoft Defender ATP kan du också hämta rapportering till Windows Defender AV-identifieringar och utföra grundläggande reparation. Mer information finns i följande resurser:
* [Distribuera, hantera och rapportera om Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Rapport om Windows Defender AV-skydd](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/report-monitor-windows-defender-antivirus)
* [Översikt över Microsoft Defender ATP-portal](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Felsökning
Information om grundläggande felsökning av fel- och händelsekoder finns i [Granska händelseloggar och felkoder för felsökning av problem med Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

Du kan också skicka problem (till exempel falska positiva identifieringar) med hjälp av windows defender security intelligence-inlämningssystemet. Mer information finns i [Skicka problem till Microsoft](https://www.microsoft.com/wdsi/filesubmission).

<a name="windows10-sec-eg"></a>
## <a name="windows-defender-exploit-guard"></a>Windows Defender Utnyttja Guard
Windows Defender Exploit Guard är en ny uppsättning funktioner för intrångsförebyggande för Windows 10. Mer information om Windows Defender Exploit Guard, minimikraven och hur du kan hantera den här funktionen finns i [Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard).

### <a name="deployment-management-and-configuration"></a>Distribution, hantering och konfiguration
Så här distribuerar, hanterar och konfigurerar du Windows Defender Exploit Guard:
* [Utnyttja skydd](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/exploit-protection-exploit-guard)
* [Attackera ytskydd](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard?ocid=cx-docs-msa4053440)
* [Nätverksskydd](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
* [Kontrollerad mappåtkomst](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)

Du kan använda en serie utvärderingsavsnitt för att utvärdera skyddsnivån och effekten av Windows Defender Exploit Guard i nätverket. Detta kan också vara användbart för att skapa en första konfiguration eller som en "snabbstartsguide" och ämnena och vägledningen uppdateras regelbundet för att ge de mest användbara rekommendationerna för att konfigurera och aktivera funktioner för att säkerställa maximalt skydd. Om du vill ha mer information [kan du utvärdera Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard).

### <a name="reporting"></a>Rapportering
Du kan hämta rapportering med hjälp av ett konfigurationsverktyg, till exempel Configuration Manager eller Intune. Du kan också få rapporter genom att använda Windows-händelseloggar i din SIEM. Om du har en licens för Microsoft Defender ATP kan du också hämta rapportering till Windows Defender AV-identifieringar och utföra grundläggande reparation. Mer information finns i följande resurser:
* [Visa windows defender exploit guard-händelser](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/event-views-exploit-guard)
* [Översikt över Microsoft Defender ATP-portal](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Felsökning
Du kan utföra grundläggande felsökning eller eventuellt förse Microsoft med .cab-filer och skicka problem (till exempel falska positiva identifieringar) med hjälp av Windows Defender Security Intelligence-inlämningssystemet. Mer information finns i [Skicka problem till Microsoft](https://www.microsoft.com/wdsi/filesubmission).


<a name="windows10-sec-atp"></a>
## <a name="microsoft-defender-advanced-threat-protection"></a>Avancerat hotskydd för Microsoft Defender
Microsoft Defender ATP, som endast är tillgängligt med Microsoft 365 E5-planen, är en säkerhetstjänst som gör det möjligt för företagskunder att upptäcka, undersöka och svara på avancerade hot i sina nätverk. Mer information om Microsoft Defender ATP, minimikraven och hur du kan hantera den här funktionen finns i:

* [Microsoft Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
* [Minimikrav](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/minimum-requirements-windows-defender-advanced-threat-protection)

### <a name="deployment-management-and-configuration"></a>Distribution, hantering och konfiguration
Om du vill distribuera Microsoft Defender ATP måste du se till att du har rätt Windows-licens. När du har verifierat att du har rätt licens måste du bestämma vilken geolokalisering du vill för var dina data ska lagras. Därefter kan du börja introduktionsslutpunkter till tjänsten.

Mer information om de här stegen finns i följande huvudavsnitt: 

* [Validera licensieringsetablering och fullständig uppsättning](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/licensing-windows-defender-advanced-threat-protection)
* [Lagring av data och sekretess](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/data-storage-privacy-windows-defender-advanced-threat-protection)
* [Inbyggda slutpunkter och installationsåtkomst](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/onboard-configure-windows-defender-advanced-threat-protection)

### <a name="detect-investigate-respond"></a>Upptäcka, undersöka, svara
När du har onboarding slutpunkter till tjänsten, kan du börja undersöka aviseringar från de olika instrumentpanelerna. När du har undersökt aviseringar kan du vidta svarsåtgärder för aviseringar. 

Mer information om hur du gör dessa finns i:
* [Översikt över Microsoft Defender ATP-portal](https://go.microsoft.com/fwlink/?linkid=861596)
* [Använda Microsoft Defender ATP-portalen](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-windows-defender-advanced-threat-protection)
* [Vidta svarsåtgärder](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/response-actions-windows-defender-advanced-threat-protection)

### <a name="integrate-with-other-products-and-tools"></a>Integrera med andra produkter och verktyg
Microsoft Defender ATP integrerar och stöder olika andra produkter och verktyg för att utöka sina säkerhetsfunktioner. 

Mer information om verktyg och andra produkter finns i:
* [SIEM-verktyg](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection)
* [Skapa anpassade aviseringar](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-custom-ti-windows-defender-advanced-threat-protection)
* [Använda API:er](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/exposed-apis-windows-defender-advanced-threat-protection)
* [Skapa Power BI-rapporter](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/powerbi-reports-windows-defender-advanced-threat-protection)

### <a name="troubleshooting"></a>Felsökning
Du kan stöta på problem när du är ombord eller när du använder produkten. Mer information om hur du åtgärdar problem finns i:
* [Felsöka problem med introduktionskörning](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-onboarding-windows-defender-advanced-threat-protection)
* [Felsöka Microsoft Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-windows-defender-advanced-threat-protection)

## <a name="next-step"></a>Nästa steg

[Exitkriterier för Windows 10 Företagsinfrastruktur](windows10-exit-criteria.md)
