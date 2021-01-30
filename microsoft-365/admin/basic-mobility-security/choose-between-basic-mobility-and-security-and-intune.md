---
title: Välja mellan Basic Mobility och Security och Intune
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
description: Basic Mobility and Security är en del av Microsoft 365-abonnemangen.
ms.openlocfilehash: ec3ffa8879bf14ab3116bbbbf5cf2a1a3fd7c6e6
ms.sourcegitcommit: ea8a096df5acedecdce1780969f2b189c3fadf73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2021
ms.locfileid: "50053807"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>Välja mellan Basic Mobility och Security eller Intune

[Microsoft Intune är](https://docs.microsoft.com/mem/intune/) en fristående produkt som ingår i vissa Microsoft 365-abonnemang, medan Basic Mobility och Security ingår i Microsoft 365-abonnemangen.

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Tillgänglighet för basic rörlighet och säkerhet och Intune

Både Basic Mobility och Security och Intune ingår i en mängd olika planer som beskrivs i följande tabell.

| Planera | Grundläggande Mobility and Security | Microsoft Intune |
|:-----|:-----|:-----|
|Microsoft 365-applikationer|Ja|Nej|
|Microsoft 365 Business Basic|Ja|Nej|
|Microsoft 365 Business Standard|Ja|Nej|
|Office 365 E1 |Ja|Nej|
|Office 365 E3 |Ja|Nej|
|Office 365 E5 |Ja|Nej|
|Microsoft 365 Business Premium |Ja|Ja|
|Microsoft 365 Firstline 3 |Ja|Ja|
|Microsoft 365 Enterprise, E3 |Ja|Ja|
|Microsoft 365 Enterprise E5 |Ja|Ja|
|Microsoft 365 Education A1 |Ja|Ja|
|Microsoft 365 Education A3 |Ja|Ja|
|Microsoft 365 Education A5 |Ja|Ja|
|Microsoft Intune |Nej|Ja|
|Enterprise Mobility & Security E3 |Nej|Ja|
|Enterprise Mobility & Security E5 |Nej|Ja|

>[!NOTE]
>Du kan inte börja använda Basic Mobility and Security om du redan använder Microsoft Intune.

 Mer information finns i [tjänstbeskrivningarna för Microsoft 365- och Office 365-plattformen.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) 

## <a name="differences-in-capabilities"></a>Skillnader i funktioner

Både Microsoft Intune och den inbyggda funktionen Basic Mobility och Security ger dig möjlighet att hantera mobila enheter i organisationen, men det finns viktiga skillnader i funktion som beskrivs i följande tabell.

>[!NOTE]
>Du kan hantera användare och deras mobila enheter med hjälp av både Intune och Basic Mobility and Security i samma Microsoft 365 Business Standard-organisation genom att först konfigurera Basic Mobility and Security och sedan lägga till *Microsoft Intune.* På så sätt kan du välja Basic Mobility and Security eller den mer funktionsrika Intune-lösningen. Tilldela en Intune-licens för att aktivera Intune-funktionerna.

| Funktionsområde | Viktiga funktioner | Grundläggande Mobility and Security | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|Enhetstyper|Hantera olika OS-plattformar och större varianter av hanteringsläge. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS, iPad OS|
|Enhetsefterlevnad|Ange och hantera säkerhetsprinciper, till exempel PIN-kodslås och identifiering av lås på enhetsnivå. |Begränsningar på Android 9 och senare enheter. Visa [information.](capabilities.md) |Ja|
|Villkorsstyrd åtkomst baserat på enhetsefterlevnad |Förhindra att enheter som inte är kompatibla kommer åt företagets e-post och data från molnet. |Stöds inte i Windows 10.<br/>Begränsad till att kontrollera åtkomsten till Exchange Online, SharePoint Online och Outlook. |Ja |
|Enhetskonfiguration  |Konfigurera enhetsinställningar (till exempel inaktivera kameran)|Begränsad uppsättning inställningar.|Ja|
|Enhetsefterlevnad  |Ange och hantera säkerhetsprinciper, till exempel PIN-kodslås och identifiering av lås på enhetsnivå. |Begränsningar på Android 9 och senare enheter. Visa [information.](capabilities.md) |Ja|
|E-postprofiler  |Etablera en inbyggd e-postprofil på enheten. |Ja|Ja|
|WiFi-profiler |Etablera en inbyggd WiFi-profil på enheten. |Nej|Ja|
|VPN-profiler |Etablera en inbyggd VPN-profil på enheten. |Nej|Ja|
|Enkel hantering av mobilitets- och säkerhetsprogram  |Distribuera dina interna verksamhetsbaserade appar och från programbutiker till användare. |Nej|Ja|
|Skydd för mobilprogram  |Gör det möjligt för användarna att få säker åtkomst till företagsinformation med hjälp av Office-mobilappar och verksamhetsappar som de känner till, samtidigt som du säkerställer datasäkerhet genom att begränsa åtgärder som att kopiera, klippa ut, klistra in och spara som, till endast de program som hanteras godkända för företagsdata. Fungerar även om enheterna inte är registrerade till Basic Mobility and Security. Se Skydda appdata med hjälp av MAM-principer. |Nej|Ja|
|Hanterad webbläsare  |Aktivera säkrare surfning med Edge-appen. |Nej|Ja|
|Program för noll pekregistrering – Autopilot) |Registrera ett stort antal företagsägda enheter, samtidigt som du förenklar användarkonfiguration. |Nej|Ja|
|||

Förutom de funktioner som anges i föregående tabell innehåller Både Basic Mobility och Security och Intune en uppsättning fjärråtgärder som skickar kommandon till enheter via Internet. Du kan till exempel ta bort Office-data från en anställds enhet medan personliga data är kvar (dra tillbaka), ta bort Office-appar från en anställds enhet (rensa) eller återställa en enhet till fabriksinställningarna (fullständig rensning). 

Grundläggande åtgärder för rörlighet och säkerhet omfattar retire, wipe and full wipe. Mer information om grundläggande mobilitets- och säkerhetsåtgärder finns i funktionerna [Basic Mobility och Security.](capabilities.md)

Med Intune har du följande uppsättning åtgärder:

-   Autopilot-återställning (endast Windows)
-  [Bitlocker-nyckelrotation](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (Endast Windows)
-  [Använda rensning, dra tillbaka eller manuellt avregistrera enheten](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [Inaktivera aktiveringslokalen](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)   (endast iOS)
-  [Börja om från början](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)   (Endast Windows)
- [Fullständig genomsökning](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Endast Windows 10)
- [Hitta enhet](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)   (endast iOS)
- [Borttappt läge](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)   (endast iOS)– [Snabbsökning](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(endast Windows 10)
- [Fjärrstyrning för Android](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)
- [Fjärrlås](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)
- [Byt namn på enhet](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)
-  [Återställa lösenordsåterställning](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset) [](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)   (endast Windows)
-  Uppdatera Windows Defender Säkerhetsinformation (endast Windows)
-  Återställning av PIN-kod i Windows 10 (endast Windows)
-  [Skicka anpassade meddelanden](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, iPad OS)
-  [Synkronisera enhet](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)

Mer information om Intune-åtgärder finns i [Microsoft Intune-dokumentationen.](https://docs.microsoft.com/mem/intune/)
