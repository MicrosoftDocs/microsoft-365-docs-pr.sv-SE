---
title: Konfigurera lokala åsidosättningar för Microsoft Defender AV-inställningar
description: Aktivera eller inaktivera användare från att ändra inställningar lokalt i Microsoft Defender AV.
keywords: lokal åsidosättning, lokal princip, grupprincip, gpo, nedlåst lista, sammanslagning, listor
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 02/13/2020
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 2d23ca6d98d86666d72b75723a2205fcd83b08d7
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924249"
---
# <a name="prevent-or-allow-users-to-locally-modify-microsoft-defender-antivirus-policy-settings"></a>Förhindra eller tillåta användare att lokalt ändra Microsoft Defender Antivirus principinställningar


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Som standard Microsoft Defender Antivirus inställningar som distribueras via ett grupprincipobjekt till slutpunkterna i nätverket hindra användare från att ändra inställningarna lokalt. Du kan ändra detta i vissa fall.

Det kan till exempel vara nödvändigt att ge vissa användargrupper (till exempel säkerhetsundersöknings- och hothot) ytterligare kontroll över enskilda inställningar i de slutpunkter de använder.

## <a name="configure-local-overrides-for-microsoft-defender-antivirus-settings"></a>Konfigurera lokala åsidosättningar för Microsoft Defender Antivirus inställningar

Standardinställningen för de här principerna är **Inaktiverad.**

Om de är inställda på Aktiverad kan användare i slutpunkter göra ändringar i den associerade inställningen med [Windows-säkerhet-appen,](microsoft-defender-security-center-antivirus.md) lokala grupprincipinställningar och PowerShell-cmdlets (vid behov).

I följande tabell visas var och en av inställningarna för åsidosättningsprincip och konfigurationsinstruktioner för den associerade funktionen eller inställningen.

Så här konfigurerar du de här inställningarna:

1. På datorn för grupprinciphantering öppnar du [Konsolen för](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

2. I **redigeraren för grupprinciphantering går** du till **Datorkonfiguration och** klickar på **Administrativa mallar**.

3. Expandera trädet för **att Windows delar > Microsoft Defender Antivirus** och sedan den **Plats** som anges i tabellen nedan.

4. Dubbelklicka på den **principinställning** som anges i tabellen nedan och ange önskat alternativ. Klicka **på OK** och upprepa för alla andra inställningar.

5. Distribuera grupprincipobjektet som vanligt.

Plats | Inställning | Artikel
---|---|---|---
KARTOR | Konfigurera åsidosättning av lokal inställning för rapportering till Microsoft MAPS | [Aktivera molnbaserat skydd](enable-cloud-protection-microsoft-defender-antivirus.md)
Karantän | Konfigurera åsidosättning av lokal inställning för borttagning av objekt från mappen Karantän | [Konfigurera åtgärd för genomsökningar](configure-remediation-microsoft-defender-antivirus.md)
Realtidsskydd | Konfigurera en lokal åsidosättning för övervakning av fil- och programaktivitet på datorn | [Aktivera och Microsoft Defender Antivirus av skydd och övervakning alltid](configure-real-time-protection-microsoft-defender-antivirus.md)
Realtidsskydd | Konfigurera åsidosättning av lokal inställning för övervakning av inkommande och utgående filaktivitet | [Aktivera och Microsoft Defender Antivirus av skydd och övervakning alltid](configure-real-time-protection-microsoft-defender-antivirus.md)
Realtidsskydd | Konfigurera åsidosättning av lokal inställning för genomsökning av alla nedladdade filer och bifogade filer | [Aktivera och Microsoft Defender Antivirus av skydd och övervakning alltid](configure-real-time-protection-microsoft-defender-antivirus.md)
Realtidsskydd | Konfigurera åsidosättning av lokal inställning för att aktivera beteendeuppföljning | [Aktivera och Microsoft Defender Antivirus av skydd och övervakning alltid](configure-real-time-protection-microsoft-defender-antivirus.md)
Realtidsskydd | Konfigurera åsidosättning av lokal inställning för att aktivera realtidsskydd | [Aktivera och Microsoft Defender Antivirus av skydd och övervakning alltid](configure-real-time-protection-microsoft-defender-antivirus.md)
Åtgärda | Konfigurera en lokal åsidosättning för tid på dagen för att köra en schemalagd fullständig genomsökning för att slutföra åtgärd | [Konfigurera åtgärd för genomsökningar](configure-remediation-microsoft-defender-antivirus.md)
Skanna | Konfigurera åsidosättning av lokal inställning för maximal procentandel av CPU-belastningen | [Konfigurera och köra genomsökningar](run-scan-microsoft-defender-antivirus.md)
Skanna | Konfigurera åsidosättning av lokal inställning för schemasökningsdag | [Konfigurera schemalagda genomsökningar](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
Skanna | Konfigurera åsidosättning av lokal inställning för schemalagd snabbsökningstid | [Konfigurera schemalagda genomsökningar](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
Skanna | Konfigurera åsidosättning av lokal inställning för schemalagd genomsökningstid | [Konfigurera schemalagda genomsökningar](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
Skanna | Konfigurera en lokal åsidosättning av lokal inställning för den genomsökningstyp som ska användas för en schemalagd sökning | [Konfigurera schemalagda genomsökningar](scheduled-catch-up-scans-microsoft-defender-antivirus.md)

<a id="merge-lists"></a>

## <a name="configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged"></a>Konfigurera hur lokalt och globalt definierade hotreparations- och undantagslistor slås samman

Du kan också konfigurera hur lokalt definierade listor kombineras eller sammanfogas med globalt definierade listor. Den här inställningen gäller [för undantagslistor,](configure-exclusions-microsoft-defender-antivirus.md) [angivna åtgärdslistor](configure-remediation-microsoft-defender-antivirus.md)och minskning [av attackytan.](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)

Som standard sammanfogas listor som har konfigurerats i den lokala grupprincipen och Windows-säkerhet-programmet med listor som definieras av lämpligt grupprincipobjekt som du har distribuerat i nätverket. Där det finns konflikter har den globalt definierade listan företräde.

Du kan inaktivera den här inställningen för att säkerställa att endast globalt definierade listor (till exempel från distribuerade GPOs) används.

### <a name="use-group-policy-to-disable-local-list-merging"></a>Använda grupprinciper för att inaktivera koppling av lokala listor

1. På datorn för grupprinciphantering öppnar du [Konsolen för](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

2. I **redigeraren för grupprinciphantering går** du till **Datorkonfiguration och** klickar på **Administrativa mallar**.

3. Expandera trädet för att **Windows komponenter > Microsoft Defender Antivirus**.

4. Dubbelklicka på Konfigurera **lokala administratörskopplingsbeteenden för listor** och ställ in alternativet på **Inaktiverad**. Klicka på **OK**.

> [!NOTE]
> Om du inaktiverar lokal listkoppling åsidosätts inställningarna för kontrollerad mappåtkomst. Den åsidosätter även eventuella skyddade mappar eller tillåtna appar som angetts av den lokala administratören. Mer information om styrda inställningar för mappåtkomst finns [i Tillåta blockerad app i Windows-säkerhet](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security).

## <a name="related-topics"></a>Relaterade ämnen

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Konfigurera slutanvändares interaktion med Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md)
