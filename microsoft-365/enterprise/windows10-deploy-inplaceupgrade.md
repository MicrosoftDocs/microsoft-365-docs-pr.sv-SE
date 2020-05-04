---
title: Distribuera Windows 10 Enterprise för befintliga enheter som en uppgradering på plats
description: Innehåller vägledning om hur du konfigurerar och distribuerar en Windows 10 Enterprise-avbildning med Microsoft Endpoint Configuration Manager som en uppgradering på plats.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-dokumentation, Windows 10 Enterprise, distribution, uppgradering på plats, Configuration Manager, Configuration Manager
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: 1c90640fa49aa102d2a4c8420feedf659b5682f2
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011823"
---
# <a name="step-2-deploy-windows-10-enterprise-for-existing-devices-as-an-in-place-upgrade"></a>Steg 2: Distribuera Windows 10 Enterprise för befintliga enheter som en uppgradering på plats

*Den här artikeln gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*

![Fas 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Den enklaste vägen för att uppgradera datorer som för närvarande kör Windows 7 eller Windows 8.1 till Windows 10 är genom en uppgradering på plats. Du kan använda en Configuration Manager -aktivitetssekvens (Configuration Manager) för att helt automatisera processen. 

Om du har befintliga datorer med Windows 7 eller Windows 8.1 rekommenderar vi den här sökvägen om din organisation distribuerar Windows 10. Detta utnyttjar Installationsprogrammet för Windows (Setup.exe) för att utföra en uppgradering på plats, som automatiskt bevarar alla data, inställningar, program och drivrutiner från den befintliga operativsystemversionen. Detta kräver minst IT-insats, eftersom det inte finns något behov av någon komplex distributionsinfrastruktur.

Följ dessa steg för att konfigurera och distribuera en Windows 10 Enterprise-avbildning med Microsoft Endpoint Configuration Manager som en uppgradering på plats.

## <a name="the-windows-10-deployment-with-configuration-manager-poster"></a>Distribution av Windows 10 med Configuration Manager (affisch)

Configuration Manager-affischen är en sida i liggande läge (17x11). Klicka på bilden nedan för att visa en PDF-fil i webbläsaren. 

[![Distribuera Windows 10 med Configuration Manager-affisch](../media/windows10-deploy-inplaceupgrade/windows10-deployment-config-manager.png)](https://docs.microsoft.com/windows/deployment/media/Windows10DeploymentConfigManager.pdf)

Du kan också ladda ned den här affischen i [PDF](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10DeploymentConfigManager.pdf)- eller [Visio](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10DeploymentConfigManager.vsdx)-format.

## <a name="part-1-verify-readiness-to-upgrade-windows"></a>Del 1: Kontrollera beredskapen för att uppgradera Windows

Använd först funktionen Uppgraderingsberedskap i Windows Analytics för att ge kraftfulla insikter och rekommendationer om datorer, program och drivrutiner i organisationen, utan extra kostnad och utan ytterligare infrastrukturkrav. Den här nya tjänsten guidar dig genom uppgraderings- och funktionsuppdateringsprojekt med hjälp av ett arbetsflöde baserat på microsofts rekommenderade metoder. Aktuella lagerdata gör att du kan balansera kostnader och risker i dina uppgraderingsprojekt.

Se [Hantera Windows-uppgraderingar med uppgraderingsberedskap](https://docs.microsoft.com/windows/deployment/upgrade/manage-windows-upgrades-with-upgrade-readiness) om du vill veta mer, komma igång, använda och felsöka uppgraderingsberedskap.

Följ sedan guiden för att använda Configuration Manager (Current Branch) för att uppgradera Windows 7 eller senare operativsystem till Windows 10. Precis som vid alla högriskdistributioner rekommenderar vi säkerhetskopiering av användardata innan du fortsätter. OneDrive-molnlagring är klar att användas för licensierade Microsoft 365-användare och kan användas för att lagra sina filer på ett säkert sätt. Mer information finns i [Snabbstartsguide för OneDrive](https://aka.ms/ODfBquickstartguide). För att komma åt den här sidan måste du logga in som klientadministratör eller global administratör i en Office 365- eller Microsoft 365-klientorganisation.

En lista över Configuration Manager-versioner och motsvarande Windows 10-klientversioner som stöds finns i [Support för Windows 10 för Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/plan-design/configs/support-for-windows-10).

**Så här verifierar du beredskapen för att uppgradera Windows**

Granska de här kraven innan du startar distributionen av Windows 10:

- **Windows-utgåvor som kan uppgraderas** – Dina enheter måste köra utgåvor av Windows 7 eller Windows 8.1 som kan uppgraderas till Windows 10 Enterprise. En lista över utgåvor som stöds finns i [uppgraderingsvägar för Windows 10](https://aka.ms/win10upgradepaths). 
- **Enheter som stöds** – De flesta datorer som är kompatibla med Windows 8.1 är kompatibla med Windows 10. Du kan behöva installera uppdaterade drivrutiner i Windows 10 för att dina enheter ska fungera korrekt. Mer information finns i Specifikationerna för [Windows 10.](https://aka.ms/windows10specifications)
- **Förberedelse för distribution** – Kontrollera att du har följande innan du börjar konfigurera distributionen:
    - Windows 10 installationsmedia - Installationsmediet måste vara placerat på en separat enhet, med ISO redan monterad. Du kan hämta ISO från [MSDN-prenumeranthämtningar](https://aka.ms/msdn-subscriber-downloads) eller från Servicecenter för [volymlicensiering](https://aka.ms/mvlsc).
    - Säkerhetskopior av användardata – Även om användardata migreras i uppgraderingen är det bäst att konfigurera ett säkerhetskopieringsscenario. Exportera till exempel alla användardata till ett OneDrive-konto, BitLocker To Go-krypterat USB-flashminne eller nätverksfilserver. Mer information finns i [Säkerhetskopiera eller överföra data i Windows](https://aka.ms/backuptransferdatawindows).
- **Förberedelse av miljö** – Du kommer att använda en befintlig Configuration Manager-serverstruktur för att förbereda för operativsystemdistribution. Förutom basinställningarna bör följande konfigurationer göras i Configuration Manager-miljön:
    1. [Utöka Active Directory-schemat](https://aka.ms/extendadschema) och [skapa en systemhanteringsbehållare](https://aka.ms/createsysmancontainer).
    2. Aktivera Identifiering av Active Directory-skog och Active Directory System Discovery. Mer information finns i [Konfigurera identifieringsmetoder för Configuration Manager](https://aka.ms/configurediscoverymethods).
    3. Skapa IP-intervallgränser och gränsgrupp för innehåll och platstilldelning. Mer information finns i [Definiera platsgränser och gränsgrupper för Configuration Manager](https://aka.ms/definesiteboundaries).
    4. Lägg till och konfigurera rollen för reporting services-rapporteringstjänster i Configuration Manager. Mer information finns [i Konfigurera rapportering i Configuration Manager](https://aka.ms/configurereporting).
    5. Skapa en filsystemmappstruktur för paket.
    6. Skapa en configuration manager-konsolmappstruktur för paket.
    7. Installera Configuration Manager -uppdateringar (Current Branch) och eventuella ytterligare Windows 10-förutsättningar.

## <a name="part-2-add-a-windows-10-os-image-using-configuration-manager"></a>Del 2: Lägga till en Windows 10 OS-avbildning med Configuration Manager
Nu måste du skapa ett uppgraderingspaket för operativsystemet som innehåller det fullständiga installationsmediet för Windows 10. I följande steg använder du Configuration Manager för att skapa ett uppgraderingspaket för Windows 10 Enterprise x64.

**Så här lägger du till en Windows 10 OS-avbildning med Configuration Manager**

1. Högerklicka på noden **Operativsystemets uppgraderingspaket** på Configuration **Manager-konsolen** och välj sedan **Lägg till uppgraderingspaket för operativsystem**.
2. På sidan **Datakälla** anger du UNC-sökvägen till Windows 10 Enterprise x64-mediet och väljer sedan **Nästa**.
3. På sidan **Allmänt** anger du Uppgradering av **Windows 10 Enterprise x64**och väljer sedan **Nästa**. 
4. På sidan **Sammanfattning** väljer du **Nästa**och väljer sedan **Stäng**. 
5. Högerklicka på det skapade **Windows 10 Enterprise x64 Update-paketet** och välj sedan **Distribuera innehåll**. 
6. Välj distributionsplats.

## <a name="part-3-configure-deployment-settings"></a>Del 3: Konfigurera distributionsinställningar
I det här steget konfigurerar du en uppgraderingsaktivitetssekvens som innehåller inställningarna för Windows 10-uppgraderingen. Du identifierar sedan de enheter som ska uppgraderas och distribuerar sedan aktivitetssekvensen till dessa enheter.

### <a name="create-a-task-sequence"></a>Skapa en aktivitetssekvens
Så här skapar du en uppgraderingsaktivitetssekvens:
  
1. Expandera **operativsystem**i configuration **manager-konsolen på arbetsytan Programvarubibliotek** . 
2. Högerklicka på noden **Aktivitetssekvenser** och välj sedan **Skapa aktivitetssekvens**.
3. På sidan **Skapa en ny aktivitetssekvens** väljer du **Uppgradera ett operativsystem från uppgraderingspaketet**och väljer sedan **Nästa**.
4. På sidan **Information om aktivitetssekvens** anger du Uppgradering av **Windows 10 Enterprise x64**och väljer sedan **Nästa**.
5. På sidan **Uppgradera operativsystemet Uppgradera operativsystemet** väljer du **Bläddra** och väljer **uppgraderingspaketet för Windows 10 Enterprise x64-uppgradering,** väljer **OK**och väljer sedan **Nästa**.
6. Fortsätt genom de återstående guidesidorna och välj sedan **Stäng**.

### <a name="create-a-device-collection"></a>Skapa en enhetssamling
När du har skapat uppgraderingsaktivitetssekvensen måste du skapa en samling som innehåller de enheter som du ska uppgradera.

> [!NOTE]
> Använd följande inställningar för att testa distributionen på en enda enhet. Du kan använda olika medlemskapsregler för att inkludera grupper av enheter när du är redo. Mer information finns [i Så här skapar du samlingar i Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/clients/manage/collections/create-collections).

1. Högerklicka på **Enhetssamlingar**i arbetsytan **Resurser och efterlevnad** i Configuration Manager-konsolen och välj sedan Skapa **enhetssamling**. 
2. Ange följande inställningar på sidan **Skapa** enhetsinsamling i guiden Skapa enhetssamling och välj sedan **Nästa:**
    - Namn: Uppgradering av Windows 10 Enterprise x64
    - Begränsa insamling: Alla system
3. På sidan **Medlemskapsregler** väljer du Lägg till > **regeldirekt-regel** för att starta guiden Skapa regel för direktmedlemskap. **Add Rule**
4. På **välkomstsidan** i guiden Skapa direktmedlemskapsregel väljer du **Nästa**.
5. På sidan **Sök efter resurser** anger du följande inställningar och ersätter platshållarvärdets text med namnet på den enhet som du uppgraderar: **Value** 
    - Resursklass: Systemresurs
    - Attributnamn: Namn
    - Värde: *PC0003*
6. På sidan **Välj resurser** väljer du enheten och väljer **Nästa**.
7. Slutför guiden Skapa regel för direktmedlemskap och guiden Skapa enhetssamling.  
8. Granska uppgraderingssamlingen för Windows 10 Enterprise x64. Fortsätt inte förrän du ser de datorer som du har lagt till i samlingen.

### <a name="create-an-operating-system-deployment"></a>Skapa en operativsystemdistribution
Följ dessa steg för att skapa en distribution för aktivitetssekvensen.

1. Högerklicka på aktivitetssekvensen som du skapade i ett föregående steg i Configuration Manager-konsolen i arbetsytan **Programvarubibliotek** och välj sedan **Distribuera**.
2. På sidan **Allmänt** väljer du uppgraderingssamlingen **för Windows 10 Enterprise x64** och väljer sedan **Nästa**.
3. På sidan **Innehåll** väljer du **Nästa**.
4. På sidan **Distributionsinställningar** väljer du följande inställningar och väljer sedan **Nästa:**

    > [!NOTE]
    > För den här testdistributionen anger du syftet **till Tillgänglig**, vilket kräver åtgärder från användaren för att starta distributionen. I en produktionsmiljö kanske du vill automatisera distributionen med det nödvändiga syftet, vilket innebär att ytterligare alternativ som schemaläggning konfigureras när distributionen körs. 

    - Åtgärd: Installera
    - Syfte: Tillgänglig

5. På sidan **Schemaläggning** godkänner du standardinställningarna och väljer sedan **Nästa**.
6. På sidan **Användarupplevelse** godkänner du standardinställningarna och väljer sedan **Nästa**.
7. På sidan **Aviseringar godkänner** du standardinställningarna och väljer sedan **Nästa**.
8. På sidan **Sammanfattning** väljer du **Nästa**och väljer sedan **Stäng**.

## <a name="part-4-start-the-windows-10-upgrade-task-sequence"></a>Del 4: Starta aktivitetssekvensen för Windows 10-uppgradering
Följ dessa steg för att starta aktivitetssekvensen För Windows 10-uppgradering på den enhet som du uppgraderar.
 
1. Logga in på Windows-datorn och starta **Software Center**.
2. Markera den aktivitetssekvens som du skapade i ett tidigare steg och välj sedan **Installera**.
3. När aktivitetssekvensen börjar initieras automatiskt uppgraderingsprocessen på plats genom att starta installationsprogrammet för Windows (Setup.exe) med nödvändiga kommandoradsparametrar för att utföra en automatisk uppgradering, som bevarar alla data, inställningar, appar och drivrutiner.
4. När aktivitetssekvensen har slutförts kommer datorn att uppgraderas helt till Windows 10.

Om du får problem när du använder Windows 10 i en företagsmiljö kan du läsa [de vanligaste Microsoft-supportlösningarna för de vanligaste problemen](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions). Dessa resurser omfattar KB-artiklar, uppdateringar och biblioteksartiklar.

Under lanseringen av uppdateringar i hela organisationen använder du funktionen Uppdatera efterlevnad i Windows Analytics för att ge en holistisk bild av kompatibiliteten för operativsystemets uppdatering, uppdateringsdistributionsförloppet och felsökning vid felfel för Windows 10-enheter. Den här nya tjänsten använder diagnostikdata, inklusive installationsförlopp, Windows Update-konfiguration och annan information för att ge sådana insikter, utan extra kostnad och utan ytterligare infrastrukturkrav. Oavsett om den används med Windows Update för företag eller andra hanteringsverktyg kan du vara säker på att dina enheter är korrekt uppdaterade.

Mer information finns i [Övervaka Windows-uppdateringar och Windows Defender Antivirus med uppdateringsefterlevnad](https://docs.microsoft.com/windows/deployment/update/update-compliance-monitor) om du vill veta mer, komma igång och använda Uppdatera efterlevnad.

Som en mellanliggande kontrollpunkt kan du se vilka [avslutsvillkor](windows10-exit-criteria.md#crit-windows10-step2) som motsvarar det här steget.

## <a name="next-step"></a>Nästa steg

|||
|:-------|:-----|
|![Steg 3](../media/stepnumbers/Step3.png)| [Distribuera Windows 10 Enterprise för nya enheter med Windows Autopilot](windows10-deploy-autopilot.md) |
