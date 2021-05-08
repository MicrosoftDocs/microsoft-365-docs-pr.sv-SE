---
title: Distribuera, hantera och rapportera Microsoft Defender Antivirus
description: Du kan distribuera och hantera Microsoft Defender Antivirus med Intune, Microsoft Endpoint Configuration Manager, Grupprincip, PowerShell eller WMI
keywords: distribuera, hantera, uppdatera, skydda Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 089a16bb76956cfb0441f8c3eeb5e70d80059845
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275186"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>Distribuera, hantera och rapportera Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Du kan distribuera, hantera och rapportera Microsoft Defender Antivirus på flera olika sätt.

Eftersom Microsoft Defender Antivirus klient installeras som en kärndel av Windows 10 gäller inte traditionell distribution av en klient till slutpunkterna.

Men i de flesta fall måste du aktivera skyddstjänsten på dina slutpunkter med Microsoft Intune, Microsoft Endpoint Configuration Manager, Azure Defender eller Group Policy Objects, som beskrivs i följande tabell.

Du ser även ytterligare länkar för:

- Hantera Microsoft Defender Antivirus skydd, inklusive hantering av produkt- och skyddsuppdateringar
- Rapportering om Microsoft Defender Antivirus skydd

> [!IMPORTANT]
> I de flesta Windows 10 inaktiveras Microsoft Defender Antivirus om den hittar ett annat antivirusprogram som körs och är uppdaterat. Du måste inaktivera eller avinstallera antivirusprodukter från tredje part innan Microsoft Defender Antivirus att fungera. Om du återaktiverar eller installerar antivirusprodukter från tredje Windows 10 du automatiskt Microsoft Defender Antivirus.

Verktyg|Distributionsalternativ (<a href="#fn2" id="ref2">2</a>)|Hanteringsalternativ (nätverksomfattande konfiguration och princip- eller baslinjedistribution) ([3](#fn3))|Rapportalternativ  
---|---|---|---  
Microsoft Intune|[Lägga till inställningar för slutpunktsskydd i Intune](/intune/endpoint-protection-configure)|[Konfigurera inställningar för enhetsbegränsning i Intune](/intune/device-restrictions-configure)| [Använda Intune-konsolen för att hantera enheter](/intune/device-management)  
Microsoft Endpoint Manager ([1](#fn1))|Använda rollen [Endpoint Protection punktwebbplatssystem och][] [aktivera Endpoint Protection med anpassade klientinställningar][]|Med [standardprinciper för skydd mot skadlig programvara och][] [klienthantering][]|Med [standardarbetsytan för övervakning av Konfigurationshanteraren och][] [e-postaviseringar][]  
Grupprincip och Active Directory (domänmedlem)|Använd ett grupprincipobjekt för att distribuera konfigurationsändringar och se Microsoft Defender Antivirus är aktiverat.|Använda grupprincipobjekt (GPOs) för att [konfigurera uppdateringsalternativ för Microsoft Defender Antivirus][] och konfigurera Windows Defender [funktioner][]|Slutpunktsrapportering är inte tillgänglig med Grupprincip. Du kan generera en lista [med grupprinciper för att avgöra om några inställningar eller principer inte tillämpas][]
PowerShell|Distribuera med grupprinciper, Microsoft Endpoint Configuration Manager eller manuellt på enskilda slutpunkter.|Använd [cmdletarna Set-MpPreference] [och Update-MpSignature] som är tillgängliga i Defender-modulen.|Använd lämpliga [Get-cmdlets som är tillgängliga i Defender-modulen][]
Windows Management Instrumentation|Distribuera med grupprinciper, Microsoft Endpoint Configuration Manager eller manuellt på enskilda slutpunkter.|Använd metoden [Set för MSFT_MpPreference klassen][] och [uppdateringsmetoden för MSFT_MpSignature klassen][]|Använd [MSFT_MpComputerStatus][] klassen och get-metoden för associerade klasser i [WMIv2-Windows Defender-providern][] för Windows Defender
Microsoft Azure|Distribuera Microsoft Antimalware för Azure i Azure-portalen genom att Visual Studio konfiguration av den virtuella datorn eller [med Azure PowerShell-cmdlets.](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios) Du kan också [installera slutpunktsskydd i Azure Defender*](/azure/security-center/security-center-install-endpoint-protection)|Konfigurera [Microsoft Antimalware för virtuella maskiner och molntjänster med Azure PowerShell cmdlets eller](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) använd [kodexempel](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe)|Använd [Microsoft Antimalware för virtuella maskiner och molntjänster med Azure PowerShell för](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) att aktivera övervakning. Du kan också granska användningsrapporter i Azure Active Directory för [][] att avgöra misstänkt aktivitet, inklusive rapporten Smittade enheter och konfigurera ett SIEM-verktyg för att rapportera [om Microsoft Defender Antivirus-händelser][] och lägga till verktyget som en app i AAD.

1. <span id="fn1" />Tillgängligheten för vissa funktioner, särskilt relaterade till skydd mot molntjänster, skiljer sig mellan Microsoft Endpoint Manager (Current Branch) och System Center 2012 Configuration Manager. I det här biblioteket fokuserar vi på Windows 10, Windows Server 2016 och Microsoft Endpoint Manager (Current Branch). Se [Använda Molnskydd i Microsoft i Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md) en tabell som beskriver de största skillnaderna. [(Återgå till tabell)](#ref2)
  
2.  <span id="fn2" />I Windows 10 är Microsoft Defender Antivirus en komponent som är tillgänglig utan installation eller distribution av ytterligare en klient eller tjänst. Det aktiveras automatiskt när antivirusprodukter från tredje part antingen avinstalleras eller är inaktiva (utom[på Windows Server 2016).](microsoft-defender-antivirus-on-windows-server.md) Traditionell distribution är därför inte obligatoriskt. Distribution här avser att säkerställa att Microsoft Defender Antivirus komponenten är tillgänglig och aktiverad på slutpunkter eller servrar. [(Återgå till tabell)](#ref2)

3. <span id="fn3" />Konfiguration av funktioner och skydd, inklusive konfiguration av uppdateringar av produkter och skydd, beskrivs mer i [avsnittet Konfigurera Microsoft Defender Antivirus funktioner](configure-notifications-microsoft-defender-antivirus.md) i det här biblioteket. [(Återgå till tabell)](#ref2)

[Endpoint Protection roll för platswebbplatssystem]: /configmgr/protect/deploy-use/endpoint-protection-site-role
[standardprinciper för program mot skadlig programvara]:  /configmgr/protect/deploy-use/endpoint-antimalware-policies
[klienthantering]:  /configmgr/core/clients/manage/manage-clients
[aktivera Endpoint Protection med anpassade klientinställningar]:  /configmgr/protect/deploy-use/endpoint-protection-configure-client
[Arbetsyta för övervakning av konfigurationshanteraren]:  /configmgr/protect/deploy-use/monitor-endpoint-protection
[e-postaviseringar]:  /configmgr/protect/deploy-use/endpoint-configure-alerts
[Deploy the Microsoft Intune client to endpoints]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune
[custom Intune policy]:  /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#configure-microsoft-intune-endpoint-protection
 [custom Intune policy]:  /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#configure-microsoft-intune-endpoint-protection 
[manage tasks]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#choose-management-tasks-for-endpoint-protection
[Monitor endpoint protection in the Microsoft Intune administration console]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#monitor-endpoint-protection
[Metod för MSFT_MpPreference klass]:  /previous-versions/windows/desktop/defender/set-msft-mppreference
[Uppdateringsmetod för MSFT_MpSignature klass]:  /previous-versions/windows/desktop/defender/set-msft-mppreference
[MSFT_MpComputerStatus]:  /previous-versions/windows/desktop/defender/msft-mpcomputerstatus
[Windows Defender WMIv2-leverantör]: /previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal
[Set-MpPreference]:  https://technet.microsoft.com/itpro/powershell/windows/defender/set-mppreference.md
[Update-MpSignature]: /powershell/module/defender/update-mpsignature
[Get- cmdlets tillgängliga i Defender-modulen]: /powershell/module/defender/
[Konfigurera uppdateringsalternativ för Microsoft Defender Antivirus]: manage-updates-baselines-microsoft-defender-antivirus.md
[Konfigurera Windows Defender funktioner]: configure-microsoft-defender-antivirus-features.md
[Grupprinciper för att avgöra om några inställningar eller principer inte tillämpas]: /previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771389(v=ws.11)
[Eventuellt smittade enheter]: /azure/active-directory/active-directory-reporting-sign-ins-from-possibly-infected-devices
[Microsoft Defender Antivirus händelser]: troubleshoot-microsoft-defender-antivirus.md

## <a name="in-this-section"></a>I det här avsnittet

Ämne | Beskrivning
---|---
[Distribuera och Microsoft Defender Antivirus skydd](deploy-microsoft-defender-antivirus.md) | Medan klienten är installerad som en central del av Windows 10, och traditionell distribution inte gäller, måste du fortfarande aktivera klienten på dina slutpunkter med Microsoft Endpoint Configuration Manager- Microsoft Intune- eller grupprincipobjekt. 
[Hantera Microsoft Defender Antivirus uppdateringar och använda baslinjer](manage-updates-baselines-microsoft-defender-antivirus.md) | Det finns två delar för att uppdatera Microsoft Defender Antivirus: uppdatera klienten på slutpunkter (produktuppdateringar) och uppdatera säkerhetsintelligens (skyddsuppdateringar). Du kan uppdatera säkerhetsintelligens på flera olika sätt med Microsoft Endpoint Configuration Manager, grupprincip, PowerShell och WMI.
[Övervaka och rapportera Microsoft Defender Antivirus skydd](report-monitor-microsoft-defender-antivirus.md) | Du kan använda Microsoft Intune, Microsoft Endpoint Configuration Manager, tillägget Update Compliance för Microsoft Operations Management Suite eller en sieM-produkt från tredje part (genom att använda Windows-händelseloggar) för att övervaka skyddsstatus och skapa rapporter om slutpunktsskydd.