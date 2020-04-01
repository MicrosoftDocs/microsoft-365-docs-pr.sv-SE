---
title: Genomgång parodi intelligens insikt
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 7/30/2018
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Se hur den nya falska intelligens insikt fungerar.
ms.openlocfilehash: 797cbc07fd068ae80edc6cea699f78b2304a8f6c
ms.sourcegitcommit: a7b2cd892cb65a61ee246268e1af2f8b9e526f6b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2020
ms.locfileid: "43081418"
---
# <a name="walkthrough-spoof-intelligence-insight"></a>Genomgång: parodi intelligens insikt

Genom att använda spoof Intelligence-insikten kan du snabbt avgöra vilka avsändare som lagligen skickar oautentiserade e-postmeddelanden till dig. Genom att tillåta dem att skicka falska meddelanden kan du minska risken för att falska positiva identifieringar går till dina användare.

Dessutom kan du också använda Spoof Intelligence-övervakare och hantera tillåtna domänpar för att tillhandahålla ett extra säkerhetslager och förhindra att osäkra meddelanden kommer till din organisation.

Du kan använda den falska informationsinsikten i Security &amp; Compliance Center om ditt arbets- eller skolkonto har fått behörigheten Office 365 global administratör, säkerhetsadministratör eller säkerhetsläsare. Mer information finns [i Behörigheter i Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).

Om du inte har tidigare information [om rapporter och &amp; insikter i Office 365 Security Compliance Center](reports-and-insights-in-security-and-compliance.md)kan det hjälpa dig att se hur du enkelt kan navigera från en instrumentpanel till en insikt och rekommenderade åtgärder.

Du kan visa den falska intelligensinsikten från &amp; mer än en instrumentpanel i Security Compliance Center. Oavsett vilken instrumentpanel du tittar på ger insikten samma information och gör att du snabbt kan utföra samma uppgifter.

Detta är en av flera genomgångar &amp; för Security Compliance Center. Om du vill navigera i rapporter och insikter finns i genomgångarna i avsnittet Närliggande ämnen.

## <a name="getting-to-the-spoof-intelligence-insight-in-the-security-amp-compliance-center"></a>Komma till falska intelligens insikt i &amp; Security Compliance Center

1. För att komma igång måste du [gå till Security &amp; Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).

2. Gå till &amp; instrumentpanelen **för hothantering** \> i Säkerhetsefterlevnadscenter. **Dashboard.**

3. Leta efter den falska intelligensinsikten i raden **Insikter.** Om du har aktiverat falska underrättelser, då insikten har rätt **Spoofed domäner som misslyckades autentisering av de senaste 30 dagarna**. Om du inte har aktiverat förfalskningsskydd uppmanas du att göra det genom att använda rubriken **Aktivera förfalskningsskydd**.

## <a name="about-the-insight-on-the-dashboard"></a>Om insikten på instrumentpanelen

Insikten på instrumentpanelen visar information som denna.

![Skärmbild av falska underrättelseinsikter](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

Den här insikten har två lägen:

 **Insiktsläge**. Om du har någon spoof politik aktiverad, då insikten visar hur många mail påverkades av vår falska intelligens kapacitet under de senaste 30 dagarna.

 **Vad händer om läge**. Om du inte har någon falska politik aktiverad, då insikten visar hur många mail *skulle* ha påverkats av vår falska intelligens kapacitet under de senaste 30 dagarna.

Hur som helst är de falska domäner som visas i insikten uppdelade i två kategorier. misstänkta domänpar och icke-misstänkta domänpar. Dessa kategorier är ytterligare indelade i tre olika buckets för dig att granska. 

Ett *domänpar* är en kombination av "Från:"-adressen och den sändande infrastrukturen. 

- "Från"-adressen är den adress som visas som Från-adressen av ditt e-postprogram. Adressen identifierar e-postmeddelandets upphovsman. Det vill säga, postlådan för personen eller systemet som ansvarar för att skriva meddelandet. Detta kallas ibland för 5322.From-adressen.

- Den sändande infrastrukturen, eller avsändaren, är organisationsdomänen för PTR-posten för den sändande IP-adressen. Om den sändande IP-adressen inte har någon PTR-post identifieras avsändaren av den sändande IP-adressen med nätmasken 255.255.255.0 i CIDR-notation (/24). Om IP-adressen till exempel är 192.168.100.100 är avsändarens fullständiga IP-adress 192.168.100.100/24.

 **Misstänkta domänpar** inkluderar:

- **Högförtroende parodi**. Office 365 fick starka signaler om att dessa domäner är misstänkta, baserat på de historiska sändningsmönstren och domänernas ryktespoäng. Office 365 är mycket säker på att domänerna förfalskar och att meddelanden som skickas från dessa domäner är mindre benägna att vara legitima. 

- **Måttligt förtroende för**. Office 365 fick måttliga signaler om att dessa domäner är misstänkta, baserat på historiska sändningsmönster och domänernas ryktespoäng. Office 365 är måttligt säker på att domänerna förfalskar och att meddelanden som skickas från dessa domäner är legitima. Denna hink har en större chans att innehålla falska positiva (FPs) än hög förtroende parodi hink.

 **Icke-misstänkta domänpar** inkluderar **räddad parodi**. Räddade spoof är domäner som har misslyckats explicita autentiseringskontroller [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), [DMARC](use-dmarc-to-validate-email.md)) men passerade våra utökade autentiseringskontroller. Som ett resultat av detta räddade Office 365 posten för din räkning och inga anti-spoofing åtgärder vidtogs på posten.

## <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>Visa detaljerad information om misstänkta domänpar från den falska intelligensinsikten

1. På falska intelligens insikt, klicka på någon av domänparen (hög, måttlig eller räddad).

Sidan **Spoof Intelligence Insight** visas som visar en lista över avsändare som skickar oautentiserade e-postmeddelanden till din organisation. Informationen på den här sidan hjälper dig att avgöra om falska meddelanden är auktoriserade eller inte eller om du behöver vidta ytterligare åtgärder. Du kan sortera informationen efter antalet meddelanden, det datum då förfalskningen senast upptäcktes med mera. (Klicka på kolumnrubriker, till exempel **Antal meddelanden** eller **Senast sedd.**

2. Välj ett objekt i tabellen för att öppna ett informationsfönster som innehåller omfattande information om domänparet, inklusive varför vi fångade detta, vad du behöver göra, en domänsammanfattning, WhoIs-data om avsändaren och liknande e-postmeddelanden som vi har sett i din klientorganisation från samma avsändare. Härifrån kan du också välja att lägga till eller ta bort domänparet från listan **Tillåtet försyre säker** avsändare.

![Skärmbild av en domän i informationsfönstret för information om falska underrättelseuppgifter](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

## <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a>Lägga till eller ta bort en domän från listan Tillåtetsumma för säker avsändare

Du lägger till eller tar bort en domän från listan TillåtetSummabehållsam avsändare när du granskar domänparet i informationsfönstret i den falska intelligensinsikten. Ställ bara in växlingen därefter.

Detta ändrar den unika domänparkombinationen av den falska domänen och den sändande infrastrukturen och ger inte täckning för hela den falska domänen eller den sändande infrastrukturen separat. Om du till exempel lägger till följande domänpar i listan Tillåten till förfalskning av avsändare: *Förfalskad domän* "gmail.com" och *Skicka infrastruktur* "tms *.mx.com",* tillåts endast e-post från det domänparet att förfalskas. Andra avsändare som försöker förfalska "gmail.com" och andra domäner som "tms.mx.com" försöker förfalska kommer att fortsätta att skyddas av falska underrättelser.

## <a name="related-topics"></a>Relaterade ämnen

[Läs mer om falska underrättelser](learn-about-spoof-intelligence.md)

[Skydd mot förfalskning i Office 365](anti-spoofing-protection.md)

[Genomgång - Från en instrumentpanel till en insikt](from-a-dashboard-to-an-insight.md)

[Genomgång - Från en detaljerad rapport till en insikt](from-a-detailed-report-to-an-insight.md)

[Genomgång - Från en insikt till en detaljerad rapport](from-an-insight-to-a-detailed-report.md)


