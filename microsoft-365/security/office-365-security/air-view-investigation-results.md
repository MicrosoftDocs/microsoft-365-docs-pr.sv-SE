---
title: Visa resultatet av en automatisk undersökning i Microsoft 365
keywords: LUFT, autoIR, ATP, automatiserad, undersökning, svar, reparation, hot, Avancerat, hot, skydd
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Under och efter en automatiserad undersökning i Microsoft 365 kan du Visa resultaten och nyckeltalen.
ms.date: 11/05/2020
ms.openlocfilehash: 0f472c117ff1f6c2b563063d0eeb9a27cc5afebe
ms.sourcegitcommit: 24826e1b61e7aace12fc9e8ae84ae3e760658b50
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2020
ms.locfileid: "48931996"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a>Information och resultat från en automatiserad undersökning i Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


När en [Automatisk undersökning](office-365-air.md) sker i [Microsoft Defender för Office 365](office-365-atp.md)finns information om undersökningen under och efter den automatiska gransknings processen. Om du har nödvändig behörighet kan du Visa den informationen i säkerhets Center för Microsoft 365. Med utrednings uppgifter får du uppdaterade status och möjlighet att godkänna väntande åtgärder.

## <a name="investigation-status"></a>Gransknings status

Undersökningen visar analys och åtgärder. När undersökningen körs ändras statusen för att ange om hot hittades och om åtgärder har godkänts.

|Status|Beskrivning|
|:---|:---|
|**Startar** | Undersökningen har utlösts och väntar på att börja köras.|
|**Aktiv** | Undersökningen har påbörjats och är igång. Det här läget inträffar även när [väntande åtgärder](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-review-approve-pending-completed-actions#approve-or-reject-pending-actions) godkänns.|
|**Inga hot hittades** | Undersökningen har avslut ATS och inga hot (användar konto, e-postmeddelande, URL eller fil) har identifierats. <br/><br/>**Tips** : om du misstänker något missade något (till exempel ett falskt-negativt) kan du vidta åtgärder med hjälp av [Threat Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer).|
|**Hot Funna** |Den automatiska undersökningen hittade problem, men det finns inga särskilda åtgärder för att åtgärda problemen.<br/><br/> **Hot som upptäckts** kan uppstå när någon typ av användar aktivitet har identifierats men inga rensnings åtgärder är tillgängliga. Exemplen innehåller följande användar aktiviteter: <br/>-En händelse för att [förhindra data förlust](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) (DLP) <br/>-Ett e-postmeddelande som skickar avvikelse <br/>-Skickade skadlig kod <br/>-Skickat Phish<br/>Undersökningen hittade inga skadliga URL-adresser, filer eller e-postmeddelanden som ska åtgärdas, och det finns ingen aktivitets post låda att åtgärda, till exempel att inaktivera regler för vidarebefordran eller delegering. <br/><br/>**Tips** : om du misstänker något har missats (till exempel ett falskt negativt) kan du undersöka och vidta åtgärder med hjälp av [Threat Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer).|
|**Avslutat av systemet** | Undersökningen har stoppats. En undersökning kan avbrytas av olika anledningar:<br/>-Undersökningen har upphört att gälla. De pågående åtgärderna avslut ATS efter godkännande i en vecka. <br/>-Det finns för många åtgärder. Om det till exempel finns för många användare att klicka på skadliga URL-adresser kan undersökningen gå vidare med att köra alla analyser. <br/><br/>**Tips** : om en undersökning stannar innan åtgärderna vidtogs kan du försöka hitta och åtgärda hot genom att använda [Threat Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) .|
|**Pågående åtgärd** | Undersökningen har hittat ett hot, till exempel ett skadligt e-postmeddelande, en skadlig URL-adress eller en riskabel inställning, och en åtgärd för att åtgärda att hotet [väntar på godkännande](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-review-approve-pending-completed-actions).<br/><br/>Det **pågående åtgärds** tillståndet utlöses när ett hot mot en motsvarande åtgärd hittas. Men listan med väntande åtgärder kan öka när undersökningen körs. Kontrol lera om det finns andra objekt i [gransknings loggen](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#playbook-log) .|
|**Åtgärdat** | Undersökningen klar och alla reparations åtgärder godkändes (detta noteras som helt åtgärdat).<br/><br/>**Obs!** godkända reparations åtgärder kan ha fel som hindrar åtgärderna från att vidtas. Oberoende av om reparations åtgärder är slutförda ändras inte gransknings status. Kontrol lera i [gransknings loggen](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results) detaljerad information.|
|**Delvis åtgärdat**| Undersökningen ledde till reparations åtgärder och vissa godkändes och slutfördes. Andra åtgärder är fortfarande [väntande](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-review-approve-pending-completed-actions).|
|**Misslyckades** | Minst en undersöknings analys stötte på ett problem där det inte gick att slutföra den. <br/><br/>**Obs!** om en undersökning Miss lyckas efter att reparations åtgärderna godkändes kan reparations åtgärderna ändå ha lyckats. Kontrol lera i [gransknings loggen](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results) detaljerad information.|
|**Köade genom begränsning** | En undersökning sparas i en kö. När andra undersökningar har genomförts börjar den köade undersökningen. Begränsning för att undvika dålig tjänst prestanda. <br/><br/>**Tips** ! väntande åtgärder kan begränsa hur många nya undersökningar som kan utföras. Se till att [godkänna (eller avvisa) väntande åtgärder](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-review-approve-pending-completed-actions#approve-or-reject-pending-actions).|
|**Avbröts av begränsning** | Om en undersökning pågår i kön för länge stannar den. <br/><br/>**Tips** : du kan [starta en undersökning från hot Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).|
|

## <a name="view-details-of-an-investigation"></a>Visa information om en undersökning

1. Gå till säkerhets & Compliance Center ( [https://protection.office.com](https://protection.office.com) ) och logga in.

2. Gör något av följande:

    - Gå till **Threat management**  >  **instrument panelen** Threat Management. Då kommer du till [säkerhets instrument panelen](security-dashboard.md). Dina AIR-widgetar visas överst på [instrument panelen](security-dashboard.md). Välj en widget, till exempel **Sammanfattning av undersökningar**.

    - Gå till **Threat Management**  >  **utredningar**.

    Båda metoderna tar dig till en lista med utredningar.

    ![Allmän undersöknings sida för luft](../../media/air-maininvestigationpage.png)

3. I listan över undersökningar väljer du ett objekt i kolumnen **ID** . Då öppnas sidan med undersöknings information, som börjar med analys diagrammet i vyn.

    ![Diagram sida för flyg undersökning](../../media/air-investigationgraphpage.png)

   Använd flikarna för att lära dig mer om undersökningen.

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>Visa information om en avisering om en undersökning

Vissa typer av aviseringar utlöser automatiserad undersökning i Microsoft 365. Mer information finns i [aviserings principer som utlöser automatiserade utredningar](office-365-air.md#which-alert-policies-trigger-automated-investigations). 

Följ anvisningarna nedan om du vill visa information om en avisering som är kopplad till en automatisk undersökning.

1. Gå till säkerhets & Compliance Center ( [https://protection.office.com](https://protection.office.com) ) och logga in.

2. Gå till **Threat Management**  >  **utredningar**.

3. I listan över undersökningar väljer du ett objekt i kolumnen **ID** .

4. Välj fliken **aviseringar** om du vill ha information om en undersökning öppen. Alla larm som utlöste undersökningen visas här.

5. Markera ett objekt i listan. En utfällbara öppning öppnas med information om aviseringen och länkar till ytterligare information och åtgärder.

6. Granska informationen om den utfällda funktionen och beroende på vad du varnar **för kan du** utföra en åtgärd, till exempel **lösa** , Visa eller **meddela användare**.

    - **Matchning** är detsamma som att stänga en avisering

    - **Förhindra** att en princip utlöser aviseringar under en viss tids period

    - **Meddela användare** att ett e-postmeddelande med användarnas e-postadresser redan har angetts och gör det möjligt för säkerhets åtgärds gruppen att skriva ett meddelande till användarna. (Det här påminner om att skicka ett meddelande till mottagarna via [Threat Explorer](threat-explorer.md).)

## <a name="how-to-use-the-various-tabs"></a>Så här använder du de olika flikarna

I följande avsnitt beskrivs de olika flikarna på sidan automatiska undersökningar och hur du kan använda informationen.

### <a name="automated-investigations-page"></a>Sidan automatiserade undersökningar

Sidan automatiserade undersökningar visar organisationens utredningar och deras aktuella status.

![Allmän undersöknings sida för luft](../../media/air-maininvestigationpage.png)

Du kan:

- Navigera direkt till en undersökning (Välj ett **undersöknings-ID** ).

- Använd filter. Välj från **undersöknings typ** , **tidsintervall** , **status** eller en kombination av dessa.

- Exportera data till en CSV-fil.

### <a name="investigation-graph"></a>Undersökning

När du öppnar en viss undersökning ser du sidan för undersöknings diagram. På den här sidan visas alla de olika entiteterna: e-postmeddelanden, användare (och deras aktiviteter) och enheter som har utlösts automatiskt som en del av den.

![Diagram sida för flyg undersökning](../../media/air-investigationgraphpage.png)

Du kan:

- Få en visuell översikt över den aktuella undersökningen.

- Visa en sammanfattning av tiden för undersökningen.

- Välj en nod i visualiseringen för att visa information om noden.

- Välj en flik överst för att visa information om den aktuella fliken.

### <a name="alert-investigation"></a>Aviserings undersökning

På fliken **aviseringar** för en undersökning kan du se vilka meddelanden som är relevanta för undersökningen. Informationen inkluderar aviseringen som utlöste undersökningen och andra korrelerade aviseringar, till exempel riskfyllda inloggningar, DLP- [regler](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) , etc., som är korrelerade med undersökningen. Från den här sidan kan en säkerhetsanalytiker också visa mer information om enskilda aviseringar.

![Sidan AIR-aviseringar](../../media/air-investigationalertspage.png)

Du kan:

- Få en visuell översikt över den aktuella utlösnings aviseringen och eventuella associerade aviseringar.

- Välj en avisering i listan för att öppna en utskrivbar sida med fullständiga aviserings uppgifter.

### <a name="email-investigation"></a>E-postundersökning

På fliken **e-post** för en undersökning kan du se de ursprungliga e-postmeddelandena och de kluster med liknande e-post som identifieras som en del av undersökningen. På fliken **e-post** visas också e-postobjekt som är relaterade till undersökningen, till exempel de uppgifter som rapporter ATS via e-post, det ursprungliga e-postmeddelandet, e-zapped (n) som orsakas av skadlig program vara/Phish.

![Undersöknings sida för flyg e-post](../../media/air-investigationemailpage.png)

Med e-postundersökning kan du:

- Få en visuell översikt över de aktuella klustrade resultaten och hoten.

- Klicka på en klustrad enhet eller en hot lista om du vill öppna en utskrivbar sida med fullständiga aviserings uppgifter.

- Granska e-postklustret ytterligare genom att klicka på länken **Öppna i Utforskaren** högst upp på fliken **information om e-postkluster**

![LUFT undersöknings epost med utfällbara uppgifter](../../media/air-investigationemailpageflyoutdetails.png)

Med den skir volymen av e-post som användare i en organisation skickar och tar emot, samt multi-användarens natur för e-postkommunikation och attacker, kan följande process ta en avsevärd tid:

1. Klustra e-postmeddelanden baserat på liknande attribut från en rubrik, brödtext, URL-adress och bifogade filer

2. Avgränsa skadlig e-post från e-post

3. Åtgärd vid skadlig e-post

AIR automatiserar den här processen och sparar din organisations tid och arbets kraft. 

#### <a name="types-of-email-clusters"></a>Typer av e-postkluster

Tre olika typer av e-postkluster kan identifieras under e-postanalys steg: likhets kluster (alla utredningar), indikator kluster (alla utredningar) och post låda/användar kluster. I följande tabell beskrivs dessa typer av e-postkluster.

|E-postkluster  |Beskrivning  |
|---------|---------|
|Likhets kluster     |E-postmeddelanden som identifieras av jakt efter e-post med liknande avsändare och innehållsfiler. Dessa kluster utvärderas efter skadligt innehåll baserat på de ursprungliga identifierings resultaten. E-postkluster som innehåller tillräckligt många skadliga e-postidentifieringar betraktas som skadliga.         |
|Indikator kluster | E-postmeddelanden som identifieras av jakt för samma indikator enhet (fil-hash eller URL) från det ursprungliga e-postmeddelandet. När den ursprungliga filen/URL-enheten identifieras som skadlig, används Verdict för hela klustret med e-postmeddelanden som innehåller den personen. En fil som identifieras som skadlig program vara innebär att det kluster med e-postmeddelanden som innehåller filen behandlas som e-postmeddelanden med skadlig program vara. |
|Post låda/användar kluster | E-postmeddelanden som är relaterade till den användare som deltar i en användares kompromiss undersökning.  Dessa e-postkluster är för ytterligare analyser av teamet för säkerhets åtgärder och skapar inga åtgärder för reparation av e-post. <br/> Den komprometterade användar säkerhets Playbook granskar de e-postmeddelanden som skickas av användaren som analyseras för att förstå den potentiella effekten hos de e-postmeddelanden som skickas från post lådan. |

> [!NOTE]
> Målet med att klustra är att söka och hitta andra relaterade e-postmeddelanden som skickas av samma avsändare som en del av en attack eller en kampanj.  I vissa fall kan legitim e-post utlösa en undersökning (till exempel en användare rapporterar en marknadsförings-e-postadress).  I det här scenariot bör e-postklustringen identifiera att e-postkluster inte är skadliga – när det stämmer, det anger inget hot och rekommenderar **inte** att du tar bort e-post.

#### <a name="email-classifications"></a>E-postklassificeringar

När e-postmeddelanden analyseras klassificeras de som *skadlig* , *misstänkt* eller *ren* (som i, *inte identifieras som ett hot* ):

- *Skadlig e-post* som skickas från en post låda/användare indikerar potentiella problem med post lådan eller kontot. Andra användare/post lådor som kan påverka skadlig e-post som en del av en kompromiss visas.

- *Misstänkta e-postmeddelanden* som skickas av post lådan/användaren anger potentialen för ett komprometterat konto eller en oönskad e-postaktivitet. Dessa meddelanden innehåller eventuell spam/Mass utskick via e-post.

- *Ren e-post* (e-postmeddelanden som inte betraktas som ett hot) som skickas av post lådan/användaren kan tillhandahålla din säkerhets åtgärds grupp med en vy över legitima e-postmeddelanden skickade. Dessa e-postmeddelanden kan också innehålla data exfiltration om e-postkontot är angripet.

#### <a name="more-about-email-counts"></a>Mer om antalet e-postmeddelanden

Antalet e-postmeddelanden som identifieras på fliken e-post representerar den summa summan av alla e-post som visas på fliken **e-post** . Eftersom e-postmeddelanden finns i flera kluster är det totala antalet e-postmeddelanden som identifieras (och som påverkas av reparations åtgärder) antalet unika e-postmeddelanden som finns i alla klustr och ursprungliga mottagares e-postmeddelanden.

Både [Utforskaren](threat-explorer.md) och Air räknar e-postmeddelanden per mottagare, eftersom säkerhets verdicts, åtgärder och leverans platser kan variera per mottagare. Därför räknas ett ursprungligt e-postmeddelande till tre användare som totalt tre e-postmeddelanden i stället för ett e-postmeddelande. 

Det kan hända att ett e-postmeddelande räknas två eller fler gånger, till exempel när ett e-postmeddelande har flera åtgärder, eller när det finns flera kopior av e-postmeddelandet när alla åtgärder utförs. 

Ett e-postmeddelande med skadlig kod som identifieras vid leverans kan till exempel resultera i både ett blockerat e-postmeddelande och ett e-postmeddelande (hot-fil ersatt med en varnings fil). Eftersom det finns två kopior av e-postmeddelandet i systemet, kan båda räknas i antal kluster.

> [!IMPORTANT]
> Här är några saker du bör tänka på:
> 
> - Antalet e-postmeddelanden beräknas vid tiden för undersökningen och vissa räknare beräknas om när du öppnar undersökningen flyouts (baserat på en underliggande fråga). 
> 
> - Antalet e-postmeddelanden som visas för e-postkluster på fliken **e-post** och antalet e-postuppgifter som visas i utfällda kluster beräknas vid tiden för undersökningen och inte ändras. 
> 
> - Antalet e-postkonton visas längst ned på fliken **e** -post i e-postklustret och antalet e-postmeddelanden som visas i Utforskaren visar de e-postmeddelanden som tagits emot efter den första analysen. 

Därför visar ett e-postkluster som visar en ursprunglig mängd om 10 e-postmeddelanden en total e-postlista med totalt 15 om fem fler e-postmeddelanden tas mellan undersökningen analys fas och när administratören granskar undersökningen. Dessutom kan gamla undersökningar komma att visa mer än vad Explorer frågar visar, eftersom data i Microsoft Defender för Office 365 abonnemang 2 upphör efter sju dagar för utvärderings versioner och efter 30 dagar för betalda licenser.  

Visar både historiska och aktuella räkningar i olika vyer för att ange e-posteffekten vid tiden för undersökningen och den aktuella påverkan fram till den tid då åtgärden körs.

> [!NOTE]
> I kontexten för e-post kan det hända att en volym avvikelse hotet visas som en del av undersökningen. En volym avvikelse anger en ökning i liknande e-postmeddelanden kring händelse tiden jämfört med tidigare tidsintervall. Den här insamling i e-posttrafik med liknande egenskaper (t. ex. ämne och avsändare, kropps likhet och avsändare) är typiskt att starta kampanjer och attacker. Men Mass utskick, skräp post och legitima e-postkampanjer delar ofta dessa egenskaper. 
>
> Volym avvikelser representerar ett potentiellt hot och kan därför bli mindre allvarligt jämfört med skadlig program vara eller Phish hot som identifieras med Antivirus motorer, spräng eller skadligt rykte.

### <a name="user-investigation"></a>Användar undersökning

På fliken **användare** ser du alla användare som identifieras som en del av undersökningen. Användar konton visas i undersökningen när det finns en händelse eller om att dessa användar konton kan påverkas eller angripas.

I följande bild innehåller AIR dessutom indikatorer för kompromisser och avvikelser baserat på en ny regel för Inkorgen som skapats. Ytterligare uppgifter (bevis) för undersökningen är tillgängliga via detaljerade vyer på den här fliken. Indikatorer för kompromisser och avvikelser kan också inkludera avvikelser från [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).

![Sidan användare av flyg utredning](../../media/air-investigationuserspage.png)

Du kan:

- Få en visuell översikt över identifierade användar resultat och risker.

- Välj en användare för att öppna en utskrivbar sida med fullständiga aviserings uppgifter.

### <a name="machine-investigation"></a>Dator undersökning

På fliken **datorer** kan du se alla datorer som identifieras som en del av undersökningen.

![Sidan AIR-prövnings maskin](../../media/air-investigationmachinepage.png)

Som en del av vissa playbooks, korrelerar AIR e-posthoten med enheter (till exempel zapped). En undersökning skickar till exempel ett skadligt filhash till [Microsoft Defender för slut punkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) för att undersöka det. Detta möjliggör automatisk undersökning av relevanta maskiner för användarna, för att se till att hot adresseras både i molnet och i alla dina slut punkter.

Du kan:

- Få en visuell översikt över de aktuella datorerna och hoten.

-  Välj en dator för att öppna en vy i motsvarande [Microsoft Defender för slut punkts undersökningar](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) i Microsoft Defender säkerhets Center.

### <a name="entity-investigation"></a>Undersökning av enheten

På fliken **entiteter** kan du se vilka enheter som identifieras och analyseras som en del av undersökningen.

Här kan du se undersökta enheter och information om typer av enheter, till exempel e-postmeddelanden, kluster, IP-adresser, användare och mycket annat. Du kan också se hur många enheter som analyser ATS och vilka hot som var kopplade till var och en.

![Sidan flyg undersöknings enheter](../../media/air-investigationentitiespage.png)

Du kan:

- Få en visuell översikt över undersöknings enheter och hot Funna.

- Välj en entitet för att öppna en utskrivbar sida med information om relaterade enheter.

![Information om flyg undersöknings enheter](../../media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a>Playbook logg

På fliken **logg** kan du se alla Playbook-steg som inträffade under undersökningen. Loggen fångar en fullständig inventering av alla analyser och åtgärder som slutförts av Office 365-funktionen för automatisk granskning som del av flyg. Det ger en översikt över alla stegen, inklusive själva åtgärden, en beskrivning och varaktigheten för det faktiska värdet från början till slut.

![Sidan för flyg Gransknings logg](../../media/air-investigationlogpage.png)

Du kan:

- Få en visuell översikt över de Playbook stegen.

- Exportera resultaten till en CSV-fil.
- Filtrera vyn.

### <a name="recommended-actions"></a>Rekommenderade åtgärder

På fliken **åtgärder** kan du se alla Playbook-åtgärder som rekommenderas för korrigeringen när undersökningen har genomförts. Åtgärder som fångar de steg som Microsoft rekommenderar att du gör i slutet av en undersökning. Du kan utföra reparations åtgärder här genom att välja en eller flera åtgärder. 

Om du väljer **Godkänn** tillåts reparation att starta. (Lämplig behörighet krävs-rollen för **sökning och rensning** krävs för att köra åtgärder från UTFORSKAREN och Air). 

En säkerhets läsare kan till exempel Visa åtgärder, men inte godkänna dem. 

> [!IMPORTANT]
> Du behöver inte godkänna varje åtgärd. Om du inte samtycker till den rekommenderade åtgärden eller om din organisation inte väljer vissa typer av åtgärder kan du välja att **avvisa** åtgärderna eller helt enkelt ignorera dem och inte vidta någon åtgärd. Om du godkänner och/eller avvisar alla åtgärder kan undersökningen avslutas helt och hållet (status blir åtgärdat), men om du lämnar vissa åtgärder ofullständiga, så ändras undersöknings status till ett delvis åtgärdat tillstånd.

![Åtgärds sidan flyg undersökningar](../../media/air-investigationactionspage.png)

Du kan:

- Få en visuell översikt över de rekommenderade Playbook åtgärderna.

- Välj en eller flera åtgärder.

- Godkänn eller avvisa rekommenderade åtgärder med kommentarer.

- Exportera resultaten till en CSV-fil.

- Filtrera vyn.

## <a name="next-steps"></a>Nästa steg

- [Granska och godkänna pågående åtgärder](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)

