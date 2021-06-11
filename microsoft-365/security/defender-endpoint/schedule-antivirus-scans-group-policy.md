---
title: Schemalägga antivirussökningar med grupprinciper
description: Använda grupprinciper för att konfigurera antivirussökningar
keywords: snabbsökning, fullständig sökning, schema, grupprincip, antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 6f6018ec8b514234ab4f98e3d5416b472ff88739
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879796"
---
# <a name="schedule-antivirus-scans-using-group-policy"></a>Schemalägga antivirussökningar med grupprinciper

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

I den här artikeln beskrivs hur du konfigurerar schemalagda genomsökningar med grupprinciper. Mer information om hur du schemalägger skanningar och om genomsökningstyper finns i [Konfigurera schemalagda snabba eller Microsoft Defender Antivirus genomsökningar.](schedule-antivirus-scans.md) 

## <a name="configure-antivirus-scans-using-group-policy"></a>Konfigurera antivirussökningar med grupprinciper

1. Gå till Administrativa mallar för datorkonfiguration på hanteringsdatorn för grupprinciper i  >    >  **grupprincipredigeraren och klicka Windows komponenter**  >  **Microsoft Defender Antivirus**  >  **Genomsökning.**

2. Högerklicka på det grupprincipobjekt du vill konfigurera och välj sedan **Redigera**.

3. Ange inställningar för grupprincipobjektet och välj sedan **OK.** 

4. Upprepa steg 1–4 för varje inställning du vill konfigurera.

5. Distribuera grupprincipobjektet som vanligt. Om du behöver hjälp med grupprincipobjekt kan du gå [till Skapa ett grupprincipobjekt.](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)

> [!TIP]
> Se Hantera [när skyddsuppdateringar ska laddas ned och tillämpas och Förhindra](manage-protection-update-schedule-microsoft-defender-antivirus.md) eller tillåta användare att lokalt ändra [principinställningar.](configure-local-policy-overrides-microsoft-defender-antivirus.md)

## <a name="group-policy-settings-for-scheduling-scans"></a>Grupprincipinställningar för att schemalägga genomsökningar

| Plats | Inställning | Beskrivning | Standardinställning (om den inte konfigurerats) |
|:---|:---|:---|:---|
| Skanna | Ange vilken skanningstyp som ska användas för en schemalagd sökning | Snabbsökning |
| Skanna | Ange veckodagen då en schemalagd sökning ska köras | Ange den dag (eller aldrig) som ska köras. | Aldrig |
| Skanna | Ange tid på dagen då en schemalagd sökning ska köras | Ange antalet minuter efter midnatt (ange till exempel **60** för 01:00). | 02:00 |
| Rot | Slumpmässigt schemalagda aktivitetstider |I Microsoft Defender Antivirus kan du slumpmässigt lokalisera starttiden för genomsökningen till ett intervall mellan 0 och 4 timmar. <p>I [S ÄR KAN](/mem/intune/protect/certificates-scep-configure)du slumpmässigt göra genomsökningarna med ett intervall plus eller minus 30 minuter. Det kan vara användbart i virtuella maskiner eller VDI-distributioner. | Aktiverad |

## <a name="group-policy-settings-for-scheduling-scans-for-when-an-endpoint-is-not-in-use"></a>Grupprincipinställningar för att schemalägga genomsökningar när en slutpunkt inte används

| Plats | Inställning | Beskrivning | Standardinställning (om den inte konfigurerats) |
|:---|:---|:---|:---|
| Skanna | Starta den schemalagda genomsökningen bara när datorn är på, men inte använder | Schemalagda genomsökningar körs inte, om inte datorn är på men inte används | Aktiverad |

> [!NOTE]
> När du schemalägger genomsökningar efter tidpunkter när slutpunkter inte används, utnyttjar inte genomsökningar CPU-begränsningskonfigurationen och kommer att dra nytta av de tillgängliga resurserna för att slutföra genomsökningen så snabbt som möjligt.

## <a name="group-policy-settings-for-scheduling-remediation-required-scans"></a>Grupprincipinställningar för att schemalägga genomsökningar som krävs

| Plats | Inställning | Beskrivning | Standardinställning (om den inte konfigurerats) |
|---|---|---|---|
| Åtgärda | Ange veckodagen då en schemalagd fullständig genomsökning ska köras | Ange den dag (eller aldrig) som ska köras. | Aldrig |
| Åtgärda | Ange tid på dagen då en schemalagd fullständig genomsökning ska köras för att slutföra åtgärd | Ange antalet minuter efter midnatt (ange till exempel **60** för 01:00) | 02:00 |

## <a name="group-policy-settings-for-scheduling-daily-scans"></a>Grupprincipinställningar för att schemalägga dagliga genomsökningar

| Plats | Inställning | Beskrivning | Standardinställning (om den inte konfigurerats) |
|:---|:---|:---|:---|
| Skanna | Ange tidsintervallet för att köra snabbsökningar per dag | Ange hur många timmar som ska förfluta före nästa snabbsökning. Om du till exempel vill köra varannan timme anger **du 2**, för en gång om dagen skriver du **24**. Ange **0 för** att aldrig köra en daglig snabbsökning. | Aldrig |
| Skanna | Ange tiden för en daglig snabbsökning | Ange antalet minuter efter midnatt (ange till exempel **60** för 01:00) | 02:00 |

## <a name="group-policy-settings-for-scheduling-scans-after-protection-updates"></a>Grupprincipinställningar för schemaläggning av genomsökningar efter skyddsuppdateringar

| Plats | Inställning | Beskrivning | Standardinställning (om den inte konfigurerats)|
|:---|:---|:---|:---|
| Signaturuppdateringar | Aktivera genomsökning efter säkerhetsintelligensuppdatering | En genomsökning görs direkt efter att en ny skyddsuppdatering har laddats ned | Aktiverad |

