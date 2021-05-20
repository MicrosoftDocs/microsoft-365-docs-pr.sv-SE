---
title: Konfigurera Microsoft Defender Antivirus meddelanden
description: Lär dig hur du konfigurerar och anpassar både standard- och Microsoft Defender Antivirus meddelanden om slutpunkter.
keywords: meddelanden, försvarare, antivirus, slutpunkt, hantering, admin
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
# <a name="configure-the-notifications-that-appear-on-endpoints"></a>Konfigurera meddelandena som visas på slutpunkter

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

I Windows 10 program meddelanden om identifiering och reparation av skadlig kod mer robusta, konsekventa och koncisa.

Meddelanden visas på slutpunkter när de utlöses manuellt och schemalagda genomsökningar slutförs och hot upptäcks. Dessa meddelanden visas också i **Meddelandecenter och** en sammanfattning av genomsökningar och hot identifieringar visas med jämna mellanrum.

Du kan också konfigurera hur standardaviseringar visas på slutpunkter, till exempel meddelanden för omstart eller när ett hot har upptäckts och åtgärdats.

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a>Konfigurera de ytterligare meddelanden som visas på slutpunkter

Du kan konfigurera visningen av ytterligare meddelanden, till exempel de senaste sammanfattningarna av hotidentifiering, [i Windows-säkerhet-appen](microsoft-defender-security-center-antivirus.md) och med Grupprincip.

> [!NOTE]
> I Windows 10, version 1607, kallades funktionen **förbättrade meddelanden** och kunde konfigureras under **Windows Inställningar** Update  >  **& säkerhets**  >  **Windows Defender**. I grupprincipinställningar i alla versioner Windows 10 kallas det **förbättrade meddelanden**.

> [!IMPORTANT]
> Om du inaktiverar ytterligare meddelanden inaktiveras inte kritiska meddelanden, till exempel aviseringar om hot identifiering och reparation.

**Använd appen Windows-säkerhet för att inaktivera ytterligare meddelanden:**

1. Öppna appen Windows-säkerhet genom att klicka på sköldikonen i Aktivitetsfältet eller söka på Start-menyn för **Säkerhet**.

2. Välj **Virus & hotskyddspanelen** (eller sköldikonen på den vänstra menyraden) och **välj sedan Virus & inställningar för skydd mot hot**

3. Bläddra till avsnittet **Meddelanden** och klicka på **Ändra meddelandeinställningar**.

4. Skjut omkopplaren till **Av** eller **På för** att inaktivera eller aktivera ytterligare meddelanden.

**Använd grupprincip för att inaktivera ytterligare meddelanden:**

1. Öppna konsolen Grupprinciphantering på datorn [grupprinciphantering](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))och högerklicka på det grupprincipobjekt som du vill konfigurera och klicka på **Redigera**.

2. Gå till **Datorkonfiguration i Redigeraren** **för grupprinciphantering**.

3. Klicka **på Administrativa mallar**.

4. Expandera trädet **Windows komponenter > Microsoft Defender Antivirus > rapportering**.

5. Dubbelklicka **på Inaktivera förbättrade meddelanden** och ställ in alternativet på **Aktiverad**. Klicka på **OK**. Detta förhindrar att ytterligare meddelanden visas.

## <a name="configure-standard-notifications-on-endpoints"></a>Konfigurera standardmeddelanden på slutpunkter

Du kan använda Grupprincip för att:

- Visa ytterligare, anpassad text på slutpunkter när användaren behöver utföra en åtgärd
- Dölja alla meddelanden på slutpunkter
- Dölja omstartsmeddelanden på slutpunkter

Att dölja aviseringar kan vara användbart i situationer där du inte kan dölja hela Microsoft Defender Antivirus gränssnittet. Se [Förhindra att användare ser eller interagerar med Microsoft Defender Antivirus för](prevent-end-user-interaction-microsoft-defender-antivirus.md) mer information. 

> [!NOTE]
> Att dölja meddelanden kommer bara att ske på punkter som principen har distribuerats till. Meddelanden relaterade till åtgärder som måste vidtas (till exempel en omstart) visas fortfarande på [Microsoft Endpoint Manager Endpoint Protection övervakningspanelen och rapporterna](/configmgr/protect/deploy-use/monitor-endpoint-protection). 

Se [Anpassa Windows-säkerhet för din organisation för instruktioner](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) om hur du lägger till anpassad kontaktinformation i de aviseringar som användarna ser på sina datorer.

**Använd Grupprincip för att dölja meddelanden:**

1. Öppna konsolen Grupprinciphantering på datorn [grupprinciphantering](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), högerklicka på det grupprincipobjekt som du vill konfigurera och klicka på **Redigera**.

2. Gå till **Datorkonfiguration i Redigeraren** **för grupprinciphantering** och klicka **på Administrativa mallar**.

3. Expandera trädet Windows **komponenter > Microsoft Defender Antivirus > klientgränssnittet**. 

4. Dubbelklicka **på Ignorera alla meddelanden** och ange alternativet **Aktiverad**. Klicka på **OK**. Detta förhindrar att ytterligare meddelanden visas.

**Använd Grupprincip för att dölja omstartsmeddelanden:**

1. Öppna konsolen Grupprinciphantering på datorn [grupprinciphantering](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))och högerklicka på det grupprincipobjekt som du vill konfigurera och klicka på **Redigera**.

2. Gå till **Datorkonfiguration i Redigeraren** **för grupprinciphantering**.

3. Klicka **på Administrativa mallar**.

4. Expandera trädet Windows **komponenter > Microsoft Defender Antivirus > klientgränssnittet**.

5. Dubbelklicka **på Ignorerar omstartsmeddelanden** och ställer in alternativet till **Aktiverad**. Klicka på **OK**. Detta förhindrar att ytterligare meddelanden visas.

## <a name="related-topics"></a>Relaterade ämnen

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Konfigurera slutanvändarinteraktion med Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md)
