---
title: Konfigurera och hantera Microsoft Threat Experts-funktioner
ms.reviewer: ''
description: Registrera dig hos Microsoft Threats-experter för att konfigurera, hantera och använda det i dina dagliga säkerhetsåtgärder och säkerhetsadministration.
keywords: Microsoft Threat Experts, hanterad hot-service, MTE, Microsoft hanterad service för fiske
search.product: Windows 10
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b578436522998ba88cb58f29c5e303ebe0b1ce45
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166107"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities"></a>Konfigurera och hantera Microsoft Threat Experts-funktioner

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="before-you-begin"></a>Innan du börjar 
> [!NOTE]
> Diskutera kraven för berättigande med din Microsoft-leverantör och ditt kontoteam innan du tillämpar på Microsoft Threat Experts – Riktad attackavisering hanterad säkerhetstjänst för hot.

Se till att du har Defender för slutpunkt distribuerad i din miljö med registrerade enheter och inte bara på en miljö.

Om du är Defender för slutpunktskund måste du söka efter **Microsoft Threat Experts – Riktade** attackmeddelanden för att få särskilda insikter och analyser som hjälper dig att identifiera de viktigaste hoten, så att du kan svara på dem snabbt. Kontakta ditt kontoteam eller din Microsoft-representant för att prenumerera på **Microsoft Threat Experts – Experts on Demand** och rådgör med våra hotexperter om relevanta identifieringar och adversaries.

## <a name="apply-for-microsoft-threat-experts---targeted-attack-notifications-service"></a>Sök efter Microsoft Threat Experts – riktad tjänst för attackmeddelanden 
Om du redan är Defender för Slutpunktskund kan du använda den via Microsoft Defender Säkerhetscenter. 

1. I navigeringsfönstret går du till Inställningar **> Allmänt > avancerade > Microsoft Threat Experts – Riktade attackmeddelanden.**

2. Klicka på **Använd**.

    ![Bild av inställningar för Microsoft Threat Experts](images/mte-collaboratewithmte.png)

3. Ange ditt namn och din e-postadress så att Microsoft kan kontakta dig i programmet.

    ![Bild på programmet Microsoft Threat Experts](images/mte-apply.png)

4. Läs [sekretesspolicyn och](https://privacy.microsoft.com/en-us/privacystatement)klicka sedan på **Skicka** när du är klar. Du får ett välkomstmeddelande via e-post när din ansökan har godkänts.

    ![Bild på programbekräftelse från Microsoft Threat Experts](images/mte-applicationconfirmation.png)

När du accepterar får du ett välkomstmeddelande  via e-post och du ser knappen Använd ändras till en växlingsknapp som är "på". Om du vill ta dig själv från tjänsten Riktad attackmeddelanden drar du reglaget "av" och klickar på Spara **inställningar** längst ned på sidan. 

## <a name="where-youll-see-the-targeted-attack-notifications-from-microsoft-threat-experts"></a>Var du ser riktade attackmeddelanden från Microsoft Threat Experts 
Du kan få riktade attackmeddelanden från Microsoft Threat Experts via följande medium:  
- Sidan Incidenter för Defender för **Slutpunktsportalen** 
- Instrumentpanelen Aviseringar i Defender för **Slutpunktsportalen**  
- OData-avisering för [API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/get-alerts) och [REST API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)
- [DeviceAlertEvents-tabell](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) i Avancerad sökning
- Din e-post, om du väljer att konfigurera den 

Om du vill ta emot riktade attackmeddelanden via e-post skapar du en regel för e-postavisering.

### <a name="create-an-email-notification-rule"></a>Skapa en regel för e-postavisering 
Du kan skapa regler för att skicka e-postaviseringar för aviseringsmottagare. Mer  [information finns i Konfigurera](configure-email-notifications.md) aviseringsmeddelanden för att skapa, redigera, ta bort eller felsöka e-postaviseringar.

## <a name="view-the-targeted-attack-notification"></a>Visa meddelandet om riktad attack  
Du kommer att få riktade attackmeddelanden från Microsoft Threat Experts i e-postmeddelandet när du har konfigurerat ditt system för att ta emot e-postaviseringar.  

1. Klicka på länken i e-postmeddelandet för att gå till motsvarande aviseringskontext i instrumentpanelen som är märkt **med hotexperter.** 

2. På instrumentpanelen väljer du samma aviseringsavsnitt som du fick i e-postmeddelandet för att visa informationen.  

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a>Prenumerera på Microsoft Threat Experts – experter på begäran
Det här är tillgängligt som en prenumerationstjänst. Om du redan är Defender för Endpoint-kund kan du kontakta din Microsoft-representant för att prenumerera på Microsoft Threat Experts – Experts on Demand. 

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a>Kontakta en Microsoft-expert om misstänkt cybersäkerhet i din organisation 
Du kan samarbeta med Microsoft Threat Experts som kan vara direkt engagerade i Microsoft Defender Säkerhetscenter för att få snabba och korrekta svar. Experter tillhandahåller insikter för att bättre förstå komplexa hot, riktade attackmeddelanden som du får eller om du behöver mer information om aviseringar, en potentiellt komprometterad enhet eller ett informationssammanhang för hot som visas på din portalinstrumentpanel. 

> [!NOTE]
> - Vi har för närvarande inte stöd för förfrågningar som rör din organisations anpassade hotinformation. Kontakta din säkerhetsgrupp eller ditt svarsteam för incidenter.
> - Du måste ha behörigheten **Hantera** säkerhetsinställningar i Säkerhetscenter-portalen för att kunna skicka en förfrågan om att "Kontakta en hotexpert".

1. Gå till portalsidan med relevant information som du vill undersöka, till exempel **sidan Incident.** Kontrollera att sidan för den relevanta aviseringen eller enheten visas innan du skickar en undersökningsförfrågan. 

2. I den övre högra menyn klickar du på **?** . Välj sedan **Rådgör med en hotexpert**. 

    ![Bild på Microsoft Threat Experts Experts på begäran från menyn](images/mte-eod-menu.png)

    En utfälld skärm öppnas. Följande skärm visas när du använder en utvärderingsprenumeration.

    ![Bild på skärmen Microsoft Threat Experts experts on Demand](images/mte-eod.png)

    Följande skärm visar när du har en komplett Prenumeration på Microsoft Threat Experts – Experter på begäran.

    ![Bild av Microsoft Threat Experts Experts on Demand i helprenumeration](images/mte-eod-fullsubscription.png)

    Fältet **Inquiry topic** är förifylld med länken till den relevanta sidan för din undersökningsförfrågan. Till exempel en länk till sidan incident, avisering eller enhetsinformation som du var på när du gjorde begäran.

3.  I nästa fält bör du ge Microsoft Threat Experts tillräckligt med information för att starta undersökningen.
  
4. Ange den e-postadress som du vill använda för att stämma av med Microsoft Threat Experts.

> [!NOTE]
> Om du vill spåra statusen för ärenden för experter på begäran via Microsoft Services Hub kan du kontakta din Technical Account Manager. 

Titta på den här videon för en snabb överblick över Microsoft Services-hubben.

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f] 


   
## <a name="sample-investigation-topics-that-you-can-consult-with-microsoft-threat-experts---experts-on-demand"></a>Exempel på undersökningsämnen som du kan rådgöra med Microsoft Threat Experts – Experter på begäran 

**Aviseringsinformation**
- Vi ser en ny typ av avisering för binär aningen off-the-land: [AlertID]. Kan du berätta något mer om den här aviseringen och hur vi kan undersöka ytterligare?
- Vi har observerat två liknande attacker som försöker köra skadliga PowerShell-skript men generera olika aviseringar. Den ena är "Misstänkt PowerShell-kommandorad" och den andra är "En skadlig fil upptäcktes baserat på indikering från O365". Vad är skillnaden?
- Jag får en udda avisering idag om felaktigt antal misslyckade inloggningar från en användares enhet. Jag kan inte hitta några ytterligare bevis för dessa inloggningsförsök. Hur kan Defender för Endpoint se de här försöken? Vilken typ av inloggning övervakas?
- Du kan ge mer kontext eller insikter om den här aviseringen: "Misstänkt beteende hos ett systemverktyg har observerats". 

**Möjlig datorkompromettering**
- Kan du svara på varför vi ser "Okänd process observerad?" Det här meddelandet eller meddelandet visas ofta på många enheter. Vi uppskattar eventuella synpunkter för att klargöra om det här meddelandet eller aviseringen är relaterat till skadlig aktivitet.
- Kan du verifiera en möjlig intrång i följande system [datum] med liknande beteenden som den tidigare identifieringen av skadlig programvara för samma system under [månad]?

**Information om hotinformation**
- Vi har upptäckt ett nätfiskemeddelande som levererade ett skadligt Word-dokument till en användare. Det skadliga Word-dokumentet orsakade en serie misstänkta händelser som utlöste flera Microsoft Defender-varningar för skadlig programvara (malware name). Har du någon information om den här skadlig programvara? Om ja, kan du skicka mig en länk?
- Jag såg nyligen en referens från [sociala medier, till exempel Twitter eller en blogg] om ett hot som riktar sig till min bransch. Kan du hjälpa mig förstå vilket skydd Defender för Endpoint tillhandahåller mot den här hotspelaren? 

**Aviseringsmeddelanden från Microsoft Threat Experts** 
- Kan ditt svarsteam för incidenter hjälpa oss att hantera det riktade attackmeddelandet vi fick?
- Jag fick den här riktade attackmeddelandet från Microsoft Threat Experts. Vi har inte vårt eget svarsteam för incidenter. Vad kan vi göra nu och hur kan vi begränsa händelsen?
- Jag fick ett meddelande om riktad attack från Microsoft Threat Experts. Vilka data kan du ge oss som vi kan skicka till vårt svarsteam för incidenter?

  >[!NOTE]
  >Microsoft Threat Experts är en hanterad säkerhetstjänst för cybersäkerhet och inte en incidenttjänst. Vid behov kan experterna vid behov smidigt gå över undersökningen till TJÄNSTEN Microsoft Cybersecurity Solutions Group (CSG) för tjänsten Detection and Response Team (PHOTOSHOP). Du kan också välja att kommunicera med din egen svarsgrupp för incidenter för att åtgärda problem som kräver ett incidentsvar. 

## <a name="scenario"></a>Scenario

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a>Få en förloppsrapport om din förfrågan om hanterad förfrågan 
Svaret från Microsoft Threat Experts varierar beroende på din förfrågan. De skickar en förloppsrapport  via e-post till dig om en expert på hot inom två dagar för att informera om undersökningsstatus från följande kategorier: 
- Mer information krävs för att fortsätta med undersökningen 
- Det krävs en eller flera filexempel för att avgöra det tekniska sammanhanget 
- Undersökning kräver mer tid   
- Den inledande informationen var tillräcklig för att slutföra undersökningen 

Det är centralt att du svarar snabbt för att hålla undersökningen i rörelse. 

## <a name="related-topic"></a>Relaterade ämnen
- [Översikt över Microsoft Threat Experts](microsoft-threat-experts.md)
