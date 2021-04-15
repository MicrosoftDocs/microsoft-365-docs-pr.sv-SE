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
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 50136c620450861c41513650f27bf24fc782e968
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764537"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a>Felsöka rapportering av Microsoft Defender Antivirus vid uppdateringsefterlevnad

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> Den 31 mars 2020 kommer rapportfunktionen för Uppdateringsefterlevnad för Microsoft Defender Antivirus att tas bort. Du kan fortsätta att definiera och granska principer för säkerhetsefterlevnad med hjälp av [Microsoft Endpoint Manager,](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)som gör att du får bättre kontroll över säkerhetsfunktioner och uppdateringar.

Du kan använda Microsoft Defender Antivirus med Uppdateringsefterlevnad. Du ser status för E3-, B-, F1-, VL- och Pro-licenser. Men för E5-licenser måste du använda [Microsoft Defender för Endpoint-portalen](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Mer information om licensalternativ finns i [Licensalternativ för Windows 10.](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)

När du använder Windows Analytics Update Compliance för att få rapporter om [skyddsstatus](/windows/deployment/update/update-compliance-using#wdav-assessment) för enheter eller slutpunkter i nätverket som använder Microsoft Defender Antivirus kan du stöta på problem eller problem.

De vanligaste indikatorerna på ett problem är vanligtvis:
- Du ser bara ett litet antal eller delmängd av alla enheter som du förväntade dig att se
- Du ser inga enheter alls
- Rapporterna och informationen som visas är inaktuell (äldre än några dagar)

Information om vanliga felkoder och händelse-IDn för den Microsoft Defender Antivirus-tjänst som inte är relaterad till Uppdateringsefterlevnad finns i [Microsoft Defender Antivirus-händelser.](troubleshoot-microsoft-defender-antivirus.md) 

Det finns tre steg för att felsöka de här problemen:

1. Kontrollera att du har uppfyllt alla krav
2. Kontrollera anslutningen till den molnbaserade tjänsten Windows Defender
3. Skicka supportloggar

>[!IMPORTANT]
>Det tar normalt 3 dagar för enheter att börja visas i Uppdateringsefterlevnad.


## <a name="confirm-prerequisites"></a>Bekräfta förutsättningarna

För att enheter ska visas korrekt i Uppdateringsefterlevnad måste du uppfylla vissa krav för både tjänsten för uppdateringsefterlevnad och för Microsoft Defender Antivirus:

>[!div class="checklist"]
>- Slutpunkter använder Microsoft Defender Antivirus som den enda antivirusskyddsappen. [Om du använder någon annan antivirusapp inaktiveras microsoft Defender AV](microsoft-defender-antivirus-compatibility.md) och slutpunkten rapporteras inte under Uppdateringsefterlevnad.
> - [Moln levererat skydd är aktiverat.](enable-cloud-protection-microsoft-defender-antivirus.md)
> - Slutpunkter kan [ansluta till Microsoft Defender AV-molnet](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)
> - Om slutpunkten kör Windows 10 version 1607 eller tidigare måste [Windows 10-diagnostikdata](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)ställas in på nivån Utökad.
> - Det har gått tre dagar sedan alla krav har uppfyllts

"Du kan använda Microsoft Defender Antivirus med Uppdateringsefterlevnad. Du ser status för E3-, B-, F1-, VL- och Pro-licenser. Men för E5-licenser måste du använda Microsoft Defender för Endpoint-portalen ( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) . Mer information om licensalternativ finns i Produktlicensieringsalternativ för Windows 10"

Om samtliga krav ovan är uppfyllda kan du behöva gå vidare till nästa steg för att samla in diagnostikinformation och skicka den till oss.

> [!div class="nextstepaction"]
> [Samla in diagnostikdata för felsökning av uppdateringsefterlevnad](collect-diagnostic-data.md)  

## <a name="related-topics"></a>Relaterade ämnen

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Distribuera Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)