---
title: Felsöka problem med Tjänsten Microsoft Defender för Slutpunkt
description: Hitta lösningar och lösningar på kända problem, till exempel serverfel när du försöker komma åt tjänsten.
keywords: felsöka Microsoft Defender för slutpunkt, felsöka Windows ATP, serverfel, åtkomst nekad, ogiltiga autentiseringsuppgifter, inga data, instrumentpanelsportal, tillåt, loggboken
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 112f682836da37ddfb51c103282518ff74563727
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186023"
---
# <a name="troubleshoot-service-issues"></a>Felsöka tjänstproblem

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


I det här avsnittet behandlas problem som kan uppstå när du använder tjänsten Microsoft Defender Advanced Threat.

## <a name="server-error---access-is-denied-due-to-invalid-credentials"></a>Serverfel – Åtkomst nekas på grund av ogiltiga autentiseringsuppgifter
Om det uppstår ett serverfel när du försöker komma åt tjänsten måste du ändra inställningarna för webbläsarens cookie.
Konfigurera webbläsaren så att den tillåter cookies.

## <a name="elements-or-data-missing-on-the-portal"></a>Element eller data saknas på portalen
Om vissa element eller data saknas i Microsoft Defender Säkerhetscenter kan det vara så att proxyinställningarna blockerar den.

Se till att `*.securitycenter.windows.com` finns med i listan över tillåtna proxyservrar.


> [!NOTE]
> Du måste använda HTTPS-protokollet när du lägger till följande slutpunkter.

## <a name="microsoft-defender-for-endpoint-service-shows-event-or-error-logs-in-the-event-viewer"></a>Microsoft Defender för slutpunktstjänsten visar händelse- eller felloggar i loggboken

Se [Granska händelser och fel med hjälp av Loggboken](event-error-codes.md) för en lista över händelse-IDt som rapporterats av Microsoft Defender för slutpunktstjänsten. Artikeln innehåller även felsökningssteg för händelsefel.

## <a name="microsoft-defender-for-endpoint-service-fails-to-start-after-a-reboot-and-shows-error-577"></a>Microsoft Defender för slutpunktstjänsten startar inte efter en omstart och visar felet 577

Om onboarding-enheter slutförs men Microsoft Defender för Slutpunkt inte startar efter en omstart och felmeddelande 577 visas kontrollerar du att Windows Defender inte har inaktiverats av en princip.

Mer information finns i Se [till att Microsoft Defender Antivirus inte är inaktiverat enligt policy.](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)

## <a name="known-issues-with-regional-formats"></a>Kända problem med nationella format

**Datum- och tidsformat**<br>
Det finns några kända problem med tids- och datumformat. 

Följande datumformat stöds:
- MM/dd/yyyy
- dd/MM/yyyy

Följande datum- och tidsformat stöds för närvarande inte:
- Datumformat yyyy/MM/dd
- Datumformat dd/MM/yy
- Datumformat med yy. Kommer bara att visa yyyy.
- Tidsformatet HH:mm:ss stöds inte (formatet 12 timmar/EM stöds inte). Endast 24-timmarsformatet stöds.

**Användning av kommatecken för att ange tusental**<br>
Stöd för användning av kommatecken som avgränsare i tal stöds inte. Regioner där ett tal avgränsas med ett kommatecken som anger tusen, ser bara användningen av en punkt som avgränsare. Till exempel visas 15,5K som 15,5K.

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshoot-belowfoldlink)

## <a name="microsoft-defender-for-endpoint-tenant-was-automatically-created-in-europe"></a>Microsoft Defender för slutpunktsklientorganisationen skapades automatiskt i Europa
När du använder Azure Säkerhetscenter för att övervaka servrar skapas automatiskt en Microsoft Defender för slutpunktsklientorganisation. Microsoft Defender för slutpunktsdata lagras i Europa som standard.





## <a name="related-topics"></a>Relaterade ämnen
- [Felsöka problem med Introduktion till Slutpunkt för Microsoft Defender](troubleshoot-onboarding.md)
- [Granska händelser och fel med hjälp av Loggboken](event-error-codes.md)
