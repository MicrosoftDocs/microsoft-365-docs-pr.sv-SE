---
title: Registrera Microsoft Defender ATP för macOS-enheter i Jamf Pro
description: Registrera Microsoft Defender ATP för macOS-enheter i Jamf Pro
keywords: microsoft, defender, atp, mac, installation, distribuera, avinstallation, intune, jamfpro, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ea71875dedf7e8706c9022420abd63bc5eb20c69
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689731"
---
# <a name="enroll-microsoft-defender-for-endpoint-on-macos-devices-into-jamf-pro"></a>Registrera Microsoft Defender för Endpoint på macOS-enheter till Jamf Pro 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a>Registrera macOS-enheter

Det finns flera sätt att registrera sig till JamF.

I den här artikeln får du vägledning om två metoder:

- [Metod 1: Registreringsinbjudningar](#enrollment-method-1-enrollment-invitations)
- [Metod 2: Prestage-registrering](#enrollment-method-2-prestage-enrollments)

En fullständig lista finns i [Om datorregistrering.](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html)


## <a name="enrollment-method-1-enrollment-invitations"></a>Registreringsmetod 1: Registreringsinbjudningar

1. Gå till Registreringsinbjudningar på **instrumentpanelen** Jamf Pro.

    ![Bild av konfigurationsinställningar1](images/a347307458d6a9bbfa88df7dbe15398f.png)

2. Välj **+ Ny.**

    ![En när bild på en logotypbeskrivning skapas automatiskt](images/b6c7ad56d50f497c38fc14c1e315456c.png)

3. I **Ange mottagare för >** under  E-postadresser anger du mottagarnas e-postadresser.

    ![Bild på konfigurationsinställningar2](images/718b9d609f9f77c8b13ba88c4c0abe5d.png)

    ![Bild på konfigurationsinställningar3](images/ae3597247b6bc7c5347cf56ab1e820c0.png)

    Till exempel: janedoe@contoso.com

    ![Bild på konfigurationsinställningar4](images/4922c0fcdde4c7f73242b13bf5e35c19.png)

4. Konfigurera meddelandet för inbjudan.

    ![Bild på konfigurationsinställningar5](images/ce580aec080512d44a37ff8e82e5c2ac.png)

    ![Bild på konfigurationsinställningar6](images/5856b765a6ce677caacb130ca36b1a62.png)

    ![Bild på konfigurationsinställningar7](images/3ced5383a6be788486d89d407d042f28.png)

    ![Bild på konfigurationsinställningar8](images/54be9c6ed5b24cebe628dc3cd9ca4089.png)

## <a name="enrollment-method-2-prestage-enrollments"></a>Registreringsmetod 2: Prestage-registrering

1. Gå till **Prestage-registrering** i instrumentpanelen Jamf Pro.

    ![Bild på konfigurationsinställningar9](images/6fd0cb2bbb0e60a623829c91fd0826ab.png)

2. Följ anvisningarna i [Datorns prestage-registrering.](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html)

## <a name="enroll-macos-device"></a>Registrera macOS-enhet

1. Välj **Fortsätt** och installera certifikatutfärdaren i fönstret **Systeminställningar.**

    ![Bild på Jamf Pro-registrering1](images/jamfpro-ca-certificate.png)

2. När CA-certifikat har installerats går du tillbaka till webbläsarfönstret **och väljer Fortsätt** och installera MDM-profilen. 

    ![Bild på Jamf Pro-registrering2](images/jamfpro-install-mdm-profile.png)

3. Välj **Tillåt** för hämtningar från JAMF.

    ![Bild på Jamf Pro-registrering3](images/jamfpro-download.png)

4. Välj **Fortsätt för** att fortsätta med installationen av MDM-profilen. 

    ![Bild på Jamf Pro-registrering4](images/jamfpro-install-mdm.png)

5. Välj **Fortsätt** för att installera MDM-profilen.

    ![Bild på Jamf Pro-registrering5](images/jamfpro-mdm-unverified.png)

6. Välj **Fortsätt**  för att slutföra konfigurationen. 

    ![Bild på Jamf Pro-registrering6](images/jamfpro-mdm-profile.png)
