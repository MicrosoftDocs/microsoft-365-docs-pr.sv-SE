---
title: Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Använd verktyg för hantering av mobila enheter för att distribuera konfigurationspaketet på enheter så att de kan kommas in i tjänsten.
ms.openlocfilehash: 1ad1115308257fa3ce63f10edebb9129638fd52f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162010"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter

**Gäller för:**

- [Microsoft 365 Dataförlustskydd i slutpunkt (DLP)](./endpoint-dlp-learn-about.md)

Du kan använda MDM-lösningar (Mobile Device Management) för att konfigurera enheter. Microsoft 365 Dataförlustskydd i slutpunkten stöder MDM genom att tillhandahålla OMA-URIs att skapa principer för hantering av enheter.


## <a name="before-you-begin"></a>Innan du börjar
Om du använder Microsoft Intune måste enheten MDM vara registrerad. Annars kommer inställningarna inte att tillämpas. 

Mer information om hur du aktiverar MDM med Microsoft Intune finns i [Enhetsregistrering (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).

## <a name="onboard-devices-using-microsoft-intune"></a>Onboard-enheter som använder Microsoft Intune

Följ instruktionerna från [Intune](/intune/advanced-threat-protection).

> [!NOTE]
> - Principen **Hälsostatus för onboarded-enheter** använder skrivskyddade egenskaper och kan inte åtgärdas.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Offboard och övervaka enheter med hjälp av verktyg för hantering av mobila enheter

Av säkerhetsskäl upphör paketet som används till Offboard-enheter 30 dagar efter det datum då det laddades ned. Utgångna offboarding-paket som skickats till en enhet kommer att avvisas. När du laddar ned ett offboarding-paket meddelas du om paketens utgångsdatum och det inkluderas också i paketnamnet.

> [!NOTE]
> Principer för onboarding och offboarding får inte distribueras på samma enhet samtidigt, annars kan det orsaka oförutsägbara tavlor.

1. Hämta offboarding-paketet från [Microsofts efterlevnadscenter.](https://compliance.microsoft.com/)

2. I navigeringsfönstret väljer du **Inställningar**  >  **Avboarding av**  >  **enheten.**

3. I fältet **Distributionsmetod** väljer du **Hantering av mobila enheter /Microsoft Intune**.
    
4. Klicka **på Ladda** ned paket och spara .zip filen.

5. Extrahera innehållet i filen .zip till en delad, skrivskyddad plats som kan nås av nätverksadministratörerna som ska distribuera paketet. Du bör ha en fil med *namnet DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.

6. Använd den Microsoft Intune konfigurationsprincipen för att distribuera följande OMA-URI-inställningar som stöds.

      OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding      
      Datumtyp: Sträng      
      Värde: [Kopiera och klistra in värdet från innehållet i DeviceCompliance_valid_until_YYYY-MM-DD.offboarding]

Mer information om Microsoft Intune finns i ändra [Windows 10 principinställningar i Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).

> [!NOTE]
> Principen **Hälsostatus för offboarded-enheter** använder skrivskyddade egenskaper och kan inte åtgärdas.

> [!IMPORTANT]
> Offboarding gör att enheten slutar skicka sensordata till portalen men data från enheten, inklusive referens till aviseringar som den haft kommer att behållas i upp till 6 månader.

## <a name="related-topics"></a>Relaterade ämnen
- [Introducera Windows 10 enheter med grupprincip](dlp-configure-endpoints-gp.md)
- [Introducera Windows 10 enheter med Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Registrera Windows 10-enheter med ett lokalt skript](dlp-configure-endpoints-script.md)
- [Registrera enheter för icke beständiga VDI-enheter (Virtual Desktop Infrastructure)](dlp-configure-endpoints-vdi.md)
- [Felsöka Microsoft Defender Avancerat skydd onboarding-problem](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)