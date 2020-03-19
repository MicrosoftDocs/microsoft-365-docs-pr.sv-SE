---
title: Genomgång av förfalskad intelligensinsikt
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
description: Se hur den nya falska intelligensinsikten fungerar.
ms.openlocfilehash: 940203bc86339e4cc749565be355d717be9e914d
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811857"
---
# <a name="walkthrough-spoof-intelligence-insight"></a>Genomgång: falska intelligens insikt

Genom att använda spoof intelligence-insikten kan du snabbt avgöra vilka avsändare som legitimt skickar dig oautentiserad e-post. Genom att tillåta dem att skicka falska meddelanden kan du minska risken för att falska positiva går till dina användare.
  
Dessutom kan du också använda Spoof Intelligence-övervakare och hantera tillåtna domänpar för att tillhandahålla ytterligare ett säkerhetslager och förhindra att osäkra meddelanden kommer till din organisation.
  
Du kan använda experten för falska &amp; underrättelseuppgifter i Security Compliance Center om ditt arbets- eller skolkonto har fått Office 365-globala administratörs-, säkerhetsadministratörs- eller säkerhetsläsarbehörigheter. Mer information finns [i Behörigheter i Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).
  
Om du inte har varit ny [i rapporter och &amp; insikter i Office 365 Security Compliance Center](reports-and-insights-in-security-and-compliance.md)kan det hjälpa dig att se hur du enkelt kan navigera från en instrumentpanel till en insikt och rekommenderade åtgärder.
  
Du kan visa spoof intelligens insikt från mer &amp; än en instrumentpanel i Security Compliance Center. Oavsett vilken instrumentpanel du tittar på ger insikten samma information och gör att du snabbt kan utföra samma uppgifter.
  
Detta är en av flera genomgångar för Security &amp; Compliance Center. Mer information om hur du navigerar i rapporter och insikter finns i genomgångarna i avsnittet Omrelaterade ämnen.
  
## <a name="getting-to-the-spoof-intelligence-insight-in-the-security-amp-compliance-center"></a>Komma till falska underrättelseinsikter i &amp; Security Compliance Center

1. För att komma igång måste du [gå till Security &amp; Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).
    
2. Gå till &amp; instrumentpanelen för säkerhetsefterlevnad i **säkerhetsefterlevnadscentret.** \> **Dashboard.**
    
3. Leta efter den falska intelligensinsikten i raden **Insights.** Om du har aktiverat falska intelligens, då insikten har rätt **Spoofed domäner som misslyckades autentisering av de senaste 30 dagarna**. Om du inte har aktiverat förfalskningsskydd uppmanas du att göra det genom att använda titeln **Aktivera spoof-skydd**. 
    
## <a name="about-the-insight-on-the-dashboard"></a>Om insikten på instrumentpanelen

Insikten på instrumentpanelen visar information som denna.
  
![Skärmdump av falska intelligens insikt](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)
  
Den här insikten har två lägen:
  
 **Insiktsläge**. Om du har aktiverat någon falska policy visar insikten hur många e-postmeddelanden som påverkats av vår falska intelligenskapacitet under de senaste 30 dagarna. 
  
 **Vad händer om läge**. Om du inte har aktiverat någon falska policy, då insikten visar dig hur många e-postmeddelanden *skulle* ha påverkats av vår parodi intelligens kapacitet under de senaste 30 dagarna. 
  
Hursomhelst, de falska domäner som visas i insikten är indelade i två kategorier; misstänkta domänpar och icke-misstänkta domänpar. Dessa kategorier är ytterligare indelade i tre olika hinkar för dig att granska. 
  
Ett *domänpar* är en kombination av adressen "Från:" och den sändande infrastrukturen. 
  
- Adressen "Från" är den adress som visas som från-adressen av ditt e-postprogram. Den här adressen identifierar e-postmeddelandets författare. Det vill, brevlådan för den person eller det system som ansvarar för att skriva meddelandet. Detta kallas ibland 5322.Från-adressen.
    
- Den sändande infrastrukturen, eller avsändaren, är organisationsdomänen för PTR-posten för den sändande IP-adressen. Om den sändande IP-adressen inte har någon PTR-post identifieras avsändaren av den sändande IP-adressen med 255.255.255.0-nätmasken i CIDR-notation (/24). Om IP-adressen till exempel är 192.168.100.100 är avsändarens fullständiga IP-adress 192.168.100.100/24.
    
 **Misstänkta domänpar** inkluderar: 
  
- **Hög självförtroende parodi**. Office 365 fick starka signaler om att dessa domäner är misstänkta, baserat på de historiska sändningsmönstren och domännamnens ryktespoäng. Office 365 är mycket säker på att domänerna är falska och att meddelanden som skickas från dessa domäner är mindre benägna att vara legitima. 
    
- **Måttligt förtroende**. Office 365 tog emot måttliga signaler om att dessa domäner är misstänkta, baserat på historiska sändningsmönster och domänens ryktespoäng. Office 365 är måttligt säker på att domänerna är falska och att meddelanden som skickas från dessa domäner är legitima. Denna hink har en större chans att innehålla falska positiva (FPs) än hög förtroende parodi hink. 
    
 **Icke-misstänkta domänpar** inkluderar **räddade parodi**. Räddade förfalskningar är domäner som har misslyckats med explicita autentiseringskontroller ( [SPF,](https://docs.microsoft.com/office365/SecurityCompliance/how-office-365-uses-spf-to-prevent-spoofing) [DKIM,](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email) [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)) men klarat våra utökade autentiseringskontroller. Som ett resultat av detta räddade Office 365 e-post för din räkning och inga anti-förfalskningsåtgärder vidtogs på posten. 
  
## <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>Visa detaljerad information om misstänkta domänpar från spoof intelligence insight

1. Klicka på något av domänparen (högt, måttligt eller räddat) på den falska intelligensinsikten.
  
Sidan **Spoof Intelligence Insight** visas som visar en lista med avsändare som skickar oautentiserad e-post till din organisation. Informationen på den här sidan hjälper dig att avgöra om falska meddelanden är auktoriserade eller inte eller om du behöver vidta ytterligare åtgärder. Du kan sortera informationen efter antal meddelanden, det datum då förfalskningen senast upptäcktes med mera. (Klicka på kolumnrubriker, till exempel **Antal meddelanden** eller **Senast sett.)** 
    
2. Välj ett objekt i tabellen om du vill öppna ett informationsfönster som innehåller omfattande information om domänparet, inklusive varför vi fångade detta, vad du behöver göra, en domänsammanfattning, WhoIs-data om avsändaren och liknande e-postmeddelanden som vi har sett i din klient från samma avsändare. Härifrån kan du också välja att lägga till eller ta bort domänparet från **listan Tillåtd säkerhet avsändare.** 
  
![Skärmbild av en domän i informationsfönstret för falska informationsinformation](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)
  
## <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a>Lägga till eller ta bort en domän från listan Tillåtd avsändare

Du lägger till eller tar bort en domän från listan Tillåtd säkerhet avsändare när du granskar domänparet i informationsfönstret i expertinformationsinsikten. Ställ bara in växlingsknappen därefter.
  
Detta ändrar den unika domänparkombinationen av den falska domänen och den sändande infrastrukturen och ger inte täckning för hela den falska domänen eller den sändande infrastrukturen isolerat. Om du till exempel lägger till följande domänpar i listan Tillåten tillSpoof: *Spoofed Domain* "gmail.com" och *Sending Infrastructure* "tms *.mx.com",* tillåts endast e-post från det domänparet att förfalskas. Andra avsändare som försöker förfalska "gmail.com" och andra domäner som "tms.mx.com" försök att förfalska kommer att fortsätta att skyddas av falska intelligens. 
  
## <a name="related-topics"></a>Relaterade ämnen

[Läs mer om falska underrättelser](learn-about-spoof-intelligence.md)
  
[Anti-förfalskningsskydd i Office 365](anti-spoofing-protection.md)
  
[Genomgång - Från en instrumentpanel till en insikt](from-a-dashboard-to-an-insight.md)
  
[Genomgång - Från en detaljerad rapport till en insikt](from-a-detailed-report-to-an-insight.md)
  
[Genomgång - Från en insikt till en detaljerad rapport](from-an-insight-to-a-detailed-report.md)
  

