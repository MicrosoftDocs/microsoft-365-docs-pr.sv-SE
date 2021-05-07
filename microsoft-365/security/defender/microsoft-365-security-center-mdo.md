---
title: Microsoft Defender för Office 365 i Microsoft 365 Säkerhetscenter
description: Läs om ändringar från Säkerhets- och efterlevnadscenter för Office 365 till Microsoft 365 Säkerhetscenter.
keywords: 'Microsoft 365 säkerhet: Komma igång med säkerhetscentret i Microsoft 365, Microsoft Defender för Office 365, Microsoft Defender för slutpunkt, MDO, MDE, en fönsterruta av glas, ny säkerhetsportal, den nya säkerhetsportalen för Defender'
ms.date: 02/21/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.prod: m365-security
ms.technology: m365d
ms.openlocfilehash: 62a917b36355335c8eb52d83caecdbba691f8175
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52242138"
---
# <a name="microsoft-defender-for-office-365-in-the-microsoft-365-security-center"></a>Microsoft Defender för Office 365 i Microsoft 365 Säkerhetscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender för Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)

Det förbättrade [Microsoft 365 Säkerhetscenter](./overview-security-center.md) i [https://security.microsoft.com](https://security.microsoft.com) kombinerar säkerhetsfunktioner från befintliga säkerhetsportaler i Microsoft, bland annat Microsoft Defender Säkerhetscenter och Säkerhets- och efterlevnadscenter för Office 365. Det här förbättrade centret hjälper säkerhetsteam att skydda organisationen från hot mer produktivt och effektivt.

Om du är bekant med Office 365 Säkerhets- och efterlevnadsportal (protection.office.com) beskriver den här artikeln några av ändringarna och förbättringarna i Microsoft 365 Säkerhetscenter.

Läs mer om fördelarna: [Översikt för Microsoft 365 Säkerhetscenter](overview-security-center.md)

Om du letar efter efterlevnadsrelaterade objekt kan du gå till [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com/homepage).

## <a name="whats-changed"></a>Se vad som har ändrats

Den här tabellen är en snabbreferens för områdena e-post och samarbete där ändringar har gjorts mellan **Säkerhets- och efterlevnadscenter** och **Microsoft 365 Säkerhets** portalen. Klicka på länkarna om du vill läsa mer om dessa områden.

<br>

****

|Område|Beskrivning av ändring|
|---|---|
|[Sidan E-postenhet](../office-365-security/mdo-email-entity-page.md)|Den här sidan **förenar** information om e-postmeddelanden som varit utspridda över olika sidor eller vyer tidigare. Undersökning av e-post efter hot och trender är *centraliserat*. Rubrikinformation och förhandsgranskning av e-post kan nås via samma e-postsida och annan användbar e-postrelaterad information. På samma sätt kan detonationsstatus för skadliga bifogade filer eller URL-adresser finnas på en flik på samma sida. Sidan E-postenhet ger administratörer och säkerhetsteam möjlighet att förstå ett hot via e-postmeddelande och dess status, snabbt, och sedan agera för att snabbt avgöra hur hanteringen ska hanteras.|
|[Undersökning](../office-365-security/office-365-air.md#changes-are-coming-soon-in-your-security-center)|Samlar AIR-funktioner i [Defender för Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) och [Defender för Endpoint](../defender-endpoint/automated-investigations.md). Med de här uppdateringarna och förbättringarna kommer säkerhetsgruppen att kunna visa information om automatiska undersökningar och åtgärder som gäller för e-post, samarbetsinnehåll, användarkonton och enheter, allt på ett och samma ställe.|
|[Varningsvyn](../../compliance/alert-policies.md)|Fönstret **Visa varningar** visas i Office Säkerhets- och efterlevnadscenter innehåller nu länkar till Microsoft 365 Säkerhetscenter. Klicka på länken **Öppna aviseringssida** så öppnas Microsoft 365 Säkerhetscenter. Du kan öppna sidan **Visa varningar** genom att klicka på en Office 365-avisering i kön Aviseringar.|
|[Attacksimulering-utbildning](../office-365-security/attack-simulation-training-insights.md)|Använd Attacksimulering-utbildning för att köra realistiska attackscenarier i din organisation. De här simulerade attackerna kan utbilda din personal innan ett riktigt angrepp påverkar din organisation. Attacksimulering-utbildning innehåller fler alternativ, förbättrade rapporter och förbättrade utbildningsflöden som gör det enklare att leverera och hantera dina attacker samt utbildningsscenarier.|
|

Inga ändringar i dessa områden:

- [Explorer](../office-365-security/threat-explorer.md)
- [Principer och regler](../../compliance/alert-policies.md)
- [Kampanj](../office-365-security/campaigns.md)
- [Insändning](../office-365-security/admin-submission.md)
- [Granska](./m365d-action-center.md)
- [Hotspårare](../office-365-security/threat-trackers.md)

Titta också i avsnittet **Relaterad information** längst ned i den här artikeln.

> [!IMPORTANT]
> Microsoft 365 säkerhetsportalen (https://security.microsoft.com) kombinerar säkerhetsfunktioner i https://securitycenter.windows.com och https://protection.office.com. Vad som visas beror dock på din prenumeration. Om du bara har Microsoft Defender för Office 365 Abonnemang 1 eller 2, som fristående prenumerationer, visas inte funktioner för säkerhet för slutpunkter och Defender för Office Abonnemang 1-kunder, ser inte objekt som hotanalys.

> [!TIP]
> Alla Exchange Online Protection (EOP) ingår i säkerhetscentret i Microsoft 365, eftersom EOP är en av grundelementen i Defender för Office 365.

## <a name="microsoft-365-security-center-home-page"></a>Startsida för Microsoft 365 Säkerhetscenter

Startsidan på portalen visar:

- Secure Score-betyg
- antalet användare och enheter som är i riskabelt
- aktiv incidentkö
- Listor över privilegierade OAuth-appar
- hälsodata för enheter
- twitter-inlägg från Microsofts twitter-feed för säkerhetsinformation
- och mer sammanfattningsinformation

Använd den **Guidade rundturen** för att ta en snabb rundtur på sidorna endpoint eller e-post och samarbete. Observera att det du ser här beror på om du har licens för Defender för Office 365 och/eller Defender för Endpoint.

Den innehåller en länk till **Office 365 Säkerhets- och efterlevnadscenter** att jämföra. Den sista länken är till sidan **Nyheter** beskriver de senaste uppdateringarna.

## <a name="improved-capabilities"></a>Förbättrade funktioner

Det vänstra navigeringsfältet eller snabbstartsfältet ser bekant ut. Det finns dock några nya och uppdaterade element i det här säkerhetscentret.

### <a name="incidents-and-alerts"></a>Incidenter och aviseringar

Samlar incidenter och aviseringar för e-post, enheter och identiteter. Aviseringar är nu tillgängliga under noden Undersökning och bidrar till att ge en bredare bild av ett angrepp. Aviseringssidan ger en fullständig kontext till aviseringen genom att kombinera attackerande signaler för att skapa en detaljerad historia. Tidigare var aviseringar specifika för olika arbetsbelastningar. I en ny, enhetlig upplevelse samlas nu en enhetlig vy av aviseringar för arbetsbelastningar. Du kan snabbt göra triage, undersöka och vidta effektiva åtgärder.

- [Läs mer om undersökningar](incidents-overview.md)
- [Läs mer om hur du hanterar varningar](/windows/security/threat-protection/microsoft-defender-atp/review-alerts)

![Snabbstartfältet Aviseringar och Åtgärder](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a>Jakt

Sök proaktivt efter hot, skadlig programvara och skadlig aktivitet i dina slutpunkter, Office 365-postlådor med mera med hjälp av [avancerade sökfrågor](advanced-hunting-overview.md). De här kraftfulla frågorna kan användas för att hitta och granska hotindikatorer och -enheter för både kända och potentiella hot.

[Anpassade identifieringsregler](/windows/security/threat-protection/microsoft-defender-atp/custom-detection-rules) kan byggas från avancerade sökfrågor för att du proaktivt ska kunna hålla koll på händelser som kan vara intrångsaktiviteter och felkonfigurerade enheter.

### <a name="action-center"></a>Åtgärdscenter

Åtgärdscenter visar de undersökningar som skapats med automatiska undersöknings- och svarsfunktioner. Den här automatiserade självläkningen i Microsoft 365 Defender kan hjälpa säkerhetsteam genom att automatiskt svara på specifika händelser.

[Läs mer om Åtgärdscenter](m365d-action-center.md)

#### <a name="threat-analytics"></a>Analys av hot

Få information om hot från Microsofts säkerhetsexpert. Hotanalys hjälper säkerhetsteam att bli mer effektiva när de står inför nya hot. Hotanalys omfattar:

- E-postrelaterade identifieringar och metoder från Microsoft Defender för Office 365. Det här är ett tillägg till de slutpunktsdata som redan är tillgängliga från Microsoft Defender för Endpoint.
- Incidenter visas relaterat till hoten.
- Förbättrad upplevelse för att snabbt identifiera och använda hanterbar information i rapporterna.
Du kan komma Hotanalys antingen från det övre vänstra navigeringsfältet i Microsoft 365 Säkerhetscenter eller från ett dedikerat instrumentpanelskort som visar de viktigaste hoten för din organisation.

Läs mer om hur du [spåra och svara på nya hot med hjälp av hotanalys](./threat-analytics.md)

### <a name="email--collaboration"></a>E-post och samarbete

Spåra och undersöka hot mot användarnas e-post, spåra kampanjer med mera. Om du har använt Säkerhets- och efterlevnadscenter för Office 365 känner du igen det här.

:::image type="content" source="../../media/converge-3-email-and-collab-new.png" alt-text="Snabbstartmenyn för E-post och samarbete (eller MSDO) till vänster i Microsoft 365 Säkerhetscenter.":::

### <a name="access-and-reports"></a>Åtkomst och rapporter

Visa rapporter, ändra dina inställningar och ändra användarroller.

:::image type="content" source="../../media/converge-4-access-and-reporting-new.png" alt-text="Snabbstartmenyn för behörigheter och rapporter i Microsoft 365 Säkerhetscenter, till vänster i säkerhetscentret.":::

> [!NOTE]
> För Defender för Office 365-användare kan  du nu hantera och rotera DKIM-tangenter (DomainKeys Identified Mail) via säkerhetscentret i Microsoft 365: eller gå till <https://security.microsoft.com/threatpolicy> Policy & **rules** \> **Threat policies** DKIM (principregler för \> **DKIM).**

## <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a>Exempel på Avancerad sökning för Microsoft Defender för Office 365

Vill du komma igång med att söka efter e-posthot med avancerad sökning? Prova det här:

Avsnittet [Komma igång](/microsoft-365/security/office-365-security/defender-for-office-365.md#getting-started) i artikeln [Microsoft Defender för Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) har en logisk tidig konfigurationsdel som ser ut så här:

1. Konfigurera allt med "anti" i namnet.
   - anti-skadlig kod
   - anti-phishing
   - anti-spam
2. Konfigurera allt med "säkra" i namnet.
   - säkra länkar
   - Säkra bifogade filer
3. Försvara arbets belastningarna (t. ex. SharePoint Online, OneDrive och Teams)
4. Skydda med Zero-Hour auto purge

Tillsammans med en [länk](../office-365-security/protect-against-threats.md) kan du hoppa direkt in och få igång konfigurationen dag 1.

Det sista steget i **Komma igång** skyddar användare med **Automatisk rensning**, även kallat ZAP. Det kan vara mycket viktigt att veta om du har lyckats med ZAP:a ett misstänkt eller skadligt e-postmeddelande efter leverans.

Att snabbt kunna navigera till Kusto frågespråk för att leta efter problem är en fördel med konvergering av dessa två säkerhetscenter. Säkerhetsteam kan övervaka ZAP-misser genom att vidta nästa steg [här,](https://security.microsoft.com/advanced-hunting)under **Sökning** \> **efter avancerad sökning.**

1. Klicka på Fråga på sidan Avancerad sökning.
1. Kopiera frågan nedan till frågefönstret.
1. Välj Kör fråga.

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="Sidan Avancerad jakt (under Jakt)med Fråga vald högst upp i frågepanelen och köra en Kusto-fråga för att fånga ZAP-åtgärder under de senaste 7 dagarna.":::

Data från den här frågan visas i resultatpanelen under själva frågan. Resultaten innehåller information som ‘Enhetsnamn’, ‘KontoVisningsNamn’ och ‘ZapTid’ i en anpassningsbar resultatuppsättning. Resultat kan även exporteras för posterna. Om frågan är en du behöver igen väljer du **Spara** > **Spara som** och lägger till frågan i din lista med frågor, delade frågor eller communityfrågor.

## <a name="related-information"></a>Relaterad information

- [Microsoft Defender för Office 365 i Microsoft 365 Säkerhetscenter](microsoft-365-security-center-mdo.md)
- [Åtgärdscentret](./m365d-action-center.md)
- [E-post- och samarbetsaviseringar](../../compliance/alert-policies.md#default-alert-policies)
- [Jaga efter hot på olika enheter, e-postmeddelanden, appar och identiteter](./advanced-hunting-query-emails-devices.md)
- [Anpassade regler för identifiering](/microsoft-365/security/defender-endpoint/custom-detection-rules)
- [Skapa en simulering av ett nätfiskeangrepp](../office-365-security/attack-simulation-training.md) och [skapa en nyttolast för utbildning av personerna](../office-365-security/attack-simulation-training-payloads.md)
