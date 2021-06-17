---
title: Konfigurera Microsoft Defender Antivirus meddelanden
description: Lär dig hur du konfigurerar och anpassar både standardmeddelanden och Microsoft Defender Antivirus standardaviseringar på slutpunkter.
keywords: meddelanden, defender, antivirus, slutpunkt, hantering, administratör
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.topic: article
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: a7a838bb15cd011b750fbfa3d6df100ddf9f713c
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985414"
---
# <a name="configure-microsoft-defender-antivirus-notifications-that-appear-on-endpoints"></a>Konfigurera Microsoft Defender Antivirus som visas på slutpunkter

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

I Windows 10 är programmeddelanden om identifiering och åtgärder av skadlig kod mer robusta, konsekventa och koncisa. Microsoft Defender Antivirus meddelanden visas på slutpunkter när genomsökningar har slutförts och hot identifieras. Meddelanden följer både schemalagda och manuellt utlösta genomsökningar. Dessa meddelanden visas också i **meddelandecentret**, och en sammanfattning av genomsökningar och identifieringar av hot visas med jämna mellanrum.

Om du är en del av organisationens säkerhetsteam kan du konfigurera hur meddelanden visas på slutpunkter, till exempel meddelanden som uppmanar till en systemstart eller som anger att ett hot har upptäckts och åtgärdats.

## <a name="configure-antivirus-notifications-using-group-policy-or-the-windows-security-app"></a>Konfigurera antivirusmeddelanden med grupprinciper eller Windows-säkerhet programmet

Du kan konfigurera visningen av ytterligare meddelanden, till exempel sammanfattningar av nya identifieringar av hot, [Windows-säkerhet appen](microsoft-defender-security-center-antivirus.md) och med Grupprincip.

> [!NOTE]
> I Windows 10 version 1607 kallades funktionen  för Utökade meddelanden och konfigurerades under **Windows Inställningar**  >  **Update & security**  >  **Windows Defender**. I Grupprincipinställningar för alla versioner Windows 10 kallas meddelandefunktionen **Utökade meddelanden.**

### <a name="use-group-policy-to-disable-additional-notifications"></a>Använda grupprinciper för att inaktivera ytterligare meddelanden

1. Öppna [Konsolen för grupprinciphantering](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) på datorn för grupprinciphantering.

2. Högerklicka på det grupprincipobjekt du vill konfigurera och välj sedan **Redigera**.

3. Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**

4. Välj **Administrativa mallar**.

5. Expandera trädet och visa **Windows komponenter**  >  **Microsoft Defender Antivirus** >**.

6. Dubbelklicka på **Inaktivera utökade meddelanden och** ställ in alternativet Aktiverad .  Välj sedan **OK**. Det gör att det inte visas fler meddelanden.

> [!IMPORTANT]
> Om du inaktiverar ytterligare meddelanden inaktiveras inte kritiska meddelanden, till exempel aviseringar om identifiering av hot och åtgärder.

### <a name="use-the-windows-security-app-to-disable-additional-notifications"></a>Använd appen Windows-säkerhet för att inaktivera ytterligare meddelanden

1. Öppna Windows-säkerhet genom att klicka på sköldikonen i aktivitetsfältet eller söka efter Säkerhet på **Start-menyn.**

2. Välj **Virus &** skydd mot hot (eller sköldikonen i den vänstra menyraden) och välj sedan Inställningar för & skydd mot **virus**

3. Bläddra till avsnittet **Meddelanden** och välj **Ändra aviseringsinställningar**.

4. Dra reglaget till **Av** eller **På för** att inaktivera eller aktivera ytterligare meddelanden.

> [!IMPORTANT]
> Om du inaktiverar ytterligare meddelanden inaktiveras inte kritiska meddelanden, till exempel aviseringar om identifiering av hot och åtgärder.

## <a name="configure-standard-notifications-on-endpoints-using-group-policy"></a>Konfigurera standardaviseringar på slutpunkter med grupprincip

Du kan använda grupprinciper för att:

- Visa ytterligare, anpassad text på slutpunkter när användaren behöver utföra en åtgärd
- Dölj alla meddelanden på slutpunkter
- Dölja meddelanden om omstart på slutpunkter

Att dölja meddelanden kan vara användbart i situationer där du inte kan dölja Microsoft Defender Antivirus gränssnittet. Mer information [finns i Hindra användare från att se Microsoft Defender Antivirus interagera med användargränssnittet.](prevent-end-user-interaction-microsoft-defender-antivirus.md) Om du döljer meddelanden visas det bara i slutpunkter där principen har distribuerats. Meddelanden om åtgärder som måste vidtas (till exempel en omstart) visas fortfarande på Microsoft Endpoint Manager Endpoint Protection [och instrumentpanelen för övervakning.](/configmgr/protect/deploy-use/monitor-endpoint-protection) 

Om du vill lägga till anpassad kontaktinformation i slutpunktsaviseringar går du [till Anpassa Windows-säkerhet för din organisation.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)

### <a name="use-group-policy-to-hide-notifications"></a>Använda grupprinciper för att dölja meddelanden

1. Öppna [Konsolen för grupprinciphantering](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) på datorn för grupprinciphantering.

2. Högerklicka på det grupprincipobjekt du vill konfigurera och välj sedan **Redigera**.

3. I **redigeraren för grupprinciphantering** går du **till Datorkonfiguration** och väljer sedan **Administrativa mallar**.

4. Expandera trädet till en **Windows Microsoft Defender Antivirus**  >    >  **klientgränssnittet**. 

5. Dubbelklicka på **Ignorera alla meddelanden** och ange alternativet **Aktiverad**. 

6. Välj **OK**. Det gör att det inte visas fler meddelanden.

### <a name="use-group-policy-to-hide-reboot-notifications"></a>Använd grupprinciper för att dölja meddelanden om omstart

1. Öppna [Konsolen för grupprinciphantering](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) på datorn för grupprinciphantering.

2. Högerklicka på det grupprincipobjekt du vill konfigurera och välj sedan **Redigera.**

2. Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**

3. Klicka **på Administrativa mallar**.

4. Expandera trädet till en **Windows Microsoft Defender Antivirus**  >    >  **klientgränssnittet**.

5. Dubbelklicka på Ignorera **meddelanden vid omstart och** ställ in alternativet **Aktiverad**. 

5. Välj **OK**. Det gör att det inte visas fler meddelanden.

