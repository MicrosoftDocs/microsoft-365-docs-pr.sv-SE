---
title: Application Guard för Office 365 (offentlig för hands version) för administratörer
keywords: Application Guard, skydd, isolering, isolerad behållare, maskin varu isolering
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Få det senaste inom maskinvarubaserad isolering. Förhindra nuvarande och framväxande attacker som att utnyttja och sabotera inte fungerar för att störa företagets produktivitet och företags säkerhet.
ms.openlocfilehash: a1d0fb857a80d5500036f6d9a95f930ec4df38a0
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616794"
---
# <a name="application-guard-for-office-public-preview-for-admins"></a>Application Guard för Office (offentlig för hands version) för administratörer

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Gäller för:** Word, Excel och PowerPoint för Microsoft 365, Windows 10 Enterprise

> [!IMPORTANT]
> Vissa uppgifter gäller för en för hands version som kan ändras väsentligt innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.

Microsoft Defender Application Guard för Office (Application Guard för Office) hindrar icke betrodda filer från att komma åt betrodda resurser, så att ditt företag är säkert mot nya och framväxande attacker. I den här artikeln får administratörer hjälp med att konfigurera enheter för förhands granskning av Application Guard för Office. Den innehåller information om system krav och installations anvisningar för att aktivera Application Guard för Office på en enhet.

## <a name="prerequisites"></a>Förutsättningar

### <a name="minimum-hardware-requirements"></a>Minsta maskin varu krav

* **CPU**: 64-bitar, 4 kärnor (fysiskt eller virtuellt), virtualiseringslösningar (Intel VT-x eller AMD-V), bas i5 motsvarande eller högre rekommenderas
* **Fysiskt minne**: 8 GB RAM-minne
* **Hård disk**: 10 GB ledigt utrymme på system enheten (SSD rekommenderas)

### <a name="minimum-software-requirements"></a>Minsta program varu krav

* **Windows 10**: Windows 10 Enterprise Edition, Client version 2004 (20H1) build 19041
* **Office**: Office beta Channel version 2008 16.0.13212 eller senare
* **Uppdaterings paket**: Windows 10 kumulativa [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756) säkerhets uppdateringar

Detaljerade system krav finns i [system krav för Microsoft Defender Application Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard). Mer information om för hands versionen av Office Insider finns i [komma igång med distribution av Office Insider-versioner](https://insider.office.com/business/deploy).

### <a name="licensing-requirements"></a>Licens krav

* Microsoft 365 E5 eller Microsoft 365 E5 Security

## <a name="deploy-application-guard-for-office"></a>Distribuera Application Guard för Office

### <a name="enable-application-guard-for-office"></a>Aktivera Application Guard för Office

1. Ladda ned och installera **Windows 10 kumulativa KB4571756 för säkerhets uppdateringar**.

2. Välj **Microsoft Defender Application Guard** under Windows-funktioner och välj **OK**. Om du aktiverar funktionen Application Guard ombeds du att starta om datorn. Du kan välja att starta om nu eller efter steg 3.

   ![Dialog rutan Windows-funktioner med AG](../../media/ag03-deploy.png)

   Du kan också aktivera funktionen genom att köra följande PowerShell-kommando som administratör:

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. Leta efter Microsoft Defender Application Guard i grup principen hanterat läge på **dator konfiguration \\ administrativa mallar \\ Windows-komponenter \\ Microsoft Defender Application Guard**. Aktivera den här principen genom att ange värdet under alternativ som **2** eller **3** och sedan klicka på **OK** eller **Använd**.

   ![Aktivera AG i hanterat läge](../../media/ag04-deploy.png)

   Alternativt kan du ange motsvarande KRYPTOGRAFIPROVIDER-princip:

   > OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** <br> Datatyp: **Integer** <br> Värde: **2**

4. Starta om systemet.

### <a name="set-diagnostics--feedback-to-send-full-data"></a>Ställa in diagnostik & feedback för att skicka fullständiga data

Det här steget ser till att de uppgifter som behövs för att identifiera och åtgärda problem når Microsoft. Följ de här anvisningarna för att aktivera diagnostik på din Windows-enhet:

1. Öppna **Inställningar** från Start-menyn.

   ![Start-menyn](../../media/ag05-diagnostic.png)

2. I **Windows-inställningar** väljer du **Sekretess**.

   ![Windows-menyn Inställningar](../../media/ag06-diagnostic.png)

3. Under sekretess väljer du **diagnostik & feedback** och väljer **valfria diagnostikdata**.

   ![Diagnostik-och feedback-menyn](../../media/ag07a-diagnostic.png)

Mer information om hur du konfigurerar inställningar för Windows-diagnostik finns i [Konfigurera diagnostikdata för Windows i organisationen](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>Kontrol lera att Application Guard för Office är aktiverat och fungerar

Innan du bekräftar att Application Guard för Office är aktiverat startar du Word, Excel eller PowerPoint på en enhet där principerna har distribuerats. Kontrol lera att Office är aktiverat. Du kan behöva använda arbets identiteten för att aktivera Office-produkten först.

Bekräfta att Application Guard för Office nu är aktiverat genom att starta Word, Excel eller PowerPoint och öppna ett icke-betrott dokument. Du kan till exempel öppna ett dokument som hämtats från Internet eller en e-postbilaga från någon utanför organisationen.

Vid den första starten av en fil som inte är betrodd visas välkomst skärmen för Office som den nedan. Det kan visas för lite tid medan Application Guard för Office aktive ras och filen öppnas. Kommande lanseringar av ej betrodda filer bör bli snabbare.

![Välkomst skärm för Office-program](../../media/ag08-confirm.png)

När filen öppnas visas en del indikatorer som filen har öppnats i Application Guard för Office:

* En bildtext i menyfliksområdet

  ![Dokument fil med en liten app Guard-anteckning](../../media/ag09-confirm.png)

* Program ikonen med en sköld i aktivitets fältet

  ![Ikon i aktivitets fältet](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a>Konfigurera Application Guard för Office

Office har stöd för följande principer som gör att du kan konfigurera funktionerna i Application Guard för Office. Dessa principer kan konfigureras via grup principer eller via moln princip tjänsten för Office.

> [!NOTE]
> Dessa principer blir snart tillgängliga.
> Om du konfigurerar dessa principer kan vissa funktioner för filer som öppnas i Application Guard för Office inte aktive ras.

|Autentiseringsprincip|Beskrivning|
|---|---|
|Inaktivera Application Guard för Office|Om du aktiverar den här principen kan Word, Excel och PowerPoint användas för att använda isolerings behållaren skyddad vy i stället för application Guard för Office. Med den här policyn kan du tillfälligt inaktivera Application Guard för Office när det finns problem med att lämna det aktiverat för Edge.|
|Inaktivera kopiera/klistra in för dokument som öppnats i Application Guard|Om du aktiverar den här principen hindras en användare från att kopiera och klistra in innehåll från ett dokument som öppnats i Application Guard för Office till ett dokument som öppnats utanför det.|
|Förhindra att användare tar bort Application Guard-skyddet för filer|Om du aktiverar den här principen tas alternativet bort (i Office-programupplevelsen) för att inaktivera Application Guard-skydd eller öppna en fil utanför Application Guard. <p> **Obs!** Användare kan fortfarande kringgå den här principen genom att manuellt ta bort egenskapen för märkning från filen eller genom att flytta ett dokument till en betrodd plats.|
|Begränsa utskrift från dokument som öppnats i Application Guard|Om du aktiverar den här principen begränsas skrivare som en användare kan skriva ut till från en fil som öppnats i Application Guard för Office. Du kan till exempel använda den här principen för att begränsa användare till endast Skriv ut till PDF.|
|Stänga av kamera-och mikrofon åtkomst för dokument som öppnats i Application Guard|Om du aktiverar den här principen tas Office-åtkomst till kamera och mikrofon i Application Guard för Office bort.|
|

> [!NOTE]
> Följande principer kräver att användaren loggar ut och sedan loggar in igen för att Windows ska fungera:
>
> * Inaktivera kopiera/klistra in för dokument som öppnats i Application Guard
> * Begränsa utskrift för dokument som öppnats i Application Guard
> * Stänga av kamera-och mikrofon åtkomst till dokument som öppnats i Application Guard

## <a name="submit-feedback"></a>Skicka feedback

### <a name="submit-feedback-via-feedback-hub"></a>Skicka feedback via feedback Hub

Om du stöter på problem när du startar Application Guard för Office uppmanas du att skicka in dina synpunkter via feedback Hub:

1. Öppna **appen feedback Hub** och logga in.

2. Om du får en dialog ruta när du startar Application Guard väljer du **rapportera till Microsoft** i fel dialog rutan för att starta en ny feedback-överföring. I annat fall navigerar du till <https://aka.ms/wdagoffice-fb> för att välja rätt kategori för application Guard och väljer sedan **+ Lägg till ny feedback** nära det övre högra hörnet.

3. Fyll i rutan **sammanfatta din feedback** om den inte redan är ifylld.

4. Fyll i rutan **förklara i mer information** med en detaljerad beskrivning av det problem du fick och vilka steg du vidtog och välj sedan **Nästa**.

5. Välj bubblan bredvid problemet. Kontrol lera att den valda kategorin är **säkerhet och sekretess \> Microsoft Defender Application Guard – Office** och välj sedan **Nästa**.

6. Välj **ny feedback** och sedan **Nästa**.

7. Samla in spår om problemet:

   1. Expandera rutan **återskapa mitt problem** .

   2. Om problemet du upplever inträffar när Application Guard körs öppnar du en Application Guard-instans. Om du gör det kan fler spårningar samlas in från Application Guard-behållaren.

   3. Välj **Starta inspelning** och vänta tills panelen stannar och säg sedan *stoppa inspelningen*.

   4. Helt återskapa problemet med Application Guard. Det kan inkludera att ett försök görs att starta en Application Guard-instans och vänta tills den inte fungerar, eller att det uppstår ett problem i en kör Application Guard-instans.

   5. Välj panelen **stoppa inspelning** .

   6. Behåll alla öppna Application Guard-instanser, till och med ett par minuter efter att du har skickat in, så att behållar diagnostik också kan samlas in.

8. Bifoga relevanta skärm bilder eller filer för problemet.

9. Välj **Skicka**.

### <a name="submit-feedback-via-office-customer-voice"></a>Skicka feedback via Office Customer Voice

Du kan också skicka feedback från Office om problemet inträffar när Office-dokument öppnas i Application Guard. Se [Office Insider-handboken](https://insider.office.com/handbook) för att skicka feedback.

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a>Integrering med Microsoft Defender för slut punkt och Microsoft Defender för Office 365

Application Guard för Office är integrerat med Microsoft Defender för slut punkt för att tillhandahålla övervakning och avisering vid skadlig aktivitet i den isolerade miljön.

Microsoft Defender för slut punkten är en säkerhets plattform som utformats för att hjälpa företags nätverk att förhindra, upptäcka, undersöka och reagera på avancerade hot. Mer information om den här plattformen finns på sidan [Microsoft Defender för slut punkt](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) . Läs mer om inbyggda enheter till den här plattformen på [inbyggda enheter till Microsoft Defender för slut punkts tjänsten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).

Du kan också konfigurera Microsoft Defender för Office 365 så att det fungerar med Defender för slut punkten. Se [integrera Defender för Office 365 med Microsoft Defender för slut punkt](integrate-office-365-ti-with-wdatp.md).

## <a name="limitations-and-considerations"></a>Begränsningar och överväganden

* Application Guard för Office är ett begränsat läge som isolerar icke betrodda dokument från åtkomst till betrodda företags resurser, intranät, användarens identitet och alla filer som finns på datorn. Om en användare försöker få till gång till en funktion som har ett samband med en sådan åtkomst, till exempel att infoga en bild från en lokal fil på disken, kommer den att Miss lyckas och skapa en ledtext som den nedan. Om du vill aktivera ett icke-betrott dokument för åtkomst till betrodda resurser måste användarna ta bort Application Guard-skydd från dokumentet.

  ![Dialog rutan som hjälper dig att skydda är den här funktionen inte tillgänglig](../../media/ag10-limitations.png)

  > [!NOTE]
  > Meddela användarna att de bara ska ta bort skydd om de litar på filen och dess källa eller var den kom ifrån.

* Aktivt innehåll i dokument som makron och ActiveX-kontroller är inaktiverade i Application Guard för Office. Användare måste ta bort Application Guard-skyddet för att aktivera aktivt innehåll.

* Icke betrodda filer som öppnats från nätverks resurser eller filer som delas från OneDrive, OneDrive för företag eller SharePoint Online från en annan organisation öppnas som skrivskyddade i Application Guard. Användare kan spara en lokal kopia av sådana filer för att fortsätta arbeta i behållaren eller ta bort skyddet för att arbeta direkt med den ursprungliga filen.

* Filer som skyddas med IRM (Information Rights Management) fortsätter att öppnas i skyddad vy.

* Eventuella anpassningar av Office-program i Application Guard för Office sparas inte när användaren loggar ut och loggar in eller startar om enheten.

* Endast hjälpmedel som använder UIA-ramverket kan erbjuda en lättillgänglig upplevelse för filer som öppnats i Application Guard för Office.

* Nätverks anslutning krävs för den första starten av Application Guard efter installationen. Det här krävs för att Application Guard ska verifiera licensen.

* I dokumentets informations avsnitt kan egenskapen *senast ändrad av* Visa WDAGUtilityAccount som användare. Det här är den anonyma användare som är konfigurerad i Application Guard med angiven att Skriv bords användarens identitet inte är delad inuti Application Guard-behållaren.

## <a name="performance-optimizations-for-application-guard"></a>Prestanda optimeringar för application Guard

Det här avsnittet innehåller en översikt över prestanda optimeringar som används i Application Guard för Office. Med hjälp av den här informationen kan administratörer diagnostisera rapporter från användare relaterade till Office-prestationer eller det övergripande systemet när Application Guard är aktiverat.

Application Guard använder en virtualiserad behållare för att isolera icke betrodda dokument från systemet. Processen med att skapa en behållare och ställa in Application Guard-behållaren för att öppna Office-dokument har en prestanda som kan påverka användarens upplevelse negativt när användare öppnar ett icke-betrott dokument.

För att användarna ska kunna använda den förväntade fil öppnings upplevelsen använder Application Guard logik för att skapa en container innan följande heuristik uppfylls på ett system: en användare har öppnat en fil i antingen skyddad vy eller program miljö under de senaste 28 dagarna.

När den här heuristiskheten är uppfylld kommer Office att skapa en program skydds behållare för användaren när de loggar in i Windows. När den här för skapande åtgärden pågår kan systemet få långsam prestanda. Detta löses så snart åtgärden har slutförts.

> [!NOTE]
> Tipsen som behövs för den heuristik som används för att skapa en container genereras av Office-program som en användare använder dem. Om en användare installerar Office på ett nytt system där Application Guard är aktive rad kommer Office inte att skapa en ny container förrän första gången en användare öppnar ett icke-betrott dokument på systemet. Användaren kommer att Observera att den här första filen tar längre tid att öppna i Application Guard.

## <a name="known-issues-in-preview"></a>Kända problem i förhands granskning

* `http`Du kan inte öppna webbläsaren genom att klicka på webb länkar (eller `https` ).
* .NET-uppdateringar gör att det inte går att öppna filer i Application Guard. Som en lösning kan användare starta om enheten när det här problemet uppstår. Läs mer om problemet med [att få ett fel meddelande när du försöker öppna Windows Defender Application Guard eller Windows sandbox](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).
