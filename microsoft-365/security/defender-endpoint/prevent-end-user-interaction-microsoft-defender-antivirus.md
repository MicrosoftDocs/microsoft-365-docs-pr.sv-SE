---
title: Dölja Antivirusgränssnittet i Microsoft Defender
description: Du kan dölja panelen för skydd mot virus och hot i Windows-säkerhetsappen.
keywords: nedlåst gränssnitt, huvudlöst läge, dölja app, dölja inställningar, dölja gränssnitt
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
ms.openlocfilehash: 06ee2f1cb68df0a957818e1fccb45628487c39fd
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274922"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a>Hindra användare från att se eller interagera med användargränssnittet i Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Du kan använda grupprinciper för att hindra användare på slutpunkter från att se Microsoft Defender Antivirus-gränssnittet. Du kan också förhindra att genomsökningar pausas.

## <a name="hide-the-microsoft-defender-antivirus-interface"></a>Dölja Antivirusgränssnittet i Microsoft Defender

Om du döljer gränssnittet i Windows 10 version 1703 döljs meddelanden från Microsoft Defender Antivirus och skyddspanelen för Virus & förhindras från att visas i Windows-säkerhetsappen.

Med inställningen **aktiverad:**

![Skärmbild av Windows-säkerhet utan sköldikonen och avsnittet om skydd mot virus och hot](images/defender/wdav-headless-mode-1703.png)

Med inställningen inställd på **Inaktiverad** eller ej konfigurerad:

![Skärmbild av Windows-säkerhet som visar sköldikonen samt avsnittet om skydd mot virus och hot](images/defender/wdav-headless-mode-off-1703.png)

>[!NOTE]
>Om du döljer gränssnittet förhindrar du också att meddelanden från Microsoft Defender Antivirus visas på slutpunkten. Microsoft Defender för slutpunktsmeddelanden visas fortfarande. Du kan också [individuellt konfigurera meddelanden som visas på slutpunkter](configure-notifications-microsoft-defender-antivirus.md)

I tidigare versioner av Windows 10 döljs Windows Defender-klientgränssnittet vid inställningen. Om användaren försöker öppna den får de ett varningsmeddelande där det står "Systemadministratören har begränsad åtkomst till den här appen".

![Varningsmeddelande när huvudlöst läge är aktiverat i Windows 10, tidigare versioner än 1703](images/defender/wdav-headless-mode-1607.png)

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a>Använda grupprinciper för att dölja Microsoft Defender AV-gränssnittet för användare

1. På hanteringsdatorn för grupprinciper öppnar du [Konsolen](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

2. Med **grupprinciphanteringsredigeraren går** du till **Datorkonfiguration**.

3. Klicka **på Administrativa mallar**.

4. Expandera trädet till **Windows-komponenter > Microsoft Defender Antivirus> klientgränssnittet**.

5. Dubbelklicka på inställningen Aktivera **huvudlöst gränssnittsläge** och ange alternativet **Aktiverad**. Klicka på **OK**. 

Mer [information om hur du hindrar användare från att](configure-local-policy-overrides-microsoft-defender-antivirus.md) ändra skydd på datorer finns i Hindra användare från att ändra principinställningar lokalt.

## <a name="prevent-users-from-pausing-a-scan"></a>Hindra användare från att pausa en genomsökning

Du kan förhindra att användare pausar genomsökningar, vilket kan vara användbart för att säkerställa att schemalagda eller on-demand-sökningar inte avbryts av användarna.

> [!NOTE]
> Den här inställningen stöds inte i Windows 10.

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a>Använda grupprinciper för att hindra användare från att pausa en genomsökning

1. På hanteringsdatorn för grupprinciper öppnar du [Konsolen](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

2. Med **grupprinciphanteringsredigeraren går** du till **Datorkonfiguration**.

3. Klicka **på Administrativa mallar**.

4. Expandera trädet till **Windows-komponenterna**  >  **Microsoft Defender Antivirus**  >  **Scan**.

5. Dubbelklicka på inställningen Tillåt **användare att pausa genomsökning** och ange alternativet **Inaktiverad**. Klicka på **OK**. 

## <a name="related-articles"></a>Relaterade artiklar

- [Konfigurera meddelanden som visas på slutpunkter](configure-notifications-microsoft-defender-antivirus.md)

- [Konfigurera interaktion med slutanvändare med Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)