---
title: Konfigurera principer för Microsoft Defender för slutpunkt på macOS i Jamf Pro
description: Lär dig konfigurera Microsoft Defender för slutpunkt på macOS-principer i Jamf Pro
keywords: principer, microsoft, defender, Microsoft Defender för slutpunkt, mac, installation, distribuera, avinstallation, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 577eea6e678b6a5d60e5bb8f2fbaaae25d239577
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53230073"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-on-macos-policies-in-jamf-pro"></a>Konfigurera principer för Microsoft Defender för slutpunkt på macOS i Jamf Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Defender för Slutpunkt på Mac](microsoft-defender-endpoint-mac.md)

På den här sidan går du igenom de steg du måste vidta för att konfigurera macOS-principer i Jamf Pro.

Du måste göra följande:

1. [Skaffa Microsoft Defender för slutpunktens onboarding-paket](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [Skapa en konfigurationsprofil i Jamf Pro använda onboarding-paketet](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [Konfigurera Microsoft Defender för slutpunktsinställningar](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [Konfigurera microsoft Defender för aviseringsinställningar för slutpunkt](#step-4-configure-notifications-settings)

5. [Konfigurera Microsoft AutoUpdate (MAU)](#step-5-configure-microsoft-autoupdate-mau)

6. [Bevilja fullständig diskåtkomst till Microsoft Defender för Slutpunkt](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [Godkänna Kernel-tillägg för Microsoft Defender för Endpoint](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [Godkänna systemtillägg för Microsoft Defender för Slutpunkt](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [Konfigurera nätverkstillägg](#step-9-configure-network-extension)

10. [Schemasökningar med Microsoft Defender för Slutpunkt i macOS](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [Distribuera Microsoft Defender för slutpunkt i macOS](#step-11-deploy-microsoft-defender-for-endpoint-on-macos)


## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a>Steg 1: Skaffa Microsoft Defender för slutpunktens introduktionspaket

1. I [Microsoft Defender Säkerhetscenter](https://securitycenter.microsoft.com)navigerar du **till Inställningar > Onboarding**.

2. Välj macOS som operativsystem och Hantering av mobila enheter /Microsoft Intune som distributionsmetod.

    ![Bild av Microsoft Defender Säkerhetscenter](images/onboarding-macos.png)

3. Välj **Hämta introduktionspaket** (WindowsDefenderATPOnboardingPackage.zip).

4. Extrahera `WindowsDefenderATPOnboardingPackage.zip` .

5. Kopiera filen till önskad plats. Till exempel  `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist` .


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a>Steg 2: Skapa en konfigurationsprofil i Jamf Pro använda onboarding-paketet

1. Leta reda på `WindowsDefenderATPOnboarding.plist` filen från föregående avsnitt.

   ![Bild på filen WindowsDefenderATPOnboarding](images/plist-onboarding-file.png)


2. I instrumentpanelen i Jamf Pro väljer du **Ny**.

    ![Bild på hur du skapar en ny Jamf Pro instrumentpanel](images/jamf-pro-configure-profile.png)

3. Ange följande information:

   **Allmänt**
   - Namn: MDATP-registrering för macOS
   - Beskrivning: MDATP Identifiering och åtgärd på slutpunkt onboarding för macOS
   - Kategori: Ingen
   - Distributionsmetod: Installera automatiskt
   - Nivå: Datornivå

4. I **Program & Egen Inställningar** du **Konfigurera**.

    ![Bild av konfigurera app och anpassade inställningar](images/jamfpro-mac-profile.png)

5. Välj **Upload (PLIST-fil)** och ange sedan: i **Preference Domain** anger du: `com.microsoft.wdav.atp` .

    ![Bild på en fil som gör det enkelt att ladda upp en fil](images/jamfpro-plist-upload.png)

    ![Bild av listfil med filegenskap](images/jamfpro-plist-file.png)

6. Välj **Öppna** och välj onboarding-filen.

    ![Bild på onboarding-fil](images/jamfpro-plist-file-onboard.png)

7. Välj **Upload**.

    ![Bild på uppladdning av plist-fil](images/jamfpro-upload-plist.png)

8. Välj **fliken Omfattning.**

    ![Bild på fliken omfattning](images/jamfpro-scope-tab.png)

9. Välj måldatorerna.

    ![Bild på måldatorer](images/jamfpro-target-computer.png)

    ![Bild av mål](images/jamfpro-targets.png)

10. Välj **Spara**.

    ![Bild av måldatorer för distribution](images/jamfpro-deployment-target.png)

    ![Bild på valda måldatorer](images/jamfpro-target-selected.png)

11. Välj **Klar**.

    ![Bild av målgruppsdatorer](images/jamfpro-target-group.png)

    ![Lista över konfigurationsprofiler](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a>Steg 3: Konfigurera Microsoft Defender för Slutpunktsinställningar

Du kan antingen använda JAMF Pro GUI för att redigera enskilda inställningar för Microsoft Defender-konfigurationen eller använda den äldre metoden genom att skapa en konfigurations-Plist i en textredigerare och ladda upp den till JAMF-Pro.

Observera att du måste använda exakt `com.microsoft.wdav` som **Inställningsdomän**, microsoft Defender använder bara det här namnet och `com.microsoft.wdav.ext` för att läsa in de hanterade inställningarna.

(Versionen kan användas i sällsynta fall när du föredrar att använda GUI-metod, men också behöver konfigurera en inställning som inte har lagts till `com.microsoft.wdav.ext` i schemat ännu.)

### <a name="gui-method"></a>GUI-metod

1. Ladda schema.jsfil från [Defenders lagringsplats GitHub och](https://github.com/microsoft/mdatp-xplat/tree/master/macos/schema) spara den i en lokal fil:

    ```bash
    curl -o ~/Documents/schema.json https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/schema/schema.json
    ```

2. Skapa en ny konfigurationsprofil under Datorer - > konfigurationsprofiler, ange följande information på **fliken** Allmänt:

    ![Ny profil](images/644e0f3af40c29e80ca1443535b2fe32.png)

    - Namn: Konfigurationsinställningar för MDATP MDAV
    - Beskrivning:\<blank\>
    - Kategori: Ingen (standard)
    - Nivå: Datornivå (standard)
    - Distributionsmetod: Installera automatiskt (standard)

3. Rulla ned till fliken & egna **Inställningar** program, välj Externa  **program,** klicka på Lägg till och använd Eget **schema** som källa för inställningsdomänen.

    ![Lägga till ett anpassat schema](images/4137189bc3204bb09eed3aabc41afd78.png)

4. Ange `com.microsoft.wdav` som inställningsdomän, klicka på **Lägg till schema** **Upload** lägg schema.jsfilen som hämtas i steg 1. Klicka på **Spara**.

    ![Upload schema](images/a6f9f556037c42fabcfdcb1b697244cf.png)

5. Du kan se alla konfigurationsinställningar som stöds av Microsoft Defender nedan, under **Preference Domain Properties**. Klicka **på Lägg till/ta** bort egenskaper för att välja vilka inställningar som ska hanteras och klicka på **Ok** för att spara ändringarna. (Inställningar omarkerad inte inkluderas i den hanterade konfigurationen kommer en slutanvändare att kunna konfigurera inställningarna på sina datorer.)

    ![Välj hanterade inställningar](images/817b3b760d11467abe9bdd519513f54f.png)

6. Ändra värdena i inställningarna till önskade värden. Du kan klicka på **Mer information** för att hitta dokumentation om en viss inställning. (Du kan klicka på **Förhandsgranskning av Plist** för att kontrollera hur konfigurations-plisten kommer att se ut. Klicka **på Formulärredigeraren** för att återgå till den visuella redigeraren.)

    ![Ändra inställningsvärden](images/a14a79efd5c041bb8974cb5b12b3a9b6.png)

7. Välj **fliken Omfattning.**

    ![Konfigurationsprofilens omfattning](images/9fc17529e5577eefd773c658ec576a7d.png)

8. Välj **Contosos datorgrupp.**

9. Välj **Lägg** till och välj sedan **Spara**.

    ![Konfigurationsinställningar – lägg till](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![Konfigurationsinställningar – spara](images/6f093e42856753a3955cab7ee14f12d9.png)

10. Välj **Klar**. Den nya konfigurationsprofilen **visas.**

    ![Konfigurationsinställningar – klar](images/dd55405106da0dfc2f50f8d4525b01c8.png)

Microsoft Defender lägger till nya inställningar med tiden. De nya inställningarna läggs till i schemat och en ny version publiceras på Github.
Allt du behöver göra för att få uppdateringar är att ladda ned ett uppdaterat schema, redigera befintlig konfigurationsprofil och Redigera **schema** på fliken **& Program Inställningar** schema.

### <a name="legacy-method"></a>Äldre metod

1. Använd följande konfigurationsinställningar för Microsoft Defender för Slutpunkt:

    - enableRealTimeProtection
    - passivläge

    >[!NOTE]
    >Inte aktiverat som standard om du planerar att köra en tredjeparts-AV för macOS ställer du in den på `true` .

    - undantag
    - excludedPath
    - excludedFileExtension
    - excludedFileName
    - exclusionsMergePolicy
    - allowedThreats

    >[!NOTE]
    >EICAR ingår i exemplet. Om du går igenom ett koncepttest bör du ta bort det särskilt om du testar EICAR.

    - disallowedThreatActions
    - potentially_unwanted_application
    - archive_bomb
    - cloudService
    - automaticSampleSubmission
    - taggar
    - hideStatusMenuIcon

     Mer information finns i [egenskapslistan för Jamf-konfigurationsprofilen](mac-preferences.md#property-list-for-jamf-configuration-profile).

     ```XML
     <?xml version="1.0" encoding="UTF-8"?>
     <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
     <plist version="1.0">
     <dict>
         <key>antivirusEngine</key>
         <dict>
             <key>enableRealTimeProtection</key>
             <true/>
             <key>passiveMode</key>
             <false/>
             <key>exclusions</key>
             <array>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <false/>
                     <key>path</key>
                     <string>/var/log/system.log</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <true/>
                     <key>path</key>
                     <string>/home</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileExtension</string>
                     <key>extension</key>
                     <string>pdf</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileName</string>
                     <key>name</key>
                     <string>cat</string>
                 </dict>
             </array>
             <key>exclusionsMergePolicy</key>
             <string>merge</string>
             <key>allowedThreats</key>
             <array>
                 <string>EICAR-Test-File (not a virus)</string>
             </array>
             <key>disallowedThreatActions</key>
             <array>
                 <string>allow</string>
                 <string>restore</string>
             </array>
             <key>threatTypeSettings</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>potentially_unwanted_application</string>
                     <key>value</key>
                     <string>block</string>
                 </dict>
                 <dict>
                     <key>key</key>
                     <string>archive_bomb</string>
                     <key>value</key>
                     <string>audit</string>
                 </dict>
             </array>
             <key>threatTypeSettingsMergePolicy</key>
             <string>merge</string>
         </dict>
         <key>cloudService</key>
         <dict>
             <key>enabled</key>
             <true/>
             <key>diagnosticLevel</key>
             <string>optional</string>
             <key>automaticSampleSubmission</key>
             <true/>
         </dict>
         <key>edr</key>
         <dict>
             <key>tags</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>GROUP</string>
                     <key>value</key>
                     <string>ExampleTag</string>
                 </dict>
             </array>
         </dict>
         <key>userInterface</key>
         <dict>
             <key>hideStatusMenuIcon</key>
             <false/>
         </dict>
     </dict>
     </plist>
     ```

2. Spara filen som `MDATP_MDAV_configuration_settings.plist` .

3. I instrumentpanelen i Jamf Pro du **Datorer** och där finns **Konfigurationsprofiler.** Klicka på **Ny(* och växla till **fliken** Allmänt.

    ![Ny profil](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. Ange följande information:

    **Allmänt**

    - Namn: Konfigurationsinställningar för MDATP MDAV
    - Beskrivning:\<blank\>
    - Kategori: Ingen (standard)
    - Distributionsmetod: Installera automatiskt(standard)
    - Nivå: Datornivå(standard)

    ![Bild av konfigurationsinställningar för MDATP MDAV](images/3160906404bc5a2edf84d1d015894e3b.png)

5. I **Program & Egen Inställningar** du **Konfigurera**.

    ![Bild av app och anpassade inställningar](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. Välj **Upload (PLIST-fil)**.

    ![Bild av plist-fil med konfigurationsinställningar](images/6f85269276b2278eca4bce84f935f87b.png)

7. I **Preferences Domain** anger du och väljer Upload `com.microsoft.wdav` **PLIST-fil**.

    ![Bild av domän med konfigurationsinställningar](images/db15f147dd959e872a044184711d7d46.png)

8. Välj **Välj fil**.

    ![Bild av konfigurationsinställningar, välj fil](images/526e978761fc571cca06907da7b01fd6.png)

9. Välj fliken **MDATP_MDAV_configuration_settings.plist** och välj sedan **Öppna**.

    ![Bild av konfigurationsinställningar för mdatpmdav](images/98acea3750113b8dbab334296e833003.png)

10. Välj **Upload**.

    ![Bild på konfigurationsinställning för uppladdning](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![Bild av uppladdningsbild för konfigurationsinställningar](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    >Om du råkar ladda upp Intune-filen får du följande felmeddelande:<br>
    >![Bild av konfigurationsinställningar för intune-filuppladdning](images/8e69f867664668796a3b2904896f0436.png)


11. Välj **Spara**.

    ![Bild av konfigurationsinställningar Spara bild](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. Filen laddas upp.

    ![Bild av konfigurationsinställningar, fil uppladdad bild](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![Bild på konfigurationsinställningsfil som laddats upp](images/a422e57fe8d45689227e784443e51bd1.png)

13. Välj **fliken Omfattning.**

    ![Bild av konfigurationsinställningars omfattning](images/9fc17529e5577eefd773c658ec576a7d.png)

14. Välj **Contosos datorgrupp.**

15. Välj **Lägg** till och välj sedan **Spara**.

    ![Bild på konfigurationsinställningar som läggs till](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![Bild av spara lägg till i konfigurationsinställningar](images/6f093e42856753a3955cab7ee14f12d9.png)

16. Välj **Klar**. Den nya konfigurationsprofilen **visas.**

    ![Bild på konfigurationsinställningar konfigurationsprofil bild](images/dd55405106da0dfc2f50f8d4525b01c8.png)

## <a name="step-4-configure-notifications-settings"></a>Steg 4: Konfigurera aviseringsinställningar

De här stegen gäller för macOS 10.15 (Catalina) eller nyare.

1. I instrumentpanelen För Pro det här **instrumentpanelen väljer du Datorer** och sedan **Konfigurationsprofiler**.

2. Klicka **på** Nytt och ange följande information för **Alternativ:**

    - Tabb **Allmänt:**
        - **Namn**: Meddelandeinställningar för MDATP MDAV
        - **Beskrivning**: macOS 10.15 (Catalina) eller nyare
        - **Kategori:** Ingen *(standard)*
        - **Distributionsmetod:** Installera automatiskt *(standard)*
        - **Nivå:** Datornivå *(standard)*

        ![Bild av skärmen med den nya macOS-konfigurationsprofilen](images/c9820a5ff84aaf21635c04a23a97ca93.png)

    - **Flikmeddelanden**, klicka **på** Lägg till och ange följande värden:
        - **Paket-ID:**`com.microsoft.wdav.tray`
        - **Viktiga aviseringar:** Klicka på **Inaktivera**
        - **Meddelanden**: Klicka på **Aktivera**
        - **Aviseringstyp för** banderoll: Välj **Inkludera** **och Tillfällig** *(standard)*
        - **Meddelanden på låsskärmen:** Klicka på **Dölj**
        - **Meddelanden i meddelandecentret:** Klicka på **Visa**
        - **Ikon för aktivitetsikonen**: Klicka på **Visa**

        ![Bild på konfigurationsinställningar mdatpmdav-meddelandefältet](images/7f9138053dbcbf928e5182ee7b295ebe.png)

    - Flikmeddelanden , klicka **på Lägg** till en gång till, bläddra ned till **Nya Inställningar** 
        - **Paket-ID:**`com.microsoft.autoupdate2`
        - Konfigurera resten av inställningarna till samma värden som ovan

        ![Bild på konfigurationsinställningar mdatpmdav-meddelanden mau](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)

        Observera att du nu har två "tabeller" med meddelandekonfigurationer, en för **Paket-ID: com.microsoft.wdav.tray** och en annan för **Paket-ID: com.microsoft.autoupdate2**. Du kan konfigurera aviseringsinställningar enligt dina krav, paket-ID måste  vara exakt samma som beskrivs tidigare och växeln Inkludera måste vara **På** för **Meddelanden.**

3. Välj fliken **Omfattning** och välj sedan Lägg **till**.

    ![Bild av tillägget för konfigurationsinställningar](images/441aa2ecd36abadcdd8aed03556080b5.png)

4. Välj **Contosos datorgrupp.**

5. Välj **Lägg** till och välj sedan **Spara**.

    ![Bild av konfigurationsinställningar spara contoso machine grp](images/09a275e321268e5e3ac0c0865d3e2db5.png)

    ![Bild av konfigurationsinställningar lägg till Spara](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

6. Välj **Klar**. Den nya konfigurationsprofilen **visas.**
    ![Bild på konfigurationsinställning klar img](images/633ad26b8bf24ec683c98b2feb884bdf.png)

## <a name="step-5-configure-microsoft-autoupdate-mau"></a>Steg 5: Konfigurera Microsoft AutoUpdate (MAU)

1. Använd följande konfigurationsinställningar för Microsoft Defender för Slutpunkt:

      ```XML
   <?xml version="1.0" encoding="UTF-8"?>
   <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
   <plist version="1.0">
   <dict>
    <key>ChannelName</key>
    <string>Current</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
   </dict>
   </plist>
   ```

2. Spara den som `MDATP_MDAV_MAU_settings.plist` .

3. I instrumentpanelen i Jamf Pro väljer du **Allmänt**.

    ![Bild av konfigurationsinställning för allmän bild](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. Ange följande information:

    **Allmänt**

    - Namn: MDATP MDAV MAU-inställningar
    - Beskrivning: Microsoft AutoUpdate-inställningar för MDATP för macOS
    - Kategori: Ingen (standard)
    - Distributionsmetod: Installera automatiskt(standard)
    - Nivå: Datornivå(standard)

5. I **Program & Egen Inställningar** du **Konfigurera**.

    ![Bild av konfigurationsinställningsapp och anpassade inställningar](images/1f72e9c15eaafcabf1504397e99be311.png)

6. Välj **Upload (PLIST-fil)**.

    ![Bild på konfigurationsinställning för plist](images/1213872db5833aa8be535da57653219f.png)

7. I **Preference Domain** anger du: och väljer Upload `com.microsoft.autoupdate2` **PLIST-fil**.

    ![Bild av konfigurationsinställning före domän](images/1213872db5833aa8be535da57653219f.png)

8. Välj **Välj fil**.

    ![Bild på konfigurationsinställning för choosefile](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. Välj **MDATP_MDAV_MAU_settings.plist**.

    ![Bild på konfigurationsinställning mdatpmdavmau-inställningar](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. Välj **Upload**.
    ![Bild på konfigurationskonfigurationskonfiguration](images/4239ca0528efb0734e4ca0b490bfb22d.png)

    ![Bild på konfigurationskonfigurationsinställningar](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. Välj **Spara**.

    ![Bild på sparaimg för konfigurationsinställningar](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. Välj **fliken Omfattning.**

     ![Bild på omfattning för konfigurationsinställningar](images/10ab98358b2d602f3f67618735fa82fb.png)

13. Välj **Lägg till**.

    ![Bild på konfigurationsinställning addimg1](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![Bild på konfigurationsinställning addimg2](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![Bild på konfigurationsinställning addimg3](images/321ba245f14743c1d5d51c15e99deecc.png)

14. Välj **Klar**.

    ![Bild på konfigurationsinställning klarbild](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a>Steg 6: Ge fullständig diskåtkomst till Microsoft Defender för Slutpunkt

1. Välj Konfigurationsprofiler Pro i **Det här instrumentpanelen .**

    ![Bild på konfigurationsinställningskonfigurationsprofil](images/264493cd01e62c7085659d6fdc26dc91.png)

2. Välj **+ Ny.**

3. Ange följande information:

    **Allmänt**
    - Namn: MDATP MDAV – tilldela fullständig diskåtkomst till Identifiering och åtgärd på slutpunkt och AV
    - Beskrivning: På macOS Catalina eller nyare, den nya kontrollen för sekretesspolicy
    - Kategori: Ingen
    - Distributionsmetod: Installera automatiskt
    - Nivå: Datornivå


    ![Bild av konfigurationsinställningar allmänt](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. I **Konfigurera principkontrollen för sekretesspolicy väljer** du **Konfigurera**.

    ![Bild av principkontrollen för konfigurationssekretess](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. Ange **följande information i Kontrollen** av sekretesspolicyn:

    - Identifierare: `com.microsoft.wdav`
    - Identifierartyp: Paket-ID
    - Kodkrav: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`


    ![Bild av konfigurationsinställningar för sekretessprincipens kontrollinformation](images/22cb439de958101c0a12f3038f905b27.png)

6. Välj **+ Lägg till.**

    ![Bild av konfigurationsinställning lägga till systemprincip för alla filer](images/bd93e78b74c2660a0541af4690dd9485.png)

    - Under App eller tjänst: Ställ in **på SystemPolicyAllFiles**

    - Under "åtkomst": Ange som **Tillåt**

7. Välj **Spara** (inte det längst ned till höger).

    ![Bild på konfigurationsinställningar för att spara bilder](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. Klicka på `+` tecknet bredvid **Appåtkomst för att** lägga till en ny post.

    ![Bild av konfigurationsinställningar för appåtkomst](images/tcc-add-entry.png)

9. Ange följande information:

    - Identifierare: `com.microsoft.wdav.epsext`
    - Identifierartyp: Paket-ID
    - Kodkrav: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

10. Välj **+ Lägg till.**

    ![Bild av konfigurationsinställningen tcc epsext-post](images/tcc-epsext-entry.png)

    - Under App eller tjänst: Ställ in **på SystemPolicyAllFiles**

    - Under "åtkomst": Ange som **Tillåt**

11. Välj **Spara** (inte det längst ned till höger).

    ![Bild på konfigurationsinställningen tcc epsext bild2](images/tcc-epsext-entry2.png)

12. Välj **fliken Omfattning.**

    ![Bild på konfigurationsinställningars omfattning](images/2c49b16cd112729b3719724f581e6882.png)

13. Välj **+ Lägg till.**

    ![Bild av konfigurationsinställnings addimage](images/57cef926d1b9260fb74a5f460cee887a.png)

14. Välj **Datorgrupper** > under **Gruppnamn** > **välj Contosos Datorgrupp.**

    ![Bild på konfigurationsinställning för contoso-maskingrp](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. Välj **Lägg till**.

16. Välj **Spara**.

17. Välj **Klar**.

    ![Bild på konfigurationsinställning donimg](images/809cef630281b64b8f07f20913b0039b.png)

    ![Bild på konfigurationsinställning donimg2](images/6c8b406ee224335a8c65d06953dc756e.png)

Du kan också ladda ned [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) och ladda upp den till JAMF-konfigurationsprofiler enligt beskrivningen i Distribuera anpassade konfigurationsprofiler med [Jamf Pro| Metod 2: Upload en konfigurationsprofil till Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).

## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a>Steg 7: Godkänna Kernel-tillägg för Microsoft Defender för Slutpunkt

> [!CAUTION]
> Apple Silicon-enheter (M1) stöder inte KEXT. Installationen av en konfigurationsprofil som består av KEXT-principer misslyckas på dessa enheter.

1. I **Konfigurationsprofiler** väljer du **+ Ny.**

    ![En skärmbild av en postbeskrivning i sociala medier som genererats automatiskt](images/6c8b406ee224335a8c65d06953dc756e.png)

2. Ange följande information:

    **Allmänt**

    - Namn: MDATP MDAV Kernel-tillägg
    - Beskrivning: MDATP-kerneltillägg (kext)
    - Kategori: Ingen
    - Distributionsmetod: Installera automatiskt
    - Nivå: Datornivå

    ![Bild av konfigurationsinställningar mdatpmdav kernel](images/24e290f5fc309932cf41f3a280d22c14.png)

3. Välj **Konfigurera i Konfigurera godkända Kernel-tillägg.** 

    ![Bild av konfigurationsinställningar godkänd kernel-ext](images/30be88b63abc5e8dde11b73f1b1ade6a.png)


4. Ange **följande information i Godkända Kernel-tillägg:**

    - Visningsnamn: Microsoft Corp.
    - Team-ID: UBF8T346G9

    ![Bild av konfigurationsinställningarappr kernel-tillägg](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. Välj **fliken Omfattning.**

    ![Bild på fliken omfattning för konfigurationsinställningar img](images/0df36fc308ba569db204ee32db3fb40a.png)

6. Välj **+ Lägg till.**

7. Välj **Datorgrupper** > under **Gruppnamn** > **sedan Contosos datorgrupp.**

8. Välj **+ Lägg till.**

    ![Bild av konfigurationsinställningar lägga till bilder](images/0dde8a4c41110dbc398c485433a81359.png)

9. Välj **Spara**.

    ![Bild på sparning av konfigurationsinställningar](images/0add8019b85a453b47fa5c402c72761b.png)

10. Välj **Klar**.

    ![Bild på konfigurationsinställningar klarbild](images/1c9bd3f68db20b80193dac18f33c22d0.png)

Du kan också ladda ned [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) och ladda upp den till JAMF-konfigurationsprofiler enligt beskrivningen i Distribuera anpassade konfigurationsprofiler med [Jamf Pro| Metod 2: Upload en konfigurationsprofil till Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).

## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a>Steg 8: Godkänna systemtillägg för Microsoft Defender för Slutpunkt

1. I **Konfigurationsprofiler** väljer du **+ Ny.**

    ![En skärmbild av en postbeskrivning i sociala medier som genererats automatiskt](images/6c8b406ee224335a8c65d06953dc756e.png)

2. Ange följande information:

    **Allmänt**

    - Namn: MDATP MDAV-systemtillägg
    - Beskrivning: MDATP-systemtillägg
    - Kategori: Ingen
    - Distributionsmetod: Installera automatiskt
    - Nivå: Datornivå

    ![Bild av konfigurationsinställningar sysext new prof](images/sysext-new-profile.png)

3. Välj **Konfigurera i** **Systemtillägg.**

   ![Bild på konfigurationsinställningar sysext config](images/sysext-configure.png)

4. Ange följande information i **Systemtillägg:**

   - Visningsnamn: Microsoft Corp. System Extensions
   - Systemtilläggstyper: Tillåtna systemtillägg
   - Team Identifier: UBF8T346G9
   - Tillåtna systemtillägg:
     - **com.microsoft.wdav.epsext**
     - **com.microsoft.wdav.netext**

    ![Bild av konfigurationsinställningar sysextconfig2](images/sysext-configure2.png)

5. Välj **fliken Omfattning.**

    ![Bild på omfattning för konfigurationsinställningar](images/0df36fc308ba569db204ee32db3fb40a.png)

6. Välj **+ Lägg till.**

7. Välj **Datorgrupper** > under **Gruppnamn** > **sedan Contosos datorgrupp.**

8. Välj **+ Lägg till.**

   ![Bild av addima för konfigurationsinställningar](images/0dde8a4c41110dbc398c485433a81359.png)

9. Välj **Spara**.

   ![Bild av konfigurationsinställningar, sysext-omfattning](images/sysext-scope.png)

10. Välj **Klar**.

    ![Bild på konfigurationsinställningar sysext-final](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a>Steg 9: Konfigurera nätverkstillägg

Som en del av funktionerna Slutpunktsidentifiering och svar inspekterar Microsoft Defender för slutpunkt på macOS sockettrafik och rapporterar den här informationen till Microsoft Defender Säkerhetscenter portalen. Med följande princip kan nätverkstillägget utföra de här funktionerna.

De här stegen gäller för macOS 10.15 (Catalina) eller nyare.

1. I instrumentpanelen För Pro det här **instrumentpanelen väljer du Datorer** och sedan **Konfigurationsprofiler**.

2. Klicka **på** Nytt och ange följande information för **Alternativ:**

    - Tabb **Allmänt:**
        - **Namn:** Microsoft Defender ATP-nätverkstillägg
        - **Beskrivning**: macOS 10.15 (Catalina) eller nyare
        - **Kategori:** Ingen *(standard)*
        - **Distributionsmetod:** Installera automatiskt *(standard)*
        - **Nivå:** Datornivå *(standard)*

    - **Flikinnehållsfilter:**
        - **Filternamn:** Microsoft Defender ATP-innehållsfilter
        - **Identifierare:**`com.microsoft.wdav`
        - Lämna **Tjänstadress,** **Organisation,** **Användarnamn,** **Lösenord,** **Certifikat** tomt **(Inkludera** *är inte* markerat)
        - **Filterordning**: Kontroll
        - **Socketfilter:**`com.microsoft.wdav.netext`
        - **Socketfilter angett krav:**`identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
        - Lämna **nätverksfilterfält** tomma **(Inkludera** *är inte* markerat)

        Observera att **exakta värden** för **identifierare, socketfilter** **och uttagsfilter angivna** krav enligt ovan.

        ![Bild på konfigurationsinställning mdatpmdav](images/netext-create-profile.png)

3. Välj **fliken Omfattning.**

   ![Bild på fliken för konfigurationsinställningar](images/0df36fc308ba569db204ee32db3fb40a.png)

4. Välj **+ Lägg till.**

5. Välj **Datorgrupper** > under **Gruppnamn** > **sedan Contosos datorgrupp.**

6. Välj **+ Lägg till.**

    ![Bild på konfigurationsinställningar](images/0dde8a4c41110dbc398c485433a81359.png)

7. Välj **Spara**.

    ![Bild på konfigurationsinställningar savimg netextscop](images/netext-scope.png)

8. Välj **Klar**.

    ![Bild av konfigurationsinställningar netextfinal](images/netext-final.png)

Du kan också ladda ned [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) och ladda upp den till JAMF-konfigurationsprofiler enligt beskrivningen i Distribuera anpassade konfigurationsprofiler med [Jamf Pro| Metod 2: Upload en konfigurationsprofil till Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).


## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>Steg 10: Schemalägga genomsökningar med Microsoft Defender för Slutpunkt i macOS
Följ anvisningarna i [Schemalägga genomsökningar med Microsoft Defender för slutpunkt på macOS.](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)


## <a name="step-11-deploy-microsoft-defender-for-endpoint-on-macos"></a>Steg 11: Distribuera Microsoft Defender för slutpunkt i macOS

1. Gå till den plats där du sparade `wdav.pkg` .

    ![Bild på utforskaren wdav pkg](images/8dde76b5463047423f8637c86b05c29d.png)

2. Byt namn på den till `wdav_MDM_Contoso_200329.pkg` .

    ![Bild på utforskaren1 wdavmdmpkg](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. Öppna instrumentpanelen för jamf Pro.

    ![Bild på konfigurationsinställningar som gör attpro kan göra det](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. Välj din dator och klicka på kugghjulsikonen högst upp och välj sedan **Datorhantering**.

    ![Bild på konfigurationsinställningar compmgmt](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. I **Packages** väljer du **+ New**.
    ![En bild med paket som automatiskt genererades av fågelbeskrivning](images/57aa4d21e2ccc65466bf284701d4e961.png)

6. Ange **följande information** i Nytt paket:

    **Fliken Allmänt**
    - Visningsnamn: Lämna det tomt för tillfället. Eftersom det återställs när du väljer ditt pkg.
    - Kategori: Ingen (standard)
    - Filnamn: Välj fil

    ![Bild av den allmänna fliken för konfigurationsinställningar](images/21de3658bf58b1b767a17358a3f06341.png)

    Öppna filen och peka på `wdav.pkg` eller `wdav_MDM_Contoso_200329.pkg` .

    ![En skärmbild av en datorskärmsbeskrivning som genereras automatiskt](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. Välj **Öppna**. Ställ in **visningsnamnet** på **Microsoft Defender Avancerat skydd och Microsoft Defender Antivirus**.

    **Manifestfil** krävs inte. Microsoft Defender för slutpunkt fungerar utan manifestfil.

    **Fliken Alternativ**<br> Behåll standardvärden.

    **Fliken Begränsningar**<br> Behåll standardvärden.

     ![Bild på fliken för konfigurationsinställningars begränsning](images/56dac54634d13b2d3948ab50e8d3ef21.png)

8. Välj **Spara**. Paketet laddas upp till Jamf Pro.

   ![Bild på konfigurationsinställningar pack upl jamf pro](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   Det kan ta några minuter innan paketet är tillgängligt för distribution.

   ![Bild på upl för konfigurationsinställningar](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. Gå till **sidan** Principer.

    ![Bild av konfigurationsinställningar](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. Välj **+ Ny för** att skapa en ny princip.

    ![Bild av ny princip för konfigurationsinställningar](images/847b70e54ed04787e415f5180414b310.png)


11. Ange  följande information i Allmänt:

    - Visningsnamn: MDATP Onboarding Contoso 200329 v100.86.92 eller senare

    ![Bild av konfigurationsinställningarmdatponboard](images/625ba6d19e8597f05e4907298a454d28.png)

12. Välj **Återkommande incheckning.**

    ![Bild av återkommande återkommande konfigureringsinställningar](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)


13. Välj **Spara**.

14. Välj **Packages > Configure**.

    ![Bild på konfigurationsinställningar för konfigurering](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. Välj Lägg **till** bredvid **Microsoft Defender Advanced Threat Protection och välj Microsoft Defender Antivirus**.

    ![Bild av konfigurationsinställningar MDATP och MDA add](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. Välj **Spara**.

    ![Bild på konfigurationsinställningarsavimg](images/9d6e5386e652e00715ff348af72671c6.png)

17. Välj **fliken Omfattning.**

    ![Bild på konfigurationsinställningar scptab](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. Välj måldatorerna.

    ![Bild på konfigurationsinställningar tgtcomp](images/6eda18a64a660fa149575454e54e7156.png)

    **Omfattning**

    Välj **Lägg till**.

    ![Bild på konfigurationsinställningar ad1img](images/1c08d097829863778d562c10c5f92b67.png)

    ![Bild på konfigurationsinställningar ad2img](images/216253cbfb6ae738b9f13496b9c799fd.png)

    **Självbetjäning**

    ![Bild av självbetjäning för konfigurationsinställningar](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. Välj **Klar**.

    ![Bild på konfigurationsinställningar do1img](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![Bild på konfigurationsinställningar do2img](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)




