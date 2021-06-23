---
title: Migrera från tredjeparts hips till ASR-regler
description: Här beskrivs hur du ska hantera en migrering från en HIPS-lösning (Host Intrusion Prevention System) från tredje part till ASR-regler.
keywords: Minskningsregler för attackytor, asr- och asr-regler, hips, värdskyddssystem mot intrång, skyddsregler, anti-sårbarhet, antiexploit, sårbarhet, skydd mot virus, Microsoft Defender för slutpunkt
search.product: eADQiWindows 10XVcnh
ms.topic: article
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: fd7c6a217c1bc1ce3b278afb911988b94a6951e0
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062157"
---
# <a name="migrating-from-a-third-party-hips-to-asr-rules"></a>Migrera från tredjeparts hips till ASR-regler

I den här artikeln får du hjälp att mappa vanliga regler till Microsoft Defender för Endpoint.

## <a name="scenarios-when-migrating-from-a-third-party-hips-product-to-asr-rules"></a>Scenarier vid migrering från en HIPS-produkt från tredje part till ASR-regler

### <a name="block-creation-of-specific-files-and-registry-keys"></a>Blockera skapandet av specifika filer och registernycklar

- **Gäller för**– alla processer
- **Åtgärd –** skapa filer
- **Exempel på filer/mappar, registernycklar/värden, processer,** tjänster - *.zemapp, *.odin, *.locky, *.jaff, *.lukitus, *.wnry, *.krab
- **Regler för att minska attackytan**– ASR-regler blockerar attacktekniker och inte symboler för kompromettering (IOC). Att blockera ett specifikt filnamnstillägg är inte alltid praktiskt, eftersom det inte hindrar en enhet från att kompromettera. Det endast delvis överlappar en attack tills attacker skapar en ny typ av förlängning för nyttolasten.
- **Andra rekommenderade funktioner**– Vi rekommenderar att du har Microsoft Defender AV aktiverat, tillsammans med molnskydds- och funktionsanalys. Vi rekommenderar att du använder andra skydd mot utpressningstrojaner, till exempel ASR-regeln "Använd avancerat skydd mot utpressningstrojaner". Detta ger bättre skydd mot utpressningstrojaner. Dessutom övervakas många av dessa registernycklar av Microsoft Defender för Endpoint, till exempel ASEP-tekniker som utlöser specifika aviseringar. De registernycklar som används kräver minst lokal administratör eller behörigheten för ett betrott installationsprogram kan ändras. Vi rekommenderar att du använder en låst miljö, med lägsta administrativa konton eller rättigheter. Andra systemkonfigurationer kan aktiveras, bland annat "Disable SeDebug for non-required roles" (inaktivera Felsökning för icke-obligatoriska roller) som är en del av våra bredare säkerhetsrekommendationer.

### <a name="block-creation-of-specific-files-and-registry-keys"></a>Blockera skapandet av specifika filer och registernycklar

- **Gäller för**– alla processer
- **Processer**– ej a:
- **Åtgärd**– registerändringar
- **Exempel på filer/mappar, registernycklar/värden, processer, tjänster** -  *\Software*,HKCU\Environment\UserInitMprLogonScript,HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs *\StartExe, HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options*\Debugger, HKEY_CURRENT_USER\Software\Microsoft\HtmlHelp Author\location, HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SilentProcessExit*\MonitorProcess
- **Regler för att minska attackytan**– ASR-regler blockerar attacktekniker och inte symboler för kompromettering (IOC). Att blockera ett specifikt filnamnstillägg är inte alltid praktiskt, eftersom det inte hindrar en enhet från att kompromettera. Det endast delvis överlappar en attack tills attacker skapar en ny typ av förlängning för nyttolasten.
- **Andra rekommenderade funktioner**– Vi rekommenderar att du har Microsoft Defender AV aktiverat, tillsammans med molnskydds- och funktionsanalys. Vi rekommenderar att du använder ytterligare skydd, till exempel ASR-regeln "Använd avancerat skydd mot utpressningstrojaner". Detta ger bättre skydd mot utpressningstrojaner. Dessutom övervakas flera av dessa registernycklar av Microsoft Defender för Endpoint, till exempel ASEP-tekniker som utlöser specifika aviseringar. Dessutom måste de registernycklar som används kräva minst lokal administratör eller behörigheten för ett betrott installationsprogram kan ändras. Vi rekommenderar att du använder en låst miljö, med lägsta administrativa konton eller rättigheter. Andra systemkonfigurationer kan aktiveras, bland annat "Disable SeDebug for non-required roles" (inaktivera Felsökning för icke-obligatoriska roller) som är en del av våra bredare säkerhetsrekommendationer.

### <a name="block-untrusted-programs-from-running-from-removable-drives"></a>Blockera program som inte är betrodda från att köras från flyttbara enheter

- **Gäller för**- Icke betrodda program från USB
- **Processer**– *
- **Operation**– Processkörning
- **Exempel på filer/mappar, registernycklar/värden, processer, tjänster:-*
- Minskningsregler för **Attack Surface**– ASR-regler har en inbyggd regel för att förhindra att icke betrodda och osignerade program startas från flyttbara enheter: "Blockera icke betrodda och osignerade processer som körs från USB", GUID "b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4".
- **Andra rekommenderade funktioner**– Utforska ytterligare kontroller för USB-enheter och andra flyttbara media med hjälp av Microsoft Defender för Slutpunkt: Styra USB-enheter och andra flyttbara medium med hjälp av [Microsoft Defender för Endpoint.](/windows/security/threat-protection/device-control/control-usb-devices-using-intune)

### <a name="block-mshta-from-launching-certain-child-processes"></a>Blockera Mshta från att starta vissa underordnade processer

- **Gäller för**- Mshta
- **Processer**– mshta.exe
- **Operation**– Processkörning
- **Exempel på filer/mappar, registernycklar/värden, processer,** tjänster - powershell.exe, cmd.exe, regsvr32.exe
- **Regler för att minska attackytan**– ASR-regler innehåller inga specifika regler för att förhindra att underordnade processer "mshta.exe". Den här kontrollen ligger inom ramen för Sårbarhetsskydd eller Windows Defender Programkontroll.
- **Andra rekommenderade funktioner**– aktivera Windows Defender för att förhindra att mshta.exe körs helt och hållet. Om din organisation kräver "mshta.exe" för verksamhetsspecifika appar konfigurerar du en specifik Windows Defender sårbarhetsskyddsregel för att förhindra mshta.exe från att starta underordnade processer.

### <a name="block-outlook-from-launching-child-processes"></a>Blockera Outlook från att starta underordnade processer

- **Gäller för**- Outlook
- **Processer**– outlook.exe
- **Operation**– Processkörning
- **Exempel på filer/mappar, registernycklar/värden, processer, tjänster**- powershell.exe
- Regler för att minska attackytan – ASR-regler har en inbyggd regel för att förhindra att Office-kommunikationsappar (Outlook, Skype och Teams) startar underordnade processer: "Blockera Office-kommunikationsprogram från att skapa underordnade processer", GUID "26190899-1602-49e8-8b27-eb1d0a1ce869".
- **Andra rekommenderade funktioner**– Vi rekommenderar att du aktiverar PowerShell begränsat språkläge för att minimera attackytan från PowerShell.


### <a name="block-office-apps-from-launching-child-processes-and-from-creating-executable-content"></a>Blockera Office appar från att starta underordnade processer och från att skapa körbart innehåll

- **Gäller för**- Office  
- **Processer**– winword.exe, powerpnt.exe, excel.exe
- **Operation**– Processkörning
- **Exempel på filer/mappar, registernycklar/värden, processer,** tjänster - powershell.exe, cmd.exe, wscript.exe, mshta.exe, EQNEDT32.EXE, regsrv32.exe
- Regler för att minska attackytan – ASR-regler har en inbyggd regel som hindrar Office-appar från att starta underordnade processer: "Blockera alla Office-program från att skapa underordnade processer", GUID "D4F940AB-401B-4EFC-AADC-AD5F3C50688A".
- **Andra rekommenderade funktioner**– ej tillgängliga
    
### <a name="block-office-apps-from-launching-child-processes-and-from-creating-executable-content"></a>Blockera Office appar från att starta underordnade processer och från att skapa körbart innehåll

- **Gäller för**- Office
- **Processer**– winword.exe, powerpnt.exe, excel.exe
- **Åtgärd –** skapa filer
- **Exempel på filer/mappar, Registernycklar/värden, processer,** tjänster - C:\Användare *\AppData **.exe, C:\ProgramData**.exe, C:\ProgramData**.com, C:\Users* AppData\Local\Temp **.com, C:\Users*\Downloads**.exe, C:\Users *\AppData **.scf, C:\ProgramData**.scf, C:\Users\Public*.exe, C:\Users*\Desktop***.exe
- **Regler för att minska attackytan**– EJ!.

### <a name="block-wscript-from-reading-certain-types-of-files"></a>Förhindra att Wscript läser vissa typer av filer

- **Gäller för**- Wscript
- **Processer**– wscript.exe
- **Åtgärd –** Läsning av fil
- **Exempel på filer/mappar, registernycklar/värden, processer,** tjänster - C:\Användare *\AppData**.js, C:\Användare*\Nedladdningar**.js
- **Minskningsregler för attackytan**– På grund av tillförlitlighets- och prestandaproblem har ASR-regler inte möjlighet att förhindra att en viss process läser en viss skriptfiltyp. Vi har en regel för att förhindra attackvektorer som kan komma från dessa scenarier. Regelnamnet är "Blockera JavaScript eller VBScript från att starta hämtat körbart innehåll" (GUID "D3E037E1-3EB8-44C8-A917-5792794759) "Blockera körning av potentiellt oönskade skript" (GUID " 5BEB7EFE-FD9A-4556-801D-275E5FFC04CC").
- Andra rekommenderade funktioner – Även om det finns specifika ASR-regler som minimerar vissa attackvektorer i sådana scenarier är det viktigt att nämna att AV som standard kan kontrollera skript (PowerShell, Windows Script Host, JavaScript, VBScript med mera) i realtid, via AMSI (Antimalware Scan Interface). Mer information finns här: [Amsi (Antimalware Scan Interface).](/windows/win32/amsi/antimalware-scan-interface-portal)

### <a name="block-launch-of-child-processes"></a>Blockera lansering av underordnade processer

- **Gäller för**- Adobe Acrobat
- **Processer**– AcroRd32.exe, Acrobat.exe
- **Operation**– Processkörning
- **Exempel på filer/mappar, registernycklar/värden, processer,** tjänster - cmd.exe, powershell.exe, wscript.exe
- **Regler för att minska attackytan**– ASR-regler tillåter att Adobe Reader inte startar underordnade processer. Regelnamnet är "Blockera Adobe Reader från att skapa underordnade processer", GUID "7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c".
- **Andra rekommenderade funktioner**– ej tillgängliga


### <a name="block-download-or-creation-of-executable-content"></a>Blockera hämtning eller skapande av körbart innehåll

- **Gäller för**- CertUtil: Blockera nedladdning eller skapande av körbara filer 
- **Processer**– certutil.exe
- **Åtgärd –** skapa filer
- **Exempel på filer/mappar, registernycklar/värden, processer, tjänster**- *.exe
- **Regler för att minska attackytan**– ASR-reglerna stöder inte dessa scenarier eftersom de är en del Microsoft Defender Antivirus skydd.
- **Andra rekommenderade funktioner**– Microsoft Defender AV förhindrar CertUtil från att skapa eller ladda ned körbart innehåll.


### <a name="block-processes-from-stopping-critical-system-components"></a>Blockera processer från att stoppa kritiska systemkomponenter

- **Gäller för**– alla processer
- **Processer**– *
- **Operation**– Processavslutning
- **Exempel på filer/mappar, registernycklar/värden, processer,** tjänster – MsSense.exe, MsMpEng.exe, NisSrv.exe, svchost.exe*, services.exe, csrss.exe, smss.exe, wininit.exe med mera.
- **Regler för att minska** attackytan – ASR-regler stöder inte dessa scenarier eftersom de är Windows 10 inbyggda säkerhetsskydd.
- **Andra rekommenderade funktioner**– ELAM (Early Launch AntiMalware), PPL (Protection Process Light), PPL AntiMalware Light och System Guard.

### <a name="block-specific-launch-process-attempt"></a>Blockera specifikt startprocessförsök

- **Gäller för**– specifika processer
- **Processer**- "Namnge din process"
- **Operation**– Processkörning
- **Exempel på filer/mappar, registernycklar/värden, processer,** tjänster - tor.exe, bittorrent.exe, cmd.exe, powershell.exe med mera
- **Regler för att minska attackytan**– ASR-regler är inte utformade för att fungera som programhanterare.
- **Andra rekommenderade funktioner**– Om du vill förhindra att användare startar specifika processer eller program bör du Windows Defender programkontrollen. Microsoft Defender för slutpunktsfiler och certifikatindikatorer kan användas i ett scenario med incidentsvar (ska inte ses som en mekanism för programkontroll).
    
### <a name="block-unauthorized-changes-to-microsoft-defender-antivirus-configurations"></a>Blockera obehöriga ändringar Microsoft Defender Antivirus konfigurationer

- **Gäller för**– alla processer
- **Processer**– *
- **Åtgärd**– registerändringar
- **Exempel på filer/mappar, registernycklar/värden, processer,** tjänster - HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\DisableAntiSpyware, HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\AllowRealTimeMonitoring och så vidare.
- **Regler för att minska attackytan**– ASR-regler täcker inte in dessa scenarier eftersom de är en del av Microsoft Defender för inbyggt skydd av Slutpunkt.
- Andra rekommenderade funktioner **–** Skydd mot manipulering (registrering, hanteras från Intune) förhindrar obehöriga ändringar av DisableAntiVirus, DisableAntiSpyware, DisableRealtimeMonitoring, DisableOnAccessProtection, DisableBehaviorMonitoring och DisableIOAVProtection-registernycklar (med mera).

Se även

- [Vanliga frågor och svar för minskning av attackytan](attack-surface-reduction-faq.yml)
- [Aktivera regler för minskning av attackytan](enable-attack-surface-reduction.md)
- [Utvärdera regler för minskning av attackytan](evaluate-attack-surface-reduction.md)
