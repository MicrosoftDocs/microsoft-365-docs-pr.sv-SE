---
title: Felsöka grundläggande rörlighet och säkerhet
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
description: Prova följande för att spåra problem med Basic Mobility och Security
ms.openlocfilehash: b8df8c17f3a2fc5b7b6cce21769ca20742dbd397
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876858"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>Felsöka grundläggande rörlighet och säkerhet

Om du får problem när du försöker registrera en enhet i Basic Mobility and Security kan du prova stegen här för att spåra problemet. Om de allmänna anvisningarna inte löser problemet finns i senare avsnitt specifika anvisningar för din enhetstyp.

## <a name="steps-to-try-first"></a>Steg att prova först

Börja med att kontrollera följande:

- Kontrollera att enheten inte redan har registrerats hos en annan leverantör för hantering av mobila enheter, till exempel Intune.

- Kontrollera att enheten är inställd på rätt datum och tid.

- Växla till ett annat WIFI-nätverk eller mobilt nätverk på enheten.

- För Android- eller iOS-enheter avinstallerar du och Intune-företagsportal appen på enheten. 

## <a name="ios-phone-or-tablet"></a>Telefon eller surfplatta med iOS

- Kontrollera att du har konfigurerat ett APNs-certifikat. Mer information finns i Skapa [ett APNs-certifikat för iOS-enheter.](create-an-apns-certificate-for-ios-devices.md)

- I **Inställningar**   >  **Allmän**   >  **profil (eller Enhetshantering)** kontrollerar du att en hanteringsprofil inte redan är installerad. Om den är det tar du bort den.

- Om du får felmeddelandet "Enheten kunde inte registreras" loggar du in på Microsoft 365 och kontrollerar att en licens som innehåller Exchange Online har tilldelats till den användare som är inloggad på enheten.

- Om du får felmeddelandet "Det gick inte att installera profilen" kan du prova något av följande:

    - Kontrollera att Safari är standardwebbläsaren på enheten och att cookies inte är inaktiverade.

    - Starta om enheten och gå sedan till portal.manage.microsoft.com. Logga in med Microsoft 365 användar-ID och lösenord och försök installera profilen manuellt.

## <a name="windows-rt"></a>Windows RT

- Kontrollera att din domän är konfigurerad i Microsoft 365 att fungera med Basic Mobility and Security. Mer information finns i [Konfigurera Grundläggande rörlighet och säkerhet.](set-up.md)
    
- Kontrollera att användaren väljer Aktivera i **stället för**   Anslut. ****

## <a name="windows-10-pc"></a>Windows 10 DATOR

- Kontrollera att din domän är konfigurerad i Microsoft 365 att fungera med Basic Mobility and Security. Mer information finns i [Konfigurera Grundläggande rörlighet och säkerhet.](set-up.md)
    
- Om du inte Azure Active Directory Premium bör du kontrollera att användaren väljer Registrera sig endast för **enhetshantering** i stället för   att välja **Anslut**.

## <a name="android-phone-or-tablet"></a>Android-telefon eller -surfplatta

- Kontrollera att enheten kör Android 4.4 eller senare.

- Kontrollera att Chrome är uppdaterat och är inställt som standardwebbläsare.

- Om du får felmeddelandet "Vi kunde inte registrera den här enheten" loggar du in på Microsoft 365 och kontrollerar att en licens som innehåller Exchange Online har tilldelats till den användare som är inloggad på enheten.

- Kontrollera meddelandefältet på enheten för att se om några obligatoriska slutanvändaråtgärder väntar, och om de behövs slutför du åtgärderna.