---
title: Manuell distribution av Microsoft Defender ATP för macOS
description: Installera Microsoft Defender ATP för macOS manuellt från kommandoraden.
keywords: microsoft, defender, atp, mac, installation, distribuera, avinstallation, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: b2629eb3d13e6eb908644dfcade46a7ac2768637
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187451"
---
# <a name="manual-deployment-for-microsoft-defender-for-endpoint-for-macos"></a>Manuell distribution av Microsoft Defender för Slutpunkt för macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

I det här avsnittet beskrivs hur du distribuerar Microsoft Defender för slutpunkt för macOS manuellt. För en lyckad distribution måste du slutföra alla följande steg:
- [Ladda ned installation- och onboarding-paket](#download-installation-and-onboarding-packages)
- [Programinstallation (macOS 10.15 och äldre versioner)](#application-installation-macos-1015-and-older-versions)
- [Programinstallation (macOS 11 och senare versioner)](#application-installation-macos-11-and-newer-versions)
- [Klientkonfiguration](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a>Krav och systemkrav

Innan du börjar kan du gå [till huvudsidan för Microsoft Defender](microsoft-defender-endpoint-mac.md) för Slutpunkt för macOS för att få en beskrivning av förutsättningarna och systemkraven för den aktuella programvaruversionen.

## <a name="download-installation-and-onboarding-packages"></a>Ladda ned installation- och onboarding-paket

Ladda ned installation- och onboarding-paketen från Microsoft Defender Säkerhetscenter:

1. I Microsoft Defender Säkerhetscenter går du till **Inställningar > Enhetshantering > Onboarding**.
2. I avsnitt 1 på sidan anger du operativsystem till **macOS** och distributionsmetod till **Lokalt skript.**
3. I avsnitt 2 på sidan väljer du Ladda **ned installationspaketet**. Spara den som wdav.pkg i en lokal katalog.
4. Välj Hämta introduktionspaket i avsnitt 2 **på sidan.** Spara den WindowsDefenderATPOnboardingPackage.zip filen i samma katalog.

    ![Skärmbild av Microsoft Defender Säkerhetscenter](images/atp-portal-onboarding-page.png)

5. Kontrollera att du har de två filerna i kommandotolken.
    
## <a name="application-installation-macos-1015-and-older-versions"></a>Programinstallation (macOS 10.15 och äldre versioner)

Du måste ha administratörsbehörighet på enheten för att slutföra den här processen.

1. Navigera till den nedladdade wdav.pkg i Finder och öppna den.

    ![Skärmbild av appinstallation1](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-28-appinstall)

2. Välj **Fortsätt**, godkänn licensvillkoren och ange lösenordet när du uppmanas att göra det.

    ![Skärmbild av appinstallation2](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-29-appinstalllogin)

   > [!IMPORTANT]
   > Du uppmanas att tillåta att en drivrutin från Microsoft installeras (antingen "Systemtillägg blockerat" eller "Installationen är spärrad" eller båda. Drivrutinen måste tillåtas att installeras.

   ![Skärmbild av appinstallation3](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-30-systemextension)

3. Välj **Öppna säkerhetsinställningar** eller **Öppna systeminställningar > säkerhetsinställningar & sekretess.** Välj **Tillåt:**

    ![Skärmbild av fönstret Säkerhet och sekretess](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-31-securityprivacysettings)

   Installationen utförs.

   > [!CAUTION]
   > Om du inte väljer **Tillåt** fortsätter installationen efter 5 minuter. Microsoft Defender för Slutpunkt läses in, men vissa funktioner, till exempel realtidsskydd, inaktiveras. Mer information [om hur du löser](mac-support-kext.md) det finns i Felsöka problem med kerneltillägg.

> [!NOTE]
> macOS kan begära att starta om enheten vid den första installationen av Microsoft Defender för Slutpunkt. Realtidsskydd är inte tillgängligt förrän enheten startas om.

## <a name="application-installation-macos-11-and-newer-versions"></a>Programinstallation (macOS 11 och senare versioner)

Du måste ha administratörsbehörighet på enheten för att slutföra den här processen.

1. Navigera till den nedladdade wdav.pkg i Finder och öppna den.

    ![Skärmbild av appinstallation4](images/big-sur-install-1.png)

2. Välj **Fortsätt**, godkänn licensvillkoren och ange lösenordet när du uppmanas att göra det.

3. I slutet av installationsprocessen godkänner du de systemtillägg som används av produkten. Välj **Öppna säkerhetsinställningar**.

    ![Godkännande av systemtillägg](images/big-sur-install-2.png)

4. I fönstret **Säkerhet & sekretess** väljer du **Tillåt**.

    ![Säkerhetsinställningar för systemtillägg1](images/big-sur-install-3.png)

5. Upprepa steg 3 & 4 för alla systemtillägg som distribueras med Microsoft Defender för Slutpunkt för Mac.

6. Som en del av funktionerna Identifiering av slutpunkt och svar inspekterar Microsoft Defender för Slutpunkt för Mac sockettrafik och rapporterar den här informationen till Microsoft Defender Säkerhetscenter-portalen. När du uppmanas att ge Microsoft Defender behörighet att filtrera nätverkstrafik väljer du **Tillåt**.

    ![Säkerhetsinställningar för systemtillägg2](images/big-sur-install-4.png)

7. Öppna **Systeminställningar för**& sekretess och gå till fliken Sekretess. Ge fullständig diskåtkomstbehörighet till Microsoft Defender ATP och  >   Microsoft Defender  **ATP Endpoint Security Extension.**  

    ![Fullständig diskåtkomst](images/big-sur-install-5.png)

## <a name="client-configuration"></a>Klientkonfiguration

1. Kopiera wdav.pkg och MicrosoftDefenderATPOnboardingMacOs.py till enheten där du distribuerar Microsoft Defender för Endpoint för macOS.

    Klientenheten är inte kopplad till orgId. Observera att *orgId-attributet* är tomt.

    ```bash
    mdatp health --field org_id
    ```

2. Kör Python-skriptet för att installera konfigurationsfilen:

    ```bash
    /usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py
    ```

3. Kontrollera att enheten nu är kopplad till din organisation och rapporterar ett *giltigt orgId:*

    ```bash
    mdatp health --field org_id
    ```

Efter installationen visas Microsoft Defender-ikonen i statusfältet i macOS i det övre högra hörnet.

   ![Microsoft Defender-ikon i skärmbild i statusfältet](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-icon-bar)
   

## <a name="how-to-allow-full-disk-access"></a>Så här tillåter du fullständig diskåtkomst

> [!CAUTION]
> macOS 10.15 (Catalina) innehåller nya förbättringar av säkerhet och sekretess. Från och med den här versionen kan program som standard inte komma åt vissa platser på disken (till exempel Dokument, Nedladdningar, Skrivbord osv.) utan uttryckligt medgivande. Om inget sådant medgivande getts kan Inte Microsoft Defender för Endpoint skydda din enhet fullt ut.

Om du vill ge medgivande öppnar du Systeminställningar – > säkerhet & sekretess – > sekretess – > fullständig diskåtkomst. Klicka på låsikonen om du vill göra ändringar (längst ned i dialogrutan). Välj Microsoft Defender för Slutpunkt.

## <a name="logging-installation-issues"></a>Loggningsinstallationsproblem

Mer [information om hur](mac-resources.md#logging-installation-issues) du hittar den automatiskt genererade loggen som skapas av installationsprogrammet när ett fel uppstår finns i Problem med loggningsinstallationen.

## <a name="uninstallation"></a>Avinstallation

Mer [information om hur](mac-resources.md#uninstalling) du tar bort Microsoft Defender för Endpoint för macOS från klientenheter finns i Avinstallera.
