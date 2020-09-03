---
title: Välj mellan grundläggande mobilitet och säkerhet och Intune
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Grundläggande mobilitet och säkerhet är en del av Microsoft 365-abonnemangen.
ms.openlocfilehash: d4595428dd2e2b14948b9f788720fcadcf9eb895
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337141"
---
# <a name="choose-between-basic-mobility-and-security-and-intune"></a>Välj mellan grundläggande mobilitet och säkerhet och Intune

Microsoft Intune är en fristående produkt som ingår i vissa Microsoft 365-abonnemang, och grundläggande & säkerhet är en del av Microsoft 365-abonnemangen. Båda är inkluderade i en mängd olika abonnemang, som beskrivs i följande tabell.

|**Planera**|**Grundläggande mobilitet och säkerhet**|**Microsoft Intune**|
|:-----|:-----|:-----|
|Microsoft 365-appar|Ja|Nej|
|Microsoft 365 Business Basic|Ja|Nej|
|Microsoft 365 Business Standard|Ja|Nej|
|Office 365 E1 |Ja|Nej|
|Office 365 E3 |Ja|Nej|
|Office 365 E5 |Ja|Nej|
|Microsoft 365 Business Premium |Ja|Ja|
|Microsoft 365 firstline 3 |Ja|Ja|
|Microsoft 365 Enterprise, E3 |Ja|Ja|
|Microsoft 365 Enterprise, E5 |Ja|Ja|
|Microsoft 365 Eductation a1 |Ja|Ja|
|Microsoft 365 Education a3 |Ja|Ja|
|Microsoft 365 Education A5 |Ja|Ja|
|Microsoft Intune |Nej|Ja|
|Företags mobilitet & säkerhet E3 |Nej|Ja|
|Företags mobilitet & säkerhet, E5 |Nej|Ja|

>[!NOTE]
>Du kan inte börja använda grundläggande mobilitet och säkerhet om du redan använder Microsoft Intune.

## <a name="differences-in-capabilities"></a>Skillnader i funktioner

Microsoft Intune med inbyggd grundläggande rörlighet och säkerhet ger båda dig möjligheten att hantera mobila enheter i organisationen, men det finns viktiga skillnader i kapaciteten, som beskrivs i följande tabell.

>[!NOTE]
>Du kan hantera användare och deras mobila enheter med både Intune och grundläggande mobilitet och säkerhet i samma Microsoft 365 Business Standard-organisation genom att konfigurera grundläggande mobilitet och säkerhet först och sedan lägga till Microsoft Intune. Det gör att du kan välja om du vill hantera en användares enheter med grundläggande mobilitet och säkerhet eller mer funktion-rik Intune-lösning. I läget bestämmer licens tilldelningen vilken tjänst enheten är registrerad med. Tilldela en Intune-licens för att aktivera endast Intune-funktioner.

|**Funktions område**|**Funktions markeringar**|**Grundläggande mobilitet och säkerhet**|**Microsoft Intune**|
|:-----|:-----|:-----|:-----|
|Enhets typer|Olika OS-plattformar och stora hanterings lägen. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>Mac OS<br/>iPad OS|
|Kompatibilitet med enheter|Ange och hantera säkerhets principer, som PIN-lås och jailbreak identifiering på enhets nivå. |Begränsningar för Android 9 och senare enheter. Mer information finns i [grundläggande mobilitet och säkerhet](capabilities-of-basic-mobility-and-secruity.md).|Ja|
|Villkorlig åtkomst baserat på enhetens efterlevnad |Förhindra att icke-kompatibla enheter får åtkomst till företagets e-post och data från molnet. |-Stöds inte i Windows 10.<br/>-Begränsad för att kontrol lera åtkomsten till Exchange Online, SharePoint Online och Outlook Services. |Nej|
|Enhetskonfiguration  |Konfigurera enhets inställningar (till exempel inaktivera kameran). |Begränsad uppsättning inställningar.Mer information finns i [grundläggande mobilitet och säkerhet](capabilities-of-basic-mobility-and-secruity.md). |Ja|
|Fjärråtgärder  |Skicka kommandon till enheter över Internet. Du kan till exempel ta bort Office-data från en anställds enhet samtidigt som du lämnar person uppgifter på plats (Pension). |Rang<br/>Rensa<br/>Ta bort|-Autopilot-återställning (endast Windows)<br/>- [Nyckel rotation](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   i BitLocker (Endast Windows)<br/>- [Ta bort](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)<br/>- [Inaktivera aktiverings](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)   plats (endast iOS)<br/>- [Ny start](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)   (Endast Windows)<br/>- [Fullständig genomsökning](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Endast Windows 10)<br/>- [Hitta enhet](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)   (endast iOS)<br/>- [Förlorat läge](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)   (endast iOS)<br/>- [Snabb sökning](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(endast Windows 10)<br/>- [Fjärrkontroll för Android](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)<br/>- [Fjärrlåsning](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)<br/>- [Byt namn på enheten](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)<br/>- [Återställ lösen ord](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset)<br/>- [Starta om](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)   (Endast Windows)<br/>- [Rang](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#retire)<br/>-Uppdatera Windows Defender säkerhets information (endast Windows)<br/>-Windows 10-PIN-återställning (endast Windows)<br/>- [Rensa](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#wipe)<br/>- [Skicka anpassade meddelanden](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, iPad OS)<br/>- [Synkronisera enhet](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)|
|E-postprofiler  |Tillhandahålla en intern e-postprofil på enheten. |Ja|Ja|
|WIFI-profiler |Tillhandahålla en inbyggd WIFI-profil på enheten. |Nej|Ja|
|VPN-profiler |Tillhandahålla en intern VPN-profil på enheten. |Nej|Ja|
|Hantering av MDM-program  |Distribuera dina interna branschspecifika program och från appar till användare. |Nej|Ja|
|Skydd för mobil program  |Gör det möjligt för dina användare att säkert komma åt företags information med hjälp av Office Mobile-och line-of Business-apparna, samtidigt som du säkerställer säkerheten för data genom att hjälpa till att begränsa åtgärderna som att kopiera, klippa ut, klistra in och Spara som, för de program som hanteras av företags data. Fungerar även om enheterna inte är registrerade i MDM. Se skydda AppData med MAM-principer. |Nej|Ja|
|Hanterad webbläsare  |Aktivera säkrare surfning med programmet Edge. |Nej|Ja|
|Nollställnings registrerings program |Registrera ett stort antal företagsägda enheter och förenkla installationen. |Nej|Ja|
