---
title: Registrera Windows 10-multisessionsenheter i det Windows Virtual Desktop
description: Läs mer i den här artikeln om onboarding av Windows 10-enheter med flera sessioner i windows virtuella skrivbord
keywords: Windows Virtual Desktop, WVD, microsoft defender, slutpunkt, onboard
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
ms.openlocfilehash: 3f925fdc514c5e53b50f748d991f54d20fb49bd0
ms.sourcegitcommit: 7ebed5810480d7c49f8ca03207b5ea84993d253f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51488151"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a>Registrera Windows 10-multisessionsenheter i det Windows Virtual Desktop 
6 minuter att läsa 

Gäller för: 
- Windows 10 med flera sessioner på Windows Virtual Desktop (WVD) 

Microsoft Defender för slutpunkten har stöd för övervakning av både VDI- och Windows Virtual Desktop-sessioner. Beroende på organisationens behov kan du behöva implementera VDI- eller Windows Virtual Desktop-sessioner för att hjälpa dina anställda att komma åt företagsdata och appar från en ohanterad enhet, fjärransluten plats eller liknande scenario. Med Microsoft Defender för Endpoint kan du övervaka dessa virtuella datorer efter avvikande aktivitet.

 ## <a name="before-you-begin"></a>Innan du börjar
Bekanta dig med överväganden [för icke-beständiga VDI.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1) [Även om Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview) inte har alternativ för beständighet, erbjuder det flera sätt att använda en gyllene Windows-bild som kan användas för att tillhandahålla nya värdar och distribuera om datorer. Det här ökar säkerheten i miljön och påverkar därmed vilka poster som skapas och underhålls i Microsoft Defender för Endpoint-portalen, vilket potentiellt minskar synligheten för dina säkerhetsanalytiker.

> [!NOTE]
> Beroende på ditt val av onboarding-metod kan enheter visas i Microsoft Defender för Endpoint-portalen som antingen: 
> - Enskild post för varje virtuellt skrivbord 
> - Flera poster för varje virtuellt skrivbord 

Microsoft rekommenderar att du registrering av Virtuellt Windows-skrivbord som en post per virtuellt skrivbord. Det säkerställer att undersökningsupplevelsen i Microsoft Defender Endpoint-portalen är i en enhets kontext baserat på datornamnet. Organisationer som ofta tar bort och distribuerar WVD-värdar bör överväga att använda den här metoden eftersom det förhindrar att flera objekt för samma dator skapas i Microsoft Defender för Endpoint-portalen. Det kan skapa förvirring när du undersöker incidenter. För testmiljöer eller ej ej beständiga miljöer kan du välja att välja ett annat. 

Microsoft rekommenderar att du lägger till Microsoft Defender för slutpunkts onboarding-skriptet i den gyllene bilden i WVD. På så sätt kan du vara säker på att det här onboarding-skriptet körs direkt vid första starten. Den körs som ett startskript vid första starten på alla WVD-datorer som är etablerade från den gyllene bilden i WVD. Men om du använder någon av galleribilderna utan att ändra det placerar du skriptet på en delad plats och anropar det från antingen lokal grupprincip eller domängruppsprincip. 

> [!NOTE]
> Startskriptet för VDI-onboarding placeras och konfigureras på den gyllene bilden i WVD som ett startskript som körs när WVD startas. Vi rekommenderar INTE att du visar den faktiska gyllene bilden i WVD. En annan faktor är metoden som används för att köra skriptet. Den bör köras så tidigt i start-/etableringsprocessen som möjligt för att minska tiden mellan den dator som är tillgänglig för att ta emot sessioner och enhetens registrering till tjänsten. Ta hänsyn till detta & 2 under scenarier 1.

### <a name="scenarios"></a>Scenarier
Det finns flera sätt att introducera en WVD-värddator:

- Kör skriptet i den gyllene bilden (eller från en delad plats) vid start.
- Använd ett hanteringsverktyg för att köra skriptet.

#### <a name="scenario-1-using-local-group-policy"></a>*Scenario 1: Använda lokal grupprincip*
Det här scenariot kräver att skriptet placeras i en gyllene bild och att lokala grupprinciper används för att köras tidigt i startprocessen.

Följ anvisningarna i Hantera [icke-beständiga VDI-enheter med virtuell skrivbordsinfrastruktur.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)

Följ instruktionerna för en enskild post för varje enhet.

#### <a name="scenario-2-using-domain-group-policy"></a>*Scenario 2: Använda domängruppsprincip*
Det här scenariot använder ett centralt placerade skript och kör det med en domänbaserad grupprincip. Du kan också placera skriptet i den gyllene bilden och köra det på samma sätt.

**Ladda ned WindowsDefenderATPOnboardingPackage.zip-filen från Windows Defender Säkerhetscenter**
1. Öppna ZIP-filen med VDI-konfigurationspaket (WindowsDefenderATPOnboardingPackage.zip)  
    - I navigeringsfönstret för Microsoft Defender Säkerhetscenter väljer du **Inställningar**  >  **Onboarding**. 
    - Välj Windows 10 som operativsystem. 
    - I fältet **Distributionsmetod** väljer du VDI-onboardingskript för icke-beständiga slutpunkter. 
    - Klicka **på Ladda ned** paket och spara ZIP-filen. 
2. Extrahera innehållet i ZIP-filen till en delad, skrivskyddad plats som kan nås av enheten. Du bör ha en mapp med namnet **OptionalParamsPolicy** och filerna **WindowsDefenderATPOnboardingScript.cmd** **ochOnboard-NonPersistentMachine.ps1**.

**Använda konsolen för hantering av grupprinciper för att köra skriptet när den virtuella datorn startar**
1. Öppna GPMC (Group Policy Management Console), högerklicka på det grupprincipobjekt (GPO) du vill konfigurera och klicka på **Redigera.**
1. Gå till Inställningar för datorkonfiguration i **redigeraren för hantering** av \>  \> **grupprinciper på Kontrollpanelen.** 
1. Högerklicka på **Schemalagda aktiviteter,** klicka **på Nytt** och klicka sedan på Direkt **aktivitet** (minst Windows 7). 
1. I uppgiftsfönstret som öppnas går du till **fliken** Allmänt. Under **Säkerhetsalternativ klickar** du **på Ändra användare eller grupp** och skriver SYSTEM. Klicka **på Kontrollera namn** och sedan på OK. NT AUTHORITY\SYSTEM visas som det användarkonto som aktiviteten körs som. 
1. Välj **Kör om användaren är inloggad eller inte** och markera kryssrutan Kör med **högst** behörighet. 
1. Gå till fliken **Åtgärder** och klicka på **Ny**. Kontrollera att **Starta ett program** är markerat i fältet Åtgärd. Ange följande: 

> Åtgärd = "Starta ett program" <br>
> Program/Skript = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe <br>
> Add arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"

Klicka **på OK** och stäng alla öppna GPMC-fönster.

#### <a name="scenario-3-onboarding-using-management-tools"></a>*Scenario 3: Introduktion med hanteringsverktyg*

Om du planerar att hantera dina datorer med ett hanteringsverktyg kan du hantera enheter med Microsoft Endpoint Configuration Manager.

Mer information finns i: Informera [Windows 10-enheter med Konfigurationshanteraren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm) 

> [!WARNING]
> Om du tänker använda minskningsregler för [attackytan](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)bör du observera att regeln " Blockera processskapanden som kommer från[PSExec-](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction#block-process-creations-originating-from-psexec-and-wmi-commands)och WMI-kommandon " inte bör användas eftersom den är inkompatibel med hantering via Microsoft Endpoint Configuration Manager eftersom den här regeln blockerar WMI-kommandon som Configuration Manager-klienten använder för att fungera korrekt. 

> [!TIP]
> När du har introducerat enheten kan du välja att köra ett identifieringstest för att verifiera att enheten är korrekt onboarded till tjänsten. Mer information finns i Köra [ett identifieringstest på en nyligen onboarded Microsoft Defender för Endpoint-enhet.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test) 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a>Tagga dina maskiner när du skapar en gyllene bild 

Som en del av introduktionen kan du överväga att ställa in en maskintagg så att det blir lättare att skilja WVD-maskinerna åt i Microsofts säkerhetscenter. Mer information finns i Lägga [till enhetstaggar genom att ange ett registernyckelvärde.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-tags#add-device-tags-by-setting-a-registry-key-value) 

#### <a name="other-recommended-configuration-settings"></a>Andra rekommenderade konfigurationsinställningar 

När du skapar den gyllene bilden kanske du även vill konfigurera inställningar för det första skyddet. Mer information finns i [Andra rekommenderade konfigurationsinställningar](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp#other-recommended-configuration-settings). 

Om du använder FSlogix-användarprofiler rekommenderar vi att du undantar följande filer från alltid-on-skydd: 

**Undanta filer:** 

> %ProgramFiles%\FSLogix\Apps\frxdrv.sys <br>
> %ProgramFiles%\FSLogix\Apps\frxdrvvt.sys <br>
> %ProgramFiles%\FSLogix\Apps\frxccd.sys <br>
> %TEMP% \* . VHD <br>
> %TEMP% \* . VHDX <br>
> %Windir%\TEMP \* . VHD <br>
> %Windir%\TEMP \* . VHDX <br>
> \\storageaccount.file.core.windows.net\share \* \* . VHD <br>
> \\storageaccount.file.core.windows.net\share \* \* . VHDX <br>

**Exkludera processer:**

> %ProgramFiles%\FSLogix\Apps\frxccd.exe <br>
> %ProgramFiles%\FSLogix\Apps\frxccds.exe <br>
> %ProgramFiles%\FSLogix\Apps\frxsvc.exe <br>

#### <a name="licensing-requirements"></a>Licenskrav 

Windows 10 Multi-session är ett klientoperativsystem. Licenskrav för Microsoft Defender för slutpunkt finns i: [Licenskrav](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).
