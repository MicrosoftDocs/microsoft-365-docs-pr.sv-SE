---
title: Identifiera och åtgärda Outlook-regler och anpassade formulärinjektionsattacker i Office 365
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
description: Lär dig hur du känner igen och åtgärdar Outlook-reglerna och anpassade formulärinjektionsattacker i Office 365
ms.openlocfilehash: c15eeb057d14cbb252bda0767a15e7c4788ece9f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42808110"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks-in-office-365"></a>Identifiera och åtgärda Outlook-regler och anpassade formulärinjektionsattacker i Office 365

**Sammanfattning** Lär dig hur du känner igen och åtgärdar Outlook-reglerna och anpassade formulärinjektioner i Office 365.

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>Vad är insprutningsattacken i Outlook-regler och anpassade formulär?

När en angripare har brutit mot ett konto i din hyresrätt och kommer in, kommer det att försöka etablera ett sätt att stanna i eller ett sätt att komma tillbaka in efter att de har upptäckts och tagits bort. Detta kallas att inrätta en persistensmekanism. Två sätt att de kan göra detta är genom att utnyttja Outlook-regler eller genom att injicera anpassade formulär i Outlook.
I båda fallen synkroniseras regeln eller formuläret från molntjänsten ner till skrivbordsklienten, så ett fullständigt format och ominstallation av klientprogramvaran eliminerar inte injektionsmekanismen. Detta beror på att när Outlook-klientprogramvaran återansluter till postlådan i molnet kommer den att ladda ned regler och formulär från molnet igen. När reglerna och formulären är på plats använder angriparen dem för att köra fjärr- eller anpassad kod, vanligtvis för att installera skadlig kod på den lokala datorn. Den skadliga koden stjäl sedan referenser eller utför annan olaglig verksamhet.
Den goda nyheten här är att om du håller dina kunder korrigeras till den senaste versionen, du är inte sårbar för hotet som nuvarande Outlook-klienten standardblockerar båda mekanismerna.

Attackerna följer vanligtvis dessa mönster:

**Reglerna utnyttjar:**

1. Angriparen stjäl användarnamn et och lösenord för en av dina användare.

2. Angriparen loggar sedan in på att användare Exchange postlåda. Postlådan kan antingen vara i Exchange online eller i Exchange lokalt.

3. Angriparen skapar sedan en vidarebefordringsregel i postlådan som utlöses när postlådan får ett e-postmeddelande som matchar regelns villkor. Regelkriterierna och innehållet i utlösarens e-post är skräddarsydda för varandra.

4. Angriparen skickar utlösningsmeddelandet till användaren som använder postlådan normalt.

5. När e-postmeddelandet tas emot utlöses regeln. Regelns åtgärd är vanligtvis att starta ett program på en fjärrserver (WebDAV).

6. Programmet installerar vanligtvis skadlig kod, till exempel [Powershell Empire](https://www.powershellempire.com/), lokalt på användarens dator.

7. Den skadliga koden gör det möjligt för angriparen att åter stjäla användarens användarnamn och lösenord eller andra autentiseringsuppgifter från den lokala datorn och utföra andra skadliga aktiviteter.

**Formulären utnyttjar:**

1. Angriparen stjäl användarnamn et och lösenord för en av dina användare.

2. Angriparen loggar sedan in på de användare Exchange-postlådan. Postlådan kan antingen vara i Exchange online eller i Exchange lokalt.

3. Angriparen skapar sedan en anpassad mall för e-postformulär och infogar den i användarens postlåda. Det anpassade formuläret utlöses när postlådan tar emot ett e-postmeddelande som kräver att postlådan läser in det anpassade formuläret. Det anpassade formuläret och formatet på e-post är skräddarsydda för varandra.
4. Angriparen skickar utlösningsmeddelandet till användaren, som använder postlådan normalt.

5. När e-postmeddelandet tas emot läses formuläret in. Formuläret startar ett program på en fjärrserver (WebDAV).

6. Programmet installerar vanligtvis skadlig kod, till exempel [Powershell Empire](https://www.powershellempire.com/), lokalt på användarens dator.

7. Den skadliga koden gör det möjligt för angriparen att åter stjäla användarens användarnamn och lösenord eller andra autentiseringsuppgifter från den lokala datorn och utföra andra skadliga aktiviteter.

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>Vad kan en injektionsattack för regler och anpassade formulär se ut som Office 365?

Dessa persistens mekanismer är osannolikt att märkas av dina användare och kan i vissa fall även vara osynlig för dem. Den här artikeln berättar hur du letar efter någon av de sju tecken (Indikatorer på kompromiss) som anges nedan. Om du hittar något av detta måste du vidta åtgärder för reparation.

- Indikatorer på regelkompromissen:

  - Regelåtgärd är att starta ett program.

  - Regel refererar till en EXE, ZIP eller URL.

  - Leta efter nya processstarter som kommer från Outlook PID på den lokala datorn.

- Indikatorer för de anpassade formulären kompromiss:

  - Anpassat formulär som sparats som sin egen meddelandeklass.

  - Meddelandeklassen innehåller körbar kod.

  - Vanligtvis lagras i personliga formulär bibliotek eller inkorg mappar.

  - Formuläret heter IPM. Observera. [anpassat namn].

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>Åtgärder för att hitta tecken på denna attack och bekräfta det

Du kan använda någon av dessa två metoder för att bekräfta attacken:

- Undersök reglerna och formulären manuellt för varje postlåda med Outlook-klienten. Den här metoden är grundlig, men du kan bara kontrollera postlådeanvändare i taget vilket kan vara mycket tidskrävande om du har många användare att kontrollera. Det kan också resultera i ett brott mot datorn som du kör kontrollen från.

- Använd [PowerShell-skriptet Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) för att automatiskt dumpa alla regler för vidarebefordran av e-post och anpassade formulär för alla användare i din hyresrätt. Detta är den snabbaste och säkraste metoden med minsta möjliga omkostnader.

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>Bekräfta regelattacken med Outlook-klienten

1. Öppna användarnas Outlook-klient som användare. Användaren kan behöva din hjälp med att undersöka reglerna för sin postlåda.

2. Se [Hantera e-postmeddelanden med hjälp av regelartikel](https://support.office.com/article/c24f5dea-9465-4df4-ad17-a50704d66c59) för procedurer för hur du öppnar regelgränssnittet i Outlook.

3. Leta efter regler som användaren inte har skapat, eller oväntade regler eller regler med misstänkta namn.

4. Titta i regelbeskrivningen för regelåtgärder som startar och program eller refererar till en . Exe. zip-fil eller för att starta en URL.

5. Leta efter nya processer som börjar använda Outlook-process-ID. Se [Hitta process-ID](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id).

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Åtgärder för att bekräfta formulärattacken med Outlook-klienten

1. Öppna användarenoutlook-klienten som användare.

2. Följ stegen [i, Visa fliken Utvecklare](https://support.office.com/article/e1192344-5e56-4d45-931b-e5fd9bea2d45) för användarversionen av Outlook.

3. Öppna fliken Nu synlig utvecklare i Outlook och klicka på **Designa ett formulär**.

4. Markera **inkorgen i** listan **Leta i.** Leta efter anpassade formulär. Anpassade formulär är sällsynta nog att om du har några anpassade formulär alls, är det värt en djupare titt.

5. Undersök alla anpassade formulär, särskilt de som är markerade som dolda.

6. Öppna alla anpassade formulär och klicka på **Visa kod** i gruppen **Formulär** för att se vad som körs när formuläret läses in.

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>Åtgärder för att bekräfta regel- och formulärattacken med PowerShell

Det enklaste sättet att verifiera en regel eller anpassade formulärattack är att köra [PowerShell-skriptet Get-AllTenantRulesAndForms.ps1.](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) Det här skriptet ansluter till varje postlåda i din klient och dumpar alla regler och formulär till två CSV-filer.

#### <a name="pre-requisites"></a>Förutsättningar

Du måste ha en global administratörsbehörighet för att köra skriptet eftersom skriptet ansluter till varje postlåda i hyresen för att läsa regler och formulär.

1. Logga in på datorn som du kör skriptet från med lokala administratörsrättigheter.

2. Ladda ned eller kopiera Get-AllTenantRulesAndForms.ps1-skriptet från GitHub till en mapp som du ska köra den från. Skriptet skapar två datumstämplade filer till den här mappen, MailboxFormsExport-yyyy-mm-dd.csv och MailboxRulesExport-yyyy-mm-dd.csv.

3. Öppna en PowerShell-instans som administratör och öppna mappen som du sparade skriptet till.

4. Kör den här PowerShell-kommandoraden enligt följande `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>Tolka utdata

- **MailboxRulesExport-*yyyy-mm-dd*.csv**: Undersök reglerna (en per rad) för åtgärdsvillkor som inkluderar program eller körbara filer:

  - **ActionType (kolumn A)**: Om du ser värdet "ID_ACTION_CUSTOM" är regeln troligen skadlig.

  - **IsPotentiallyMalicious (kolumn D)**: Om det här värdet är "SANT" är regeln troligen skadlig.

  - **ActionCommand (kolumn G):** Om detta visar ett program eller en fil med ett .exe, zip-tillägg eller en post som refererar till en URL, som inte är tänkt att vara där, är regeln sannolikt skadlig.

- **MailboxFormsExport-*yyyy-mm-dd*.csv**: I allmänhet är användningen av anpassade formulär mycket sällsynt. Om du hittar några i den här arbetsboken öppnar du användarens postlåda och undersöker själva formuläret. Om din organisation inte lade den där avsiktligt är den troligen skadlig.

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>Så här stoppar och åtgärdar du outlook-reglerna och formulärattacken

Om du hittar några bevis för någon av dessa attacker, är reparation enkel, bara ta bort regeln eller formuläret från brevlådan. Du kan göra detta med Outlook-klienten eller använda fjärrpowershell för att ta bort regler.

### <a name="using-outlook"></a>Använda Outlook

1. Identifiera alla enheter som användaren har använt med Outlook. De kommer alla att behöva rengöras från potentiella malware. Låt inte användaren logga in och använda e-post förrän alla enheter har rensats.

2. Följ stegen i [Ta bort en regel](https://support.office.com/article/2f0e7139-f696-4422-8498-44846db9067f) för varje enhet.

3. Om du är osäker på förekomsten av annan skadlig kod kan du formatera och installera om all programvara på enheten. För mobila enheter kan du följa tillverkarnas steg för att återställa enheten till fabriksavbildningen.

4. Installera de senaste versionerna av Outlook. Kom ihåg att den aktuella versionen av Outlook blockerar båda typerna av den här attacken som standard.

5. När alla offlinekopior av postlådan har tagits bort återställer du användarens lösenord (använd ett högkvalitativt lösenord) och följer stegen i [installationsmultifaktorautentisering för Office 365-användare](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) om MFA inte redan har aktiverats. Detta säkerställer att användarens autentiseringsuppgifter inte exponeras på andra sätt (t.ex. nätfiske eller återanvändning av lösenord).

### <a name="using-powershell"></a>Använda PowerShell

Det finns två fjärr-PowerShell-cmdlets som du kan använda för att ta bort eller inaktivera farliga regler. Följ bara stegen.

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>Steg för postlådor som finns på en Exchange-server

1. Anslut till Exchange-servern med fjärrstyrning av PowerShell. Följ stegen i [Connect to Exchange-servrar med fjärrpowershell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

2. Om du vill ta bort en enskild regel helt, flera regler eller alla regler från en postlåda använder du cmdleten [Remove-InboxRule.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule)

3. Om du vill behålla regeln och dess innehåll för vidare undersökning använd cmdleten [Disable-InboxRule.](https:https://docs.microsoft.com/powershell/module/exchange/mailboxes/disable-inboxrule/library/dd298120(v=exchg.160).aspx)

#### <a name="steps-for-mailboxes-in-exchange-online"></a>Steg för postlådor i Exchange Online

1. Följ stegen i [Anslut till Exchange Online med PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Om du vill ta bort en enskild regel helt, flera regler eller alla regler från en postlåda använder du cmdleten [Ta bort inkorgsregel.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule)

3. Om du vill behålla regeln och dess innehåll för vidare undersökning använd cmdleten [Disable-InboxRule.](https:https://docs.microsoft.com/powershell/module/exchange/mailboxes/disable-inboxrule/library/dd298120(v=exchg.160).aspx)

## <a name="how-to-minimize-future-attacks"></a>Hur man minimerar framtida attacker

### <a name="first-protect-your-accounts"></a>För det första: skydda dina konton

Regel- och formulärbedrifterna används endast av en angripare när de har stulit eller brutit mot ett av användarens konton. Så, ditt första steg för att förhindra användningen av dessa bedrifter mot din organisation är att aggressivt skydda dina användarkonton. Några av de vanligaste sätten att konton bryts är genom nätfiske eller [lösenordsbesprutningsattacker.](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/)

Det bästa sättet att skydda dina användarkonton, och särskilt dina administratörskonton, är att [konfigurera multifaktorautentisering för Office 365-användare](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication). Du bör också:

- Övervaka hur dina användarkonton [används och används](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports). Du får inte förhindra den första överträdelsen, men du kommer att förkorta överträdelsens varaktighet och inverkan genom att upptäcka den tidigare. Du kan använda dessa säkerhetsprinciper för [Office 365 Cloud App](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) för att övervaka konton och aviseringar om ovanlig aktivitet:

  - **Flera misslyckade inloggningsförsök**: Den här principen profilerar din miljö och utlöser aviseringar när användare utför flera misslyckade inloggningsaktiviteter i en enda session med avseende på den inlärda baslinjen, vilket kan tyda på ett försök till överträdelse.

  - **Omöjlig adtid:** Den här policyn profilerar din miljö och utlöser aviseringar när aktiviteter upptäcks från samma användare på olika platser inom en tidsperiod som är kortare än den förväntade restiden mellan de två platserna. Detta kan tyda på att en annan användare använder samma autentiseringsuppgifter. Att upptäcka detta avvikande beteende kräver en inledande inlärningsperiod på sju dagar under vilken den lär sig en ny användares aktivitetsmönster.

  - **Ovanlig personifieringsaktivitet (av användaren):** Den här principen profilerar din miljö och utlöser aviseringar när användare utför flera personifierade aktiviteter i en enda session med avseende på den inlärda baslinjen, vilket kan tyda på ett försök till överträdelse.

- Utnyttja ett verktyg som [Office 365 Secure Score](https://securescore.office.com/) för att hantera kontosäkerhetskonfigurationer och beteenden.

### <a name="second-keep-your-outlook-clients-current"></a>För det andra: Håll dina Outlook-klienter aktuella

Helt uppdaterade och korrigerade versioner av Outlook 2013 och 2016 inaktivera regel/formuläråtgärden "Starta program" som standard. Detta säkerställer att regel- och formuläråtgärderna blockeras även om en angripare bryter mot kontot. Du kan installera de senaste uppdateringarna och säkerhetskorrigeringarna genom att följa stegen i [Installera Office-uppdateringar](https://support.office.com/article/2ab296f3-7f03-43a2-8e50-46de917611c5).

Här är korrigeringsversionerna för dina Outlook 2013- och 2016-klienter:

- **Utsikter 2016**: 16.0.4534.1001 eller mer.

- **Utsikter 2013**: 15.0.4937.1000 eller mer.

Mer information om de enskilda säkerhetskorrigeringarna finns i:

- [Säkerhetskorrigering för Outlook 2016](https://support.microsoft.com/help/3191883)

- [Säkerhetskorrigering för Outlook 2013](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>För det tredje: Övervaka dina Outlook-klienter

Observera att även med de patchar och uppdateringar installerade, är det möjligt för en angripare att ändra den lokala maskinkonfigurationen för att återaktivera beteendet "Starta program". Du kan använda [Avancerad grupprinciphantering](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) för att övervaka och tillämpa lokala datorprinciper för dina kunder.

Du kan se om "Startprogram" har aktiverats på om via en åsidosättning i registret med hjälp av informationen i [Så här visar du systemregistret med hjälp av 64-bitarsversioner av Windows](https://support.microsoft.com/help/305097/how-to-view-the-system-registry-by-using-64-bit-versions-of-windows). Kontrollera dessa undernycklar:

- **Outlook 2016**:`HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013**:`HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

Leta efter nyckeln EnableUnsafeClientMailRules. Om den är där och är inställd på 1 har säkerhetskorrigeringen i Outlook åsidosatts och datorn är sårbar för formulär-/regelattacken. Om värdet är 0 inaktiveras åtgärden "Starta program". Om den uppdaterade och korrigerade versionen av Outlook är installerad och den här registernyckeln inte finns, är ett system inte sårbart för dessa attacker.

Kunder med lokala Exchange-installationer bör överväga att blockera äldre versioner av Outlook som inte har patchar tillgängliga. Information om den här processen finns i artikeln [Konfigurera Outlook-klientblockering](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help).

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>Säkra Office 365 som ett cybersäkerhetsproffs

Din Office 365-prenumeration levereras med en kraftfull uppsättning säkerhetsfunktioner som du kan använda för att skydda dina data och dina användare. Använd [säkerhetsöversikten för Office 365 – de viktigaste prioriteringarna för de första 30 dagarna, 90 dagarna och därefter](security-roadmap.md) för att implementera Microsofts rekommenderade metodtips för att skydda din Office 365-klientorganisation.

- Uppgifter att utföra under de första 30 dagarna. Dessa har omedelbar affekt och är små påverkan på användarna.

- Uppgifter att utföra på 90 dagar. Dessa tar lite mer tid att planera och genomföra men avsevärt förbättra din säkerhet hållning.

- Bortom 90 dagar. Dessa förbättringar bygga under dina första 90 dagar arbete.

## <a name="see-also"></a>Se även:

- [Skadliga Outlook-regler](https://silentbreaksecurity.com/malicious-outlook-rules/) från SilentBreak Security Post om Regelvektor ger en detaljerad genomgång av hur Outlook-reglerna.

- [MAPI över HTTP och Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) på Sensepost-bloggen om Mailrule Pwnage diskuterar ett verktyg som heter Linjal som låter dig utnyttja postlådor genom Outlook-regler.

- [Outlook-formulär och skal](https://sensepost.com/blog/2017/outlook-forms-and-shells/) på Sensepost-bloggen om Forms Threat Vector.

- [Linjal kodbas](https://github.com/sensepost/ruler)

- [Linjalindikatorer för kompromisser](https://github.com/sensepost/notruler/blob/master/iocs.md)
