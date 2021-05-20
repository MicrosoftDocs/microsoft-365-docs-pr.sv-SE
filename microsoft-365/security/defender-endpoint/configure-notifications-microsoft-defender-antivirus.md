---
title: Konfigurera Microsoft Defender Antivirus meddelanden
description: Lär dig hur du konfigurerar och anpassar både standard- och Microsoft Defender Antivirus standardaviseringar på slutpunkter.
keywords: meddelanden, defender, antivirus, slutpunkt, hantering, administratör
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f885b6d7991e4175cd14be5bbe9e0a7c96b1580f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572351"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a>Konfigurera meddelanden som visas på slutpunkter

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

I Windows 10 är programmeddelanden om identifiering och åtgärder av skadlig kod mer robusta, konsekventa och koncisa.

Meddelanden visas på slutpunkter när manuellt utlösta och schemalagda genomsökningar har slutförts och hot identifieras. Dessa meddelanden visas också i **meddelandecentret**, och en sammanfattning av genomsökningar och identifieringar av hot visas med jämna mellanrum.

Du kan också konfigurera hur standardmeddelanden visas på slutpunkter, till exempel meddelanden för omstart eller när ett hot har upptäckts och åtgärdats.

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a>Konfigurera ytterligare meddelanden som visas på slutpunkter

Du kan konfigurera visningen av ytterligare meddelanden, till exempel sammanfattningar av nya identifieringar av hot, [Windows-säkerhet appen](microsoft-defender-security-center-antivirus.md) och med Grupprincip.

> [!NOTE]
> I Windows 10 version 1607 kallades funktionen  för Utökade meddelanden och kan konfigureras under **Windows Inställningar**  >  **Update & security**  >  **Windows Defender**. I grupprincipinställningar i alla versioner Windows 10 kallas det **utökade meddelanden.**

> [!IMPORTANT]
> Om du inaktiverar ytterligare meddelanden inaktiveras inte kritiska meddelanden, till exempel aviseringar om identifiering av hot och åtgärder.

**Använd Windows-säkerhet för att inaktivera ytterligare meddelanden:**

1. Öppna Windows-säkerhet genom att klicka på sköldikonen i aktivitetsfältet eller söka efter Säkerhet på **Start-menyn.**

2. Välj **Virus &** skydd mot hot (eller sköldikonen i den vänstra menyraden) och välj sedan Inställningar för & skydd mot **virus**

3. Bläddra till avsnittet **Meddelanden** och klicka på **Ändra aviseringsinställningar**.

4. Dra reglaget till **Av** eller **På för** att inaktivera eller aktivera ytterligare meddelanden.

**Använd Grupprincip för att inaktivera ytterligare meddelanden:**

1. På datorn för grupprinciphantering öppnar du [Konsolen för](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

2. Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**

3. Klicka **på Administrativa mallar**.

4. Expandera trädet för att **Windows komponenter > Microsoft Defender Antivirus > rapportering.**

5. Dubbelklicka på **Inaktivera utökade meddelanden och** ställ in alternativet Aktiverad.  Klicka på **OK**. Det gör att det inte visas fler meddelanden.

## <a name="configure-standard-notifications-on-endpoints"></a>Konfigurera standardaviseringar på slutpunkter

Du kan använda grupprinciper för att:

- Visa ytterligare, anpassad text på slutpunkter när användaren behöver utföra en åtgärd
- Dölj alla meddelanden på slutpunkter
- Dölja meddelanden om omstart på slutpunkter

Att dölja meddelanden kan vara användbart i situationer där du inte kan dölja Microsoft Defender Antivirus gränssnittet. Mer information [finns i Hindra användare från att se Microsoft Defender Antivirus interagera med användargränssnittet.](prevent-end-user-interaction-microsoft-defender-antivirus.md) 

> [!NOTE]
> Om du döljer meddelanden visas det bara i slutpunkter där principen har distribuerats. Meddelanden om åtgärder som måste vidtas (till exempel en omstart) visas fortfarande på Microsoft Endpoint Manager Endpoint Protection [och instrumentpanelen för övervakning.](/configmgr/protect/deploy-use/monitor-endpoint-protection) 

Se [Anpassa Windows-säkerhet för din organisation](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) för anvisningar om hur du lägger till anpassad kontaktinformation i meddelanden som användarna ser på sina datorer.

**Använd grupprinciper för att dölja meddelanden:**

1. På datorn för grupprinciphantering öppnar du [Konsolen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

2. I **redigeraren för grupprinciphantering går** du till **Datorkonfiguration och** klickar på **Administrativa mallar**.

3. Expandera trädet och visa **Windows i > Microsoft Defender Antivirus > klientgränssnittet.** 

4. Dubbelklicka på **Ignorera alla meddelanden** och ange alternativet **Aktiverad**. Klicka på **OK**. Det gör att det inte visas fler meddelanden.

**Använd Grupprincip för att dölja meddelanden om omstart:**

1. På datorn för grupprinciphantering öppnar du [Konsolen för](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

2. Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**

3. Klicka **på Administrativa mallar**.

4. Expandera trädet och visa **Windows i > Microsoft Defender Antivirus > klientgränssnittet.**

5. Dubbelklicka på Ignorera **meddelanden vid omstart och** ställ in alternativet **Aktiverad**. Klicka på **OK**. Det gör att det inte visas fler meddelanden.

## <a name="related-topics"></a>Relaterade ämnen

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Konfigurera slutanvändares interaktion med Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md)
