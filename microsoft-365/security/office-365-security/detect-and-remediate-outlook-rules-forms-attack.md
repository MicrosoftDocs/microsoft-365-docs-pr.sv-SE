---
title: Identifiera och åtgärda Outlook-regler och attacker mot anpassade formulär.
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 04/23/2018
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Lär dig hur du känner igen och reparerar Outlook-regler och anpassade formulär injektioner i Office 365
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cbdc41315d64d341248d6900147aabc5a0b9877c
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663649"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a>Identifiera och åtgärda Outlook-regler och attacker mot anpassade formulär

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Sammanfattning** Lär dig hur du känner igen och reparerar Outlook-regler och anpassade formulär injektioner i Office 365.

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>Vad är Outlook-regler och inmatning av anpassade formulär?

När angriparen har brutit mot ett konto i ditt innehav och får i, kommer du att pröva ett sätt att hålla dig informerad eller ett sätt att gå tillbaka när de har upptäckts och tagits bort. Detta kallas för att etablera en beständig mekanism. Två sätt som de kan göra detta är genom att utnyttja Outlook-regler eller genom att infoga egna formulär i Outlook.
I båda fallen synkroniseras regeln eller formuläret från moln tjänsten ned till Skriv bords klienten, så en fullständig formatering och ominstallation av klient program varan eliminerar inte injektions mekanismen. Detta beror på att när klient program varan för Outlook återansluter till post lådan i molnet laddas reglerna och formulären igen från molnet igen. När reglerna och formulären är på plats använder angripare dem för att köra fjärr-eller anpassad kod, vanligt vis för att installera skadlig program vara på den lokala datorn. Den skadliga program varan sedan återstjälar dina uppgifter eller utför annan olaglig aktivitet.
Den goda nyheten är att om du håller klienterna uppdaterad till den senaste versionen är du inte utsatt för hotet eftersom aktuella standardinställningar för Outlook-klienter blockerar båda mekanismerna.

Angrepp följer normalt dessa mönster:

**Reglerna utnyttjar**:

1. Angriparen stjäl användar namn och lösen ord för en användare.

2. Angriparen loggar sedan in på den användare som har Exchange-postlådan. Post lådan kan antingen vara i Exchange Online eller lokalt.

3. Angriparen skapar sedan en vidarebefordrings regel i post lådan som utlöses när post lådan får ett e-postmeddelande som matchar regelns villkor. Reglerna för regler och innehållet i e-postmeddelandet är skräddarsydda – gjorda för varandra.

4. Angripare skickar utlösaren via e-post till den användare som använder sin post låda normalt.

5. När e-postmeddelandet tas emot utlöses regeln. Åtgärden för regeln är oftast att starta ett program på en fjärran sluten Server.

6. Programmet installerar vanligt vis skadlig program vara, till exempel [PowerShell Empire](https://www.powershellempire.com/), lokalt på användarens dator.

7. Den skadliga program varan gör det möjligt för angriparen att stjäla användarens användar namn och lösen ord eller andra autentiseringsuppgifter från den lokala datorn och utföra andra skadliga aktiviteter.

**Formulären**:

1. Angriparen stjäl användar namn och lösen ord för en användare.

2. Angriparen loggar sedan in på den andra Exchange-postlådan. Post lådan kan antingen vara i Exchange Online eller lokalt.

3. Angriparen skapar en anpassad formulärmall och infogar den i användarens post låda. Det anpassade formuläret utlöses när post lådan får ett e-postmeddelande som kräver att post lådan läser in det anpassade formuläret. Det anpassade formuläret och formatet för e-post är skräddarsydda-för varandra.
4. Angripare skickar e-postmeddelandet till användaren, som använder sin post låda normalt.

5. När e-postmeddelandet tas emot laddas formuläret. Formuläret öppnar ett program på en fjärran sluten Server.

6. Programmet installerar vanligt vis skadlig program vara, till exempel [PowerShell Empire](https://www.powershellempire.com/), lokalt på användarens dator.

7. Den skadliga program varan gör det möjligt för angriparen att stjäla användarens användar namn och lösen ord eller andra autentiseringsuppgifter från den lokala datorn och utföra andra skadliga aktiviteter.

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>Vad finns det för att använda Office 365?

Dessa beständiga mekanismer är osannolika för användarna och kan i vissa fall vara osynliga för dem. I den här artikeln beskrivs hur du söker efter ett av de sju tecknen (indikatorer för kompromiss) som visas nedan. Om du hittar något av dessa måste du genomföra reparations stegen.

- Indikatorer för reglerna:

  - Regel åtgärd är att starta ett program.

  - Regeln refererar till en EXE-, ZIP-eller URL-adress.

  - Leta efter ny process som kommer från Outlook PID på den lokala datorn.

- Indikatorer för kompromiss med anpassade former:

  - Anpassat formulär sparas som sin egen meddelande klass.

  - Meddelande klassen innehåller körbar kod.

  - Lagras vanligt vis i personliga formulär bibliotek eller Inkorgen.

  - Formuläret heter IPM. Fotnot. [eget namn].

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>Anvisningar för att hitta tecken på det här angreppet och bekräfta det

Du kan använda någon av de här två metoderna för att bekräfta angreppet:

- Kontrol lera regler och formulär manuellt för varje post låda med Outlook-klienten. Den här metoden är fullständig, men du kan bara kontrol lera användare av post lådor i en tid som kan vara mycket tidsödande om du har många användare att kontrol lera. Det kan även leda till intrång på den dator som du kör kontrollen från.

- Använd [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell-skriptet för att automatiskt dumpa alla regler för e-postvidarebefordran och anpassade formulär för alla användare i ditt innehav. Det här är den snabbaste och säkraste metoden med minsta möjliga omkostnader.

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>Bekräfta angrepps funktionen för regler med Outlook-klienten

1. Öppna användarens Outlook-klient som användare. Användaren kan behöva hjälp för att kontrol lera reglerna i post lådan.

2. Information om hur du öppnar regel gränssnittet i Outlook finns i [Hantera e-postmeddelanden med hjälp av regler](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) artikel.

3. Leta efter regler som användaren inte har skapat eller oväntade regler eller regler med misstänkta namn.

4. Titta i regel beskrivningen för regel åtgärder som startas och programmet eller som refererar till en. EXE,. ZIP-fil eller en URL-adress.

5. Leta efter nya processer som börjar använda process-ID för Outlook. Se [hitta process-ID](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id).

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Instruktioner för att bekräfta formulär angrepp med Outlook-klienten

1. Öppna användarens Outlook-klient som användare.

2. Följ stegen i och [Visa fliken Utvecklare](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) för användarens version av Outlook.

3. Öppna fliken Utvecklare i Outlook och klicka på **designa ett formulär**.

4. Välj **Inkorgen** i listan **Leta i** . Leta efter egna formulär. Anpassade formulär är sällsynta nog om du har anpassade formulär alls är det värt ett djupare utseende.

5. Undersök anpassade formulär, särskilt de som är markerade som dolda.

6. Öppna något anpassat formulär och **Klicka på** **Visa kod** för att se vad som körs när formuläret laddas.

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>Anvisningar för att bekräfta reglerna och Forms-attacken med PowerShell

Det enklaste sättet att kontrol lera regler och anpassade formulär är att köra PowerShell-skriptet [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) . Detta skript ansluter till alla post lådor i din klient organisation och dumpar alla regler och formulär till två CSV-filer.

#### <a name="pre-requisites"></a>Förutsättningar

Du måste ha en global administratör för att köra skriptet eftersom skriptet ansluter till alla post lådor i innehavaren för att läsa reglerna och formulären.

1. Logga in på den dator som du kör skriptet från med lokal administratörs behörighet.

2. Ladda ned eller kopiera Get-AllTenantRulesAndForms.ps1-skriptet från GitHub till en mapp som du vill köra det från. Skriptet skapar två textstämplade filer till den här mappen MailboxFormsExport-yyyy-mm-dd.csv och MailboxRulesExport-yyyy-mm-dd.csv.

3. Öppna en PowerShell-instans som administratör och öppna mappen där du sparade skriptet.

4. Kör den här PowerShell-kommandoraden enligt följande `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>Tolka utdata

- **MailboxRulesExport-*åååå-mm-dd*. csv**: granska reglerna (en per rad) för åtgärds villkor som inkluderar program eller körbara filer:

  - **ActionType (kolumn A)**: om du ser värdet "ID_ACTION_CUSTOM" är regeln troligen skadlig.

  - **IsPotentiallyMalicious (kolumn D)**: om det här värdet är "true" är regeln troligt vis skadlig.

  - **ActionCommand (kolumn G)**: om den här listan visar ett program eller en fil med ett. exe-,. zip-tillägg eller en post som refererar till en URL-adress som inte ska finnas där är regeln troligt vis skadlig.

- **MailboxFormsExport-*åååå-mm-dd*. csv**: i allmänhet är det väldigt sällsynt att använda anpassade formulär. Om du hittar något i den här arbets boken kan du öppna användarens post låda och granska själva formuläret. Om din organisation inte har placerat den där, är det troligt vis skadligt.

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>Så här stoppar och åtgärdar du Outlook-regler och formulär attacker

Om du hittar något tecken på någon av dessa attacker är det enkelt att vidta en åtgärd, ta bara bort regeln eller formuläret från post lådan. Du kan göra det med Outlook-klienten eller använda Remote PowerShell för att ta bort regler.

### <a name="using-outlook"></a>Använda Outlook

1. Identifiera alla enheter som användaren har använt med Outlook. De kommer att behöva rengöras med eventuell skadlig program vara. Tillåt inte att användaren loggar på och använder e-post förrän alla enheter har rengjorts.

2. Följ stegen i [ta bort en regel](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) för varje enhet.

3. Om du är osäker på närvaron av annan skadlig kod kan du formatera och ominstallera all program vara på enheten. För mobila enheter kan du följa de här stegen för att återställa enheten till fabriks bilden.

4. Installera den senaste versionen av Outlook. Kom ihåg att den aktuella versionen av Outlook blockerar båda typerna av det här angreppet.

5. När alla offlinekopior av post lådan har tagits bort återställer du användarens lösen ord (Använd en högkvalitativ bild) och följer anvisningarna i [Konfigurera multifaktorautentisering för användare](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) om MFA inte redan har Aktiver ATS. Detta garanterar att användarens autentiseringsuppgifter inte visas på annat sätt (till exempel nätfiske eller återanvändning av lösen ord).

### <a name="using-powershell"></a>Använda PowerShell

Det finns två PowerShell-cmdlets för fjärrklienter som du kan använda för att ta bort eller inaktivera farliga regler. Följ bara anvisningarna.

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>Anvisningar för post lådor som är på en Exchange-Server

1. Anslut till Exchange-servern via Remote PowerShell. Följ stegen i [ansluta till Exchange-servrar med fjärr-PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-servers-using-remote-powershell).

2. Om du vill ta bort en enskild regel, flera regler eller alla regler från en post låda använder du cmdleten [Remove-InboxRule](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) .

3. Om du vill behålla regeln och dess innehåll för ytterligare undersökningar använder du cmdleten [disable-InboxRule](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) .

#### <a name="steps-for-mailboxes-in-exchange-online"></a>Steg för post lådor i Exchange Online

1. Följ stegen i [ansluta till Exchange Online med PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

2. Om du vill ta bort en enskild regel helt och hållet, flera regler eller alla regler från en post låda använder du cmdleten [ta bort inkorg](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) .

3. Om du vill behålla regeln och dess innehåll för ytterligare undersökningar använder du cmdleten [disable-InboxRule](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) .

## <a name="how-to-minimize-future-attacks"></a>Minimera framtida attacker

### <a name="first-protect-your-accounts"></a>Först: skydda dina konton

Reglerna och formulär användningarna används bara av angripare efter att de har blivit stulna eller har brutit mot en av dina användar konton. Det första steget för att förhindra användningen av dessa utnyttjanden mot organisationen är att aggressivt skydda dina användar konton. Här är några av de vanligaste sätten som konton har brutit mot – attacker och [lösen ord](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/) .

Det bästa sättet att skydda dina användar konton och särskilt administratörs konton är att [Konfigurera multifaktorautentisering för användare](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication). Du bör också:

- Övervaka hur dina användar konton används [och används](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports). Du får inte förhindra den inledande överträdelsen, men du kommer att förkorta varaktigheten och effekten av överträdelsen genom att upptäcka det snart. Du kan använda dessa [Office 365-Cloud App-säkerhetsprinciper](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) för att övervaka konton och aviseringar om ovanliga aktiviteter:

  - **Flera misslyckade inloggnings försök**: den här policyn profilerar din miljö och utlöser aviseringar när användare utför flera misslyckade inloggnings aktiviteter i en session med avseende på den inlärda original planen, som kan tyda på ett försök till intrång

  - **Omöjlig resa**: den här policyn profilerar din miljö och utlöser aviseringar när aktiviteter upptäcks från samma användare på olika platser under en tids period som är kortare än den förväntade res tiden mellan de båda platserna. Det kan betyda att en annan användare använder samma autentiseringsuppgifter. Att upptäcka detta avvikande beteende kräver en inledande inlärnings period på sju dagar då den lär sig en ny användares aktivitets mönster.

  - **Ovanlig personifierad aktivitet (enligt användare)**: den här principen profilerar din miljö och utlöser aviseringar när användare utför flera personifierade aktiviteter i en enda session med avseende på den inlärda integriteten, vilket kan tyda på ett försök till intrång.

- Använd ett verktyg som [Office 365 Secure score](https://securescore.office.com/) för att hantera konto säkerhets konfigurationer och-funktioner.

### <a name="second-keep-your-outlook-clients-current"></a>S: Låt Outlook-klienterna vara aktuella

Fullständig uppdatering och uppdaterade versioner av Outlook 2013 och 2016 Inaktivera regel/formulär åtgärd för "starta program" som standard. Detta garanterar att även om angriparen bryter mot kontot blockeras reglerna och formulär åtgärderna. Du kan installera de senaste uppdateringarna och säkerhets korrigeringarna genom att följa stegen i [installera Office-uppdateringar](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5).

Här är de här korrigerings versionerna för dina Outlook 2013-och 2016-klienter:

- **Outlook 2016**: 16.0.4534.1001 eller senare.

- **Outlook 2013**: 15.0.4937.1000 eller senare.

Mer information om de enskilda säkerhets korrigeringarna finns i:

- [Säkerhets korrigering för Outlook 2016](https://support.microsoft.com/help/3191883)

- [Säkerhets korrigering för Outlook 2013](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>Tredje: övervaka dina Outlook-klienter

Observera att även med de korrigeringar och uppdateringar som är installerade är det möjligt för en angripare att ändra den lokala datorns konfiguration så att "starta program"-funktionen aktive ras igen. Du kan använda [Avancerad grup princip hantering](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) för att övervaka och verkställa lokala dator principer på dina klienter.

Du kan se om "starta program" har Aktiver ATS på nytt genom en åsidosättning i registret genom att använda informationen i [hur du visar system registret med hjälp av 64-bitars versioner av Windows](https://support.microsoft.com/help/305097). Kontrol lera följande nycklar:

- **Outlook 2016**: `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013**: `HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

Leta efter EnableUnsafeClientMailRules. Om den finns där och är inställd på 1 har säkerhets korrigeringen för Outlook åsidosatts och datorn är sårbar för angrepps formen för former/regler. Om värdet är 0 avaktiveras åtgärden "starta program". Om den uppdaterade och uppgraderade versionen av Outlook är installerad och den här register nyckel saknas är ett system inte känsligt för dessa attacker.

Kunder med lokala Exchange-installationer bör överväga att blockera äldre versioner av Outlook som inte har några korrigeringsfiler tillgängliga. Information om den här processen finns i artikeln [Konfigurera blockering av Outlook-klient](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help).

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Skydda Microsoft 365 som en expert på cybersäkerhet

Din Microsoft 365-prenumeration innehåller kraftfulla säkerhetsfunktioner som du kan använda för att skydda dina data och dina användare. Använd [Säkerhetsöversikt för Microsoft 365 – de vanligaste prioriteringarna för de första 30 dagarna, 90 dagarna och bortom](security-roadmap.md) för att implementera Microsofts metodtips för att skydda din Microsoft 365-klientorganisation.

- Uppgifter som ska utföras under de första 30 dagarna. De har omedelbar effekt och påverkar inte användarna i någon större utsträckning.

- Uppgifter som ska utföras inom 90 dagar. De tar lite längre tid att planera och implementera men förbättrar din säkerhet avsevärt.

- Efter 90 dagar. De här förbättringarna uppnås under de första 90 dagarna.

## <a name="see-also"></a>Se även:

- [Illasinnade Outlook-regler](https://silentbreaksecurity.com/malicious-outlook-rules/) av SilentBreak säkerhets inlägg om regel vektor ger en detaljerad recension av hur Outlook-reglerna.

- [MAPI över HTTP-och Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) på Sensepost-bloggen om regeln Pwnage diskuterar ett verktyg som heter linjal med vilken du kan utnyttja post lådor via Outlook-regler.

- [Outlook-formulär och-gränssnitt](https://sensepost.com/blog/2017/outlook-forms-and-shells/) på Sensepost blogg om formulärbaserada formulär.

- [Kodbas](https://github.com/sensepost/ruler)

- [Linjalens indikatorer](https://github.com/sensepost/notruler/blob/master/iocs.md)
