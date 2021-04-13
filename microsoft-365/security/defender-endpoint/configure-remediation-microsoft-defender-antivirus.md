---
title: Konfigurera åtgärder för identifiering av Microsoft Defender Antivirus
description: Konfigurera vad Microsoft Defender Antivirus ska göra när programmet upptäcker ett hot och hur länge filer i karantän ska behållas i karantänmappen
keywords: åtgärd, åtgärda, ta bort, hot, karantän, genomsökning, återställning
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 03/16/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7f41e9c5b38e93ce84fbd971e02ebc2d77432c3f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690857"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a>Konfigurera åtgärder för identifiering av Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

När en genomsökning körs med Microsoft Defender Antivirus görs ett försök att åtgärda eller ta bort identifierade hot. Du kan konfigurera hur Microsoft Defender Antivirus ska hantera vissa hot, om en återställningspunkt ska skapas innan en återställningspunkt åtgärdas och när hot ska tas bort.

I den här artikeln beskrivs hur du konfigurerar de här inställningarna med grupprinciper, men du kan också använda [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) och Microsoft [Intune.](/intune/device-restrictions-configure) 

Du kan också använda [ `Set-MpPreference` PowerShell-cmdleten eller](/powershell/module/defender/set-mppreference) [ `MSFT_MpPreference` WMI-klassen för](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) att konfigurera de här inställningarna.

## <a name="configure-remediation-options"></a>Konfigurera alternativ för åtgärder

1. På datorn för grupprinciphantering öppnar du [Konsolen för](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

2. I **redigeraren för hantering av grupprinciper** går **du till Datorkonfiguration** och **väljer Administrativa mallar**.

3. Expandera trädet till **Windows-komponenterna**  >  **Microsoft Defender Antivirus.** 

4. Välj en plats i tabellen nedan och redigera sedan principen efter behov. 

5. Välj **OK**.

|Plats | Inställning | Beskrivning | Standardinställning (om den inte konfigurerats) |
|:---|:---|:---|:---|
|Skanna | Skapa en systemåterställningspunkt | En systemåterställningspunkt skapas varje dag innan du försöker rensa eller skanna | Inaktiverad|
|Skanna | Aktivera borttagning av objekt från mappen genomsökningshistorik | Ange hur många dagar objekt ska sparas i genomsökningshistoriken | 30 dagar |
|Rot | Inaktivera rutinreparation | Du kan ange om Microsoft Defender Antivirus automatiskt åtgärdar hot eller om den ska fråga slutpunktsanvändaren vad som ska göras. | Inaktiverad (hot åtgärdas automatiskt) |
|Karantän | Konfigurera borttagning av objekt från mappen Karantän | Ange hur många dagar objekt ska behållas i karantän innan de tas bort | 90 dagar |
|Hot | Ange varningsnivåer för hot där standardåtgärden inte ska vidtas när den upptäcks | Alla hot som upptäcks av Microsoft Defender Antivirus tilldelas en hotnivå (låg, medium, hög eller allvarligt). Du kan använda den här inställningen för att definiera hur alla hot för de olika hotnivåerna ska åtgärdas (karantän, tas bort eller ignoreras) | Ej tillämpligt |
|Hot | Ange hot där standardåtgärden inte ska vidtas när den identifieras | Ange hur specifika hot (med hjälp av deras hot-ID) ska åtgärdas. Du kan ange om det specifika hotet ska sätts i karantän, tas bort eller ignoreras | Ej tillämpligt |

> [!IMPORTANT]
> Microsoft Defender Antivirus identifierar och åtgärdar filer baserat på många faktorer. Ibland krävs en omstart för att slutföra en åtgärd. Även om identifieringen senare bestäms som en falsk positiv identifiering måste omstarten slutföras för att säkerställa att alla ytterligare åtgärder har slutförts.
>
> Om du har vissa Microsoft Defender Antivirus i karantän en fil baserat på en felaktighet, kan du återställa filen från karantän när enheten startas om. Se [Återställa filer i karantän i Microsoft Defender Antivirus.](restore-quarantined-files-microsoft-defender-antivirus.md)
> 
> Du kan undvika det här problemet i framtiden genom att utesluta filer från genomsökningarna. Se [Konfigurera och validera undantag för Microsoft Defender Antivirus-genomsökningar.](configure-exclusions-microsoft-defender-antivirus.md)

Se även [Konfigurera åtgärd krävs för fullständiga genomsökningar](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) för Microsoft Defender Antivirus för fler åtgärdsrelaterade inställningar.

## <a name="see-also"></a>Se även

- [Konfigurera sökalternativ för Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Konfigurera schemalagda genomsökningar för Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Konfigurera och köra genomsökningar för Microsoft Defender Antivirus på begäran](run-scan-microsoft-defender-antivirus.md)
- [Konfigurera meddelanden som visas på slutpunkter](configure-notifications-microsoft-defender-antivirus.md)
- [Konfigurera interaktion med slutanvändaren Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [Anpassa, initiera och granska resultatet av genomsökningar och åtgärder i Microsoft Defender Antivirus](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)