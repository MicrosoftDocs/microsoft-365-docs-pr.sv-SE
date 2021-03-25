---
title: Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter
description: Använd verktyg för hantering av mobila enheter för att distribuera konfigurationspaketet på enheter så att de kan kommas in i tjänsten.
keywords: onboard-enheter som använder mdm, enhetshantering, onboard Windows ATP-enheter, onboard Microsoft Defender för Endpoint-enheter, mdm
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
ms.openlocfilehash: 85dd6b50280f54b9d39bbb134e466171fc6268ff
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166155"
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

Mer information om hur du aktiverar MDM med Microsoft Intune finns i [Enhetsregistrering (Microsoft Intune).](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)

## <a name="onboard-devices-using-microsoft-intune"></a>Onboard-enheter med Microsoft Intune

[![Bild av PDF-filen som visar onboarding-enheter för Defender för Endpoint med Microsoft Intune ](images/onboard-intune.png)](images/onboard-intune-big.png#lightbox)

Ta en titta på [PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  [eller Visio-filen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) för att se de olika sökvägarna i distribuera Defender för Endpoint. 

Följ instruktionerna från [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).

Mer information om hur du använder Defender för slutpunkt-CSP finns i [WindowsAdvancedThreatProtection CSP-](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) och [WindowsAdvancedThreatProtection DDF-fil.](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)


> [!NOTE]
> - Principen **Hälsostatus för onboarded-enheter** använder skrivskyddade egenskaper och kan inte åtgärdas.
> - Konfiguration av frekvens för diagnostikdatarapportering är endast tillgänglig för enheter i Windows 10 version 1703.


>[!TIP]
> När du har introducerat enheten kan du välja att köra ett identifieringstest för att verifiera att en enhet är korrekt onboarded till tjänsten. Mer information finns i Köra [ett identifieringstest på en nyligen onboarded Microsoft Defender för Endpoint-enhet.](run-detection-test.md)


Ta en titta på [PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  [eller Visio-filen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) för att se de olika sökvägarna i distributionen av Microsoft Defender ATP. 

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Offboard och övervaka enheter med hjälp av verktyg för hantering av mobila enheter
Av säkerhetsskäl upphör paketet som används till Offboard-enheter 30 dagar efter det datum då det laddades ned. Utgångna offboarding-paket som skickats till en enhet kommer att avvisas. När du laddar ned ett offboarding-paket meddelas du om paketens utgångsdatum och det inkluderas också i paketnamnet.

> [!NOTE]
> Principer för onboarding och offboarding får inte distribueras på samma enhet samtidigt, annars kan det orsaka oförutsägbara tavlor.

1. Hämta offboarding-paketet från [Microsoft Defender Säkerhetscenter:](https://securitycenter.windows.com/)

   1. I navigeringsfönstret väljer du **Inställningar**  >  **offboarding**.

   1. Välj Windows 10 som operativsystem.

   1. I fältet **Distributionsmetod** väljer du **Hantering av mobila enheter/Microsoft Intune.**
    
   1. Klicka **på Ladda ned** paket och spara ZIP-filen.

2. Extrahera innehållet i ZIP-filen till en delad, skrivskyddad plats som kan nås av nätverksadministratörerna som ska distribuera paketet. Du bör ha en fil med *namnet WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding*.

3. Använd den anpassade konfigurationsprincipen för Microsoft Intune för att distribuera följande OMA-URI-inställningar som stöds.

      OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding<br/>
      Datumtyp: Sträng<br/>
      Värde: [Kopiera och klistra in värdet från innehållet i WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding]

Mer information om Inställningar för Microsoft Intune-princip finns i [Principinställningar för Windows 10 i Microsoft Intune.](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)


> [!NOTE]
> Principen **Hälsostatus för offboarded-enheter** använder skrivskyddade egenskaper och kan inte åtgärdas.

> [!IMPORTANT]
> Offboarding gör att enheten slutar skicka sensordata till portalen men data från enheten, inklusive referens till aviseringar som den haft kommer att behållas i upp till 6 månader.

## <a name="related-topics"></a>Relaterade ämnen
- [Introducera Windows 10-enheter med grupprincip](configure-endpoints-gp.md)
- [Introducera Windows 10-enheter med Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Registrera Windows 10-enheter med ett lokalt skript](configure-endpoints-script.md)
- [Registrera icke beständiga enheter för virtual desktop infrastructure (VDI)](configure-endpoints-vdi.md)
- [Köra ett identifieringstest på en nyligen onboarded Microsoft Defender för Endpoint-enhet](run-detection-test.md)
- [Felsöka problem med Introduktion till Slutpunkt för Microsoft Defender](troubleshoot-onboarding.md)
