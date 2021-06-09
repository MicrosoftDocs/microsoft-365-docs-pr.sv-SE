---
title: Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter
description: Använd verktyg för hantering av mobila enheter för att distribuera konfigurationspaketet på enheter så att de kan kommas in i tjänsten.
keywords: onboard devices using mdm, device management, onboard Microsoft Defender for Endpoint devices, mdm
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 45aa406212fe39f088f58bf311b1aed3fed16498
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843440"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)

Du kan använda MDM-lösningar (Mobile Device Management) för att konfigurera enheter. Defender för Endpoint stöder MDM genom att tillhandahålla OMA-URIs att skapa principer för att hantera enheter.

Mer information om hur du använder Defender för slutpunkt-CSP finns i [WindowsAdvancedThreatProtection CSP-](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) och [WindowsAdvancedThreatProtection DDF-fil.](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)

## <a name="before-you-begin"></a>Innan du börjar
Om du använder Microsoft Intune måste enheten MDM vara registrerad. Annars kommer inställningarna inte att tillämpas. 

Mer information om hur du aktiverar MDM med Microsoft Intune finns i [Enhetsregistrering (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).

## <a name="onboard-devices-using-microsoft-intune"></a>Onboard-enheter som använder Microsoft Intune

[![Bild av PDF-filen som visar onboarding-enheter för Defender för Endpoint med Microsoft Intune ](images/onboard-intune.png)](images/onboard-intune-big.png#lightbox)

Läs PDF- [eller](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) se de olika sökvägarna i distribuera Defender för Endpoint. 

Följ instruktionerna från [Intune](/intune/advanced-threat-protection).

Mer information om hur du använder Defender för slutpunkt-CSP finns i [WindowsAdvancedThreatProtection CSP-](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) och [WindowsAdvancedThreatProtection DDF-fil.](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)


> [!NOTE]
> - Principen **Hälsostatus för onboarded-enheter** använder skrivskyddade egenskaper och kan inte åtgärdas.
> - Konfiguration av frekvens för diagnostikdatarapportering är endast tillgänglig för enheter Windows 10, version 1703.


>[!TIP]
> När du har introducerat enheten kan du välja att köra ett identifieringstest för att verifiera att en enhet är korrekt onboarded till tjänsten. Mer information finns i Köra [ett identifieringstest på en nyligen onboarded Microsoft Defender för Endpoint-enhet.](run-detection-test.md)


Läs PDF- [eller](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) om du vill se de olika sökvägarna i distributionen av Microsoft Defender för Slutpunkt.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Offboard och övervaka enheter med hjälp av verktyg för hantering av mobila enheter
Av säkerhetsskäl upphör paketet som används till Offboard-enheter 30 dagar efter det datum då det laddades ned. Utgångna offboarding-paket som skickats till en enhet kommer att avvisas. När du laddar ned ett offboarding-paket meddelas du om paketens utgångsdatum och det inkluderas också i paketnamnet.

> [!NOTE]
> Principer för onboarding och offboarding får inte distribueras på samma enhet samtidigt, annars kan det orsaka oförutsägbara tavlor.

1. Hämta offboarding-paketet från [Microsoft Defender Säkerhetscenter:](https://securitycenter.windows.com/)

   1. I navigeringsfönstret väljer du **Inställningar**  >  **Offboarding**.

   1. Välj Windows 10 som operativsystem.

   1. I fältet **Distributionsmetod** väljer du **Hantering av mobila enheter /Microsoft Intune**.
    
   1. Klicka **på Ladda** ned paket och spara .zip filen.

2. Extrahera innehållet i filen .zip till en delad, skrivskyddad plats som kan nås av nätverksadministratörerna som ska distribuera paketet. Du bör ha en fil med *namnet WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding*.

3. Använd den Microsoft Intune konfigurationsprincipen för att distribuera följande OMA-URI-inställningar som stöds.

      OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding<br/>
      Datumtyp: Sträng<br/>
      Värde: [Kopiera och klistra in värdet från innehållet i WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding]

Mer information om Microsoft Intune finns i ändra [Windows 10 principinställningar i Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).


> [!NOTE]
> Principen **Hälsostatus för offboarded-enheter** använder skrivskyddade egenskaper och kan inte åtgärdas.

> [!IMPORTANT]
> Offboarding gör att enheten slutar skicka sensordata till portalen men data från enheten, inklusive referens till aviseringar som den haft kommer att behållas i upp till 6 månader.

## <a name="related-topics"></a>Relaterade ämnen
- [Introducera Windows 10 enheter med grupprincip](configure-endpoints-gp.md)
- [Introducera Windows 10 enheter med Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Registrera Windows 10-enheter med ett lokalt skript](configure-endpoints-script.md)
- [Registrera enheter för icke beständiga VDI-enheter (Virtual Desktop Infrastructure)](configure-endpoints-vdi.md)
- [Köra ett identifieringstest på en nyligen onboarded Microsoft Defender för Endpoint-enhet](run-detection-test.md)
- [Felsöka problem med Introduktion till Slutpunkt för Microsoft Defender](troubleshoot-onboarding.md)
