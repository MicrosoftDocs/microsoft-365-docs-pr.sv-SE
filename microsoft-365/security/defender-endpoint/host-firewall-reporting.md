---
title: Rapportering av värdbrandvägg i Microsoft Defender för Endpoint
description: Vara värd för och visa brandväggsrapportering Microsoft 365 säkerhetscenter.
keywords: windows defender, brandvägg
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 0289d6f920fd6ff35fd446f9c2b8c5516883a4d2
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809342"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a>Rapportering av värdbrandvägg i Microsoft Defender för Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Om du är administratör kan du nu hantera brandväggsrapportering till [Microsoft 365 säkerhetscenter.](https://security.microsoft.com) Med den här funktionen kan du visa Windows 10 och Windows för Server 2019-brandväggen från en central plats. 

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar? 

- Du måste köra Windows 10 eller Windows Server 2019.
- Information om hur du onboardar enheter till Microsoft Defender för slutpunktstjänsten finns [här](onboard-configure.md). 
- Om Microsoft 365 säkerhetscenter ska börja ta emot data måste du aktivera **granskningshändelser för** Windows Defender-brandväggen med avancerad säkerhet: 
    - [Granskningsfiltrering av plattform för släpp](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
    - [Anslutning till granskningsfiltreringsplattform](/windows/security/threat-protection/auditing/audit-filtering-platform-connection) 
- Aktivera dessa händelser med hjälp av Grupprincipobjektredigeraren, Lokal säkerhetsprincip eller auditpol.exe säkerhetskommandon. Mer information finns i [här](/windows/win32/fwp/auditing-and-logging). 
    - De två PowerShell-kommandona är:
        - **auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable** 
        - **auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable** 

## <a name="the-process"></a>Processen
> [!NOTE]
> Se till att följa anvisningarna i avsnittet ovan och konfigurera dina enheter på rätt sätt inför förhandsdeltagandet.

- När du har Microsoft 365 säkerhetscentret övervaka data.
    - Fjärr-IP, fjärrport, lokal port, lokal IP, datornamn, process för inkommande och utgående anslutningar.
- Administratörer kan nu se Windows aktiviteten för värdbrandväggen [här](https://security.microsoft.com/firewall).
    - Ytterligare rapportering kan underlättas genom att hämta skriptet [Anpassad](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) rapportering för att övervaka de Windows Defender-brandväggen som använder Power BI. 
    - Det kan ta upp till 12 timmar innan data visas.

## <a name="supported-scenarios"></a>Scenarier som stöds
Följande scenarier stöds under förhandsversionen av Ring0. 

### <a name="firewall-reporting-in-security-center"></a>Brandväggsrapportering i säkerhetscenter

Här är några exempel på brandväggsrapportsidorna. Här hittar du en sammanfattning av inkommande, utgående och programaktivitet. Du kan komma åt den här sidan direkt genom att gå till https://security.microsoft.com/firewall . 

> [!div class="mx-imgBorder"]
> ![Rapportsida för värdbrandvägg](\images\host-firewall-reporting-page.png)

Du kommer åt de här rapporterna genom att gå till **Reports** Security Report Devices (avsnitt) längst ned på kortet  >    >   **Firewall Blocked Inbound Connections.**

### <a name="from-computers-with-a-blocked-connection-to-device"></a>Från "Datorer med en blockerad anslutning" till en enhet

Kort stöder interaktiva objekt. Du kan granska aktiviteten på en enhet genom att klicka på enhetens namn, som startas på en ny flik, och ta dig direkt https://securitycenter.microsoft.com till fliken Tidslinje **på** enheten. 

> [!div class="mx-imgBorder"]
> ![Datorer med blockerad anslutning](\images\firewall-reporting-blocked-connection.png)

Nu kan du välja fliken **Tidslinje,** som ger dig en lista över händelser som är kopplade till den enheten. 

När du har **klickat på** knappen Filter i det övre högra hörnet i visningsfönstret väljer du den typ av händelse som du vill använda. I det här fallet väljer **du Brandväggshändelser** så filtreras fönstret till brandväggshändelser. 

> [!div class="mx-imgBorder"]
> ![Knappen Filter](\images\firewall-reporting-filters-button.png)

### <a name="drill-into-advanced-hunting-preview-refresh"></a>Öka detalj detalj för avancerad sökning (uppdatera förhandsversion)

Med brandväggsrapporter går det att göra en sökning från kortet direkt **till Avancerad sökning** genom att klicka på knappen Öppna **avancerad** sökning. Frågan fylls i på förhand. 

> [!div class="mx-imgBorder"]
> ![Knappen Öppna avancerad sökning](\images\firewall-reporting-advanced-hunting.png)

Frågan kan nu utföras och alla relaterade brandväggshändelser från de senaste 30 dagarna kan undersökas. 

För ytterligare rapportering eller anpassade ändringar kan frågan exporteras till ett Power BI för vidare analys. Anpassad rapportering kan underlättas genom att hämta skriptet [Anpassad](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) rapportering för att övervaka de Windows Defender-brandväggen som använder Power BI. 

 