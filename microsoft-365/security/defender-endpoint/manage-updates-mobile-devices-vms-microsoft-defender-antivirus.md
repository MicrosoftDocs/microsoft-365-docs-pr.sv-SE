---
title: Definiera hur mobila enheter uppdateras av Microsoft Defender Antivirus
description: Hantera hur mobila enheter, till exempel bärbara datorer, ska uppdateras med uppdateringar för Microsoft Defender Antivirus Protection.
keywords: uppdateringar, skydd, schemalägg uppdateringar, batteri, mobil enhet, bärbar dator, anteckningsbok, välja till, microsoft update, wsus, åsidosätt
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
ms.openlocfilehash: 143b0cb4bac1d3307e440f98fa4278f38e07c7f2
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269546"
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

Du kan använda Microsoft Update för att hålla Säkerhetsinformation på mobila enheter som kör Microsoft Defender Antivirus uppdaterat när de inte är anslutna till företagsnätverket eller annars inte har en WSUS-anslutning. 

Det innebär att skyddsuppdateringar kan levereras till enheter (via Microsoft Update) även om du har angett att WSUS ska åsidosätta Microsoft Update.

Du kan registrera dig för Microsoft Update på den mobila enheten på något av följande sätt:

- Ändra inställningen med Grupprincip.
- Använd VBScript för att skapa ett skript och kör det sedan på varje dator i nätverket.
- Registrera dig manuellt på alla datorer i nätverket via **menyn** Inställningar.

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a>Använd grupprincip för att registrera dig för Microsoft Update

1. På hanteringsdatorn för grupprinciper öppnar du [Konsolen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och väljer **Redigera.**

2. Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**

3. Välj **Principer** och **sedan Administrativa mallar.**

4. Expandera trädet till **Windows-komponenterna**  >  **Microsoft Defender Antivirus** Signature  >  **Updates**.

5. Ange **Tillåt säkerhetsintelligensuppdateringar från Microsoft Update** **till** Aktiverat och välj sedan **OK.**


### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a>Använda VBScript för att registrera sig för Microsoft Update

1. Använd anvisningarna i [MSDN-artikeln Välja att Microsoft Update ska användas för](/windows/win32/wua_sdk/opt-in-to-microsoft-update) att skapa VBScript-koden.

2. Kör VBScript-koden som du skapade på varje dator i nätverket.

### <a name="manually-opt-in-to-microsoft-update"></a>Registrera dig för Microsoft Update manuellt

1. Öppna **Windows Update** i & **säkerhetsinställningarna** på den dator som du vill registrera dig för.

2. Välj **Avancerade** alternativ.

3. Markera kryssrutan för Ge mig **uppdateringar för andra Microsoft-produkter när jag uppdaterar Windows.**

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a>Förhindra säkerhetsintelligensuppdateringar när de körs på batteri

Du kan konfigurera Microsoft Defender Antivirus för att bara ladda ned uppdateringar om datorn är ansluten till en kabelansluten strömkälla. 

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a>Använda grupprinciper för att förhindra säkerhetsintelligensuppdateringar på batterikraft

1.  Öppna Grupprinciphanteringskonsol på hanteringsdatorn för [grupprinciper,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))välj det grupprincipobjekt du vill konfigurera och öppna det för redigering.

2.  Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**

3.  Välj **Principer** och **sedan Administrativa mallar.**

4.  Expandera trädet till **Windows-komponenter** Microsoft Defender Antivirus Signature Updates och ange sedan Tillåt säkerhetsintelligensuppdateringar när  >    >   **batterikraften körs** till **Inaktiverad.** Välj sedan **OK**. 

Den här åtgärden förhindrar att uppdateringar laddas ned när datorn är på batterinivå.

## <a name="related-articles"></a>Relaterade artiklar

- [Hantera uppdateringar för Microsoft Defender Antivirus och tillämpa baslinjer](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Uppdatera och hantera Microsoft Defender Antivirus i Windows 10](deploy-manage-report-microsoft-defender-antivirus.md)