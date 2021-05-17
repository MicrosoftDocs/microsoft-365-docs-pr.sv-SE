---
title: Mer information om dataförlustskydd för slutpunkter i Microsoft 365
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 'Dataförlustskyddet för slutpunkter i Microsoft 365 utökar övervakningen av filaktiviteter och skyddsåtgärder för dessa filer till slutpunkter. Filerna visas i lösningarna för Microsoft 365 Efterlevnadscenter '
ms.openlocfilehash: b5aa6c737bc54129ce49378a7dcaf81e9d5c612f
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162990"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a>Mer information om dataförlustskydd för slutpunkter i Microsoft 365

Du kan använda dataförlustskyddet (DLP) i Microsoft 365 till att övervaka åtgärder som vidtas för objekt som du har fastställt vara känsliga och för att förhindra oavsiktlig delning av dessa objekt. Mer information om DLP finns i [Mer information om dataförlustskydd](dlp-learn-about-dlp.md).

**Dataförlustskyddet för slutpunkter** (slutpunkts-DLP) utökar funktionerna för aktivitetsövervakning och säkerhet i DLP till känsliga objekt som finns på Windows 10-enheter. När enheter har registrerats i efterlevnadslösningarna för Microsoft 365 blir informationen om vad användare gör med känsliga objekt synlig i [aktivitetsutforskaren](data-classification-activity-explorer.md) och du kan vidta skyddsåtgärder för dessa objekt via [DLP-principer](create-test-tune-dlp-policy.md).

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a>Slutpunktsaktiviteter som du kan övervaka och vidta åtgärder för

Med Microsofts slutpunkts-DLP kan du granska och hantera följande typer av aktiviteter som användare utför på känsliga objekt som finns på Windows 10-enheter. 

|Aktivitet |Beskrivning  | Granskningsbar/begränsningsbar|
|---------|---------|---------|
|ladda upp till molntjänst, eller ge åtkomst till otillåtna webbläsare    | Upptäcker när en användare försöker ladda upp ett objekt till en begränsad tjänstdomän eller öppna ett objekt via en webbläsare.  Om en webbläsare används som anges i DLP som en otillåten webbläsare, blockeras uppladdningen och användaren omdirigeras till Edge Chromium. Edge Chromium tillåter eller blockerar sedan uppladdningen eller åtkomsten baserat på DLP-principkonfigurationen         |granskningsbart och begränsningsbart|
|kopiera till en annan app    |Upptäcker när en användare försöker kopiera information från ett skyddat objekt och sedan klistra in den i en annan app, en annan process eller ett annat objekt. Att kopiera och klistra in information i samma app, process eller objekt identifieras inte av den här aktiviteten.         | granskningsbart och begränsningsbart|
|kopiera till USB-flyttbart medium |Upptäcker när en användare försöker kopiera ett objekt eller information till ett flyttbart medium eller en USB-enhet.         | granskningsbart och begränsningsbart|
|kopiera till en nätverksresurs    |Upptäcker när en användare försöker kopiera ett objekt till en nätverksresurs eller en mappad nätverksenhet         |granskningsbart och begränsningsbart|
|skriva ut ett dokument    |Upptäcker när en användare försöker skriva ut ett skyddat objekt till en lokal skrivare eller en nätverksskrivare.| granskningsbart och begränsningsbart         |
|kopiera till en fjärrsession|Upptäcker när en användare försöker kopiera ett objekt till en session för fjärrdatorer |  granskningsbart och begränsningsbart|
|kopiera till en Bluetooth-enhet|Upptäcker när en användare försöker kopiera ett objekt till en otillåten Bluetooth-app (enligt definitionen i listan med otillåtna Bluetooth-appar i inställningarna för slutpunkts-DLP:n).| granskningsbart och begränsningsbart|
|skapa ett objekt.|Upptäcker när en användare skapar ett objekt| granskningsbart|
|byta namn på ett objekt|Upptäcker när en användare byter namn på ett objekt| granskningsbart|

 ## <a name="monitored-files"></a>Övervakade filer

Slutpunkts-DLP:n stöder övervakning av följande filtyper:

- Word-filer
- PowerPoint-filer
- Excel-filer
- PDF-filer
- .csv-filer
- .tsv-filer
- .txt-filer
- .rtf-filer
- .c-filer
- .class-filer
- .cpp-filer
- .cs-filer
- .h-filer
- .java-filer
 
Som standard granskar slutpunkts-DLP:n aktiviteterna för dessa filtyper, även om det inte finns någon principmatchning. Om du bara vill övervaka data från principmatchningar kan du stänga av **Granska alltid filaktivitet för enheter** i de globala inställningarna för slutpunkts-DLP:n. Om inställningen är på granskas alltid aktiviteter i Word-, PowerPoint-, Excel-, PDF- och .csv-filer, även om enheten inte omfattas av någon princip.

Slutpunkts-DLP:n övervakar aktivitet baserat på MIME-typ, så aktiviteterna samlas in även om filtillägget ändras. 

## <a name="whats-different-in-endpoint-dlp"></a>Vad är annorlunda i slutpunkts-DLP?

Det finns några fler begrepp som du behöver känna till innan du fördjupar dig i slutpunkts-DLP:n.

### <a name="enabling-device-management"></a>Aktivera enhetshantering

Enhetshantering är den funktion som samlar in telemetri från enheter och matar in den i Microsoft 365-efterlevnadslösningar som slutpunkts-DLP och [hantering av interna risker](insider-risk-management.md). Du måste registrera alla enheter som ska användas som platser i DLP-principerna.

> [!div class="mx-imgBorder"]
> ![aktivera enhetshantering](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

Registrering och avregistrering hanteras via skript som du hämtar från Enhetshanteringscenter. Centret har anpassade skript för var och en av dessa distributionsmetoder:

- lokalt skript (upp till 10 datorer)
- Grupprincip
- System Center Configuration Manager (version 1610 eller senare)
- Hantering av mobila enheter/Microsoft Intune
- VDI-registreringsskript för icke-beständiga datorer

> [!div class="mx-imgBorder"]
> ![enhetsregistreringssida](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 Använd procedurerna i [Komma igång med slutpunkts-DLP i Microsoft 365](endpoint-dlp-getting-started.md) för att registrera enheter.

Om du har registrerat enheter via [Microsoft Defender för Endpoint](/windows/security/threat-protection/) visas de enheterna automatiskt i listan med enheter.

> [!div class="mx-imgBorder"]
> ![lista med hanterade enheter](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a>Visa data för slutpunkts-DLP

Du kan se aviseringar om DLP-principer som tillämpas på slutpunktsenheter genom att gå till [instrumentpanelen för hantering av DLP-aviseringar](dlp-configure-view-alerts-policies.md).

> [!div class="mx-imgBorder"]
> ![Aviseringsinformation](../media/Alert-info-1.png)

Du kan också se information om den associerade händelsen med omfattande metadata i samma instrumentpanel

> [!div class="mx-imgBorder"]
> ![händelseinformation](../media/Event-info-1.png)

När en enhet har registrerats flödar information om granskade aktiviteter till aktivitetsutforskaren redan innan du har konfigurerat och distribuerat DLP-principer som har enheter som en plats.

> [!div class="mx-imgBorder"]
> ![händelser för slutpunkts-DLP i aktivitetsutforskaren](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

Slutpunkts-DLP:n samlar in omfattande information om den granskade aktiviteten.

Om en fil till exempel kopieras till ett flyttbart USB-medium visas följande attribut i aktivitetsinformationen:

- aktivitetstyp
- klient-IP
- sökväg till målfil
- tidsstämpel
- filnamn
- användare
- filtillägg
- filstorlek
- typ av känslig information (om tillämpligt)
- sha1-värde
- sha256-värde
- tidigare filnamn
- plats
- överordnad
- filsökväg
- källplatstyp
- plattform
- enhetsnamn
- målplatstyp
- program som utförde kopian
- Enhets-ID till Microsoft Defender för Endpoint (om tillämpligt)
- tillverkare av flyttbar medieenhet
- modell för flyttbar medieenhet
- serienummer för flyttbar medieenhet

> [!div class="mx-imgBorder"]
> ![kopiera till USB-aktivitetsattribut](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

## <a name="next-steps"></a>Nästa steg

Nu när du har lärt dig mer om slutpunkts-DLP är nästa steg:

1) [Komma igång med Microsofts dataförlustskydd för slutpunkter](endpoint-dlp-getting-started.md)
2) [Använda Microsofts dataförlustskydd för slutpunkter](endpoint-dlp-using.md)

## <a name="see-also"></a>Se även

- [Komma igång med Microsofts dataförlustskydd för slutpunkter](endpoint-dlp-getting-started.md)
- [Använda Microsofts dataförlustskydd för slutpunkter](endpoint-dlp-using.md)
- [Mer information om dataförlustskydd](dlp-learn-about-dlp.md)
- [Skapa, testa och justera en DLP-princip](create-test-tune-dlp-policy.md)
- [Kom igång med aktivitetsutforskaren](data-classification-activity-explorer.md)
- [Microsoft Defender för Endpoint](/windows/security/threat-protection/)
- [Hantering av interna risker](insider-risk-management.md)