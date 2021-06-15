---
title: Konfigurera åtgärd för identifiering för Microsoft Defender Antivirus
description: Konfigurera vad Microsoft Defender Antivirus ska göra när den upptäcker ett hot och hur länge filer i karantän ska behållas i karantänmappen
keywords: åtgärd, åtgärda, ta bort, hot, karantän, genomsökning, återställning
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
ms.date: 03/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 9b765d14e31d6c4890aeace41e4fe79bafdd889e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925581"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a>Konfigurera åtgärd för identifiering för Microsoft Defender Antivirus


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

När Microsoft Defender Antivirus kör en genomsökning försöker den åtgärda eller ta bort hot som upptäcks. Du kan konfigurera hur Microsoft Defender Antivirus ska hantera vissa hot, om en återställningspunkt ska skapas innan en återställningspunkt åtgärdas och när hot ska tas bort.

I den här artikeln beskrivs hur du konfigurerar de här inställningarna med grupprinciper, men du kan [också använda Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) och [Microsoft Intune.](/intune/device-restrictions-configure) 

Du kan också använda [ `Set-MpPreference` PowerShell-cmdleten eller](/powershell/module/defender/set-mppreference) [ `MSFT_MpPreference` WMI-klassen för](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) att konfigurera de här inställningarna.

## <a name="configure-remediation-options"></a>Konfigurera alternativ för åtgärder

1. På datorn för grupprinciphantering öppnar du [Konsolen för](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

2. I **redigeraren för hantering av grupprinciper** går **du till Datorkonfiguration** och **väljer Administrativa mallar**.

3. Expandera trädet och visa **Windows komponenter**  >  **Microsoft Defender Antivirus**. 

4. Välj en plats i tabellen nedan och redigera sedan principen efter behov. 

5. Välj **OK**.

|Plats | Inställning | Beskrivning | Standardinställning (om den inte konfigurerats) |
|:---|:---|:---|:---|
|Skanna | Skapa en systemåterställningspunkt | En systemåterställningspunkt skapas varje dag innan du försöker rensa eller skanna | Inaktiverad|
|Skanna | Aktivera borttagning av objekt från mappen genomsökningshistorik | Ange hur många dagar objekt ska sparas i genomsökningshistoriken | 30 dagar |
|Rot | Inaktivera rutinreparation | Du kan ange Microsoft Defender Antivirus automatiskt åtgärdar hot eller om slutpunktsanvändaren ska fråga vad han eller hon ska göra. | Inaktiverad (hot åtgärdas automatiskt) |
|Karantän | Konfigurera borttagning av objekt från mappen Karantän | Ange hur många dagar objekt ska behållas i karantän innan de tas bort | 90 dagar |
|Hot | Ange varningsnivåer för hot där standardåtgärden inte ska vidtas när den upptäcks | Alla hot som upptäcks av Microsoft Defender Antivirus tilldelas en hotnivå (låg, medium, hög eller allvarligt). Du kan använda den här inställningen för att definiera hur alla hot för de olika hotnivåerna ska åtgärdas (karantän, tas bort eller ignoreras) | Ej tillämpligt |
|Hot | Ange hot där standardåtgärden inte ska vidtas när den identifieras | Ange hur specifika hot (med hjälp av deras hot-ID) ska åtgärdas. Du kan ange om det specifika hotet ska sätts i karantän, tas bort eller ignoreras | Ej tillämpligt |

> [!IMPORTANT]
> Microsoft Defender Antivirus identifierar och åtgärdar filer baserat på många faktorer. Ibland krävs en omstart för att slutföra en åtgärd. Även om identifieringen senare bestäms som en falsk positiv identifiering måste omstarten slutföras för att säkerställa att alla ytterligare åtgärder har slutförts.
>
> Om du är säker Microsoft Defender Antivirus i karantän för en fil baserat på en felaktighet, kan du återställa filen från karantän efter att enheten startats om. Se [Återställa filer i karantän i Microsoft Defender Antivirus](restore-quarantined-files-microsoft-defender-antivirus.md).
> 
> Du kan undvika det här problemet i framtiden genom att utesluta filer från genomsökningarna. Se [Konfigurera och validera undantag för Microsoft Defender Antivirus genomsökningar](configure-exclusions-microsoft-defender-antivirus.md).

Mer [åtgärdsrelaterade inställningar finns även i Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) schemalagda helskärmssökningar.

## <a name="see-also"></a>Se även

- [Konfigurera alternativ för genomsökning i Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Konfigurera schemalagda Microsoft Defender Antivirus genomsökningar](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Konfigurera och kör genomsökningar på begäran för Microsoft Defender Antivirus](run-scan-microsoft-defender-antivirus.md)
- [Konfigurera meddelanden som visas på slutpunkter](configure-notifications-microsoft-defender-antivirus.md)
- [Konfigurera interaktion mellan slutanvändare Microsoft Defender Antivirus slutanvändare](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [Anpassa, initiera och granska resultaten av Microsoft Defender Antivirus genomsökningar och åtgärder](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
