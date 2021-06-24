---
title: Skapa en anpassad stegvis införandeprocess för Microsoft Defender-uppdateringar
description: Lär dig hur du använder verktyg som stöds för att skapa en anpassad gradvis utrullningsprocess för uppdateringar
keywords: uppdateringsverktyg, gpo, intune, mdm, microsoft endpoint manager, policy, powershell
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: a506f4913369e53fd2ed4943bb2557935f1d62e5
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105566"
---
# <a name="create-a-custom-gradual-rollout-process-for-microsoft-defender-updates"></a>Skapa en anpassad stegvis införandeprocess för Microsoft Defender-uppdateringar

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> Den här funktionen Microsoft Defender Antivirus version 4.18.2106.X eller senare.

Om du vill skapa en egen, stegvis utrullningsprocess för Defender-uppdateringar kan du använda Grupprincip, Microsoft Endpoint Manager och PowerShell.

I följande tabell finns tillgängliga grupprincipinställningar för konfigurering av uppdateringskanaler:

| Ange rubrik  | Beskrivning  | Plats  |
|-|-|-|
| Välj gradvis utrullningskanal för månatlig uppdatering av Microsoft Defender-plattformen  | Aktivera den här principen för att ange när enheter ska få uppdateringar av Microsoft Defender-plattformen under den månatliga gradvisa utrullningen. Betakanal: Enheter som är inställda på den här kanalen blir först med att ta emot nya uppdateringar. Välj Betakanal för att delta i identifiering och rapportering av problem till Microsoft. Enheter i Windows Insider Program prenumererar på den här kanalen som standard. Endast för användning i (manuella) testmiljöer och ett begränsat antal enheter.  <br><br>  Aktuell kanal (förhandsversion): Enheter som använder den här kanalen kommer att erbjudas tidigast under den månatliga gradvisa versionen. Förslag för miljöer före produktion/validering.  <br><br>  Aktuell kanal (stegvis): Enheter erbjuds uppdateringar efter den månatliga gradvisa utgivningscykeln. Rekommenderas att gälla för en liten, representativ del av produktionspopulationen (~10 %).  <br><br>  Aktuell kanal (bred): Enheter erbjuds endast uppdateringar efter att den gradvisa versionen har slutförts. Rekommenderas att användas på en omfattande uppsättning enheter i produktionspopulationen (~10–100 %).  <br><br>   Om du inaktiverar eller inte konfigurerar den här principen kommer enheten att uppdateras automatiskt under den gradvisa versionen. Passar för de flesta enheter.  | Windows Components\Microsoft Defender Antivirus  |
| Välj gradvis utrullningskanal för månadsuppdatering av Microsoft Defender  | Aktivera den här principen för att ange när enheter får Microsoft Defender-motoruppdateringar under den månatliga gradvisa utrullningen.  <br><br>  Betakanal: Enheter som är inställda på den här kanalen blir först med att ta emot nya uppdateringar. Välj Betakanal för att delta i identifiering och rapportering av problem till Microsoft. Enheter i Windows Insider Program prenumererar på den här kanalen som standard. Endast för användning i (manuella) testmiljöer och ett begränsat antal enheter.  <br><br>  Aktuell kanal (förhandsversion): Enheter som använder den här kanalen kommer att erbjudas tidigast under den månatliga gradvisa versionen. Förslag för miljöer före produktion/validering.  <br><br>  Aktuell kanal (stegvis): Enheter erbjuds uppdateringar efter den månatliga gradvisa utgivningscykeln. Rekommenderas att gälla för en liten, representativ del av produktionspopulationen (~10 %).  <br><br>  Aktuell kanal (bred): Enheter erbjuds endast uppdateringar efter att den gradvisa versionen har slutförts. Rekommenderas att användas på en omfattande uppsättning enheter i produktionspopulationen (~10–100 %).  <br><br>  Om du inaktiverar eller inte konfigurerar den här principen kommer enheten att uppdateras automatiskt under den gradvisa versionen. Passar för de flesta enheter.  | Windows Components\Microsoft Defender Antivirus  |
| Utrullningskanal för dagliga uppdateringar för Microsoft Defender gradvis  | Aktivera den här principen för att ange när enheter ska få uppdateringar av Microsoft Defender-definition under den dagliga gradvisa utrullningen. <br><br> Aktuell kanal (fasad): Enheter erbjuds uppdateringar efter utgivningscykeln. Rekommenderas att gälla för en liten, representativ del av produktionspopulationen (~10 %). <br><br>   Aktuell kanal (bred): Enheter erbjuds endast uppdateringar efter att den gradvisa versionen har slutförts. Rekommenderas att användas på en omfattande uppsättning enheter i produktionspopulationen (~10–100 %). <br><br>   Om du inaktiverar eller inte konfigurerar den här principen kommer enheten att uppdateras automatiskt under den dagliga versionen. Passar för de flesta enheter.  | Windows Components\Microsoft Defender Antivirus  |
| Inaktivera gradvis utrullning av Microsoft Defender-uppdateringar  | Aktivera den här principen för att inaktivera gradvis utrullning av Defender-uppdateringar. <br><br> Aktuell kanal (bred): Enheter som är inställda på den här kanalen kommer att erbjudas uppdateringar senast under den gradvisa utgivningscykeln. Bäst för datacenterdatorer som bara får begränsade uppdateringar. <br><br> Obs! Den här inställningen gäller för både månatliga och dagliga Defender-uppdateringar och åsidosätter tidigare konfigurerade kanalval för plattforms- och motoruppdateringar. <br><br> Om du inaktiverar eller inte konfigurerar den här principen finns enheten kvar i aktuell kanal (standard) om inget annat anges i specifika kanaler för plattforms- och motoruppdateringar. Håll dig uppdaterad automatiskt under den gradvisa utgivningscykeln. Passar för de flesta enheter.  | Windows Components\Microsoft Defender Antivirus  |

## <a name="group-policy"></a>Grupprincip

> [!NOTE]
> En uppdaterad Defender ADMX-mall publiceras tillsammans med 21H2-versionen av Windows 10. En icke lokaliserad version kan laddas ned på https://github.com/microsoft/defender-updatecontrols .

Du kan använda [grupprinciper](/windows/win32/srvnodes/group-policy?redirectedfrom=MSDN)   för att konfigurera Microsoft Defender Antivirus och hantera e-Microsoft Defender Antivirus slutpunkter.

I allmänhet kan du använda följande procedur för att konfigurera eller ändra Microsoft Defender Antivirus grupprincipinställningar:

1. Öppna grupprinciphanteringskonsolen på hanteringsdatorn för **grupprinciper,** högerklicka på det grupprincipobjekt  (GPO) du vill konfigurera och klicka på **Redigera.**

2. Med grupprinciphanteringsredigeraren går du till **Datorkonfiguration**.

3. Klicka **på Administrativa mallar**.

4. Expandera trädet för att **Windows komponenter > Microsoft Defender Antivirus**.

5. Expandera det avsnitt (kallas för Plats i tabellen i det här avsnittet) som innehåller den inställning du vill konfigurera, dubbelklicka på inställningen för att öppna den och gör ****   konfigurationsändringar.

6. [Distribuera det uppdaterade GPO:t på normalt sätt.](https://msdn.microsoft.com/library/ee663280(v=vs.85).aspx)

## <a name="intune"></a>Intune

Följ länken nedan för att skapa en anpassad princip i Intune:

[Lägga till anpassade inställningar Windows 10 enheter i Microsoft Intune – Azure \| Microsoft Docs](/mem/intune/configuration/custom-settings-windows-10)

## <a name="powershell"></a>PowerShell

Använd `Set-MpPreference` cmdleten för att konfigurera de gradvisa uppdateringarna.

Använd följande parametrar:

```powershell
Set-MpPreference
-PlatformUpdatesChannel Beta|Preview|Staged|Broad|NotConfigured
-EngineUpdatesChannel Beta|Preview|Staged|Broad|NotConfigured
-DisableGradualRelease True|False
-SignaturesUpdatesChannel Staged|Broad|NotConfigured
```

Exempel:

Används `Set-MpPreference -PlatformUpdatesChannel Beta` för att konfigurera plattformsuppdateringar så att de kommer från Beta-kanalen.

Mer information om parametrar och hur du konfigurerar dem finns i [Set-MpPreference (Defender) | Microsoft Docs.](/powershell/module/defender/set-mppreference?view=windowsserver2019-ps&preserve-view=true)
