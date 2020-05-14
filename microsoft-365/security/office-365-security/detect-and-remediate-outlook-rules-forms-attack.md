---
title: Identifiera och åtgärda Outlook-regler och anpassade formulär injektioner attacker.
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
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
description: Lär dig hur du känner igen och åtgärdar Outlook-regler och anpassade formulärinjektioner i Office 365
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e18635b9b9d090dbc2808b5b8142b59ec1f29c6e
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224595"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a>Identifiera och åtgärda Outlook-regler och anpassade formulär injections attacker

**Sammanfattning** Lär dig hur du känner igen och åtgärdar Outlook-regler och anpassade formulärinjektioner i Office 365.

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>Vad är outlook-reglerna och injektionsattacken för anpassade formulär?

När en angripare har brutit mot ett konto i din hyresrätt och kommer in, det kommer att försöka etablera ett sätt att stanna i eller ett sätt att komma tillbaka in efter att de upptäcks och tas bort. Detta kallas att inrätta en persistensmekanism. Två sätt att göra detta är att utnyttja Outlook-regler eller genom att injicera anpassade formulär i Outlook.
I båda fallen synkroniseras regeln eller formuläret från molntjänsten ner till skrivbordsklienten, så ett fullständigt format och ominstallation av klientprogramvaran eliminerar inte insprutningsmekanismen. Detta beror på att när Outlook-klientprogramvaran återansluter till postlådan i molnet kommer det att åter hämta regler och formulär från molnet. När reglerna och formulären är på plats använder angriparen dem för att köra fjärr- eller anpassad kod, vanligtvis för att installera skadlig kod på den lokala datorn. Den skadliga koden stjäl sedan referenser eller utför annan olaglig aktivitet.
Den goda nyheten här är att om du håller dina kunder lappat till den senaste versionen, är du inte sårbar för hotet som nuvarande Outlook-klientstandarder blockera båda mekanismerna.

Attackerna följer vanligtvis dessa mönster:

**Reglerna Utnyttja:**

1. Angriparen stjäl användarnamn och lösenord för en av dina användare.

2. Angriparen loggar sedan in på den användare Exchange-postlådan. Postlådan kan antingen vara i Exchange online eller i Exchange lokalt.

3. Angriparen skapar sedan en vidarebefordringsregel i postlådan som utlöses när postlådan tar emot ett e-postmeddelande som matchar regelvillkoren. Regelkriterierna och innehållet i utlösningsmeddelandet är skräddarsydda för varandra.

4. Angriparen skickar utlösarmeddelandet till den användare som använder sin postlåda normalt.

5. När e-postmeddelandet tas emot utlöses regeln. Regelns åtgärd är vanligtvis att starta ett program på en fjärrserver (WebDAV).

6. Programmet installerar vanligtvis skadlig kod, till exempel [Powershell Empire](https://www.powershellempire.com/), lokalt på användarens dator.

7. Den skadliga koden gör det möjligt för angriparen att åter stjäla användarens användarnamn och lösenord eller andra autentiseringsuppgifter från den lokala datorn och utföra andra skadliga aktiviteter.

**Formulären Exploit:**

1. Angriparen stjäl användarnamn och lösenord för en av dina användare.

2. Angriparen loggar sedan in på den användare Exchange-postlådan. Postlådan kan antingen vara i Exchange online eller i Exchange lokalt.

3. Angriparen skapar sedan en anpassad mall för e-postformulär och infogar den i användarens postlåda. Det anpassade formuläret utlöses när postlådan tar emot ett e-postmeddelande som kräver att postlådan läser in det anpassade formuläret. Det anpassade formuläret och formatet på e-post är skräddarsydda för varandra.
4. Angriparen skickar utlösarmeddelandet till användaren, som använder sin postlåda normalt.

5. När e-postmeddelandet tas emot läses formuläret in. Formuläret startar ett program på en fjärrserver (WebDAV).

6. Programmet installerar vanligtvis skadlig kod, till exempel [Powershell Empire](https://www.powershellempire.com/), lokalt på användarens dator.

7. Den skadliga koden gör det möjligt för angriparen att åter stjäla användarens användarnamn och lösenord eller andra autentiseringsuppgifter från den lokala datorn och utföra andra skadliga aktiviteter.

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>Vilken attack av injektionsregler och anpassade formulär kan se ut som Office 365?

Dessa persistensmekanismer är osannolikt att märkas av dina användare och kan i vissa fall även vara osynlig för dem. I den här artikeln beskrivs hur du letar efter något av de sju tecknen (Indikatorer på kompromisser) som anges nedan. Om du hittar något av detta måste du vidta åtgärder för att åtgärda.

- Indikatorer för kompromissen i arbetsordningen:

  - Regelåtgärd är att starta ett program.

  - Regelreferensen refererar till ett EXE, ZIP eller EN URL.

  - På den lokala datorn letar du efter nya processstarter som kommer från Outlook PID.

- Indikatorer för de anpassade formulären kompromiss:

  - Anpassad formulärpresent sparad som sin egen meddelandeklass.

  - Meddelandeklass innehåller körbar kod.

  - Lagras vanligtvis i mappar för personliga formulärbibliotek eller inkorgar.

  - Formuläret heter IPM. Observera. [eget namn].

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>Åtgärder för att hitta tecken på denna attack och bekräfta den

Du kan använda någon av dessa två metoder för att bekräfta attacken:

- Undersök regelerna och formulären manuellt för varje postlåda med Outlook-klienten. Denna metod är grundlig, men du kan bara kontrollera brevlådan användare vid en tidpunkt som kan vara mycket tidskrävande om du har många användare att kontrollera. Det kan också resultera i ett brott mot datorn som du kör checken från.

- Använd [PowerShell-skriptet Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) för att automatiskt dumpa alla regler för vidarebefordring av e-post och anpassade formulär för alla användare i din hyresrätt. Detta är den snabbaste och säkraste metoden med minst mängd omkostnader.

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>Bekräfta regelattacken med Outlook-klienten

1. Öppna användarens Outlook-klient som användare. Användaren kan behöva din hjälp med att undersöka reglerna på sin postlåda.

2. Se [Hantera e-postmeddelanden med hjälp av regelartikeln](https://support.office.com/article/c24f5dea-9465-4df4-ad17-a50704d66c59) för procedurer om hur du öppnar regelgränssnittet i Outlook.

3. Leta efter regler som användaren inte har skapat, eller oväntade regler eller regler med misstänkta namn.

4. Titta i regelbeskrivningen efter regelåtgärder som startar och program eller refererar till en . Exe. ZIP-filen eller för att starta en URL.

5. Leta efter nya processer som börjar använda Outlook-process-ID. Se [Hitta process-ID](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id).

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Åtgärder för att bekräfta forms-attacken med Outlook-klienten

1. Öppna användarens Outlook-klient som användare.

2. Följ stegen i Visa [fliken Utvecklare](https://support.office.com/article/e1192344-5e56-4d45-931b-e5fd9bea2d45) för användarversionen av Outlook.

3. Öppna den nu synliga utvecklarfliken i Outlook och klicka på **designa ett formulär**.

4. Välj **inkorgen i** listan **Leta efter.** Leta efter anpassade formulär. Anpassade former är sällsynta nog att om du har några anpassade formulär alls, är det värt en djupare titt.

5. Undersök alla anpassade formulär, särskilt de som markerats som dolda.

6. Öppna alla anpassade formulär och klicka på **Visa kod** i gruppen **Formulär** för att se vad som körs när formuläret läses in.

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>Åtgärder för att bekräfta regel- och formulärattacken med PowerShell

Det enklaste sättet att verifiera en regel eller anpassade formulär attack är att köra [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell skriptet. Skriptet ansluter till alla postlådor i din klientorganisation och dumpar alla regler och formulär i två CSV-filer.

#### <a name="pre-requisites"></a>Förutsättningar

Du måste ha en global administratörsberättigad för att köra skriptet eftersom skriptet ansluter till alla postlådor i hyresrätten för att läsa regler och formulär.

1. Logga in på datorn som du ska köra skriptet från med lokala administratörsrättigheter.

2. Ladda ned eller kopiera Get-AllTenantRulesAndForms.ps1-skriptet från GitHub till en mapp som du ska köra det från. Skriptet kommer att skapa två datum stämplade filer till den här mappen, MailboxFormsExport-yyyy-mm-dd.csv och MailboxRulesExport-yyyy-mm-dd.csv.

3. Öppna en PowerShell-instans som administratör och öppna mappen som du sparade skriptet till.

4. Kör den här PowerShell-kommandoraden enligt följande `.\Get-AllTenantRulesAndForms.ps1` .\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>Tolka utdata

- **MailboxRulesExport-*yyyy-mm-dd*.csv**: Undersök reglerna (en per rad) för åtgärdsvillkor som innehåller program eller körbara filer:

  - **ActionType (kolumn A)**: Om du ser värdet "ID_ACTION_CUSTOM" är regeln troligen skadlig.

  - **IsPotentiallyMalicious (kolumn D)**: Om det här värdet är "SANT" är regeln troligen skadlig.

  - **ActionCommand (kolumn G):** Om detta visar ett program eller en fil med en .exe, .zip-tillägg eller en post som refererar till en URL, som inte ska finnas där, är regeln troligen skadlig.

- **MailboxFormsExport-*yyyy-mm-dd*.csv**: I allmänhet är användningen av anpassade formulär mycket sällsynt. Om du hittar några i den här arbetsboken öppnar du användarens postlåda och undersöker själva formuläret. Om din organisation inte har placerat den där avsiktligt, är det sannolikt skadligt.

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>Så här stoppar och åtgärdar du outlook-regel- och formulärattacken

Om du hittar några bevis för något av dessa attacker är reparation enkel, ta bara bort regeln eller formuläret från postlådan. Du kan göra detta med Outlook-klienten eller använda fjärr-PowerShell för att ta bort regler.

### <a name="using-outlook"></a>Använda Outlook

1. Identifiera alla enheter som användaren har använt med Outlook. De kommer alla att behöva rengöras från potentiella skadliga program. Låt inte användaren logga in och använda e-post förrän alla enheter har rengjorts.

2. Följ stegen i [Ta bort en regel](https://support.microsoft.com/en-us/office/delete-a-rule-2f0e7139-f696-4422-8498-44846db9067f) för varje enhet.

3. Om du är osäker på om det finns annan skadlig kod kan du formatera och installera om all programvara på enheten. För mobila enheter kan du följa tillverkarens steg för att återställa enheten till fabriksavbildningen.

4. Installera de senaste versionerna av Outlook. Kom ihåg att den aktuella versionen av Outlook blockerar båda typerna av den här attacken som standard.

5. När alla offlinekopior av postlådan har tagits bort återställer du användarens lösenord (använd ett lösenord av hög kvalitet) och följer stegen i [installationsprogrammets multifaktorautentisering för användare](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) om MFA inte redan har aktiverats. Detta säkerställer att användarens autentiseringsuppgifter inte exponeras på annat sätt (t.ex. nätfiske eller återanvändning av lösenord).

### <a name="using-powershell"></a>Använda PowerShell

Det finns två PowerShell-fjärr-PowerShell-cmdlets som du kan använda för att ta bort eller inaktivera farliga regler. Följ bara stegen.

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>Steg för postlådor som finns på en Exchange-server

1. Anslut till Exchange-servern med fjärr-PowerShell. Följ stegen i [Connect to Exchange-servrar med fjärr-PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

2. Om du vill ta bort en enda regel, flera regler eller alla regler från en postlåda använder du cmdleten [Ta bort inkorgen.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule)

3. Om du vill behålla regeln och dess innehåll för vidare undersökning använder du cmdleten [Inaktivera inkorgRegel.](https:https://docs.microsoft.com/powershell/module/exchange/mailboxes/disable-inboxrule/library/dd298120(v=exchg.160).aspx)

#### <a name="steps-for-mailboxes-in-exchange-online"></a>Steg för postlådor i Exchange Online

1. Följ stegen i [Anslut till Exchange Online med PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Om du vill ta bort en enda regel, flera regler eller alla regler från en postlåda använder du cmdleten [Ta bort inkorgsregeln.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule)

3. Om du vill behålla regeln och dess innehåll för vidare undersökning använder du cmdleten [Inaktivera inkorgRegel.](https:https://docs.microsoft.com/powershell/module/exchange/mailboxes/disable-inboxrule/library/dd298120(v=exchg.160).aspx)

## <a name="how-to-minimize-future-attacks"></a>Så här minimerar du framtida attacker

### <a name="first-protect-your-accounts"></a>Första: skydda dina konton

Bedrifterna regler och formulär används endast av en angripare efter att de har stulit eller brutit mot ett av dina användares konton. Så, ditt första steg för att förhindra användningen av dessa bedrifter mot din organisation är att aggressivt skydda dina användarkonton. Några av de vanligaste sätten att konton bryts är genom phishing eller [lösenord sprutning](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/) attacker.

Det bästa sättet att skydda dina användarkonton, och särskilt dina administratörskonton, är att [konfigurera multifaktorautentisering för användare](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication). Du bör också:

- Övervaka hur dina användarkonton [används och används](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports). Du får inte förhindra den första överträdelsen, men du kommer att förkorta varaktigheten och effekten av överträdelsen genom att upptäcka det tidigare. Du kan använda dessa säkerhetsprinciper för [Office 365 Cloud App](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) för att övervaka konton och aviseringar om ovanlig aktivitet:

  - **Flera misslyckade inloggningsförsök**: Den här principen profilerar din miljö och utlöser aviseringar när användare utför flera misslyckade inloggningsaktiviteter i en enda session med avseende på den inlärda baslinjen, vilket kan tyda på ett försök att bryta.

  - **Omöjlig resa**: Den här principen profilerar din miljö och utlöser aviseringar när aktiviteter upptäcks från samma användare på olika platser inom en tidsperiod som är kortare än den förväntade restiden mellan de två platserna. Detta kan tyda på att en annan användare använder samma autentiseringsuppgifter. Om du upptäcker det här avvikande beteendet krävs en inledande inlärningsperiod på sju dagar under vilken den lär sig en ny användares aktivitetsmönster.

  - **Ovanlig personifierad aktivitet (efter användare):** Den här principen profilerar din miljö och utlöser aviseringar när användare utför flera personifierade aktiviteter i en enda session med avseende på den inlärda baslinjen, vilket kan tyda på ett försök till överträdelse.

- Utnyttja ett verktyg som [Office 365 Secure Score](https://securescore.office.com/) för att hantera kontosäkerhetskonfigurationer och beteenden.

### <a name="second-keep-your-outlook-clients-current"></a>För det andra: Håll dina Outlook-klienter aktuella

Fullständigt uppdaterade och korrigerade versioner av Outlook 2013 och 2016 inaktiverar regel/formuläråtgärd för "Starta program" som standard. Detta säkerställer att regel- och formuläråtgärder blockeras även om en angripare bryter mot kontot. Du kan installera de senaste uppdateringarna och säkerhetskorrigeringarna genom att följa stegen i [Installera Office-uppdateringar](https://support.office.com/article/2ab296f3-7f03-43a2-8e50-46de917611c5).

Här är korrigeringsversionerna för dina Outlook 2013- och 2016-klienter:

- **Outlook 2016**: 16.0.4534.1001 eller mer.

- **Outlook 2013**: 15.0.4937.1000 eller mer.

Mer information om de enskilda säkerhetskorrigeringarna finns i:

- [Säkerhetskorrigering i Outlook 2016](https://support.microsoft.com/help/3191883)

- [Säkerhetskorrigering i Outlook 2013](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>Tredje: Övervaka dina Outlook-klienter

Observera att även med korrigeringsfiler och uppdateringar installerade, är det möjligt för en angripare att ändra den lokala datorns konfiguration för att återaktivera "Starta program"-beteendet. Du kan använda [Avancerad grupprinciphantering](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) för att övervaka och tillämpa principer för lokala datorer på dina klienter.

Du kan se om "Starta program" har återaktiverats via en åsidosättning i registret med hjälp av informationen i Så här visar du [systemregistret med hjälp av 64-bitarsversioner av Windows](https://support.microsoft.com/help/305097/how-to-view-the-system-registry-by-using-64-bit-versions-of-windows). Kontrollera dessa undernycklar:

- **Utsikter 2016**:`HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013**:`HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

Leta efter nyckeln EnableUnsafeClientMailRules. Om den finns där och är inställd på 1 har säkerhetskorrigeringen i Outlook åsidosättts och datorn är sårbar för attacken mellan formulär och regler. Om värdet är 0 inaktiveras åtgärden "Starta program". Om den uppdaterade och korrigerade versionen av Outlook är installerad och den här registernyckeln inte finns, är ett system inte sårbart för dessa attacker.

Kunder med lokala Exchange-installationer bör överväga att blockera äldre versioner av Outlook som inte har korrigeringsfiler tillgängliga. Information om den här processen finns i artikeln [Konfigurera Outlook-klientblockering](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help).

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Skydda Microsoft 365 som en expert på cybersäkerhet

Din Microsoft 365-prenumeration innehåller kraftfulla säkerhetsfunktioner som du kan använda för att skydda dina data och dina användare. Använd [Säkerhetsöversikt för Microsoft 365 – de vanligaste prioriteringarna för de första 30 dagarna, 90 dagarna och bortom](security-roadmap.md) för att implementera Microsofts metodtips för att skydda din Microsoft 365-klientorganisation.

- Uppgifter som ska utföras under de första 30 dagarna. De har omedelbar effekt och påverkar inte användarna i någon större utsträckning.

- Uppgifter som ska utföras inom 90 dagar. De tar lite längre tid att planera och implementera men förbättrar din säkerhet avsevärt.

- Efter 90 dagar. De här förbättringarna uppnås under de första 90 dagarna.

## <a name="see-also"></a>Se även:

- [Malicious Outlook Rules](https://silentbreaksecurity.com/malicious-outlook-rules/) by SilentBreak Security Post about Rules Vector ger en detaljerad genomgång av hur Outlook-reglerna.

- [MAPI över HTTP och Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) på Sensepost blogg om Mailrule Pwnage diskuterar ett verktyg som heter Linjal som låter dig utnyttja brevlådor genom Outlook-regler.

- [Outlook-formulär och -skal](https://sensepost.com/blog/2017/outlook-forms-and-shells/) på Sensepost-bloggen om Forms Threat Vector.

- [Kodbas för linjal](https://github.com/sensepost/ruler)

- [Linjal indikatorer för kompromiss](https://github.com/sensepost/notruler/blob/master/iocs.md)
