---
title: Dölja Microsoft Defender Antivirus gränssnittet
description: Du kan dölja panel för skydd mot virus och hot Windows-säkerhet appen.
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
ms.openlocfilehash: ff0e134d38288b12cbc46dc3ca5f103fbf8c7ad9
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007675"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a>Hindra användare från att se eller interagera Microsoft Defender Antivirus användargränssnittet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Du kan använda Grupprincip för att hindra användare i slutpunkter från att se Microsoft Defender Antivirus gränssnitt. Du kan också förhindra att genomsökningar pausas.

## <a name="hide-the-microsoft-defender-antivirus-interface"></a>Dölja Microsoft Defender Antivirus gränssnittet

I Windows 10 version 1703 döljs Microsoft Defender Antivirus-meddelanden och skyddspanelen för Virus & förhindras från att visas i Windows-säkerhet-appen.

Med inställningen **aktiverad:**

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="Windows-säkerhet utan sköldikonen och avsnittet om skydd mot virus och hot":::

Med inställningen inställd på **Inaktiverad** eller ej konfigurerad:

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="Skärmbild av Windows-säkerhet med avsnitten sköldikon och skydd mot hot":::

>[!NOTE]
>Om du döljer gränssnittet förhindras Microsoft Defender Antivirus meddelanden från att visas på slutpunkten. Microsoft Defender för slutpunktsmeddelanden visas fortfarande. Du kan också [individuellt konfigurera meddelanden som visas på slutpunkter](configure-notifications-microsoft-defender-antivirus.md)

I tidigare Windows 10 döljs klientgränssnittet i Windows Defender inställningar. Om användaren försöker öppna den får de ett varningsmeddelande där det står "Systemadministratören har begränsad åtkomst till den här appen".

:::image type="content" source="../../media/wdav-headless-mode-1607.png" alt-text="Varningsmeddelande när huvudlöst läge är aktiverat i Windows 10, tidigare versioner än 1703":::

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a>Använda grupprinciper för att dölja Microsoft Defender AV-gränssnittet för användare

1. På hanteringsdatorn för grupprinciper öppnar du [Konsolen](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

2. Med **grupprinciphanteringsredigeraren går** du till **Datorkonfiguration**.

3. Klicka **på Administrativa mallar**.

4. Expandera trädet och visa **Windows i > Microsoft Defender Antivirus > klientgränssnittet.**

5. Dubbelklicka på inställningen Aktivera **huvudlöst gränssnittsläge** och ange alternativet **Aktiverad**. Klicka på **OK**. 

Mer [information om hur du hindrar användare från att](configure-local-policy-overrides-microsoft-defender-antivirus.md) ändra skydd på datorer finns i Hindra användare från att ändra principinställningar lokalt.

## <a name="prevent-users-from-pausing-a-scan"></a>Hindra användare från att pausa en genomsökning

Du kan förhindra att användare pausar genomsökningar, vilket kan vara användbart för att säkerställa att schemalagda eller on-demand-sökningar inte avbryts av användarna.

> [!NOTE]
> Den här inställningen stöds inte på Windows 10.

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a>Använda grupprinciper för att hindra användare från att pausa en genomsökning

1. På hanteringsdatorn för grupprinciper öppnar du [Konsolen](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

2. Med **grupprinciphanteringsredigeraren går** du till **Datorkonfiguration**.

3. Klicka **på Administrativa mallar**.

4. Expandera trädet för att **Windows komponenter**  >  **Microsoft Defender Antivirus**  >  **Sök**.

5. Dubbelklicka på inställningen Tillåt **användare att pausa genomsökning** och ange alternativet **Inaktiverad**. Klicka på **OK**. 

## <a name="related-articles"></a>Relaterade artiklar

- [Konfigurera meddelanden som visas på slutpunkter](configure-notifications-microsoft-defender-antivirus.md)

- [Konfigurera slutanvändares interaktion med Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)