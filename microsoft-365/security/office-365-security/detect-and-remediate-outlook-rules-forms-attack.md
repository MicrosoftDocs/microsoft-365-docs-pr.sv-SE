---
title: Identifiera och åtgärda Outlook-regler och egna formulärattacker.
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
description: Lär dig att identifiera och åtgärda Outlook-regler och anpassade formulärattacker i Office 365
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0846051b65b34ec26358f87bb4ca49302573e6e7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917052"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a>Identifiera och åtgärda Outlook-regler och egna formulärattacker

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Sammanfattning** Lär dig hur du känner igen och åtgärdar Outlook-regler och anpassade Forms- dollarattacker i Office 365.

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>Vad är rutorna för Outlook-regler och anpassad forms-attacker?

När en attackerare får åtkomst till organisationen försöker de upprätta ett fothåll för att stanna kvar eller komma tillbaka in när de har identifierats. Den här aktiviteten kallas *för att fastställa en mekanism för beständighet.* Det finns två sätt som en attackerare kan använda Outlook för att upprätta en mekanism för beständighet:

- Genom att utnyttja Outlook-regler.
- Genom att mata in anpassade formulär i Outlook.

Det hjälper inte att installera om Outlook, och inte ens ge den berörda personen någon ny dator. När den nya installationen av Outlook ansluter till postlådan synkroniseras alla regler och formulär från molnet. Reglerna eller formulären är vanligtvis utformade för att köra fjärrkod och installera skadlig programvara på den lokala datorn. Skadlig programvara stjäl autentiseringsuppgifter eller utför andra aktiviteter i aktiviteten.

Den goda nyheten är: om du behåller dina Outlook-klienter korrigerat till den senaste versionen är du inte sårbar för risken eftersom den aktuella Outlook-klientens standardinställningar blockerar båda mekanismerna.

Attackerna följer vanligtvis dessa mönster:

**Utnyttja regler:**

1. Attackeraren stjäl en användares autentiseringsuppgifter.

2. Attackeraren loggar in på den användarens Exchange-postlåda (Exchange Online eller lokal Exchange).

3. Attackeraren skapar en vidare vidarebefordransregel för Inkorgen i postlådan. Vidarebefordransregeln utlöses när postlådan får ett specifikt meddelande från attacken som matchar villkoren i regeln. Regelvillkoren och meddelandeformatet är anpassade efter varandra.

4. Då skickar attackeraren e-postmeddelandet till den komprometterade postlådan, som fortfarande används som vanligt av den intet ont anande användaren.

5. När postlådan får ett meddelande som matchar villkoren i regeln tillämpas åtgärden av regeln. Regelåtgärden är vanligtvis att starta ett program på en fjärrserver (WebDAV).

6. Vanligtvis installerar programmet skadlig programvara på användarens dator (till exempel [PowerShell Empire).](https://www.powershellempire.com/)

7. Den skadliga programvaran gör att attacker kan stjäla (eller stjäla igen) användarens användarnamn och lösenord eller andra autentiseringsuppgifter från den lokala datorn och utföra andra skadliga aktiviteter.

**Utnyttja formulären:**

1. Attackeraren stjäl en användares autentiseringsuppgifter.

2. Attackeraren loggar in på den användarens Exchange-postlåda (Exchange Online eller lokal Exchange).

3. Attackeraren infogar en anpassad e-postformulärmall i användarens postlåda. Det anpassade formuläret utlöses när postlådan får ett specifikt meddelande från attacken som kräver att postlådan läser in det anpassade formuläret. Det anpassade formuläret och meddelandeformatet är anpassade efter varandra.

4. Då skickar attackeraren e-postmeddelandet till den komprometterade postlådan, som fortfarande används som vanligt av den intet ont anande användaren.

5. När postlådan får meddelandet läser postlådan in formuläret som krävs. Formuläret startar ett program på en fjärrserver (WebDAV).

6. Vanligtvis installerar programmet skadlig programvara på användarens dator (till exempel [PowerShell Empire).](https://www.powershellempire.com/)

7. Den skadliga programvaran gör att attacker kan stjäla (eller stjäla igen) användarens användarnamn och lösenord eller andra autentiseringsuppgifter från den lokala datorn och utföra andra skadliga aktiviteter.

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>Hur en attack med regler och anpassad formulärinsamling kan se ut som Office 365?

De här mekanismerna för beständighet är osannolikt att synas av dina användare och kan i vissa fall även vara osynliga för dem. I den här artikeln beskrivs hur du letar efter de sju skyltar (Indikatorer på komprometterade) som anges nedan. Om du hittar något av detta måste du vidta åtgärder.

- **Indikatorer på regelkompromettering:**
  - Regelåtgärden är att starta ett program.
  - Regelreferenser för EXE, ZIP eller URL.
  - På den lokala datorn letar du efter nya processstarter som kommer från Outlook PID.

- **Indikatorer på kompromettering av anpassade formulär:**
  - Anpassade formulär finns sparade som en egen meddelandeklass.
  - Meddelandeklass innehåller körbar kod.
  - Skadliga formulär lagras vanligtvis i mapparna Personligt formulärbibliotek eller Inkorgen.
  - Formuläret heter IPM. Obs! [eget namn].

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>Steg för att hitta tecken på den här attacken och bekräfta den

Du kan använda någon av följande metoder för att bekräfta attacken:

- Granska regler och formulär för varje postlåda manuellt med hjälp av Outlook-klienten. Den här metoden är noggrann, men du kan bara kontrollera en postlåda i taget. Den här metoden kan vara mycket tidskrävande om du har många användare att kontrollera och kan även smitta datorn du använder.

- Använd [ PowerShellGet-AllTenantRulesAndForms.ps1postskriptet ](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) för att automatisktdumpa alla vidarekopplingsregler och anpassade formulär för alla användare i ditt innehavare. Det här är den snabbaste och säkraste metoden med minsta möjliga overhead.

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>Bekräfta regelattacken med Outlook-klienten

1. Öppna outlook-klienten för användare som användare. Användaren kan behöva hjälp med att granska reglerna för postlådan.

2. I Hantera [e-postmeddelanden med hjälp av regelartikeln](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) finns procedurer för hur du öppnar regelgränssnittet i Outlook.

3. Leta efter regler som användaren inte har skapat eller oväntade regler eller regler med misstänkta namn.

4. Leta i regelbeskrivningen för regelåtgärder som startar och används i programmet, eller referera till en . EXE, . ZIP-fil eller för att starta en URL.

5. Leta efter nya processer som börjar använda process-ID för Outlook. Mer information [finns i Hitta process-ID.](/windows-hardware/drivers/debugger/finding-the-process-id)

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Steg för att bekräfta Forms-attacken med Outlook-klienten

1. Öppna Användarens Outlook-klient som användare.

2. Följ anvisningarna i [Visa fliken Utvecklare](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) för användarens version av Outlook.

3. Öppna den nu synliga utvecklarfliken i Outlook och klicka på **Designa ett formulär**.

4. Välj **Inkorgen** i **listan Leta i.** Leta efter eventuella anpassade formulär. Anpassade formulär är tillräckligt sällsynta för att det ska vara värt att titta närmare på anpassade formulär.

5. Undersök alla anpassade formulär, särskilt de som markerats som dolda.

6. Öppna alla anpassade formulär och klicka **på Visningskod** i **gruppen Formulär för** att se vad som körs när formuläret läses in.

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>Steg för att bekräfta attacken med Regler och formulär med PowerShell

Det enklaste sättet att verifiera en regel eller ett anpassat formulär-angrepp är att köra [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell-skript. Med det här skriptet ansluts alla postlådor i klientorganisationen och alla regler och formulär till två CSV-filer.

#### <a name="pre-requisites"></a>Förutsättningar

Du måste ha global administratörsbehörighet för att köra skriptet eftersom skriptet ansluter till varje postlåda i innehavare för att läsa regler och formulär.

1. Logga in på den dator som du kör skriptet från med lokala administratörsrättigheter.

2. Ladda ned eller Get-AllTenantRulesAndForms.ps1 skriptet från GitHub till en mapp som du ska köra det från. Skriptet skapar två datumstämplade filer i den här mappen, MailboxFormsExport-yyyy-mm-dd.csv och MailboxRulesExport-yyyy-mm-dd.csv.

3. Öppna en PowerShell-instans som administratör och öppna mappen där du sparade skriptet.

4. Kör den här PowerShell-kommandoraden enligt `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>Tolka utdata

- **MailboxRulesExport-*yyyy-mm-dd*.csv**: Undersök reglerna (en per rad) för åtgärdsvillkor som innehåller program eller körbara filer:

  - **ActionType (kolumn A)**: Om värdet "ID_ACTION_CUSTOM" visas är regeln sannolikt skadlig.

  - **IsViliallyMalicious (kolumn D)**: Om det här värdet är "SANT" är regeln sannolikt skadlig.

  - **ActionCommand (kolumn G)**: Om den här kolumnen visar ett program eller en fil med .exe- eller .zip-tillägg, eller en okänd post som refererar till en URL, är regeln sannolikt skadlig.

- **MailboxFormsExport-*yyyy-mm-dd*.csv**: I allmänhet är användningen av anpassade formulär sällsynta. Om det finns några i arbetsboken öppnar du den användarens postlåda och undersöker själva formuläret. Om organisationen inte lagt upp den där avsiktligt är den sannolikt skadlig.

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>Hur du stoppar och åtgärdar Outlook-regler och formulär-angrepp

Om du hittar bevis för någon av dessa attacker är det enkelt att åtgärda, bara ta bort regeln eller formuläret från postlådan. Du kan göra detta med Outlook-klienten eller med fjärr-PowerShell för att ta bort regler.

### <a name="using-outlook"></a>Använda Outlook

1. Identifiera alla enheter som användaren har använt med Outlook. Alla dessa måste rensas för eventuell skadlig programvara. Tillåt inte användaren att logga in och använda e-post förrän alla enheter har rensats.

2. Följ anvisningarna i [Ta bort en regel](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) för varje enhet.

3. Om du är osäker på om det finns annan skadlig programvara kan du formatera och installera om all programvara på enheten. För mobila enheter kan du följa tillverkarens anvisningar för att återställa enheten till fabriksbilden.

4. Installera de senaste versionerna av Outlook. Kom ihåg att den aktuella versionen av Outlook blockerar båda typerna av den här attacken som standard.

5. När alla offlinekopior av postlådan har tagits bort återställer du användarens lösenord (använd ett lösenord av hög kvalitet) och följer stegen i Konfigurera multifaktorautentisering för användare om MFA inte redan har aktiverats. [](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) Detta garanterar att användarens autentiseringsuppgifter inte exponeras på annat sätt (t.ex. nätfiske eller lösenordsanvändning).

### <a name="using-powershell"></a>Använda PowerShell

Det finns två PowerShell-fjärr cmdlets som du kan använda för att ta bort eller inaktivera skadliga regler. Följ bara anvisningarna.

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>Steg för postlådor som finns på en Exchange-server

1. Anslut till Exchange-servern med fjärr-PowerShell. Följ stegen i Ansluta [till Exchange-servrar med fjärr-PowerShell.](/powershell/exchange/connect-to-exchange-servers-using-remote-powershell)

2. Om du helt vill ta bort en enda regel, flera regler eller alla regler från en postlåda använder du cmdleten [Remove-InboxRule.](/powershell/module/exchange/Remove-InboxRule)

3. Om du vill behålla regeln och dess innehåll för vidare undersökning använder du cmdleten [Disable-InboxRule.](/powershell/module/exchange/disable-inboxrule)

#### <a name="steps-for-mailboxes-in-exchange-online"></a>Steg för postlådor i Exchange Online

1. Följ anvisningarna i [Ansluta till Exchange Online med PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Om du helt vill ta bort en enda regel, flera regler eller alla regler från en postlåda använder du cmdleten [Ta](/powershell/module/exchange/Remove-InboxRule) bort inkorgsregel.

3. Om du vill behålla regeln och dess innehåll för vidare undersökning använder du cmdleten [Disable-InboxRule.](/powershell/module/exchange/disable-inboxrule)

## <a name="how-to-minimize-future-attacks"></a>Hur du minimerar framtida attacker

### <a name="first-protect-your-accounts"></a>Först: skydda dina konton

Sårbarheterna i Regler och Formulär används bara av en attackerare efter att de har stulit eller brutit mot ett av dina användares konton. Därför är ditt första steg för att förhindra användningen av dessa sårbarheter mot din organisation att aggressivt skydda dina användarkonton. Några av de vanligaste sätten som konton bryter mot är nätfiske- eller [lösenordsattacker.](https://www.microsoft.com/security/blog/2020/04/23/protecting-organization-password-spray-attacks/)

Det bästa sättet att skydda användarkonton, och särskilt administratörskonton, är [att konfigurera multifaktorautentisering för användare.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) Du bör också:

- Övervaka hur användarkonton används [och används.](/azure/active-directory/active-directory-view-access-usage-reports) Du kan inte förhindra den första intrånget, men du förkortar varaktigheten och påverkan på intrånget genom att upptäcka det snabbare. Du kan använda dessa [Säkerhetsprinciper för Office 365 Cloud App för](/cloud-app-security/what-is-cloud-app-security) att övervaka dina konton och avisering om ovanlig aktivitet:

  - **Flera misslyckade inloggningsförsök:** Den här principen profilerar din miljö och utlöser aviseringar när användare utför flera misslyckade inloggningsaktiviteter i en enskild session med avseende på den inlärda baslinjen, vilket kan indikera ett försök till intrång.

  - **Omöjligt** att resa: De här principprofilerna din miljö och utlöser aviseringar när aktiviteter identifieras från samma användare på olika platser inom en tidsperiod som är kortare än den förväntade restiden mellan de två platserna. Det kan ange att en annan användare använder samma autentiseringsuppgifter. Om den upptäcker detta avvikande beteende krävs en inledande utbildningsperiod på sju dagar då den lär sig en ny användares aktivitetsmönster.

  - **Ovanliga imiterade aktiviteter (efter användare)**: Den här principen profilerar din miljö och utlöser aviseringar när användare utför flera imiterade aktiviteter i en enskild session med avseende på den grundläggande läran, vilket kan indikera ett försök till intrång.

- Använd ett verktyg som [Office 365 Secure Score](https://securescore.office.com/) för att hantera kontosäkerhetskonfigurationer och -beteenden.

### <a name="second-keep-your-outlook-clients-current"></a>För det andra: Håll Outlook-klienterna aktuella

Helt uppdaterade och korrigerade versioner av Outlook 2013 och 2016 inaktiverar som standard åtgärden "Starta program" regel/formulär. Detta säkerställer att även om en attack bryter mot kontot blockeras åtgärderna för regler och formulär. Du kan installera de senaste uppdateringarna och säkerhetskorrigeringarna genom att följa stegen i [Installera Office-uppdateringar.](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)

Här är korrigeringsversionerna för dina Outlook 2013- och 2016-klienter:

- **Outlook 2016**: 16.0.4534.1001 eller större.

- **Outlook 2013**: 15.0.4937.1000 eller större.

Mer information om de enskilda säkerhetskorrigeringarna finns i:

- [Säkerhetskorrigering för Outlook 2016](https://support.microsoft.com/help/3191883)

- [Säkerhetskorrigering för Outlook 2013](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>Tredje: Övervaka Dina Outlook-klienter

Observera att även med korrigeringar och uppdateringar installerade är det möjligt för en attackerare att ändra den lokala datorkonfigurationen och återaktivera beteendet "Starta program". Du kan använda [Avancerad grupprinciphantering för](/microsoft-desktop-optimization-pack/agpm/) att övervaka och tillämpa lokala datorprinciper på dina klienter.

Du kan se om "Starta program" har aktiverats på nytt via en åsidosättning i registret genom att använda informationen i Så här visar du systemregistret med hjälp av [64-bitarsversioner av Windows.](https://support.microsoft.com/help/305097) Kontrollera följande undernycklar:

- **Outlook 2016**: `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013**: `HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

Leta efter nyckeln EnableUnsafeClientMailRules. Om den finns där och är inställd på 1 har Säkerhetskorrigeringen för Outlook åsidosättts och datorn är sårbar för formulär/regler-attacken. Om värdet är 0 inaktiveras åtgärden "Starta program". Om den uppdaterade och korrigerade versionen av Outlook är installerad och den här registernyckeln inte finns, är ett system inte sårbart för dessa attacker.

Kunder med lokala Exchange-installationer bör överväga att blockera äldre versioner av Outlook som inte har några korrigeringar. Information om den här processen finns i artikeln Konfigurera [klientblockering i Outlook.](/exchange/configure-outlook-client-blocking-exchange-2013-help)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Skydda Microsoft 365 som en expert på cybersäkerhet

Din Microsoft 365-prenumeration innehåller kraftfulla säkerhetsfunktioner som du kan använda för att skydda dina data och dina användare. Använd [Säkerhetsöversikt för Microsoft 365 – de vanligaste prioriteringarna för de första 30 dagarna, 90 dagarna och bortom](security-roadmap.md) för att implementera Microsofts metodtips för att skydda din Microsoft 365-klientorganisation.

- Uppgifter som ska utföras under de första 30 dagarna. De har omedelbar effekt och är små påverkan på användarna.

- Uppgifter som ska utföras inom 90 dagar. De tar lite längre tid att planera och implementera men förbättrar din säkerhet avsevärt.

- Efter 90 dagar. De här förbättringarna uppnås under de första 90 dagarna.

## <a name="see-also"></a>Se även:

- [Malicious Outlook Rules](https://silentbreaksecurity.com/malicious-outlook-rules/) by SilentBreak Security Post about Rules Vector ger en detaljerad granskning av hur Outlook-regler.

- [MAPI over HTTP and Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) on the Sensepost blog about Mailrule Pwnage discusses a tool called Ruler that lets you exploit mailboxes through Outlook rules.

- [Outlook-formulär och skal på](https://sensepost.com/blog/2017/outlook-forms-and-shells/) Sensepost-bloggen om Forms Threat Vector.

- [Kodbas för linjal](https://github.com/sensepost/ruler)

- [Linjalindikatorer för kompromett](https://github.com/sensepost/notruler/blob/master/iocs.md)