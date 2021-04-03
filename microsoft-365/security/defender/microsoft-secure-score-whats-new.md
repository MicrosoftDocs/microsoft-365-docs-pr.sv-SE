---
title: Vad är nytt i Microsoft Secure Score
description: Här beskrivs vilka nya ändringar som har hänt med Microsoft Secure Score i Säkerhetscenter för Microsoft 365.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 5a868904a43e17952368e097c0b0e963252d5bed
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570369"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Vad är nytt i Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Vi har gjort några ändringar för att Microsoft Secure Score ska bli en bättre representant för din säkerhetsrepresentant. Mer information om planerade ändringar finns [i Vad kommer i Microsoft Secure Score?](microsoft-secure-score-whats-coming.md)

Microsoft Secure Score finns på https://security.microsoft.com/securescore Säkerhetscenter för [Microsoft 365.](overview-security-center.md)
    
## <a name="february-2021"></a>Februari 2021

### <a name="compatibility-with-graph-api"></a>Kompatibilitet med Graph API

Microsoft Secure Score-rekommendationer som levereras via Graph API ser ut och viktas på samma sätt som de rekommendationer som du ser för närvarande i Säkerhetscenter för Microsoft 365.

## <a name="january-2021"></a>Januari 2021

### <a name="added-our-first-security-recommendation-for-microsoft-teams"></a>Lade till vår första säkerhetsrekommendationer för Microsoft Teams

Microsoft Teams-kunder ser "Begränsa anonyma användare från att ansluta till möten" som en ny förbättringsåtgärd i Secure Score.

## <a name="december-2020"></a>December 2020

### <a name="added-six-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Sex kontorelaterade förbättringsåtgärder för Microsoft Defender för Endpoint (tidigare Microsoft Defender ATP):

- Ange "Minsta lösenordslängd" till 14 eller fler tecken
- Ange "Framtvinga lösenordshistorik" till 24 eller fler lösenord
- Ange Maximal ålder för lösenord till 60 dagar eller färre, men inte 0.
- Ange Lägsta ålder för lösenord till 1 eller fler dagar
- Inaktivera det inbyggda administratörskontot
- Inaktivera det inbyggda gästkontot

## <a name="november-2020"></a>November 2020

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a>Tog bort möjligheten att skapa ServiceNow-biljetter via Secure Score 

Möjligheten att skapa ServiceNow-biljetter via Secure Score genom att gå till **Share > ServiceNow** är inte längre tillgänglig. Tack för din feedback och fortsatt support medan vi fastställer nästa steg.

### <a name="added-three-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Tre tjänstrelaterade förbättringsåtgärder för Microsoft Defender för Slutpunkt (tidigare Microsoft Defender ATP):

- Åtgärda okvotad tjänstsökväg för Windows-tjänster
- Ändra den körbara sökvägen för tjänsten till en gemensam skyddad plats
- Ändra tjänstkonto för att undvika cachelagrat lösenord i Windows-registret

## <a name="october-2020"></a>Oktober 2020

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a>Ta bort förbättringsåtgärd relaterad till Microsoft Defender för Slutpunkt

- Ställ in webbinnehållskontroll för Microsoft Defender SmartScreen-appen i Windows Store för att varna

## <a name="august-2020"></a>Augusti 2020

### <a name="updated-improvement-action-for-azure-active-directory"></a>Uppdaterad förbättringsåtgärd för Azure Active Directory

- Aktivera princip för att blockera äldre autentisering

## <a name="incompatibility-with-identity-secure-score"></a>Inkompatibilitet med Identity Secure Score

I den senaste versionen av Microsoft Secure Score har en förbättrad poängmodell släppts. Dessa ändringar möjliggör en mer flexibel och korrekt vy av din säkerhetsrisk. Men dessa uppdateringar har gjort Microsoft Secure Score tillfälligt inkompatibelt med Identity Secure Score.

Med tiden kommer Identity Secure Score att använda den nya poängmodellen. Tills dess kommer kunderna att se skillnader i poäng som rapporterats av Microsoft Secure Score och Identity Secure Score. Vi ber om ursäkt för eventuella besvär detta orsakar och arbetar för att dessa upplevelser ska bli mer kompatibla i framtiden.

## <a name="updated-improvement-actions"></a>Uppdaterade förbättringsåtgärder

- Åtgärder för att förbättra Azure Active Directory har lagts till
- Microsoft Defender har lagts till för åtgärder för identitetsförbättring
- Stöd för Microsoft Defender för slutpunktshot & [säkerhetsrekommendationer för sårbarhetshantering](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
    - Alla släppta säkerhetsrekommendationer som tillhandahålls av TVM är nu tillgängliga

## <a name="updated-interface-and-functionality"></a>Uppdaterat gränssnitt och funktioner

* Alla nya mätvärden och trender för CISO- och leadnivådiskussioner
* Nya sätt att spåra och skapa prestanda för ditt resultat
* Bättre spårning och förståelse för poäng regressioner
* Filtrera, tagga, söka och gruppera förbättringsåtgärder
* Hantera mot dina framtida mål med hjälp av poängprojektioner och planerade åtgärder
* Och mycket mer!

## <a name="we-want-to-hear-from-you"></a>Vi vill höra från dig

Om du har problem kan du meddela oss genom att publicera i communityn [säkerhet, & sekretess och](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) efterlevnad. Vi övervakar communityn och kommer att hjälpa dig.

## <a name="related-resources"></a>Relaterade resurser

- [Utvärdera din säkerhetsstatus](microsoft-secure-score-improvement-actions.md)
- [Spåra din Microsoft Secure Score-historik och nå dina mål](microsoft-secure-score-history-metrics-trends.md)
- [Kommer snart](microsoft-secure-score-whats-coming.md)