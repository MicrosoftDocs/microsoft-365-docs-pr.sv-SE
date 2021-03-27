---
title: Skapa anpassade identifieringsregler i Microsoft Defender ATP
ms.reviewer: ''
description: Lär dig hur du skapar anpassade identifieringsregler som baseras på avancerade sökfrågor
keywords: anpassade identifieringar, skapa, hantera, aviseringar, redigera, köra på begäran, frekvens, intervall, identifieringsregler, avancerad sökning, sökning, fråga, svarsåtgärder, mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 48b1f1bf9506acc8491887fca49295d5e4ccbd69
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382715"
---
# <a name="create-custom-detection-rules"></a>Skapa anpassade identifieringsregler

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Anpassade identifieringsregler skapade av [avancerade](advanced-hunting-overview.md) sökfrågor gör att du proaktivt kan övervaka olika händelser och systemhändelser, inklusive misstänkt intrång och felkonfigurerade enheter. Du kan ange att de ska köras med jämna mellanrum, generera aviseringar och vidta svarsåtgärder när det finns matchningar.

I den här artikeln får du lära dig hur du skapar nya anpassade identifieringsregler. Du [kan också visa och hantera befintliga regler.](custom-detections-manage.md)

> [!NOTE]
> För att skapa eller hantera anpassade identifieringar [måste din roll](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) ha behörighet att hantera **säkerhetsinställningar.**

## <a name="1-prepare-the-query"></a>1. Förbereda frågan.

I Microsoft Defender Säkerhetscenter går du till **Avancerad sökning** och väljer en befintlig fråga eller skapar en ny fråga. När du använder en ny fråga kör du frågan för att identifiera fel och förstå möjliga resultat.

>[!IMPORTANT]
>För att förhindra att tjänsten returnerar för många aviseringar är varje regel begränsad till att generera endast 100 aviseringar när den körs. Innan du skapar en regel bör du justera frågan för att undvika aviseringar om normal aktivitet.

### <a name="required-columns-in-the-query-results"></a>Obligatoriska kolumner i frågeresultatet

Om du vill använda en fråga för en anpassad identifieringsregel måste frågan returnera följande kolumner:

- `Timestamp`
- `DeviceId`
- `ReportId`

Enkla frågor, till exempel de som inte använder operatorn eller för att anpassa eller sammanställa resultat, returnerar `project` `summarize` vanligtvis dessa gemensamma kolumner.

Det finns olika sätt att säkerställa att mer komplexa frågor returnerar dessa kolumner. Om du till exempel föredrar att aggregera och räkna efter kan du fortfarande returnera och genom att hämta dem från den senaste händelsen `DeviceId` `Timestamp` som innefattar varje `ReportId` enhet.

I exempelfrågan nedan räknas antalet unika enheter () med antivirusidentifiering och används för att endast hitta de enheter som har `DeviceId` fler än fem identifieringar. För att returnera det `Timestamp` senaste och motsvarande används `ReportId` `summarize` operatorn med `arg_max` funktionen.

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> För att få bättre frågeprestanda kan du ange ett tidsfilter som matchar den avsedda körningsfrekvensen för regeln. Eftersom det minsta antalet körningar är en gång per dygn omfattar filtreringen för den senaste dagen alla nya data.

## <a name="2-create-a-new-rule-and-provide-alert-details"></a>2. Skapa en ny regel och ange aviseringsinformation.

Med frågan i frågeredigeraren väljer du **Skapa identifieringsregel** och anger följande aviseringsinformation:

- **Identifieringsnamn**– namnet på identifieringsregeln
- **Frekvens**– intervall för att köra frågan och vidta åtgärder. [Mer information finns nedan](#rule-frequency)
- **Aviseringsrubrik**– rubrik som visas med aviseringar som utlöses av regeln
- **Allvarlighetsgrad**– potentiell risk för den komponent eller aktivitet som identifieras av regeln. [Läs mer om allvarlighetsgraderna för aviseringar](alerts-queue.md#severity)
- **Kategori**– typ av hotkomponent eller aktivitet, om det finns någon. [Läs mer om aviseringskategorier](alerts-queue.md#understanding-alert-categories)
- **MITRE ATT&CK-tekniker**– en eller flera attacktekniker som identifieras av regeln enligt finns i MITRE ATT&CK-ramverket. Det här avsnittet är inte tillgängligt för vissa aviseringskategorier, till exempel skadlig kod, utpressningstrojaner, misstänkt aktivitet och oönskad programvara
- **Beskrivning**– mer information om komponenten eller aktiviteten som identifieras av regeln 
- **Rekommenderade åtgärder**– ytterligare åtgärder som svarare kan vidta för en avisering

Mer information om hur aviseringsinformation visas finns [i om aviseringskön](alerts-queue.md).

### <a name="rule-frequency"></a>Regelfrekvens

När den sparas körs en ny anpassad identifieringsregel direkt och söker efter matchningar från de senaste 30 dagarnas data. Regeln körs sedan igen med fasta intervall och söklängder baserat på den frekvens du väljer:

- **Körs en gång per dygn** och kontrollerar data från de senaste 30 dagarna
- **Körs var 12:e** timme per dygn och kontrollerar data från de senaste 24 timmarna
- **Körs var tredje timme** och kontrollerar data från de senaste 6 timmarna
- **Varje timme** körs varje timme och du kontrollerar data från de senaste två timmarna

När du redigerar en regel körs den med tillämpade ändringar under nästa körning enligt den frekvens du har angett.


> [!TIP]
> Matcha tidsfiltren i frågan med tillbakaslagslängden. Resultat utanför återställningsvaraktigheten ignoreras.

Välj den frekvens som matchar hur nära du vill övervaka identifieringar och ta hänsyn till organisationens kapacitet att svara på aviseringarna.

## <a name="3-choose-the-impacted-entities"></a>3. Välj de berörda enheterna.

Identifiera kolumnerna i frågeresultatet där du förväntar dig att hitta den viktigaste påverkade eller påverkade enheten. En fråga kan till exempel returnera både enhets- och användar-ID. Genom att identifiera vilka av dessa kolumner som representerar den viktigaste påverkade enheten bidrar tjänsten till att slå samman relevanta aviseringar, korrelera incidenter och målsvarsåtgärder.

Du kan bara välja en kolumn för varje entitetstyp. Kolumner som inte returneras av frågan kan inte markeras.

## <a name="4-specify-actions"></a>4. Ange åtgärder.

Den anpassade identifieringsregeln kan automatiskt utföra åtgärder på filer eller enheter som returneras av frågan.

### <a name="actions-on-devices"></a>Åtgärder på enheter

Dessa åtgärder tillämpas på enheter i `DeviceId` kolumnen med frågeresultat:

- **Isolera enhet**– tillämpar fullständig nätverksisolering, vilket hindrar enheten från att ansluta till något program eller en tjänst, förutom Defender för Slutpunkt-tjänsten. [Läs mer om enhetsisolering](respond-machine-alerts.md#isolate-devices-from-the-network)
- Samla in **undersökningspaket**– samlar in enhetsinformation i en ZIP-fil. [Läs mer om undersökningspaketet](respond-machine-alerts.md#collect-investigation-package-from-devices)
- **Kör en antivirussökning**– utför en fullständig sökning i Microsoft Defender Antivirus på enheten
- **Initiera undersökning**– startar [en automatiserad undersökning](automated-investigations.md) på enheten
- **Begränsa programkörning**– anger begränsningar på enheten så att endast filer som är signerade med ett certifikat utfärdat av Microsoft kan köras. [Läs mer om att begränsa programkörning](respond-machine-alerts.md#restrict-app-execution)

### <a name="actions-on-files"></a>Åtgärder för filer

Dessa åtgärder tillämpas på filer i `SHA1` eller `InitiatingProcessSHA1` kolumnen i frågeresultatet:

- **Tillåt/blockera**– lägger automatiskt till filen i din [anpassade indikatorlista](manage-indicators.md) så att den alltid kan köras eller blockeras. Du kan ange omfattningen av den här åtgärden så att den endast vidtas på valda enhetsgrupper. Den här omfattningen är oberoende av regelns omfattning.
- **Karantänfil**– tar bort filen från dess aktuella plats och placerar en kopia i karantän

### <a name="actions-on-users"></a>Åtgärder för användare

- **Markera användare som komprometterade**– anger att användarens risknivå är "hög" i Azure Active Directory, vilket utlöser motsvarande [principer för identitetsskydd.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels)

## <a name="5-set-the-rule-scope"></a>5. Ange regelns omfattning.

Ange omfattningen för att ange vilka enheter som omfattas av regeln:

- Alla enheter
- Specifika enhetsgrupper

Endast data från enheter i omfattningen kommer att tillfrågas. Dessutom kommer åtgärder endast att vidtas på de enheterna.

## <a name="6-review-and-turn-on-the-rule"></a>6. Granska och aktivera regeln.

När du har granskat regeln väljer du **Skapa för** att spara den. Regeln för anpassad identifiering körs direkt. Den körs igen baserat på konfigurerad frekvens för att söka efter matchningar, generera aviseringar och vidta svarsåtgärder.

Du kan [visa och hantera anpassade identifieringsregler](custom-detections-manage.md), kontrollera deras tidigare körningar och granska aviseringarna som de har utlöst. Du kan även köra en regel på begäran och ändra den.

## <a name="related-topics"></a>Relaterade ämnen

- [Visa och hantera anpassade identifieringsregler](custom-detections-manage.md)
- [Översikt över anpassade identifieringar](overview-custom-detections.md)
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig språket för avancerad fråga om sökning](advanced-hunting-query-language.md)
- [Visa och ordna aviseringar](alerts-queue.md)
