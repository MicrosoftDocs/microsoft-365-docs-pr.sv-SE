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
ms.openlocfilehash: cfd1a68c313d1a1335490e2b8d6938de192fe3f3
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877098"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>Välj mellan grundläggande mobilitet och säkerhet eller Intune

[Microsoft Intune](https://docs.microsoft.com/mem/intune/) är en fristående produkt som ingår i vissa Microsoft 365-abonnemang, och grundläggande mobilitet och säkerhet är en del av Microsoft 365-abonnemangen. 

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Till gång till grundläggande mobilitet och säkerhet och Intune
 
Både grundläggande mobilitet och säkerhet och Intune ingår i en mängd olika abonnemang, som beskrivs i följande tabell.

| Planera | Grundläggande Mobility and Security | Microsoft Intune |
|:-----|:-----|:-----|
|Microsoft 365-applikationer|Ja|Nej|
|Microsoft 365 Business Basic|Ja|Nej|
|Microsoft 365 Business Standard|Ja|Nej|
|Office 365 E1 |Ja|Nej|
|Office 365 E3 |Ja|Nej|
|Office 365 E5 |Ja|Nej|
|Microsoft 365 Business Premium |Ja|Ja|
|Microsoft 365 firstline 3 |Ja|Ja|
|Microsoft 365 Enterprise, E3 |Ja|Ja|
|Microsoft 365 Enterprise, E5 |Ja|Ja|
|Microsoft 365 Education a1 |Ja|Ja|
|Microsoft 365 Education a3 |Ja|Ja|
|Microsoft 365 Education A5 |Ja|Ja|
|Microsoft Intune |Nej|Ja|
|Företags mobilitet & säkerhet E3 |Nej|Ja|
|Företags mobilitet & säkerhet, E5 |Nej|Ja|

>[!NOTE]
>Du kan inte börja använda grundläggande mobilitet och säkerhet om du redan använder Microsoft Intune.

 Mer information finns i [Beskrivning av tjänst beskrivningar för Microsoft 365 och Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description). 

## <a name="differences-in-capabilities"></a>Skillnader i funktioner

Microsoft Intune med inbyggd grundläggande rörlighet och säkerhet ger båda dig möjligheten att hantera mobila enheter i organisationen, men det finns viktiga skillnader i kapaciteten, som beskrivs i följande tabell.

>[!NOTE]
>Du kan hantera användare och deras mobila enheter med både Intune och grundläggande mobilitet och säkerhet i samma Microsoft 365 Business Standard-organisation *genom att konfigurera grundläggande mobilitet och säkerhet först och sedan lägga till Microsoft Intune*. Med det här alternativet kan du välja grundläggande mobilitet och mer funktionalitet-rika Intune-lösning. Tilldela en Intune-licens för att aktivera Intune-funktioner.

| Funktions område | Funktions markeringar | Grundläggande Mobility and Security | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|Enhets typer|Hantera olika OS-plattformar och stora hanterings lägen. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>Mac OS, iPad OS|
|Kompatibilitet med enheter|Ange och hantera säkerhets principer, som PIN-lås och jailbreak identifiering på enhets nivå. |Begränsningar för Android 9 och senare enheter. Visa [information](capabilities.md). |Ja|
|Villkorlig åtkomst baserat på enhetens efterlevnad |Förhindra att icke-kompatibla enheter får åtkomst till företagets e-post och data från molnet. |Stöds inte i Windows 10.<br/>Begränsat för att kontrol lera åtkomsten till Exchange Online, SharePoint Online och Outlook. |Ja |
|Enhetskonfiguration  |Konfigurera enhets inställningar (till exempel att inaktivera kameran)|Begränsad uppsättning inställningar.|Ja|
|Kompatibilitet med enheter  |Ange och hantera säkerhets principer, som PIN-lås och jailbreak identifiering på enhets nivå. |Begränsningar för Android 9 och senare enheter. Visa [information](capabilities.md). |Ja|
|E-postprofiler  |Tillhandahålla en intern e-postprofil på enheten. |Ja|Ja|
|WiFi-profiler |Tillhandahålla en inbyggd WiFi-profil på enheten. |Nej|Ja|
|VPN-profiler |Tillhandahålla en intern VPN-profil på enheten. |Nej|Ja|
|Grundläggande hantering av mobilitet och säkerhets program  |Distribuera dina interna branschspecifika program och från appar till användare. |Nej|Ja|
|Skydd för mobil program  |Gör det möjligt för dina användare att säkert komma åt företags information med hjälp av Office Mobile-och line-of Business-apparna, samtidigt som du säkerställer säkerheten för data genom att hjälpa till att begränsa åtgärderna som att kopiera, klippa ut, klistra in och Spara som, för de program som hanteras av företags data. Fungerar även om enheterna inte är registrerade för grundläggande mobilitet och säkerhet. Se skydda AppData med MAM-principer. |Nej|Ja|
|Hanterad webbläsare  |Aktivera säkrare surfning med programmet Edge. |Nej|Ja|
|Autopilotering med Zero Touch-program) |Registrera ett stort antal företagsägda enheter och förenkla användar inställningar. |Nej|Ja|
|||

Utöver de funktioner som visas i den föregående tabellen inkluderar grundläggande mobilitet och säkerhet och Intune båda en uppsättning fjärråtgärder som skickar kommandon till enheter över Internet. Du kan till exempel ta bort Office-data från en anställds enhet samtidigt som du lämnar person uppgifter på plats (från en person), tar bort Office-appar från en anställds enhet (rensning) eller återställer en enhet till fabriks inställningarna (fullständig rensning). 

Grundläggande funktioner för rörlighet och säkerhet inkluderar borttagning, rensning och fullständig rensning. Mer information om grundläggande funktioner för rörlighet och säkerhet finns i [grundläggande mobilitet och säkerhet](capabilities.md).

Med Intune kan du göra följande:

-   Autopilot-återställning (endast Windows)
-  [Nyckel rotation](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   i BitLocker (Endast Windows)
-  [Använda rensning, ta bort eller avregistrera enheten manuellt](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [Inaktivera aktiverings](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)   plats (endast iOS)
-  [Ny start](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)   (Endast Windows)
- [Fullständig genomsökning](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Endast Windows 10)
- [Hitta enhet](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)   (endast iOS)
- [Förlorat läge](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)   (endast iOS)- [snabb sökning](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(endast Windows 10)
- [Fjärrkontroll för Android](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)
- [Fjärrlåsning](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)
- [Byt namn på enheten](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)
-  [Återställ omstart för lösen ord](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset) [](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)   (endast Windows)
-  Uppdatera Windows Defender säkerhets information (endast Windows)
-  PIN-återställning för Windows 10 (endast Windows)
-  [Skicka anpassade meddelanden](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, iPad OS)
-  [Synkronisera enhet](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)

Mer information om Intune-åtgärder finns i [dokumentationen för Microsoft Intune](https://docs.microsoft.com/mem/intune/).
