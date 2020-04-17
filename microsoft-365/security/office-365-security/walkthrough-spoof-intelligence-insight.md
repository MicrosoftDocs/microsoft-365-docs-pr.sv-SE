---
title: Genomgång - Spoof intelligens insikt
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
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
description: Se hur den falska intelligensinsikten fungerar i Office 365 Advanced Threat Protection.
ms.openlocfilehash: 92e922bf3045e98de16b07a47113effd9dc6ccdd
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537491"
---
# <a name="walkthrough---atp-spoof-intelligence-insight-in-office-365"></a>Genomgång – ATP:s falska intelligensinsikt i Office 365

I Office 365-organisationer med atp (Advanced Threat Protection) kan du använda den falska intelligensinsikten för att snabbt avgöra vilka avsändare som lagligen skickar oautentiserade e-postmeddelanden till dig. Genom att tillåta dem att skicka falska meddelanden kan du minska risken för att falska positiva identifieringar går till dina användare. Du kan också använda den falska intelligensinsikten för att övervaka och hantera tillåtna domänpar för att tillhandahålla ett extra säkerhetslager och förhindra att osäkra meddelanden kommer till din organisation.

Om du inte har tidigare information [om rapporter och insikter i Säkerhets- & Compliance Center för Office 365](reports-and-insights-in-security-and-compliance.md)kan det hjälpa dig att se hur du enkelt kan navigera från en instrumentpanel till en insikt och rekommenderade åtgärder.

Den här genomgången är en av flera för Security & Compliance Center. Om du vill navigera i rapporter och insikter finns i genomgångarna i avsnittet Närliggande ämnen.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt <https://protection.office.com/searchandinvestigation/dashboard>till **instrumentpanelssidan för säkerhet** använder du .

  Du kan visa den falska intelligensinsikten från mer än en instrumentpanel i Security & Compliance Center. Oavsett vilken instrumentpanel du tittar på ger insikten samma information och gör att du snabbt kan utföra samma uppgifter.

- Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna. Om du vill använda den falska informationsinsikten måste du vara medlem i rollgrupperna **Organisationshantering,** **Säkerhetsadministratör**eller **Säkerhetsläsare.** Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter för Office 365](permissions-in-the-security-and-compliance-center.md).

- Du aktiverar och inaktiverar falska underrättelser i ATP:s principer för phishing.You enable and disable spoof intelligence in ATP anti-phishing policies. Mer information finns [i Konfigurera ATP-principer för nätfiske i Office 365](configure-atp-anti-phishing-policies.md).

- I Office 365-organisationer med Exchange Online-postlådor och i fristående Exchange Online Protection (EOP) utan Exchange Online-postlådor kan du använda falska underrättelser för att övervaka och hantera avsändare som du skickar meddelanden som inte har autentiseringslag. Mer information finns [i Konfigurera falska underrättelser i Office 365](learn-about-spoof-intelligence.md).

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Öppna den falska intelligensinsikten i Security & Compliance Center

1. Gå till **instrumentpanelen** **för &-efterlevnad i** \> Säkerhets- & Compliance Center.

2. Leta efter något av följande objekt på raden **Insikter:**

   - **Falska underrättelser är aktiverad:** Insikten heter **Falska domäner som misslyckades autentisering av de senaste 30 dagarna**. Detta är standardvärdet.

   - **Falska underrättelser är inaktiverat**: Insikten i namnet **Aktivera Spoof Protection**, och genom att klicka på den kan du aktivera falska underrättelser.

3. Insikten på instrumentpanelen visar information så här:

   ![Skärmbild av falska underrättelseinsikter](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Den här insikten har två lägen:

   - **Insiktsläge**. Om du har någon spoof politik aktiverad, då insikten visar hur många mail påverkades av vår falska intelligens kapacitet under de senaste 30 dagarna.

   - **Vad händer om läge**. Om du inte har någon falska politik aktiverad, då insikten visar hur många mail *skulle* ha påverkats av vår falska intelligens kapacitet under de senaste 30 dagarna.

   Hursomhelst, de falska domäner som visas i insikten är uppdelade i två kategorier: **misstänkta domänpar** och **icke-misstänkta domänpar**. Dessa kategorier är ytterligare indelade i tre olika buckets för dig att granska.

   Ett **domänpar** är en kombination av Från-adressen och den sändande infrastrukturen:

   - Från-adressen är avsändarens e-postadress som visas i e-postklienter. Adressen identifierar e-postmeddelandets upphovsman. Det vill säga, postlådan för personen eller systemet som ansvarar för att skriva meddelandet. Den här adressen kallas `5322.From` även adressen.

   - Den sändande infrastrukturen, eller avsändaren, är organisationsdomänen för ptr-posten (reverse DNS lookup) för den sändande IP-adressen. Om den sändande IP-adressen inte har någon PTR-post identifieras avsändaren av den sändande IP-adressen med nätmasken 255.255.255.0 i CIDR-notation (/24). Om IP-adressen till exempel är 192.168.100.100 är avsändarens fullständiga IP-adress 192.168.100.100/24.

   **Misstänkta domänpar** inkluderar:

   - **Högförtroende:** Office 365 fick starka signaler om att dessa domäner är misstänkta, baserat på de historiska sändningsmönstren och domänernas ryktespoäng. Office 365 är mycket säker på att domänerna förfalskar och att meddelanden som skickas från dessa domäner är mindre benägna att vara legitima.

   - **Måttlig förtroende:** Office 365 fick måttliga signaler om att dessa domäner är misstänkta, baserat på historiska sändningsmönster och domänernas ryktespoäng. Office 365 är måttligt säker på att domänerna förfalskar och att meddelanden som skickas från dessa domäner är legitima. Denna hink har en större chans att innehålla falska positiva (FPs) än hög förtroende parodi hink.

   - **Icke-misstänkta domänpar** (inkluderar **räddad parodi):** Räddad parodi är domäner som har misslyckats med de explicita autentiseringskontrollerna [SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md), [DMARC](use-dmarc-to-validate-email.md)) men som har klarat våra implicita e-postautentiseringskontroller ([sammansatt autentisering](email-validation-and-authentication.md#composite-authentication)). Som ett resultat räddade Office 365 e-postmeddelandet för din räkning och inga anti-spoofing åtgärder vidtogs på meddelandet.

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>Visa detaljerad information om misstänkta domänpar från den falska intelligensinsikten

1. På falska intelligens insikt, klicka på någon av domänparen (hög, måttlig eller räddad).

   Sidan **Spoof Intelligence-statistik** visas som visar en lista över avsändare som skickar oautentiserade e-postmeddelanden till din organisation. Informationen på den här sidan hjälper dig att avgöra om falska meddelanden är auktoriserade eller om du behöver vidta ytterligare åtgärder. Du kan sortera informationen efter antalet meddelanden, det datum då förfalskningen senast upptäcktes med mera. (Klicka på kolumnrubriker, till exempel **Antal meddelanden** eller **Senast sedd.**

2. Välj ett objekt i tabellen för att öppna ett informationsfönster som innehåller omfattande information om domänparet, inklusive varför vi fångade detta, vad du behöver göra, en domänsammanfattning, WhoIs-data om avsändaren och liknande e-postmeddelanden som vi har sett i din klientorganisation från samma avsändare. Härifrån kan du också välja att lägga till eller ta bort domänparet från listan **Tillåtet försyre säker** avsändare.

   ![Skärmbild av en domän i informationsfönstret för information om falska underrättelseuppgifter](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a>Lägga till eller ta bort en domän från listan Tillåtetsumma för säker avsändare

Du lägger till eller tar bort en domän från listan TillåtetSummabehållsam avsändare när du granskar domänparet i informationsfönstret i den falska intelligensinsikten. Ställ bara in växlingen därefter.

Detta ändrar den unika domänparkombinationen av den falska domänen och den sändande infrastrukturen och ger inte täckning för hela den falska domänen eller den sändande infrastrukturen separat.

Om du till exempel lägger till följande domänpar i listan Tillåten till förfalskning av avsändare: *Förfalskad domän* "gmail.com" och *Skicka infrastruktur* "tms *.mx.com",* tillåts endast e-post från det domänparet att förfalskas. Andra avsändare som försöker förfalska "gmail.com" och andra domäner som "tms.mx.com" försöker förfalska kommer att fortsätta att skyddas av falska underrättelser.

## <a name="related-topics"></a>Relaterade ämnen

[Skydd mot förfalskning i Office 365](anti-spoofing-protection.md)

[Genomgång – Från en instrumentpanel till en insikt](from-a-dashboard-to-an-insight.md)

[Genomgång – Från en detaljerad rapport till en insikt](from-a-detailed-report-to-an-insight.md)

[Genomgång – Från en insikt till en detaljerad rapport](from-an-insight-to-a-detailed-report.md)
