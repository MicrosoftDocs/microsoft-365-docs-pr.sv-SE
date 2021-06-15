---
title: Definiera hur mobila enheter uppdateras genom att Microsoft Defender Antivirus
description: Hantera hur mobila enheter, till exempel bärbara datorer, ska uppdateras med Microsoft Defender Antivirus säkerhetsuppdateringar.
keywords: uppdateringar, skydd, schemalägg uppdateringar, batteri, mobil enhet, bärbar dator, anteckningsbok, välja till, microsoft update, wsus, åsidosätt
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 809f4573c91f7f1882693cbd8c63d88b06b55c67
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926013"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a>Hantera uppdateringar för mobila enheter och virtuella datorer(VM)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Mobila enheter och virtuella maskiner kan kräva mer konfiguration för att säkerställa att prestanda inte påverkas av uppdateringar.

Det finns två inställningar som är användbara för dessa enheter:

- Registrera dig för Microsoft Update på mobila datorer utan WSUS-anslutning
- Förhindra säkerhetsintelligensuppdateringar när de körs på batteri

Följande artiklar kan också vara användbara i dessa situationer:
- [Konfigurera schemalagda och uppläsningssökningar](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Hantera uppdateringar för slutpunkter som är in uppdaterade](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Distributionsguide för Microsoft Defender Antivirus i en VDI-miljö (Virtual Desktop Infrastructure)](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a>Registrera dig för Microsoft Update på mobila datorer utan WSUS-anslutning

Du kan använda Microsoft Update för att hålla Säkerhetsinformation på mobila enheter som kör Microsoft Defender Antivirus uppdaterade när de inte är anslutna till företagsnätverket eller annars inte har en WSUS-anslutning. 

Det innebär att skyddsuppdateringar kan levereras till enheter (via Microsoft Update) även om du har angett att WSUS ska åsidosätta Microsoft Update.

Du kan registrera dig för Microsoft Update på den mobila enheten på något av följande sätt:

- Ändra inställningen med Grupprincip.
- Använd VBScript för att skapa ett skript och kör det sedan på varje dator i nätverket.
- Registrera dig manuellt på alla datorer i nätverket via **Inställningar** dator.

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a>Använd grupprincip för att registrera dig för Microsoft Update

1. På hanteringsdatorn för grupprinciper öppnar du [Konsolen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och väljer **Redigera.**

2. Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**

3. Välj **Principer** och **sedan Administrativa mallar.**

4. Expandera trädet så att **det Windows komponenter**  >  **Microsoft Defender Antivirus**  >  **Signaturuppdateringar**.

5. Ange **Tillåt säkerhetsintelligensuppdateringar från Microsoft Update** **till** Aktiverat och välj sedan **OK.**


### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a>Använda VBScript för att registrera sig för Microsoft Update

1. Använd anvisningarna i [MSDN-artikeln Välja att Microsoft Update ska användas för](/windows/win32/wua_sdk/opt-in-to-microsoft-update) att skapa VBScript-koden.

2. Kör VBScript-koden som du skapade på varje dator i nätverket.

### <a name="manually-opt-in-to-microsoft-update"></a>Registrera dig för Microsoft Update manuellt

1. Öppna **Windows i** **Uppdatera & säkerhetsinställningarna** på den dator som du vill registrera dig för.

2. Välj **Avancerade** alternativ.

3. Markera kryssrutan för Ge **mig uppdateringar för andra Microsoft-produkter när jag uppdaterar Windows**.

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a>Förhindra säkerhetsintelligensuppdateringar när de körs på batteri

Du kan Microsoft Defender Antivirus att endast ladda ned skyddsuppdateringar när datorn är ansluten till en kabelansluten strömkälla. 

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a>Använda grupprinciper för att förhindra säkerhetsintelligensuppdateringar på batterikraft

1.  Öppna Grupprinciphanteringskonsol på hanteringsdatorn för [grupprinciper,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))välj det grupprincipobjekt du vill konfigurera och öppna det för redigering.

2.  Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**

3.  Välj **Principer** och **sedan Administrativa mallar.**

4.  Expandera trädet så att **Windows-komponenter** Microsoft Defender Antivirus signaturuppdateringar och ange sedan Tillåt säkerhetsintelligensuppdateringar när batteriet  >    >   **körs** till **Inaktiverat.** Välj sedan **OK**. 

Den här åtgärden förhindrar att uppdateringar laddas ned när datorn är på batterinivå.

## <a name="related-articles"></a>Relaterade artiklar

- [Hantera Microsoft Defender Antivirus uppdateringar och använda baslinjer](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Uppdatera och hantera Microsoft Defender Antivirus i Windows 10](deploy-manage-report-microsoft-defender-antivirus.md)