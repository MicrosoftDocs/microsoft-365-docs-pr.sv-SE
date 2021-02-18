---
title: Identifiera och åtgärda Outlook-regler och anpassade insamlingsattacker.
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
localization_priority: Normal
search.appverid:
- MET150
description: Lär dig hur du känner igen och åtgärdar Outlook-regler och anpassade formulärinsamlingsattacker i Office 365
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e22cfa97ae59fdd094c161cdaeff899dc1dd6507
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286399"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a>Identifiera och åtgärda Outlook-regler och anpassade formulärinsamlingsattacker

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Sammanfattning** Lär dig hur du känner igen och åtgärdar Outlook-regler och anpassade Forms-attacker i Office 365.

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>Vad är Outlook-regler och custom Forms-injiceringsattack?

När en attack har brutit mot ett konto i ditt användarkonto och kommer in kommer du att försöka etablera ett sätt att stanna kvar eller komma tillbaka in när de upptäcks och tas bort. Det här kallas för att upprätta en mekanism för beständighet. Det kan de göra på två sätt genom att utnyttja Outlook-regler eller genom att mata in anpassade formulär i Outlook.
I båda fallen synkroniseras regeln eller formuläret från molntjänsten till skrivbordsklienten, så att ett fullständigt format och en ominstallation av klientprogramvaran inte tar bort inlösningen. Det beror på att regler och formulär hämtas igen från molnet när Outlook-klientprogramvaran återansluts till postlådan i molnet. När reglerna och formulären är på plats använder attackerarna dem för att köra fjärr- eller anpassad kod, vanligtvis för att installera skadlig programvara på den lokala datorn. Den skadliga programvaran stjäl sedan autentiseringsuppgifter igen eller utför andra aktiviteter som kan vara affärsverksamhet.
Den goda nyheten här är att om du håller dina klienter uppdaterade till den senaste versionen är du inte sårbar för risken eftersom den aktuella Outlook-klientens standardinställningar blockerar båda mekanismerna.

Attackerna följer vanligtvis dessa mönster:

**Utnyttja reglerna:**

1. Attackeraren stjäl användarnamn och lösenord för en av dina användare.

2. Attackeraren loggar sedan in på den användarens Exchange-postlåda. Postlådan kan antingen finnas i Exchange Online eller lokalt i Exchange.

3. Då skapas en vidarebefordransregel i postlådan som utlöses när postlådan får ett e-postmeddelande som matchar villkoren i regeln. Villkoren för regeln och innehållet i e-postmeddelandet med utlösaren är anpassade efter varandra.

4. Attackeraren skickar utlösarmeddelandet till den användare som normalt använder postlådan.

5. När e-postmeddelandet tas emot utlöses regeln. Regelns åtgärd är vanligtvis att starta ett program på en fjärrserver (WebDAV).

6. Programmet installerar vanligtvis skadlig programvara, till exempel [Powershell Empire,](https://www.powershellempire.com/)lokalt på användarens dator.

7. Den skadlig programvara gör att attackeraren kan stjäla användarens användarnamn och lösenord eller andra autentiseringsuppgifter från den lokala datorn igen och utföra andra skadliga aktiviteter.

**Sårbarheten i Forms:**

1. Attackeraren stjäl användarnamn och lösenord för en av dina användare.

2. Attackeraren loggar sedan in på den användarens Exchange-postlåda. Postlådan kan antingen finnas i Exchange Online eller lokalt i Exchange.

3. Då skapas en egen e-postformulärmall för attackeret och den infogas i användarens postlåda. Det anpassade formuläret utlöses när postlådan får ett e-postmeddelande som kräver att postlådan läser in det anpassade formuläret. Det anpassade formuläret och formatet på e-post är anpassade efter varandra.
4. Attackeraren skickar utlösarmeddelandet till användaren, som normalt använder postlådan.

5. När e-postmeddelandet tas emot läses formuläret in. Formuläret öppnar ett program på en fjärrserver (WebDAV).

6. Programmet installerar vanligtvis skadlig programvara, till exempel [Powershell Empire,](https://www.powershellempire.com/)lokalt på användarens dator.

7. Den skadlig programvara gör att attackeraren kan stjäla användarens användarnamn och lösenord eller andra autentiseringsuppgifter från den lokala datorn igen och utföra andra skadliga aktiviteter.

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>Hur en regel och en anpassad formulärinsamlingsattack kan se ut som i Office 365?

De här beständighetsmetoderna kommer inte att synas av dina användare och kan i vissa fall till och med vara osynliga för dem. Den här artikeln beskriver hur du söker efter de sju tecken (indikatorer på komprometterade) som anges nedan. Om du hittar något av detta måste du vidta åtgärder.

- Indikatorer på regelprometten:

  - Regelåtgärd är att starta ett program.

  - Regelreferenser med EXE, ZIP eller URL.

  - På den lokala datorn letar du efter nya processer som kommer från Outlook PID.

- Indikatorer på att anpassade formulär har komprometterats:

  - Anpassade formulär som har sparats som en egen meddelandeklass.

  - Meddelandeklass innehåller körbar kod.

  - Lagras vanligtvis i personliga formulärbibliotek eller inkorgsmappar.

  - Formuläret heter IPM. Obs! [eget namn].

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>Steg för att hitta tecken på den här attacken och bekräfta den

Du kan använda någon av dessa två metoder för att bekräfta attacken:

- Granska regler och formulär manuellt för varje postlåda med Hjälp av Outlook-klienten. Den här metoden är genomgående, men du kan bara kontrollera postlådeanvändare i en tid som kan ta mycket tid om du har många användare att kontrollera. Det kan också leda till ett brott mot datorn som du kör kontrollen från.

- Använd [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell-skriptet för att automatisktdumpa alla regler för vidarebefordran av e-post och anpassade formulär för alla användare i ditt tiotal. Det här är den snabbaste och säkraste metoden med minsta möjliga overhead.

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>Bekräfta regelattacken med Outlook-klienten

1. Öppna outlook-klienten för användare som användare. Användaren kan behöva hjälp med att granska reglerna för postlådan.

2. Se Hantera [e-postmeddelanden med hjälp av regelartikeln](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) för procedurer för hur du öppnar regelgränssnittet i Outlook.

3. Leta efter regler som användaren inte har skapat eller oväntade regler eller regler med misstänkta namn.

4. Titta i regelbeskrivningen för regelåtgärder som startar och program, eller referera till en . EXE, . ZIP-fil eller för att starta en URL.

5. Leta efter nya processer som börjar använda process-ID för Outlook. Mer information [finns i Hitta process-ID: t.](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id)

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Steg för att bekräfta Forms-attacken med Outlook-klienten

1. Öppna användarens Outlook-klient som användare.

2. Följ anvisningarna i [Visa fliken Utvecklare för](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) användarversionen av Outlook.

3. Öppna den nu synliga fliken Utvecklare i Outlook och klicka på **Designa ett formulär.**

4. Välj **Inkorgen** i **listan Leta i.** Leta efter eventuella anpassade formulär. Anpassade formulär är sällsynta så att om du har några anpassade formulär alls är det värt att se djupare.

5. Undersök eventuella anpassade formulär, särskilt de som markerats som dolda.

6. Öppna alla anpassade formulär och klicka **på Visa** kod i gruppen **Formulär för** att se vad som körs när formuläret läses in.

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>Steg för att bekräfta rules and forms-attacken med PowerShell

Det enklaste sättet att verifiera en regel eller ett anpassat formulär-angrepp är att köra [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell-skriptet. Med det här skriptet ansluts alla postlådor i klientorganisationen och alla regler och formulär till två CSV-filer.

#### <a name="pre-requisites"></a>Förutsättningar

Du måste ha global administratörsbehörighet för att köra skriptet eftersom skriptet ansluter till varje postlåda under innehavare för att läsa regler och formulär.

1. Logga in på den dator som du kör skriptet från med lokala administratörsrättigheter.

2. Ladda ned eller Get-AllTenantRulesAndForms.ps1 skriptet från GitHub till en mapp som du ska köra det från. Skriptet skapar två datumstämplade filer till den här mappen, MailboxFormsExport-yyyy-mm-dd.csv och MailboxRulesExport-yyyy-mm-dd.csv.

3. Öppna en PowerShell-instans som administratör och öppna mappen där du sparade skriptet.

4. Kör den här PowerShell-kommandoraden enligt `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>Tolka utdata

- **MailboxRulesExport-*yyyy-mm-dd*.csv:** Undersök reglerna (en per rad) för åtgärdsvillkor som innehåller program eller körbara filer:

  - **ActionType (kolumn A)**: Om du ser värdet "ID_ACTION_CUSTOM" är regeln sannolikt skadlig.

  - **ÄrIIallyMalicious (kolumn D)**: Om det här värdet är "SANT" är regeln sannolikt skadlig.

  - **ActionCommand (kolumn G)**: Om det här listar ett program eller en fil med filnamnstillägget .exe, .zip eller en post som refererar till en URL-adress som inte ska finnas där är regeln sannolikt skadlig.

- **MailboxFormsExport-*yyyy-mm-dd*.csv:** I allmänhet är användningen av anpassade formulär mycket ovanligt. Om det finns några i arbetsboken öppnar du användarens postlåda och undersöker själva formuläret. Om organisationen inte lagt upp det avsiktligt är det troligt att det är skadligt.

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>Så här stoppar och åtgärdar du attacken med Outlook-regler och formulär

Om du hittar bevis för något av dessa attacker är det enkelt att åtgärda, ta bara bort regeln eller formuläret från postlådan. Du kan göra detta med Outlook-klienten eller med fjärr-PowerShell för att ta bort regler.

### <a name="using-outlook"></a>Använda Outlook

1. Identifiera alla enheter som användaren har använt med Outlook. Alla måste rensas från eventuell skadlig programvara. Tillåt inte att användaren loggar in och använder e-post förrän alla enheter har rensats.

2. Följ anvisningarna i [Ta bort en regel](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) för varje enhet.

3. Om du är osäker på om det finns annan skadlig programvara kan du formatera och installera om all programvara på enheten. För mobila enheter kan du följa tillverkarens steg för att återställa enheten till fabriksbilden.

4. Installera de senaste versionerna av Outlook. Kom ihåg att den aktuella versionen av Outlook blockerar båda typerna av den här attacken som standard.

5. När alla offlinekopior av postlådan har tagits bort återställer du användarens lösenord (använd [](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) ett lösenord av hög kvalitet) och följer stegen i Konfigurera multifaktorautentisering för användare om MFA inte redan har aktiverats. Detta garanterar att användarens autentiseringsuppgifter inte exponeras på annat sätt (t.ex. nätfiske eller lösenord).

### <a name="using-powershell"></a>Använda PowerShell

Det finns två PowerShell-fjärr cmdlets som du kan använda för att ta bort eller inaktivera skadliga regler. Följ bara anvisningarna.

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>Steg för postlådor som finns på en Exchange-server

1. Anslut till Exchange-servern med fjärr-PowerShell. Följ stegen i Ansluta [till Exchange-servrar med fjärr-PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-servers-using-remote-powershell)

2. Om du helt vill ta bort en enda regel, flera regler eller alla regler från en postlåda använder du cmdleten [Remove-InboxRule.](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule)

3. Om du vill behålla regeln och dess innehåll för vidare undersökning använder du cmdleten [Disable-InboxRule.](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule)

#### <a name="steps-for-mailboxes-in-exchange-online"></a>Steg för postlådor i Exchange Online

1. Följ anvisningarna i [Ansluta till Exchange Online med PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. Om du helt vill ta bort en enda regel, flera regler eller alla regler från en postlåda använder du cmdleten [Ta](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) bort inkorgsregel.

3. Om du vill behålla regeln och dess innehåll för vidare undersökning använder du cmdleten [Disable-InboxRule.](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule)

## <a name="how-to-minimize-future-attacks"></a>Hur du minimerar framtida attacker

### <a name="first-protect-your-accounts"></a>Först: skydda dina konton

De regler och formulär-sårbarheter som bara används av en attackerare efter att de har stulit eller bryter mot ett av dina användares konton. Det första steget för att förhindra användning av dessa sårbarheter mot organisationen är därför att aggressivt skydda användarkonton. Några av de vanligaste sätten som konton bryter mot är nätfiske- eller [lösenordsattacker.](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/)

Det bästa sättet att skydda användarkonton, och särskilt administratörskonton, är att [konfigurera multifaktorautentisering för användare.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) Du bör också:

- Övervaka hur användarkonton är [åtkomlade och används.](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports) Du kan inte förhindra den första intrånget, men du förkortar varaktigheten och påverkan på intrånget genom att upptäcka det snabbare. Du kan använda de här [säkerhetsprinciperna för Office 365 Cloud App](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) för att övervaka dina konton och varna för ovanlig aktivitet:

  - **Flera misslyckade inloggningsförsök:** Den här principprofilen profilerar din miljö och utlöser aviseringar när användare utför flera misslyckade inloggningsaktiviteter i en enskild session med avseende på den inlärda baslinjen, vilket kan ange ett försök till intrång.

  - **Omöjligt** att resa: Den här principprofilen profilerar din miljö och utlöser aviseringar när aktiviteter identifieras från samma användare på olika platser inom en tidsperiod som är kortare än den förväntade restiden mellan de två platserna. Det kan indikera att en annan användare använder samma autentiseringsuppgifter. När detta avvikande beteende identifieras måste den första utbildningsperioden vara sju dagar då den lär sig en ny användares aktivitetsmönster.

  - **Ovanliga imiterade aktiviteter (efter användare)**: Den här principen profilerar din miljö och utlöser aviseringar när användare utför flera imiterade aktiviteter i en enskild session med avseende på den grundläggande läran, vilket kan ange ett försök till intrång.

- Använd ett verktyg som [Office 365 Secure Score för](https://securescore.office.com/) att hantera konfigurationer och beteenden för kontosäkerhet.

### <a name="second-keep-your-outlook-clients-current"></a>Andra: Håll Outlook-klienterna aktuella

Helt uppdaterade och korrigerade versioner av Outlook 2013 och 2016 inaktiverar som standard åtgärden "Starta program" med regler och formulär. På så sätt kan du se till att regeln och formuläråtgärder blockeras, även om en attack bryter mot kontot. Du kan installera de senaste uppdateringarna och säkerhetskorrigeringarna genom att följa stegen i [Installera Office-uppdateringar.](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)

Här är korrigeringsversionerna för Outlook 2013- och 2016-klienter:

- **Outlook 2016**: 16.0.4534.1001 eller större.

- **Outlook 2013**: 15.0.4937.1000 eller större.

Mer information om de enskilda säkerhetskorrigeringarna finns i:

- [Säkerhetskorrigering för Outlook 2016](https://support.microsoft.com/help/3191883)

- [Säkerhetskorrigering för Outlook 2013](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>Tredje: Övervaka Outlook-klienter

Observera att även med korrigeringarna och uppdateringarna installerade är det möjligt för en attack att ändra den lokala datorkonfigurationen för att återaktivera beteendet "Starta program". Du kan använda [Advanced grupprincip Management för](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) att övervaka och tillämpa lokala datorprinciper på dina klienter.

Du kan se om "Starta program" har aktiverats på nytt via en åsidosättning i registret med hjälp av informationen i Så här visar du systemregistret med hjälp av [64-bitarsversioner](https://support.microsoft.com/help/305097)av Windows. Kontrollera följande undernycklar:

- **Outlook 2016**: `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013**: `HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

Leta efter nyckeln EnableUnsafeClientMailRules. Om den finns där och är inställd på 1 har Säkerhetskorrigeringen för Outlook åsidosättts och datorn är sårbar för form-/regel-attacken. Om värdet är 0 inaktiveras åtgärden "Starta program". Om den uppdaterade och korrigerade versionen av Outlook är installerad och den här registernyckeln inte finns är ett system inte sårbart för dessa attacker.

Kunder med lokala Exchange-installationer bör överväga att blockera äldre versioner av Outlook som inte har några korrigeringar. Information om den här processen finns i artikeln Konfigurera [klientblockering i Outlook.](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Skydda Microsoft 365 som en expert på cybersäkerhet

Din Microsoft 365-prenumeration innehåller kraftfulla säkerhetsfunktioner som du kan använda för att skydda dina data och dina användare. Använd [Säkerhetsöversikt för Microsoft 365 – de vanligaste prioriteringarna för de första 30 dagarna, 90 dagarna och bortom](security-roadmap.md) för att implementera Microsofts metodtips för att skydda din Microsoft 365-klientorganisation.

- Uppgifter som ska utföras under de första 30 dagarna. De har omedelbar effekt och påverkar inte användarna i någon större utsträckning.

- Uppgifter som ska utföras inom 90 dagar. De tar lite längre tid att planera och implementera men förbättrar din säkerhet avsevärt.

- Efter 90 dagar. De här förbättringarna uppnås under de första 90 dagarna.

## <a name="see-also"></a>Se även:

- [Outlook-regler](https://silentbreaksecurity.com/malicious-outlook-rules/) med SilentBreak-säkerhetsinlägg om Rules Vector ger en detaljerad översikt över hur Outlook-reglerna fungerar.

- [MAPI over HTTP and Mailrule Pwnage on](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) the Sensepost blog about Mailrule Pwnage discusses a tool called Ruler that lets you exploit mailboxes through Outlook rules.

- [Outlook-formulär och shells](https://sensepost.com/blog/2017/outlook-forms-and-shells/) på Sensepost-bloggen om Forms Threat Vector.

- [Linjalkodbas](https://github.com/sensepost/ruler)

- [Linjalindikatorer för kompromett](https://github.com/sensepost/notruler/blob/master/iocs.md)
