---
title: Microsoft Defender Offline i Windows 10
description: Du kan använda Microsoft Defender Offline direkt från Windows Defender Antivirus appen. Du kan också hantera hur den distribueras i nätverket.
keywords: skanna, defender, offline
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: b2a6ee7c3f3ea2fb31b31d2f1db178bfd9847fbc
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007482"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>Kör och granska resultatet av en genomsökning för Microsoft Defender Offline

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Offline är ett sökverktyg mot skadlig programvara som gör att du kan starta och köra en sökning från en betrodd miljö. Genomsökningen körs från det vanliga Windows kernel-programmet så att det kan rikta skadlig programvara som försöker kringgå Windows-gränssnittet, till exempel virus och rootkits som smittar eller skriver över huvudstartsposten (MBR).

Du kan använda Microsoft Defender Offline om du misstänker att det har smittat skadlig programvara eller om du vill bekräfta att slutpunkten har rensat helt efter ett utbrott av skadlig programvara.

I Windows 10 kan Microsoft Defender Offline köras med ett klick direkt från Windows-säkerhet [appen.](microsoft-defender-security-center-antivirus.md) I tidigare versioner av Windows var en användare tvungen att installera Microsoft Defender Offline för att starta om media, starta om slutpunkten och läsa in startbara media.

## <a name="prerequisites-and-requirements"></a>krav och förutsättningar

Microsoft Defender Offline i Windows 10 har samma maskinvarukrav som för Windows 10. 

Mer information om Windows 10 finns i följande avsnitt:

- [Minimikrav för maskinvara](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [Riktlinjer för maskinvarukomponenter](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> Microsoft Defender Offline stöds inte på datorer med ARM-processorer eller på Windows I Server Stock Keeping Units.

Om Microsoft Defender Offline från slutpunkten måste användaren vara inloggad med administratörsbehörighet.
 
## <a name="microsoft-defender-offline-updates"></a>Microsoft Defender Offline uppdateringar

Microsoft Defender Offline använder de senaste skyddsuppdateringarna som finns tillgängliga på slutpunkten. uppdateras när Windows Defender Antivirus uppdateras. 

> [!NOTE]
> Innan du kör en offlinesökning bör du försöka uppdatera Microsoft Defender AV-skyddet. Du kan antingen tvinga fram en uppdatering med grupprinciper eller hur du normalt distribuerar uppdateringar till slutpunkter, eller så kan du manuellt ladda ned och installera de senaste skyddsuppdateringarna [från Microsoft Malware Protection Center.](https://www.microsoft.com/security/portal/definitions/adl.aspx)

Mer information [finns Microsoft Defender Antivirus i avsnittet](manage-protection-updates-microsoft-defender-antivirus.md) Hantera säkerhetsintelligensuppdateringar.

## <a name="usage-scenarios"></a>Användningsscenarier

I Windows 10, version 1607, kan du manuellt tvinga fram en offlinesökning. Om du Windows Defender avgöra Microsoft Defender Offline måste köras uppmanas användaren i slutpunkten. 

Att du behöver göra en offlinesökning visas också i Microsoft Endpoint Manager om du använder det för att hantera dina slutpunkter.

Uppmaningen kan visas via ett meddelande, ungefär så här:

:::image type="content" source="../../media/notification.png" alt-text="Avisering om att köra Microsoft Defender Offline":::

Användaren meddelas också Windows Defender klienten.

I Konfigurationshanteraren kan du identifiera slutpunktens status genom att gå till Övervaknings- > **– > Säkerhets- > Endpoint Protection Status > System Center Endpoint Protection Status**. 

Microsoft Defender Offline genomsökningar visas under Status för skadlig kod **som Offlinesökning** **krävs.**

:::image type="content" source="../../media/sccm-wdo.png" alt-text="Microsoft Defender Offline sökning krävs":::

## <a name="configure-notifications"></a>Konfigurera meddelanden

Microsoft Defender Offline konfigureras i samma principinställning som andra Av-meddelanden i Microsoft Defender.

Mer information om meddelanden i Windows Defender finns i avsnittet [Konfigurera meddelanden som visas på slutpunkter.](configure-notifications-microsoft-defender-antivirus.md)

## <a name="run-a-scan"></a>Köra en genomsökning 

> [!IMPORTANT]
> Innan du Microsoft Defender Offline program måste du spara alla filer och stänga av program som körs. Skanningen Microsoft Defender Offline tar ca 15 minuter att köra. När genomsökningen är klar startar den om slutpunkten. Skanningen utförs utanför den vanliga Windows operativsystemet. Användargränssnittet ser annorlunda ut än det som utförs i Windows Defender. När genomsökningen har slutförts startas slutpunkten om och Windows läsas in normalt.

Du kan köra en Microsoft Defender Offline genomsökning med följande:

- PowerShell
- Windows Management Instrumentation (WMI)
- Appen Windows-säkerhet



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>Använda PowerShell-cmdlets för att köra en offlinesökning

Använd följande cmdlets:

```PowerShell
Start-MpWDOScan
```

Se [Använda PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets för](/powershell/module/defender/) mer information om hur du använder PowerShell med Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>Använd Windows instruktion (WMI) för att köra en offlinesökning

Använd [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) att köra en offlinesökning.

Följande WMI-skriptavsnitt kör omedelbart en Microsoft Defender Offline-genomsökning, vilket gör att slutpunkten startas om, kör offlinesökningen och startar sedan om och startar Windows.

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

Mer information finns i följande avsnitt:
- [Windows Defender WMIv2-API:er](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>Använda appen Windows Defender-säkerhet för att köra en offlinesökning

1. Öppna Windows-säkerhet genom att klicka på sköldikonen i aktivitetsfältet eller söka efter Defender på **startmenyn.**

2. Klicka på **& för skydd mot** hot (eller sköldikonen på den vänstra menyraden) och sedan på etiketten Avancerad **genomsökning:**
    
3. Välj **Microsoft Defender Offline skanna och** klicka på Sök **nu**.

    > [!NOTE]
    > I Windows 10 version 1607 kan offlinesökningen köras **under** Windows Inställningar Update & Security  >    >  **Windows Defender** eller Windows Defender-klienten.


## <a name="review-scan-results"></a>Granska genomsökningsresultat

Microsoft Defender Offline sökresultat visas i avsnittet [Skanningshistorik i Windows-säkerhet appen](microsoft-defender-security-center-antivirus.md). 


## <a name="related-articles"></a>Relaterade artiklar

- [Anpassa, initiera och granska resultatet av genomsökningar och åtgärder](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)