---
title: Appbaserad distribution av Microsoft Defender ATP för iOS
ms.reviewer: ''
description: Här beskrivs hur du distribuerar Microsoft Defender ATP för iOS med hjälp av en app
keywords: microsoft, defender, atp, ios, app, installation, distribuera, avinstallation, intune
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c7f60df38ce9f34fecae975be40206d7270b0863
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070570"
---
# <a name="deploy-microsoft-defender-for-endpoint-for-ios"></a>Distribuera Microsoft Defender för slutpunkt för iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

I det här avsnittet beskrivs hur du distribuerar Defender för Slutpunkt för iOS på registrerade enheter i Intune-företagsportal. Mer information om registrering av Intune-enheter finns i [Registrera iOS-/iPadOS-enheter i Intune.](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll)

## <a name="before-you-begin"></a>Innan du börjar

- Kontrollera att du har åtkomst till [administrationscentret för Microsoft Endpoint Manager.](https://go.microsoft.com/fwlink/?linkid=2109431)

- Se till att iOS-registreringen utförs för dina användare. Användarna måste ha en Defender för slutpunktslicens tilldelad för att kunna använda Defender för slutpunkt för iOS. Anvisningar om [hur du tilldelar licenser](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) finns i Tilldela licenser till användare.

> [!NOTE]
> Microsoft Defender ATP (Microsoft Defender för slutpunkt) för iOS är nu tillgängligt [i Apple App Store.](https://aka.ms/mdatpiosappstore)

## <a name="deployment-steps"></a>Distributionssteg

Distribuera Defender för Slutpunkt för iOS via Intune-företagsportalen.

### <a name="add-ios-store-app"></a>Lägg till en iOS Store-app

1. I [administrationscentret för Microsoft Endpoint manager](https://go.microsoft.com/fwlink/?linkid=2109431)går du till **Appar**  ->  **iOS/iPadOS Lägg**  ->  **till**  ->  **iOS Store-app och** klickar på **Välj**.

    > [!div class="mx-imgBorder"]
    > ![Bild av Administrationscenter för Microsoft Endpoint Manager1](images/ios-deploy-1.png)

1. På sidan Lägg till app klickar du på **Sök i App Store** och skriver Microsoft Defender **ATP** i sökfältet. I avsnittet med sökresultat klickar du på *Microsoft Defender ATP och* klickar på **Välj**.

1. Välj **iOS 11.0** som Minimum-operativsystem. Granska resten av informationen om programmet och klicka på **Nästa**.

1. Gå till *avsnittet Obligatoriska* i avsnittet Uppgifter **och** välj Lägg **till grupp**. Du kan sedan välja den användargrupp(er) som du vill rikta Defender för Endpoint för iOS-appen till. Klicka **på Markera** och sedan på **Nästa.**

    > [!NOTE]
    > Den valda användargruppen ska bestå av intune-registrerade användare.

    > [!div class="mx-imgBorder"]
    > ![Bild av Administrationscenter för Microsoft Endpoint Manager2](images/ios-deploy-2.png)

1. I avsnittet *Granska + Skapa* kontrollerar du att all information som angetts är korrekt och väljer sedan **Skapa**. Inom en liten stund bör appen Defender för Slutpunkt skapas korrekt och ett meddelande bör visas i det övre högra hörnet på sidan.

1. På sidan med appinformation som  visas i avsnittet Övervaka väljer du Enhetsinstallationsstatus **för** att verifiera att enhetsinstallationen har slutförts.

    > [!div class="mx-imgBorder"]
    > ![Bild av Administrationscenter för Microsoft Endpoint Manager3](images/ios-deploy-3.png)

## <a name="complete-onboarding-and-check-status"></a>Fullständig registrering och kontrollstatus

1. När Defender för Slutpunkt för iOS har installerats på enheten visas appikonen.

    ![En skärmbild av en beskrivning av en smartphone som genererats automatiskt](images/41627a709700c324849bf7e13510c516.png)

2. Tryck på appikonen Defender för slutpunkt och följ instruktionerna på skärmen för att slutföra introduktionsstegen. Informationen innefattar godkännande av iOS-behörigheter som krävs av Defender för Endpoint för iOS.

3. Om onboarding lyckas visas enheten i listan Enheter i Microsoft Defender Säkerhetscenter.

    > [!div class="mx-imgBorder"]
    > ![En skärmbild av en beskrivning av en mobiltelefon automatiskt genererad](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a>Konfigurera Microsoft Defender för slutpunkt för övervakat läge

Appen Microsoft Defender för Endpoint för iOS har särskild kapacitet för övervakade iOS-/iPadOS-enheter, givet de utökade hanteringsfunktionerna som tillhandahålls av plattformen på dessa typer av enheter. Om du vill dra nytta av de här funktionerna behöver appen Defender för slutpunkt veta om en enhet är i övervakat läge.

### <a name="configure-supervised-mode-via-intune"></a>Konfigurera övervakat läge via Intune

Med Intune kan du konfigurera appen Defender för iOS via en princip för appkonfiguration.

   > [!NOTE]
   > Den här appkonfigurationsprincipen för övervakade enheter gäller endast hanterade enheter och bör riktas för alla hanterade iOS-enheter.

1. Logga in på [administrationscentret för Microsoft Endpoint Manager och](https://go.microsoft.com/fwlink/?linkid=2109431) gå till Appkonfigurationsprinciper   >  **Lägg**  >  **till**. Klicka på **Hanterade enheter.**

    > [!div class="mx-imgBorder"]
    > ![Bild av Administrationscenter för Microsoft Endpoint Manager4](images/ios-deploy-4.png)

1. Ange *följande* information på sidan Skapa appkonfigurationsprincip:
    - Principnamn
    - Plattform: Välj iOS/iPadOS
    - Riktad app: Välj **Microsoft Defender ATP** i listan

    > [!div class="mx-imgBorder"]
    > ![Bild av Administrationscenter för Microsoft Endpoint Manager5](images/ios-deploy-5.png)

1. På nästa skärm väljer du **Använd konfigurationsdesignern** som format. Ange följande egenskap:
    - Konfigurationsnyckel: issupervised
    - Värdetyp: Sträng
    - Konfigurationsvärde: {{issupervised}}
    
    > [!div class="mx-imgBorder"]
    > ![Bild av Administrationscenter för Microsoft Endpoint Manager](images/ios-deploy-6.png)

1. Klicka **på Nästa** så att sidan **Omfattningstaggar** öppnas. Omfattningstaggar är valfria. Klicka **på Nästa** för att fortsätta.

1. På sidan **Uppgifter väljer** du de grupper som ska få den här profilen. I det här scenariot är det bäst att rikta alla **enheter mot mål.** Mer information om hur du tilldelar profiler finns i [Tilldela användar- och enhetsprofiler.](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)

   När du distribuerar till användargrupper måste en användare logga in på en enhet innan principen tillämpas.

   Klicka på **Nästa**.

1. På sidan **Granska + skapa** väljer du Skapa när du är **klar.** Den nya profilen visas i listan över konfigurationsprofiler.

1. För förbättrade funktioner mot nätfiske kan du därefter distribuera en anpassad profil på de övervakade iOS-enheterna. Följ stegen nedan:
    - Ladda ned konfigurationsprofilen från [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)
    - Gå till  ->  **Konfigurationsprofiler för enheter iOS/iPadOS**  ->    ->  **Skapa profil**

    > [!div class="mx-imgBorder"]
    > ![Bild av Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)

    - Ange ett namn på profilen. När du uppmanas att importera en konfigurationsprofilfil väljer du den som hämtats ovan.
    - I avsnittet **Uppgift** väljer du den enhetsgrupp för vilken du vill använda den här profilen. Det är en bra metod att detta ska tillämpas på alla hanterade iOS-enheter. Klicka på **Nästa**.
    - På sidan **Granska + skapa** väljer du Skapa när du är **klar.** Den nya profilen visas i listan över konfigurationsprofiler.

## <a name="next-steps"></a>Nästa steg

[Konfigurera Defender för slutpunkt för iOS-funktioner](ios-configure-features.md)
