---
title: Felsöka problem med rapporteringsverktyg för Microsoft Defender AV
description: Identifiera och lösa vanliga problem när du försöker rapportera i Microsoft Defender AV-skyddsstatus i Uppdateringsefterlevnad
keywords: felsökning, fel, korrigering, uppdateringsefterlevnad, oms, bildskärm, rapport, Microsoft Defender AV
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
ms.openlocfilehash: 405955de63de9f84a783ca1b8c0348c3935440cd
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926181"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a>Felsök rapportering för Microsoft Defender Antivirus i Uppdateringsefterlevnad

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> Den 31 mars 2020 Microsoft Defender Antivirus bort rapporteringsfunktionen i Uppdateringsefterlevnad. Du kan fortsätta att definiera och granska principer för säkerhetsefterlevnad [med hjälp Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager), vilket ger bättre kontroll över säkerhetsfunktioner och uppdateringar.

Du kan använda Microsoft Defender Antivirus med Uppdateringsefterlevnad. Status för E3, B, F1, VL och Pro licens. Men för E5-licenser måste du använda [Microsoft Defender för Endpoint-portalen](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Mer information om licensalternativ finns i Windows 10 [licensalternativ.](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)

När du använder Windows analysuppdateringsefterlevnad för att få rapporter om [skyddsstatus](/windows/deployment/update/update-compliance-using#wdav-assessment) för enheter eller slutpunkter i ditt nätverk som använder Microsoft Defender Antivirus kan du stöta på problem eller problem.

De vanligaste indikatorerna på ett problem är vanligtvis:
- Du ser bara ett litet antal eller delmängd av alla enheter som du förväntade dig att se
- Du ser inga enheter alls
- Rapporterna och informationen som visas är inaktuell (äldre än några dagar)

Information om vanliga felkoder och händelse-IDt som är Microsoft Defender Antivirus tjänst som inte är relaterad till Uppdateringsefterlevnad finns [i Microsoft Defender Antivirus händelser.](troubleshoot-microsoft-defender-antivirus.md) 

Det finns tre steg för att felsöka de här problemen:

1. Kontrollera att du har uppfyllt alla krav
2. Kontrollera anslutningen till Windows Defender molnbaserad tjänst
3. Skicka supportloggar

>[!IMPORTANT]
>Det tar normalt 3 dagar för enheter att börja visas i Uppdateringsefterlevnad.


## <a name="confirm-prerequisites"></a>Bekräfta förutsättningarna

För att enheter ska visas korrekt i Uppdateringsefterlevnad måste du uppfylla vissa krav för både tjänsten för uppdateringsefterlevnad och för Microsoft Defender Antivirus:

>[!div class="checklist"]
>- Slutpunkter använder Microsoft Defender Antivirus som den enda antivirusskyddsappen. [Om du använder någon annan antivirusapp inaktiveras microsoft Defender AV](microsoft-defender-antivirus-compatibility.md) och slutpunkten rapporteras inte under Uppdateringsefterlevnad.
> - [Moln levererat skydd är aktiverat.](enable-cloud-protection-microsoft-defender-antivirus.md)
> - Slutpunkter kan [ansluta till Microsoft Defender AV-molnet](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)
> - Om slutpunkten körs med Windows 10 version 1607 eller tidigare [måste Windows 10 av diagnostikdata](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)anges till nivån Utökad.
> - Det har gått tre dagar sedan alla krav har uppfyllts

"Du kan använda Microsoft Defender Antivirus med uppdateringsefterlevnad. Status för E3, B, F1, VL och Pro licens. Men för E5-licenser måste du använda Microsoft Defender för Slutpunktsportalen (/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Mer information om licensalternativ finns i Windows 10 licensalternativ"

Om samtliga krav ovan är uppfyllda kan du behöva gå vidare till nästa steg för att samla in diagnostikinformation och skicka den till oss.

> [!div class="nextstepaction"]
> [Samla in diagnostikdata för felsökning av uppdateringsefterlevnad](collect-diagnostic-data.md)  

## <a name="related-topics"></a>Relaterade ämnen

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Distribuera Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)