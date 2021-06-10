---
title: Application Guard för Office 365 för administratörer
keywords: application guard, protection, isolation, isolerad behållare, maskinvaruisolering
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Få den senaste versionen av maskinvarubaserad isolering. Förhindra aktuella och nya attacker som sårbarheter eller skadliga länkar från att störa personalens produktivitet och företagssäkerhet.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d0fa6ad884c6b21457c8359cf82e32e4b8c100ba
ms.sourcegitcommit: 7ebed5810480d7c49f8ca03207b5ea84993d253f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51488317"
---
# <a name="application-guard-for-office-for-admins"></a>Application Guard för Office för administratörer

**Gäller för:** Word, Excel och PowerPoint för Microsoft 365, Windows 10 Enterprise

Microsoft Defender Application Guard för Office (Application Guard för Office) förhindrar otillförlitliga filer från att komma åt betrodda resurser, vilket skyddar ditt företag från nya och nya attacker. I den här artikeln får administratörer hjälp med att konfigurera enheter för en förhandsgranskning av Application Guard för Office. Den tillhandahåller information om systemkrav och installationssteg för att aktivera Application Guard för Office på en enhet.

## <a name="prerequisites"></a>Förutsättningar

### <a name="minimum-hardware-requirements"></a>Minimikrav för maskinvara

* **CPU**: 64-bitars, 4 kärnor (fysiska eller virtuella), virtualiseringstillägg (Intel VT-x ELLER AMD-V), motsvarande Core i5 eller senare rekommenderas
* **Fysiskt** minne: 8 GB RAM-minne
* **Hårddisk:** 10 GB ledigt utrymme på systemenheten (SSD rekommenderas)

### <a name="minimum-software-requirements"></a>Lägsta programvarukrav

* **Windows 10**: Windows 10 Enterprise version, klientversion version 2004 (20H1) version 19041 eller senare
* **Office**: Office Aktuell kanal och Månatlig Enterprise-kanal, version 2011 16.0.13530.10000 eller senare. Både 32-bitars- och 64-bitarsversioner Office stöds.
* **Uppdateringspaket:** Windows 10 kumulativ månatlig säkerhetsuppdatering [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)

Detaljerade systemkrav finns i [Systemkrav för Microsoft Defender Application Guard](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard). Mer information om hur du aktiverar virtualiseringsteknik finns i datortillverkarens guider.
Mer information om hur Office kanaler finns i [Översikt över uppdateringskanaler för Microsoft 365.](/deployoffice/overview-update-channels)

### <a name="licensing-requirements"></a>Licensieringskrav

* Microsoft 365 E5 eller Microsoft 365 E5 Security

## <a name="deploy-application-guard-for-office"></a>Distribuera Application Guard för Office

### <a name="enable-application-guard-for-office"></a>Aktivera Application Guard för Office

1. Ladda ned och installera **Windows 10 kumulativa månatliga säkerhetsuppdateringar KB4571756.**

2. Välj **Microsoft Defender Application Guard** under Windows funktioner och välj **OK.** Om du aktiverar Application Guard-funktionen uppmanas du att starta om systemet. Du kan välja att starta om nu eller efter steg 3.

   ![Windows Dialogrutan Funktioner med AG](../../media/ag03-deploy.png)

   Funktionen kan också aktiveras genom att köra följande PowerShell-kommando som administratör:

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. Sök efter **Microsoft Defender Application Guard i hanterat läge**, en grupprincip i administrativa mallar för datorkonfiguration Windows komponenter **\\ \\ \\ Microsoft Defender Application Guard**. Aktivera den här principen genom att ange värdet under Alternativ **som 2** eller **3** och sedan välja **OK** eller **Använd**.

   ![Aktivera AG i hanterat läge](../../media/ag04-deploy.png)

   I stället kan du ange motsvarande princip för CSP:

   > OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Inställningar/AllowWindowsDefenderApplicationGuard** <br> Datatyp: **Heltal** <br> Värde: **2**

4. Starta om systemet.

### <a name="set-diagnostics--feedback-to-send-full-data"></a>Ställ in diagnostik & feedback för att skicka fullständiga data

> [!NOTE]
> Det här är dock inte obligatoriskt om du konfigurerar valfria diagnostikdata för att diagnostisera rapporterade problem.

Det här steget säkerställer att de data som behövs för att identifiera och åtgärda problem når Microsoft. Följ de här anvisningarna för att aktivera diagnostik på Windows enhet:

1. Öppna **Inställningar** från Start-menyn.

   ![Start-menyn](../../media/ag05-diagnostic.png)

2. På **Windows Inställningar** väljer du **Sekretess**.

   ![Windows Inställningar meny](../../media/ag06-diagnostic.png)

3. Under Sekretess väljer du **Diagnostik & feedback och** Valfri **diagnostikdata**.

   ![Menyn Diagnostik och feedback](../../media/ag07a-diagnostic.png)

Mer information om hur Windows för diagnostikinställningar finns i [Konfigurera Windows för diagnostikdata i din organisation.](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>Bekräfta att Application Guard för Office är aktiverat och fungerar

Innan du bekräftar att Application Guard för Office är aktiverat startar du Word, Excel eller PowerPoint på en enhet där principerna har distribuerats. Kontrollera Office är aktiverat. Du kan behöva använda din arbets-ID för att aktivera Office produkten först.

Bekräfta att Application Guard för Office är aktiverat genom att starta Word, Excel eller PowerPoint och sedan öppna ett dokument som inte är betrodd. Du kan till exempel öppna ett dokument som har laddats ned från Internet eller en e-postbilaga från någon utanför organisationen.

När du först öppnar en fil som inte är betrodd kan du se en Office välkomstskärm som följande exempel. Det kan visas under en tid medan Application Guard för Office aktiveras och filen öppnas. Senare öppningar av filer som inte är betrodda bör vara snabbare.

![Office-appen välkomstskärm](../../media/ag08-confirm.png)

När filen öppnas bör den visa några visuella indikatorer på att filen öppnades i Application Guard för Office:

* En bildtext i menyfliksområdet

  ![Doc-fil som visar liten App Guard-anteckning](../../media/ag09-confirm.png)

* Programikonen med en sköld i Aktivitetsfältet

  ![Ikon i Aktivitetsfältet](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a>Konfigurera Application Guard för Office

Office kan använda följande principer för att konfigurera funktionerna i Application Guard för Office. De här principerna kan konfigureras via grupprinciper eller Office [molnprinciptjänsten.](/DeployOffice/overview-office-cloud-policy-service)
Se konfiguration som angetts av administratören genom att granska grupprincipinställningarna i Administrativa mallar för användarkonfiguration **\\ Microsoft Office \\ 2016 \\ Säkerhetscenter Inställningar Application \\ \\ Guard**.


> [!NOTE]
> Om du konfigurerar de här principerna kan vissa funktioner inaktiveras för filer som öppnas i Application Guard för Office.

|Princip|Beskrivning|
|---|---|
|Använd inte Application Guard för Office|Aktivering av den här principen tvingar Word, Excel och PowerPoint att använda den skyddade vyisolering i stället för Application Guard för Office. Den här principen kan användas för att tillfälligt inaktivera Application Guard för Office när det finns problem med att lämna det aktiverat för Microsoft Edge.|
|Konfigurera Application Guard för Office för att skapa en behållare|Den här principen bestämmer om Application Guard för Office-behållare, för att isolera icke betrodda filer, är förskapad för förbättrad prestanda under körning. Om du aktiverar den här inställningen kan du ange hur många dagar det ska gå att fortsätta att skapa en behållare eller låta Office inbyggda heuristiska för att skapa behållaren.
|Tillåt inte kopiering/inklistring för Office dokument som öppnats i Application Guard för Office|Om du aktiverar den här principen förhindras användare från att kopiera och klistra in innehåll från ett dokument som öppnas i Application Guard för Office till ett dokument som öppnas utanför det.|
|Inaktivera maskinvaruacceleration i Application Guard för Office|Den här principen styr om Application Guard för Office använder maskinvaruacceleration för att återge grafik. Om du aktiverar den här inställningen använder Application Guard för Office programvarubaserad återgivning (CPU) och läser inte in några grafikdrivrutiner från tredje part eller interagerar med ansluten grafikmaskinvara.
|Inaktivera filtyper som inte stöds i Application Guard för Office|Den här principen styr om Application Guard för Office blockerar filtyper som inte stöds från att öppnas eller om det aktiverar omdirigeringen till Skyddad vy.
|Inaktivera åtkomst till kameran och mikrofonen för dokument som öppnas i Application Guard för Office|Om du aktiverar den här Office åtkomsten till kameran och mikrofonen i Application Guard för Office.|
|Begränsa utskrift från dokument som öppnas i Application Guard för Office|Aktivering av den här principen begränsar vilka skrivare som en användare kan skriva ut till från en fil som öppnas i Application Guard för Office. Du kan till exempel använda den här principen för att begränsa användare till att bara skriva ut till PDF.|
|Hindra användare från att ta bort Application Guard Office skydd för filer|Aktivering av den här principen tar bort alternativet (inom Office-programupplevelsen) för att inaktivera Application Guard för Office-skydd eller för att öppna en fil utanför Application Guard för Office. <p> **Obs!** Användare kan fortfarande kringgå den här principen genom att manuellt ta bort egenskapen Mark-of-the-web från filen eller genom att flytta ett dokument till en betrodd plats.|
|

> [!NOTE]
> Följande principer kräver att användaren loggar ut och loggar in igen för att Windows ska gälla:
>
> * Inaktivera kopiera/klistra in för dokument som öppnas i Application Guard för Office
> * Begränsa utskrift av dokument som öppnas i Application Guard för Office
> * Inaktivera kamera- och mikrofonåtkomst till dokument som öppnas i Application Guard för Office

## <a name="submit-feedback"></a>Skicka feedback

### <a name="submit-feedback-via-feedback-hub"></a>Skicka feedback via Feedbackhubben

Om du stöter på problem när du startar Application Guard för Office uppmanas du att skicka feedback via Feedbackhubben:

1. Öppna **appen Feedbackhubben** och logga in.

2. Om du får en dialogruta när du startar Application Guard väljer du Rapportera till **Microsoft** i feldialogrutan för att starta en ny feedback som skickas. Annars navigerar du <https://aka.ms/mdagoffice-fb> för att välja rätt kategori för Application Guard och väljer sedan Lägg till ny **+ &nbsp; feedback** uppe till höger.

3. Ange en sammanfattning i **rutan Summera din feedback** om den inte redan är ifylld åt dig.

4. Ange en detaljerad beskrivning av problemet du upplevt och vilka steg du gick i **rutan Förklara mer i** detalj och välj sedan **Nästa.**

5. Välj bubblan bredvid **Problem**. Kontrollera att den valda kategorin är **Säkerhet och Microsoft Defender Application Guard – \> Office** och välj sedan **Nästa.**

6. Välj **Ny feedback** och sedan **Nästa.**

7. Samla in spårningar om problemet:

   1. Expandera panelen **Återskapa** mitt problem.

   2. Om problemet du upplever uppstår medan Application Guard körs öppnar du en Application Guard-instans. Om du öppnar en instans kan ytterligare spårningar samlas in från Application Guard-behållaren.

   3. Välj **Starta inspelning** och vänta till panelen slutar snurra och säg Stoppa *inspelning*.

   4. Återskapa problemet med Application Guard helt. Reproducering kan inkludera försök att starta en Application Guard-instans och vänta tills den misslyckas eller återger ett problem i en Application Guard-instans som körs.

   5. Välj panelen **Stoppa** inspelning.

   6. Ha alla Application Guard-instanser öppna, även några minuter efter inskickat, så att behållardiagnostik också kan samlas in.

8. Bifoga alla relevanta skärmbilder eller filer som är relaterade till problemet.

9. Välj **Skicka**.

### <a name="submit-feedback-via-office-customer-voice"></a>Skicka feedback via Office Customer Voice

Du kan också skicka feedback Office om problemet inträffar Office dokument öppnas i Application Guard. Mer information finns [i Office Insider-handboken](https://insider.office.com/handbook) för att skicka feedback.

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a>Integrering med Microsoft Defender för Endpoint och Microsoft Defender för Office 365

Application Guard för Office är integrerad med Microsoft Defender för Endpoint för att tillhandahålla övervakning och avisering om skadlig aktivitet som sker i den isolerade miljön.

[Valv Documents i Microsoft E365 E5](/microsoft-365/security/office-365-security/safe-docs) är en funktion som använder Microsoft Defender för Endpoint för att söka igenom dokument som öppnas i Application Guard för Office. För ytterligare ett skyddslager kan användarna inte lämna Application Guard för Office förrän resultatet av genomsökningen har hittats.

Microsoft Defender för Endpoint är en säkerhetsplattform som utformats för att hjälpa företagsnätverk att förhindra, upptäcka, undersöka och hantera avancerade hot. Mer information om den här plattformen finns i [Microsoft Defender för Endpoint.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) Mer information om onboarding-enheter till den här plattformen finns i [Onboard-enheter i Microsoft Defender för Endpoint-tjänsten.](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)

Du kan också konfigurera Microsoft Defender för Office 365 att arbeta med Defender för Slutpunkt. Mer information finns i Artikeln om [att integrera Defender för Office 365 med Microsoft Defender för slutpunkt.](integrate-office-365-ti-with-mde.md)

## <a name="limitations-and-considerations"></a>Begränsningar och överväganden

* Application Guard för Office är ett skyddat läge som isolerar dokument som inte är betrodda så att de inte kan komma åt betrodda företagsresurser, ett intranät, användarens identitet och godtyckliga filer på datorn. Om en användare försöker komma åt en funktion som är beroende av sådan åtkomst, till exempel att en bild från en lokal fil infogas på disken, misslyckas åtkomsten och visar en uppmaning som följande exempel. Om du vill aktivera ett dokument som inte är betrott för åtkomst till betrodda resurser måste användare ta bort Application Guard-skyddet från dokumentet.

  ![Dialogruta som säger att funktionen inte är tillgänglig för att hjälpa dig att hålla dig säker](../../media/ag10-limitations.png)

  > [!NOTE]
  > Informera användarna att endast ta bort skydd om de litar på filen och dess källa eller var den kommer från.

* Aktivt innehåll i dokument som makron och ActiveX inaktiveras i Application Guard för Office. Användare behöver ta bort Application Guard-skydd för att aktivera aktivt innehåll.

* Filer som inte är betrodda från nätverksresurser eller filer som delas från OneDrive, OneDrive för företag eller SharePoint Online från en annan organisation öppnas som skrivskyddade i Application Guard. Användare kan spara en lokal kopia av sådana filer för att fortsätta arbeta i behållaren eller ta bort skydd för att direkt arbeta med den ursprungliga filen.

* Filer som skyddas av IRM (Information Rights Management) är blockerade som standard. Om användarna vill öppna sådana filer i Skyddad vy måste en administratör konfigurera principinställningar för filtyper som inte stöds för organisationen.

* Eventuella anpassningar av Office-program i Application Guard för Office kommer inte att finnas kvar när en användare loggar ut och loggar in igen eller när enheten startar om.

* Endast hjälpmedelsverktyg som använder UIA-ramverket kan ge en tillgänglig upplevelse för filer som öppnas i Application Guard för Office.

* Nätverksanslutning krävs för första lanseringen av Application Guard efter installationen. Anslutning krävs för att Application Guard ska kunna validera licensen.

* I dokumentets informationsavsnitt kan egenskapen *Senast ändrad av* visa **WDAGUtilityAccount** som användare. WDAGUtilityAccount är den anonyma användare som konfigurerats i Application Guard. Skrivbordsanvändarens identitet delas inte i Application Guard-behållaren.

## <a name="performance-optimizations-for-application-guard-for-office"></a>Prestandaoptimeringar för Application Guard för Office

Det här avsnittet innehåller en översikt över de prestandaoptimeringar som används i Application Guard för Office. Den här informationen kan hjälpa administratörer att diagnostisera rapporter från användare som är relaterade till prestanda i Office eller det övergripande systemet när Application Guard är aktiverat.

Application Guard använder en virtualiserad behållare för att isolera dokument som inte är betrodda från systemet. Processen att skapa en behållare och konfigurera Application Guard-behållaren för att öppna Office-dokument har en prestanda overhead som kan påverka användarupplevelsen negativt när användare öppnar ett dokument som inte är betrodd.

För att ge användarna den förväntade filöppnande upplevelsen använder Application Guard logik för att för skapa en behållare när följande heuristisk uppfylls på ett system: En användare har öppnat en fil i antingen Skyddad vy eller Application Guard under de senaste 28 dagarna.

När den här heuristisk uppfylls skapar Office en Application Guard-behållare för användaren när de har loggat in på Windows. Medan den här för skapat-åtgärden pågår kan prestandan vara långsam i systemet, men effekten löses så snart åtgärden har slutförts.

> [!NOTE]
> De tips som behövs för att göra det möjligt att skapa behållaren i förväg Office när en användare använder dem. Om en användare installerar Office på ett nytt system där Application Guard är aktiverat skapar Office inte behållaren förrän efter första gången en användare öppnar ett dokument som inte är betrodd i systemet. Användaren ser att den här första filen tar längre tid att öppna i Application Guard.

## <a name="known-issues"></a>Kända problem

* Om du väljer `http` `https` webblänkar ( eller ) öppnas inte webbläsaren.
* Att klistra in RTF-innehåll eller -bilder i Office dokument som öppnats med Application Guard stöds inte för närvarande.
* Standardinställningen för skyddsprincipen för filtyper som inte stöds är att blockera öppning av filtyper som inte stöds av IRM (Information Rights Management), CSV eller HTML som inte stöds.
* Uppdateringar av .NET kan orsaka att filer inte öppnas i Application Guard. Som en lösning kan användare starta om enheten när de får det här felet. Läs mer om problemet under Ta [emot ett felmeddelande när du försöker öppna ett begränsat Windows Defender Application Guard eller Windows begränsat läge.](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)
