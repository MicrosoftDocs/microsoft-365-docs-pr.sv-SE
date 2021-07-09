---
title: Registrera Windows 10-multisessionsenheter i det Windows Virtual Desktop
description: Läs mer i den här artikeln om registrering av Windows 10 flersessionsenheter i Windows virtuellt skrivbord
keywords: Windows Virtuellt skrivbord, WVD, microsoft defender, slutpunkt, onboard
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 9114a825ad011f0b2a17cea4929ab2a09bfa2172
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339484"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a>Registrera Windows 10-multisessionsenheter i det Windows Virtual Desktop 
6 minuter att läsa 

Gäller för: 
- Windows 10 flersessionssession på Windows Virtual Desktop (WVD) 

Microsoft Defender för Endpoint har stöd för övervakning av både VDI Windows sessioner för virtuellt skrivbord. Beroende på organisationens behov kan du behöva implementera VDI- eller Windows Virtual Desktop-sessioner för att hjälpa dina anställda att få åtkomst till företagsdata och appar från en ohanterad enhet, fjärransluten plats eller liknande scenario. Med Microsoft Defender för Endpoint kan du övervaka dessa virtuella datorer efter avvikande aktivitet.

 ## <a name="before-you-begin"></a>Innan du börjar
Bekanta dig med överväganden [för icke-beständiga VDI.](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1) Även [om Windows Virtual Desktop](/azure/virtual-desktop/overview) inte har alternativ för att inte ha möjlighet att beständighet, erbjuder den ett sätt att använda en gyllene Windows-bild som kan användas för att tillhandahålla nya värdar och distribuera om datorer. Det här ökar säkerheten i miljön och påverkar därmed vilka poster som skapas och underhålls i Microsoft Defender för Endpoint-portalen, vilket potentiellt minskar synligheten för dina säkerhetsanalytiker.

> [!NOTE]
> Beroende på ditt val av onboarding-metod kan enheter visas i Microsoft Defender för Endpoint-portalen som antingen: 
> - Enskild post för varje virtuellt skrivbord 
> - Flera poster för varje virtuellt skrivbord 

Microsoft rekommenderar registrering av Windows virtuella skrivbordet som en enskild post per virtuellt skrivbord. Det säkerställer att undersökningsupplevelsen i Microsoft Defender Endpoint-portalen är i en enhets kontext baserat på datornamnet. Organisationer som ofta tar bort och distribuerar WVD-värdar bör överväga att använda den här metoden eftersom det förhindrar att flera objekt för samma dator skapas i Microsoft Defender för Endpoint-portalen. Det kan skapa förvirring när du undersöker incidenter. För testmiljöer eller ej ej beständiga miljöer kan du välja att välja ett annat. 

Microsoft rekommenderar att du lägger till Microsoft Defender för slutpunkts onboarding-skriptet i den gyllene bilden i WVD. På så sätt kan du vara säker på att det här onboarding-skriptet körs direkt vid första starten. Den körs som ett startskript vid första starten på alla WVD-datorer som är etablerade från den gyllene bilden i WVD. Men om du använder någon av galleribilderna utan att ändra det placerar du skriptet på en delad plats och anropar det från antingen lokal grupprincip eller domängruppsprincip. 

> [!NOTE]
> Startskriptet för VDI-onboarding placeras och konfigureras på den gyllene bilden i WVD som ett startskript som körs när WVD startas. Vi rekommenderar INTE att du visar den faktiska gyllene bilden i WVD. En annan faktor är metoden som används för att köra skriptet. Den bör köras så tidigt i start-/etableringsprocessen som möjligt för att minska tiden mellan den dator som är tillgänglig för att ta emot sessioner och enhetens registrering till tjänsten. Ta hänsyn till detta & 2 under scenarier 1.

### <a name="scenarios"></a>Scenarier
Det finns flera sätt att introducera en WVD-värddator:

- Kör skriptet i den gyllene bilden (eller från en delad plats) vid start.
- Använd ett hanteringsverktyg för att köra skriptet.

#### <a name="scenario-1-using-local-group-policy"></a>*Scenario 1: Använda lokal grupprincip*
Det här scenariot kräver att skriptet placeras i en gyllene bild och att lokala grupprinciper används för att köras tidigt i startprocessen.

Följ anvisningarna i [Hantera de icke-beständiga VDI-enheterna (Virtual Desktop Infrastructure).](configure-endpoints-vdi.md#onboard-the-non-persistent-virtual-desktop-infrastructure-vdi-devices)

Följ instruktionerna för en enskild post för varje enhet.

#### <a name="scenario-2-using-domain-group-policy"></a>*Scenario 2: Använda domängruppsprincip*
Det här scenariot använder ett centralt placerade skript och kör det med en domänbaserad grupprincip. Du kan också placera skriptet i den gyllene bilden och köra det på samma sätt.

**Ladda WindowsDefenderATPOnboardingPackage.zip filen från säkerhetscentret Windows Defender säkerhetscentret**

1. Öppna filen för VDI-.zip (WindowsDefenderATPOnboardingPackage.zip)  

    1. I Microsoft Defender Säkerhetscenter väljer du Inställningar   >  **Onboarding**. 
    1. Välj Windows 10 som operativsystem. 
    1. I fältet **Distributionsmetod** väljer du VDI-onboardingskript för icke-beständiga slutpunkter. 
    1. Klicka **på Ladda ned** paket och spara .zip filen. 

2. Extrahera innehållet i filen .zip till en delad, skrivskyddad plats som kan nås av enheten. Du bör ha en mapp med namnet **OptionalParamsPolicy** och filerna **WindowsDefenderATPOnboardingScript.cmd** **ochOnboard-NonPersistentMachine.ps1**.

**Använda konsolen för hantering av grupprinciper för att köra skriptet när den virtuella datorn startar**

1. Öppna GPMC (Group Policy Management Console), högerklicka på det grupprincipobjekt (GPO) du vill konfigurera och klicka på **Redigera.**

2. Gå till Inställningar för datorkonfiguration i **redigeraren för hantering** av \>  \> **grupprinciper på Kontrollpanelen.** 

3. Högerklicka på **Schemalagda aktiviteter,** klicka **på Ny** och klicka sedan på Direkt **aktivitet** (minst Windows 7). 

4. I uppgiftsfönstret som öppnas går du till **fliken** Allmänt. Under **Säkerhetsalternativ klickar** du **på Ändra användare eller grupp** och skriver SYSTEM. Klicka **på Kontrollera namn** och sedan på OK. NT AUTHORITY\SYSTEM visas som det användarkonto som aktiviteten körs som. 

5. Välj **Kör om användaren är inloggad eller inte** och markera kryssrutan Kör med **högst** behörighet. 

6. Gå till fliken **Åtgärder** och klicka på **Ny**. Kontrollera att **Starta ett program** är markerat i fältet Åtgärd. Ange följande: 

   `Action = "Start a program"`

   `Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe`

   `Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"`

   Välj sedan **OK** och stäng alla öppna GPMC-fönster.

#### <a name="scenario-3-onboarding-using-management-tools"></a>*Scenario 3: Introduktion med hanteringsverktyg*

Om du planerar att hantera dina maskiner med ett hanteringsverktyg kan du hantera enheter Microsoft Endpoint Configuration Manager.

Mer information finns i Informera [Windows 10 enheter med Konfigurationshanteraren.](configure-endpoints-sccm.md)

> [!WARNING]
> Om du tänker använda minskningsregler för [attackytan](attack-surface-reduction.md)bör du observera att regeln " Blockera processskapanden som kommer från[PSExec-](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)och WMI-kommandon " inte bör användas, eftersom regeln är inkompatibel med hantering via Microsoft Endpoint Configuration Manager. Regeln blockerar WMI-kommandon som Configuration Manager-klienten använder för att fungera korrekt. 

> [!TIP]
> När du har introducerat enheten kan du välja att köra ett identifieringstest för att verifiera att enheten är korrekt onboarded till tjänsten. Mer information finns i Köra [ett identifieringstest på en nyligen onboarded Microsoft Defender för Endpoint-enhet.](run-detection-test.md) 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a>Tagga dina maskiner när du skapar en gyllene bild 

Som en del av introduktionen kan du överväga att ställa in en maskintagg så att det blir lättare att skilja WVD-maskinerna åt i Microsofts säkerhetscenter. Mer information finns i Lägga [till enhetstaggar genom att ange ett registernyckelvärde.](machine-tags.md#add-device-tags-by-setting-a-registry-key-value) 

#### <a name="other-recommended-configuration-settings"></a>Andra rekommenderade konfigurationsinställningar 

När du skapar den gyllene bilden kanske du även vill konfigurera inställningar för det första skyddet. Mer information finns i [Andra rekommenderade konfigurationsinställningar](configure-endpoints-gp.md#other-recommended-configuration-settings). 

Om du använder FSlogix-användarprofiler rekommenderar vi att du undantar följande filer från alltid-on-skydd: 

**Undanta filer:** 

`%ProgramFiles%\FSLogix\Apps\frxdrv.sys`

`%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys`

`%ProgramFiles%\FSLogix\Apps\frxccd.sys`

`%TEMP%\*.VHD`

`%TEMP%\*.VHDX`

`%Windir%\TEMP\*.VHD`

`%Windir%\TEMP\*.VHDX`

`\\storageaccount.file.core.windows.net\share\*\*.VHD`

`\\storageaccount.file.core.windows.net\share\*\*.VHDX`

**Exkludera processer:**

`%ProgramFiles%\FSLogix\Apps\frxccd.exe`

`%ProgramFiles%\FSLogix\Apps\frxccds.exe`

`%ProgramFiles%\FSLogix\Apps\frxsvc.exe`

#### <a name="licensing-requirements"></a>Licensieringskrav 

Anmärkning om licensiering: När du använder Windows 10 Enterprise flera sessioner, beroende på dina krav, kan du välja att antingen ha alla användare licensierade via Microsoft Defender för slutpunkt (per användare), Windows Enterprise E5, Microsoft 365 Security eller Microsoft 365 E5, eller ha VM-licensen licensierad via Azure Defender.
Licenskrav för Microsoft Defender för slutpunkt finns i: [Licenskrav](minimum-requirements.md#licensing-requirements).

#### <a name="related-links"></a>Relaterade länkar

[Lägga till undantag för Microsoft Defender med hjälp av PowerShell](/azure/architecture/example-scenario/wvd/windows-virtual-desktop-fslogix#add-exclusions-for-windows-defender-by-using-powershell)
