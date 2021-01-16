---
title: Felsöka grundläggande mobilitet och säkerhet
f1.keywords: NOCSH
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
ms.custom: AdminSurgePortfolio
description: Prova de här stegen för att spåra grundläggande problem med mobilitet och säkerhet
ms.openlocfilehash: b8df8c17f3a2fc5b7b6cce21769ca20742dbd397
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876858"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>Felsöka grundläggande mobilitet och säkerhet

Om du stöter på problem när du försöker registrera en enhet i grundläggande mobilitet och säkerhet kan du prova stegen här för att spåra problemet. Om de allmänna anvisningarna inte löser problemet kan du läsa en av de senare avsnitten med specifika anvisningar för din enhets typ.

## <a name="steps-to-try-first"></a>Steg för att pröva först

Starta genom att kontrol lera följande:

- Kontrol lera att enheten inte redan har registrerats hos en annan leverantör för hantering av mobila enheter, till exempel Intune.

- Kontrol lera att enheten är inställd på rätt datum och tid.

- Byt till ett annat WIFI-eller cellulärt nätverk på enheten.

- För Android-eller iOS-enheter avinstallerar och installerar du om Intune-företagsportalsappen på enheten. 

## <a name="ios-phone-or-tablet"></a>iOS-telefon eller-surfplatta

- Se till att du har konfigurerat ett APN-certifikat. Mer information finns i [skapa ett APN-certifikat för iOS-enheter](create-an-apns-certificate-for-ios-devices.md).

- I **Inställningar** för   >  **allmän**   >  **profil (eller enhets hantering)** kontrollerar du att det inte redan finns en hanterings profil. Om den är det tar du bort den.

- Om du får fel meddelandet "enheten kunde inte registreras", loggar du in på Microsoft 365 och kontrollerar att en licens som innehåller Exchange Online har tilldelats till den användare som är inloggad på enheten.

- Om du får fel meddelandet "Det gick inte att installera profilen" kan du försöka med något av följande:

    - Kontrol lera att Safari är standard webbläsaren på enheten och att cookies inte är inaktiverade.

    - Starta om enheten och navigera sedan till portal.manage.microsoft.com. Logga in med ditt användar-ID och lösen ord för Microsoft 365 och försök installera profilen manuellt.

## <a name="windows-rt"></a>Windows RT

- Kontrol lera att din domän är konfigurerad i Microsoft 365 för att fungera med grundläggande mobilitet och säkerhet. Mer information finns i [Konfigurera grundläggande mobilitet och säkerhet](set-up.md).
    
- Se till att användaren väljer **Aktivera**   i stället för att välja **Anslut**.

## <a name="windows-10-pc"></a>Windows 10-dator

- Kontrol lera att din domän är konfigurerad i Microsoft 365 för att fungera med grundläggande mobilitet och säkerhet. Mer information finns i [Konfigurera grundläggande mobilitet och säkerhet](set-up.md).
    
- Om du inte har Azure Active Directory Premium bör du kontrol lera att användaren väljer **Registrera bara i enhets hanteringen** i   stället för att välja **Anslut**.

## <a name="android-phone-or-tablet"></a>Android-telefon eller-surfplatta

- Kontrol lera att enheten kör Android 4,4 eller senare.

- Kontrol lera att Chrome är uppdaterat och har angetts som standard webbläsare.

- Om du får fel meddelandet "Det gick inte att registrera den här enheten", loggar du in på Microsoft 365 och kontrollerar att en licens som innehåller Exchange Online har tilldelats till den användare som är inloggad på enheten.

- Kontrol lera meddelande fältet på enheten för att se om eventuella åtgärder för slutanvändare är väntande och om de är det, utför du åtgärderna.