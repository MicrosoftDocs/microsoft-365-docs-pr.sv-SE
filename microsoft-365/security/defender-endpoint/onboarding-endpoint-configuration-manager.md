---
title: Introduktion med hjälp av Microsoft Endpoint Configuration Manager
description: Lär dig hur du onboardar till Microsoft Defender för Endpoint med Microsoft Endpoint Configuration Manager
keywords: onboarding, configuration, deploy, deployment, endpoint configuration manager, Microsoft Defender for Endpoint, collection creation, endpoint detection response, next generation protection, attack surface reduction, microsoft endpoint configuration manager
search.product: eADQiWindows 10XVcnh
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
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: eab23ddeb9011e80cf2835b8d38b2d3fad4b7089
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843512"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a>Introduktion med hjälp av Microsoft Endpoint Configuration Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Den här artikeln är en del av distributionsguiden och fungerar som ett exempel på onboarding-metod. 

I ämnet [Planering](deployment-strategy.md) finns det flera metoder för att introducera enheter till tjänsten. Det här avsnittet behandlar arkitekturen för samtidig hantering. 

![Bild av molnbaserad arkitektur ](images/co-management-architecture.png)
 *Diagram över miljöarkitekturer*


Defender för Endpoint har stöd för registrering av olika slutpunkter och verktyg, men den här artikeln täcker inte in dem. Mer information om allmän onboarding med andra distributionsverktyg och metoder som stöds finns i [Översikt över onboarding.](onboarding.md)



Det här avsnittet leder användarna i:
- Steg 1: Windows enheter till tjänsten 
- Steg 2: Konfigurera Defender för slutpunktsfunktioner

Den här introduktionsvägledningen går igenom följande grundläggande steg som du måste vidta när du använder Microsoft Endpoint Configuration Manager:
- **Skapa en samling i Microsoft Endpoint Configuration Manager**
- **Konfigurera Microsoft Defender för slutpunktsfunktioner med Microsoft Endpoint Configuration Manager**

>[!NOTE]
>Endast Windows enheter omfattas av den här exempeldistributionen. 



## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a>Steg 1: Onboard Windows enheter med Microsoft Endpoint Configuration Manager

### <a name="collection-creation"></a>Skapa samling
Om du Windows 10 registrera Microsoft Endpoint Configuration Manager-enheter med hjälp av Microsoft Endpoint Configuration Manager kan distributionen ha en befintlig samling som mål, eller så kan en ny samling skapas för testning. 

Registrering med verktyg som grupprincip eller manuell metod installerar inte någon agent i systemet. 

I Microsoft Endpoint Configuration Manager konsolen konfigureras onboarding-processen som en del av inställningarna för efterlevnad i konsolen.

Alla system som får den här nödvändiga konfigurationen behåller den konfigurationen så länge Konfigurationshanteraren-klienten fortsätter att ta emot den här principen från hanteringspunkten. 

Följ stegen nedan för att registrera slutpunkter med hjälp Microsoft Endpoint Configuration Manager.

1. I Microsoft Endpoint Configuration Manager navigera till Enhetssamlingar **för tillgångar och \> \> efterlevnadsöversikt.**            

    ![Bild på Microsoft Endpoint Configuration Manager 1](images/configmgr-device-collections.png)

2. Högerklicka på **Enhetssamling** och välj **Skapa enhetssamling**.

    ![Bild på Microsoft Endpoint Configuration Manager 2](images/configmgr-create-device-collection.png)

3. Ange ett **namn** och **en begränsad samling** och välj sedan **Nästa.**

    ![Bild på Microsoft Endpoint Configuration Manager 3](images/configmgr-limiting-collection.png)

4. Välj **Lägg till regel** och välj **Frågeregel.**

    ![Bild av Microsoft Endpoint Configuration Manager guiden4](images/configmgr-query-rule.png)

5.  Klicka **på** Nästa i **guiden Direktmedlemskap och** klicka på Redigera **frågeutdrag.**

     ![Bild på Microsoft Endpoint Configuration Manager 5](images/configmgr-direct-membership.png)

6. Välj **Villkor** och välj sedan stjärnikonen.

     ![Bild på Microsoft Endpoint Configuration Manager 6](images/configmgr-criteria.png)

7. Se till att villkorstypen är ett enkelt värde  , välj var som operativsystem **–** versionsnummer , operator som är större än eller lika med och **värde 14393** och klicka på **OK.** 

    ![Bild på Microsoft Endpoint Configuration Manager 7](images/configmgr-simple-value.png)

8. Välj **Nästa** och **Stäng.**

    ![Bild av Microsoft Endpoint Configuration Manager guiden8](images/configmgr-membership-rules.png)

9. Välj **Nästa**.

    ![Bild på Microsoft Endpoint Configuration Manager guiden9](images/configmgr-confirm.png)


När du har slutfört den här uppgiften har du en enhetssamling med Windows 10 alla slutpunkter i miljön. 


## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a>Steg 2: Konfigurera Microsoft Defender för slutpunktsfunktioner 
I det här avsnittet får du hjälp med att konfigurera följande funktioner Microsoft Endpoint Configuration Manager på Windows enheter:

- [**Identifiering och svar för slutpunkt**](#endpoint-detection-and-response)
- [**Nästa generations skydd**](#next-generation-protection)
- [**Minskning av attackytan**](#attack-surface-reduction)


### <a name="endpoint-detection-and-response"></a>Identifiering och svar av slutpunkt
#### <a name="windows-10"></a>Windows 10
I Microsoft Defender Säkerhetscenter kan du ladda ned onboarding-principen som kan användas för att skapa principen i System Center Configuration Manager och distribuera den till Windows 10 enheter.

1. På en Microsoft Defender Säkerhetscenter portal väljer [du Inställningar och sedan Onboarding](https://securitycenter.windows.com/preferences2/onboarding).



2. Under Distributionsmetod väljer du den version **av** Microsoft Endpoint Configuration Manager .

    ![Bild av introduktionsguiden för Microsoft Defender för slutpunkt10](images/mdatp-onboarding-wizard.png)

3. Välj **Ladda ned paket**.

    ![Bild av introduktionsguiden för Microsoft Defender för slutpunkt11](images/mdatp-download-package.png)

4. Spara paketet på en tillgänglig plats.
5. I Microsoft Endpoint Configuration Manager du till: **Tillgångar och efterlevnad > Översikt > Endpoint Protection > Microsoft Defender ATP Principer.**

6. Högerklicka på Microsoft Defender ATP **och** välj **Skapa Microsoft Defender ATP princip**.

    ![Bild på Microsoft Endpoint Configuration Manager 12](images/configmgr-create-policy.png)

7. Ange namn och beskrivning, kontrollera **att Onboarding** är markerat och välj sedan **Nästa**.

    ![Bild på Microsoft Endpoint Configuration Manager 13](images/configmgr-policy-name.png)


8. Klicka **på Bläddra**.

9. Navigera till platsen för den nedladdade filen från steg 4 ovan.

10. Klicka på **Nästa**.
11. Konfigurera agenten med lämpliga exempel **(Ingen eller** **Alla filtyper).**

    ![Bild av konfigurationsinställningar1](images/configmgr-config-settings.png)

12. Välj lämplig telemetri **(Normal eller** **Expedited)** och klicka sedan på **Nästa.**

    ![Bild på konfigurationsinställningar2](images/configmgr-telemetry.png)

14. Verifiera konfigurationen och klicka sedan på **Nästa.**

     ![Bild på konfigurationsinställningar3](images/configmgr-verify-configuration.png)

15. Klicka **på** Stäng när guiden är klar.

16.  Högerklicka Microsoft Endpoint Configuration Manager Defender för slutpunktsprincip du just skapade i konsolen och välj **Distribuera**.

     ![Bild på konfigurationsinställningar4](images/configmgr-deploy.png)

17. På den högra panelen markerar du den tidigare skapade samlingen och klickar på **OK.**

    ![Bild på konfigurationsinställningar5](images/configmgr-select-collection.png)


#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a>Tidigare versioner av Windows (version Windows 7 och Windows 8.1)
Följ stegen nedan för att identifiera defender för slutpunktsarbetsyta och arbetsytenyckel, som krävs för registrering av tidigare versioner av Windows.

1. På en Microsoft Defender Säkerhetscenter väljer du **Inställningar > Onboarding**.

2. Under Operativsystem väljer du **Windows 7 SP1 och 8.1.**

3. Kopiera **arbetsyte-ID** **och arbetsytenyckel** och spara dem. De kommer att användas senare i processen.

    ![Bild på onboarding](images/91b738e4b97c4272fd6d438d8c2d5269.png)

4. Installera Microsoft Monitoring Agent (MMA). <br>
    MMA stöds för närvarande (från och med januari 2019) på följande Windows operativsystem:

    -   Server-SKU:er: Windows Server 2008 SP1 eller nyare

    -   Klient-SKU:er: Windows 7 SP1 och senare

    MMA-agenten måste installeras på Windows enheter. För att kunna installera agenten måste vissa system ladda ned uppdateringen för kundupplevelse och diagnostisk [telemetri](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) för att kunna samla in data med MMA. Dessa systemversioner omfattar men kan inte begränsas till:

    -   Windows 8.1

    -   Windows 7

    -   Windows Server 2016

    -   Windows Server 2012 R2

    -   Windows Server 2008 R2

    Mer specifikt Windows 7 SP1 måste följande korrigeringar installeras:

    -   Installera [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)

    -   Installera [antingen .NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (eller senare) **eller** 
         [KB3154518.](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)
        Installera inte båda på samma system.

5. Om du använder en proxyserver för att ansluta till Internet kan du gå till avsnittet Konfigurera proxyinställningar.

När den är klar bör du se onboarded endpoints i portalen inom en timme.

### <a name="next-generation-protection"></a>Nästa generations skydd 
Microsoft Defender Antivirus är en inbyggd antimalwarelösning som ger nästa generations skydd för stationära datorer, bärbara datorer och servrar.

1. I Microsoft Endpoint Configuration Manager navigerar du till Översikt över tillgångar och **\> efterlevnad Endpoint Protection \> \> antimalware-policyer** och väljer Skapa programprincip för **program mot skadlig programvara.**

    ![Bild på program mot skadlig programvara](images/9736e0358e86bc778ce1bd4c516adb8b.png)

2. Välj Schemalagda genomsökningar **,** Sökinställningar **,** Standardåtgärder **,** Realtidsskydd , **Undantagsinställningar,** Avancerat, Åsidosättningar av hot, **Molnskyddstjänst** och Säkerhetsintelligensuppdateringar och välj **OK.**   

    ![Bild av nästa generations skyddsfönster1](images/1566ad81bae3d714cc9e0d47575a8cbd.png)

    I vissa branscher eller vissa utvalda företagskunder kan ha specifika behov av hur Antivirus är konfigurerat.

  
    [Snabbsökning kontra fullständig sökning och anpassad sökning](/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    Mer information finns i Windows-säkerhet [konfigurationsramverket](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)
  
    ![Bild av nästa generations skyddsfönster2](images/cd7daeb392ad5a36f2d3a15d650f1e96.png)

    ![Bild av nästa generations skyddsfönster3](images/36c7c2ed737f2f4b54918a4f20791d4b.png)

    ![Bild av nästa generations skyddsfönster4](images/a28afc02c1940d5220b233640364970c.png)

    ![Bild av nästa generations skyddsfönster5](images/5420a8790c550f39f189830775a6d4c9.png)

    ![Bild av nästa generations skyddsfönster6](images/33f08a38f2f4dd12a364f8eac95e8c6b.png)

    ![Bild av nästa generations skyddsfönster7](images/41b9a023bc96364062c2041a8f5c344e.png)

    ![Bild av nästa generations skyddsfönster8](images/945c9c5d66797037c3caeaa5c19f135c.png)

    ![Bild av nästa generations skyddsfönster9](images/3876ca687391bfc0ce215d221c683970.png)

3. Högerklicka på den nyligen skapade programprincipen för program mot skadlig programvara och välj **Distribuera**.

    ![Bild av nästa generations skyddsfönster10](images/f5508317cd8c7870627cb4726acd5f3d.png)

4. Rikta den nya program mot skadlig programvara till din Windows 10 och klicka på **OK.**

     ![Bild av nästa generations skyddsfönster11](images/configmgr-select-collection.png)

När du har slutfört den här uppgiften har du nu konfigurerat Windows Defender Antivirus.

### <a name="attack-surface-reduction"></a>Minska attackytan
Minskning av attackytan hos Defender för Endpoint inkluderar funktionsuppsättningen som är tillgänglig under Exploit Guard. ASR-regler (Attack Surface Reduction), kontrollerad mappåtkomst, nätverksskydd och sårbarhetsskydd. 

Alla dessa funktioner ger ett granskningsläge och ett blockläge. I granskningsläge påverkas inte slutanvändarna. Allt som samlas in är ytterligare telemetri och gör den tillgänglig i Microsoft Defender Säkerhetscenter. Syftet med en distribution är att stegvis flytta säkerhetskontroller till blockläge.

Så här anger du ASR-regler i granskningsläge:

1. På Microsoft Endpoint Configuration Manager navigerar du till Översikt över tillgångar och **\> efterlevnad Endpoint Protection Windows Defender \> \> Sårbarhetsskydd** och **väljer Skapa sårbarhetspolicy.**

   ![Bild på Microsoft Endpoint Configuration Manager konsol0](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2.  Välj **Minska attackytan**.
   

3. Ange att regler **ska granskas** och klicka på **Nästa.**


    ![Bild på Microsoft Endpoint Configuration Manager konsol1](images/d18e40c9e60aecf1f9a93065cb7567bd.png)

4. Bekräfta den nya Exploit Guard-policyn genom att klicka på **Nästa.**

    ![Bild på Microsoft Endpoint Configuration Manager konsol2](images/0a6536f2c4024c08709cac8fcf800060.png)

    
5. När principen har skapats klickar du på **Stäng.**

    ![Bild på Microsoft Endpoint Configuration Manager console3](images/95d23a07c2c8bc79176788f28cef7557.png)

    ![Bild på Microsoft Endpoint Manager konsol1](images/95d23a07c2c8bc79176788f28cef7557.png)
   

6.  Högerklicka på den nya principen och välj **Distribuera.**
    
    ![Bild på Microsoft Endpoint Configuration Manager konsol4](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. Rikta principen mot den nya Windows 10 och klicka på **OK.**

    ![Bild på Microsoft Endpoint Configuration Manager konsol5](images/0ccfe3e803be4b56c668b220b51da7f7.png)

När du har slutfört den här uppgiften har du nu konfigurerat ASR-regler i granskningsläge.  
  
Nedan följer ytterligare steg för att verifiera om ASR-regler tillämpas korrekt på slutpunkter. (Det kan ta några minuter)


1. Från en webbläsare går du till <https://securitycenter.windows.com> .

2.  Välj **Konfigurationshantering** på menyn till vänster.

3. Klicka **på Gå till hantering av attackytor** i hanteringspanelen för attackytor. 
    
    ![Bild på hantering av attackytor](images/security-center-attack-surface-mgnt-tile.png)

4. Klicka **på fliken** Konfiguration i rapporterna för minskning av attackytan. Den visar en översikt över asr-regler och status för ASR-regler på varje enhet.

    ![En skärmbild av rapporterna för minskning av attackytan1](images/f91f406e6e0aae197a947d3b0e8b2d0d.png)

5. Klicka på varje enhet visar konfigurationsinformation för ASR-regler.

    ![En skärmbild av minskningsregler för attackytan2](images/24bfb16ed561cbb468bd8ce51130ca9d.png)

Mer [information finns i Optimera ASR-regeldistribution](/microsoft-365/security/defender-endpoint/configure-machines-asr)   och identifieringar.  


#### <a name="set-network-protection-rules-in-audit-mode"></a>Ange nätverksskyddsregler i granskningsläge:
1. På Microsoft Endpoint Configuration Manager navigerar du till Översikt över tillgångar och **\> efterlevnad Endpoint Protection Windows Defender \> \> Sårbarhetsskydd** och **väljer Skapa sårbarhetspolicy.**

    ![En skärmbild System Center Konfigurationshanteraren1](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. Välj **Nätverksskydd**.

3. Ange inställningen Granskning **och** klicka på **Nästa.** 

    ![En skärmbild System Center Confirugatiom Manager2](images/c039b2e05dba1ade6fb4512456380c9f.png)

4. Bekräfta den nya Exploit Guard-policyn genom att klicka **på Nästa.**
    
    ![En skärmbild av Sårbarhet GUard-policy1](images/0a6536f2c4024c08709cac8fcf800060.png)

5. Klicka på Stäng när principen har **skapats.**

    ![En skärmbild av Sårbarhet GUard-policy2](images/95d23a07c2c8bc79176788f28cef7557.png)

6. Högerklicka på den nya principen och välj **Distribuera.**

    ![En skärmbild av Microsoft Endpoint Configuration Manager1](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. Välj principen för den nya Windows 10 och välj **OK**.

    ![En skärmbild av Microsoft Endpoint Configuration Manager2](images/0ccfe3e803be4b56c668b220b51da7f7.png)



När du har slutfört den här uppgiften har du nu konfigurerat nätverksskydd i granskningsläge.

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a>Så här ställer du in regler för kontrollerad mappåtkomst i granskningsläge:

1. På Microsoft Endpoint Configuration Manager navigerar du till Översikt över tillgångar och **\> efterlevnad Endpoint Protection Windows Defender \> \> Sårbarhetsskydd** och **väljer Skapa sårbarhetspolicy.**

    ![En skärmbild av Microsoft Endpoint Configuration Manager3](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. Välj **Reglerad mappåtkomst.**
    
3. Ange att konfigurationen ska **granskas och** klicka på **Nästa.**

    ![En skärmbild av Microsoft Endpoint Configuration Manager4](images/a8b934dab2dbba289cf64fe30e0e8aa4.png)    
    
4. Bekräfta den nya Exploit Guard-policyn genom att klicka på **Nästa.**

    ![En skärmbild av Microsoft Endpoint Configuration Manager5](images/0a6536f2c4024c08709cac8fcf800060.png)

5. Klicka på Stäng när principen har **skapats.**

    ![En skärmbild av Microsoft Endpoint Configuration Manager6](images/95d23a07c2c8bc79176788f28cef7557.png)

6. Högerklicka på den nya principen och välj **Distribuera.**

    ![En skärmbild av Microsoft Endpoint Configuration Manager7](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7.  Rikta principen mot den nya Windows 10 och klicka på **OK.**

    ![En skärmbild av Microsoft Endpoint Configuration Manager8](images/0ccfe3e803be4b56c668b220b51da7f7.png)

Nu har du konfigurerat kontrollerad mappåtkomst i granskningsläge.

## <a name="related-topic"></a>Relaterat ämne
- [Introduktion med Microsoft Endpoint Manager](onboarding-endpoint-manager.md)
