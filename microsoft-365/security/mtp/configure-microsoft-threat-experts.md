---
title: Konfigurera och hantera Microsoft Threat Experts-funktioner via Microsoft 365 Defender
description: Prenumerera på Microsoft Threats Experts via Microsoft 365 Defender för att konfigurera, hantera och använda det i dina dagliga säkerhetsåtgärder och säkerhetsadministration.
keywords: Microsoft Threat Experts, hanterad hot-service, MTE, Microsoft hanterad service för fiske
search.product: Windows 10
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-maave
author: martyav
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.topic: article
ms.openlocfilehash: e1ccd4404eb94193695239def7f26ba64e70d51d
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476575"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities-through-microsoft-365-defender"></a>Konfigurera och hantera Microsoft Threat Experts-funktioner via Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!INCLUDE [Prerelease](../includes/prerelease.md)]

## <a name="before-you-begin"></a>Innan du börjar

> [!IMPORTANT]
> Innan du ansöker kontrollerar du att du tar upp behörighetskraven för Microsoft Threat Experts – Targeted Attack Notifications som hanteras av din Microsoft Technical Service-leverantör och ditt kontoteam.

Om du vill ta emot riktade attackmeddelanden måste du ha Microsoft 365 Defender distribuerat med registrerade enheter. Skicka sedan ett program via M365-portalen för Microsoft Threat Experts – Riktade attackmeddelanden.

Kontakta ditt kontoteam eller din Microsoft-representant för att prenumerera på Microsoft Threat Experts – Experts on Demand. Med experter på begäran kan du rådgöra med våra hotexperter om hur du skyddar organisationen från relevanta identifieringar och adversaries.

## <a name="apply-for-microsoft-threat-experts---targeted-attack-notifications-service"></a>Sök efter Microsoft Threat Experts – riktad tjänst för attackmeddelanden

Om du redan har Microsoft Defender för Endpoint och Microsoft 365 Defender kan du ansöka om Microsoft Threat Experts – Targeted Attack Notifications via Microsoft 365 Defender-portalen.  Riktade attackmeddelanden ger dig särskilda insikter och analyser som hjälper dig att identifiera de viktigaste hoten för din organisation, så att du kan svara på dem snabbt.

1. I navigeringsfönstret går du till Inställningar **> slutpunkter > Allmänna > avancerade > Microsoft Threat Experts – Riktade attackmeddelanden.**

2. Välj **Använd**.

    ![Bild av inställningar för Microsoft Threat Experts](../../media/mte/mte-collaboratewithmte.png)

3. Ange ditt namn och din e-postadress så att Microsoft kan kontakta dig om programmet.

    ![Bild på programmet Microsoft Threat Experts](../../media/mte/mte-apply.png)

4. Läs [sekretesspolicyn](https://privacy.microsoft.com/en-us/privacystatement)och välj sedan **Skicka** när du är klar. Du får ett välkomstmeddelande via e-post när din ansökan har godkänts.

    ![Bild på programbekräftelse från Microsoft Threat Experts](../../media/mte/mte-applicationconfirmation.png)

5. När du får välkomstmeddelandet får du automatiskt riktade attackmeddelanden.

6. Du kan kontrollera din status genom att gå **till Inställningar > Slutpunkter > Allmänt > Avancerade funktioner.** När den godkänts **kommer Microsoft Threat Experts – Targeted Attack Notification-knappen** att visas och vara **påslagen.**

## <a name="where-youll-see-the-targeted-attack-notifications-from-microsoft-threat-experts"></a>Var du ser riktade attackmeddelanden från Microsoft Threat Experts

Du kan få riktade attackmeddelanden från Microsoft Threat Experts via följande medium:

- Sidan Incidenter på Microsoft 365 **Defender-portalen**
- Instrumentpanelen Aviseringar på Microsoft 365 **Defender-portalen**
- OData-avisering för [API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/get-alerts) och [REST API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)
- [DeviceAlertEvents-tabell](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) i Avancerad sökning
- Din inkorg om du väljer att få riktade attackmeddelanden skickade till dig via e-post. Se Skapa [en regel för e-postavisering](#create-an-email-notification-rule) nedan.

### <a name="create-an-email-notification-rule"></a>Skapa en regel för e-postavisering

Du kan skapa regler för att skicka e-postaviseringar för aviseringsmottagare. Fullständig information finns i Konfigurera  [aviseringsmeddelanden för](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) att skapa, redigera, ta bort eller felsöka e-postaviseringar.

## <a name="view-targeted-attack-notifications"></a>Visa riktade attackmeddelanden

Du kommer att få riktade attackmeddelanden från Microsoft Threat Experts i e-postmeddelandet när du har konfigurerat ditt system för att ta emot e-postaviseringar.

1. Välj länken i e-postmeddelandet för att gå till motsvarande aviseringskontext i instrumentpanelen som är märkt **med hotexperter.**

2. Välj  samma aviseringsavsnitt på sidan Aviseringar som i e-postmeddelandet om du vill visa mer information.

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a>Prenumerera på Microsoft Threat Experts – experter på begäran

Om du redan är Microsoft Defender för Endpoint-kund kan du kontakta din Microsoft-representant för att prenumerera på Microsoft Threat Experts – Experts on Demand.

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a>Kontakta en Microsoft-expert om misstänkt cybersäkerhet i din organisation

Du kan kontakta Microsoft Threat Experts inifrån Microsoft 365 Defender-portalen. Experter kan hjälpa dig att förstå komplexa hot och riktade attackmeddelanden. Samarbeta med experter för mer information om aviseringar och incidenter, eller råd om hantering av komprometteringar. Få insyn i det hotinformationssammanhang som beskrivs av din portalinstrumentpanel.

> [!NOTE]
>
> - Aviseringsförfrågningar som rör din organisations anpassade hotinformation stöds inte för närvarande. Kontakta din säkerhets- eller svarsgrupp för incidenter för mer information.
> - Du måste ha  behörigheten Hantera säkerhetsinställningar i Säkerhetscenter i Microsoft 365 Defender-portalen för att skicka en förfrågan via Formuläret Konsultera en expert **på** hot.

1. Gå till portalsidan som är relaterad till den information som du vill **undersöka:** till exempel **Enhet,** **Avisering** eller Incident. Kontrollera att portalsidan som är relaterad till din förfrågan visas innan du skickar en undersökningsförfrågan.

2. I den översta menyn väljer du **? Kontakta en hotexpert**.

    ![Bild på Microsoft Threat Experts Experts på begäran från menyn](../../media/mte/incidents-action-mte-highlighted.png)

    En utfälld skärm öppnas.

    Sidhuvudet anger om du använder en utvärderingsprenumeration eller en komplett Microsoft Threat Experts – Experts on-Demand-prenumeration.

    ![Bild på utvärderingsprenumerationsskärmen med Microsoft Threat Experts on Demand](../../media/mte/mte-trial.png)

    Fältet **Undersökningsämne** innehåller redan länken till den aktuella sidan för din begäran.

3. I nästa fält bör du ge Microsoft Threat Experts tillräckligt med information för att starta undersökningen.

4. Ange den e-postadress som du vill använda för att stämma av med Microsoft Threat Experts.

> [!NOTE]
> Om du vill spåra status för ärenden av den tekniska experten på begäran via Microsoft Services Hub kan du kontakta din tekniska kontohanterare.

Titta på den här videon för en snabb överblick över Microsoft Services-hubben.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f]

## <a name="sample-investigation-topics"></a>Exempel på undersökningsavsnitt

### <a name="alert-information"></a>Aviseringsinformation

- Vi såg en ny typ av varning för en binär bo-off-the-land binär. Vi kan ange aviserings-ID:t. Kan du berätta mer om den här aviseringen och hur vi kan undersöka den ytterligare?
- Vi har observerat två liknande attacker som båda försöker köra skadliga PowerShell-skript men generera olika aviseringar. Den ena är "Misstänkt PowerShell-kommandorad" och den andra är "En skadlig fil upptäcktes baserat på indikering från O365". Vad är skillnaden?
- Vi fick en udda avisering idag om ett felaktigt antal misslyckade inloggningar från en användares enhet. Vi hittar inga ytterligare bevis för försöken. Hur kan Microsoft 365 Defender se de här försöken? Vilken typ av inloggning övervakas?
- Kan du ge mer kontext eller information om aviseringen, "Misstänkt beteende av ett systemverktyg har observerats"?
- Jag har sett en avisering med namnet "Skapande av vidare vidarebefordran/omdirigeringsregel". Jag tror att aktiviteten är sann. Kan du berätta varför jag fick en avisering?

### <a name="possible-machine-compromise"></a>Möjlig datorkompromettering

- Kan du hjälpa dig att förklara varför vi ser ett meddelande eller en avisering om att "okänd process observeras" på många enheter i vår organisation? Vi uppskattar eventuella synpunkter för att klargöra om det här meddelandet eller aviseringen är relaterat till skadlig aktivitet.
- Kan du verifiera en möjlig kompromett på följande system, från förra veckan? Det fungerar ungefär som en tidigare identifiering av skadlig programvara på samma system för sex månader sedan.

### <a name="threat-intelligence-details"></a>Information om hotinformation

- Vi har upptäckt ett nätfiskemeddelande som levererade ett skadligt Word-dokument till en användare. Dokumentet orsakade en serie misstänkta händelser, vilket utlöste flera aviseringar för en viss skadlig programvara-familj. Har du någon information om den här skadlig programvara? Om ja, kan du skicka oss en länk?
- Vi såg nyligen ett blogginlägg om ett hot som riktar sig till vår bransch. Kan du hjälpa oss att förstå vilket skydd Microsoft 365 Defender ger mot den här hot aktören?
- Vi har nyligen observerat en nätfiskekampanj som utförts mot vår organisation. Kan du tala om för oss om detta var specifikt riktat till vårt företag eller lodrätt?

### <a name="microsoft-threat-experts-alert-communications"></a>Aviseringsmeddelanden från Microsoft Threat Experts

- Kan ditt svarsteam för incidenter hjälpa oss att hantera det riktade attackmeddelandet vi fick?
- Vi har fått den här riktade attackmeddelandet från Microsoft Threat Experts. Vi har inte vårt eget svarsteam för incidenter. Vad kan vi göra nu och hur kan vi begränsa händelsen?
- Vi har fått en riktad attackavisering från Microsoft Threat Experts. Vilka data kan du ge oss som vi kan skicka till vårt svarsteam för incidenter?

> [!NOTE]
> Microsoft Threat Experts är en hanterad tjänst för hot efter hot och inte en svarstjänst för incidenter. Vid behov kan experterna vid behov smidigt gå över undersökningen till TJÄNSTEN Microsoft Cybersecurity Solutions Group (CSG) för tjänsten Detection and Response Team (PHOTOSHOP). Du kan också välja att kommunicera med din egen svarsgrupp för incidenter för att åtgärda problem som kräver ett incidentsvar.

## <a name="scenario"></a>Scenario

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a>Få en förloppsrapport om din förfrågan om hanterad förfrågan

Svaret från Microsoft Threat Experts varierar beroende på din förfrågan. I allmänhet får du något av följande svar:

- Mer information krävs för att fortsätta med undersökningen
- Det krävs en eller flera filexempel för att avgöra det tekniska sammanhanget
- Undersökning kräver mer tid
- Den inledande informationen var tillräcklig för att slutföra undersökningen

Om en expert begär mer information eller filprov är det centralt att svara snabbt för att hålla undersökningen igång.

## <a name="see-also"></a>Se även

- [Översikt över Microsoft Threat Experts](microsoft-threat-experts.md)
