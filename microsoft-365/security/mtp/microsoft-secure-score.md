---
title: Microsoft Secure Score
description: Här beskrivs säker Poäng i Microsoft 365 Security Center, hur du förbättrar Posture och vilka säkerhets administratörer som kan förvänta dig.
keywords: Microsoft säkra poäng, säkra poäng, Office 365 säkra poäng, säkerhets poäng, Microsoft 365 säkerhets Center, förbättrings åtgärder
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
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
ms.openlocfilehash: 39abcbde82c2902b091b42db3dbc8e1ee2cbd924
ms.sourcegitcommit: 8b3ff6e9f8931327b6f0541fd882107687cd123e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/23/2021
ms.locfileid: "49942796"
---
# <a name="microsoft-secure-score"></a>Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft Secure score är ett mått på en organisations säkerhets Posture, med ett högre nummer som indikerar fler förbättrings åtgärder. Den finns https://security.microsoft.com/securescore i [säkerhets Center för Microsoft 365](overview-security-center.md).

Genom att följa rekommendationerna för säker Poäng kan du skydda din organisation mot hot. Från en central instrument panel i Microsoft 365 Security Center kan organisationer övervaka och arbeta med säkerheten hos sina Microsoft 365-identiteter, appar och enheter.

Säkra poäng gör att organisationer:  

* Rapportera om organisationens säkerhets Posture.
* Förbättra deras säkerhets Posture genom att tillhandahålla upptäckter, synlighet, vägledning och kontroll.  
* Jämför med benchmarks och skapa KPI: er (Key Performance Indicators).

Organisationer får till gång till stabila visualiseringar av mått och trender, integrering med andra Microsoft-produkter, resultat jämförelse med liknande organisationer och mycket mer. Poängen kan också återspegla när lösningar från tredje part har åtgärdat rekommenderade åtgärder.

![Säkra Poäng start sidan](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>Så här fungerar det

Du får poäng för följande åtgärder:

- Konfigurera rekommenderade säkerhetsfunktioner
- Utföra säkerhetsrelaterade uppgifter
- Adressera förbättrings åtgärden med ett program eller program från tredje part, eller en alternativ minskning

Vissa förbättrings åtgärder ger bara poäng när det är fullständigt ifyllt. Vissa delar ger ofullständiga punkter om de är klara för vissa enheter eller användare. Om du inte kan eller inte vill använda en av förbättrings åtgärderna kan du välja att acceptera risken eller återstående risk.

Om du har en licens för en av de Microsoft-produkter som stöds, ser du rekommendationer för dessa produkter. Vi visar alla möjliga förbättringar för en produkt, oavsett om det gäller licens, abonnemang eller abonnemang. På så sätt förstår du säkerhets rekommendationer och förbättrar poängen. Dina absoluta säkerhets Posture, som representeras av säkra poäng, förblir desamma, oavsett vilka licenser organisationen äger för en viss produkt. Tänk på att säkerheten bör balanseras med användbarhet och inte varje rekommendation kan fungera för din miljö.

Resultatet uppdateras i real tid för att visa informationen som visas i åtgärds sidorna visualiseringar och förbättring. Säkra Poäng synkroniserar också varje dag med att ta emot system data om dina erhållna Poäng för varje åtgärd.

### <a name="key-scenarios"></a>Viktiga scenarier

- [Kontrol lera aktuell Poäng](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [Jämför poängen med dina organisationer som dina](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [Visa förbättrings åtgärder och bestäm ett åtgärds abonnemang](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [Initiera och implementera arbets flöden](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a>Hur förbättrings åtgärder betygs ätts

Varje förbättrings åtgärd är värt 10 Poäng eller mindre och de flesta är på ett binärt sätt. Om du implementerar förbättrings åtgärden, till exempel skapa en ny princip eller aktiverar en specifik inställning, får du 100% av punkterna. För andra förbättrings åtgärder anges Poäng som en procent andel av den totala konfigurationen.

En förbättrings åtgärd visar till exempel 10 Poäng genom att skydda alla användare med multifaktorautentisering. Du har bara 50 av 100 totalt antal användare som är skyddade, så du får lite poäng med 5 Poäng (50 skyddat/100 totalt * 10 Max punkter = 5 punkter).

### <a name="products-included-in-secure-score"></a>Produkter ingår i säkra Poäng

För närvarande finns det rekommendationer för följande produkter:

- Microsoft 365 (inklusive Exchange Online)
- Azure Active Directory
- Microsoft Defender för Endpoint
- Microsoft Defender for Identity
- Cloud App Security
- Microsoft Teams

Rekommendationer för andra säkerhets produkter kommer snart. Rekommendationerna täcker inte alla de attack ytor som är associerade med varje produkt, men de är en bra original plan. Du kan också markera förbättrings åtgärderna som täcks av tredje part eller annan åtgärd.

### <a name="security-defaults"></a>Standardinställningar för säkerhet

Microsofts säkra poäng har uppdaterat förbättrings åtgärder för att hantera [säkerhets standarder i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), vilket gör det enklare att skydda din organisation med förkonfigurerade säkerhets inställningar för vanliga angrepp.

Om du aktiverar säkerhets inställningar får du fullständiga Points för följande förbättringar:

- Se till att alla användare kan slutföra multifaktorautentisering för säker åtkomst (9 Poäng)
- Kräv MFA för administrativa roller (10 Poäng)
- Aktivera princip för blockering av bakåtkompatibel-inloggningsautentisering (7 Poäng)

>[!IMPORTANT]
>Säkerhets standarder inkluderar säkerhetsfunktioner som ger liknande säkerhet i avsnittet "policy för inloggnings risker" och "förbättring av användar risk policy". I stället för att konfigurera dessa principer ovanpå säkerhets standardinställningarna rekommenderar vi att du uppdaterar deras status till "löst via annan begränsning".

## <a name="required-permissions"></a>Nödvändiga behörigheter

För att få åtkomst till Microsoft Secure score måste du ha en av följande roller i Azure Active Directory.

### <a name="read-and-write-roles"></a>Läsa och skriva roller

Med Läs-och skriv åtkomst kan du göra ändringar och direkt interagera med säkra poäng. Du kan också tilldela skrivskyddad åtkomst till andra användare.

* Global administratör
* Säkerhetsadministratör
* Exchange-administratör
* SharePoint-administratör
* Konto administratör

### <a name="read-only-roles"></a>Skrivskyddade roller

Med skrivskyddad åtkomst kan du inte redigera status eller anteckningar för en förbättrings åtgärd, redigera Poäng zoner eller redigera anpassade jämförelser.

* Helpdesk-administratör
* Användaradministratör
* Tjänst administratör
* Säkerhetsläsare
* Säkerhetsoperatör
* Global läsare

## <a name="risk-awareness"></a>Risk medvetenhet

Microsofts säkra poäng är en numerisk Sammanfattning av dina säkerhets Posture, baserat på systemkonfigurationer, användar beteende och andra säkerhetsrelaterade mått. Det är inte ett absolut mått på hur troligt det är att systemet eller data blir. I stället representerar den utsträckning som du har antagit säkerhets kontroller i din Microsoft-miljö som kan hjälpa till att undanröja risken att bli intrång. Ingen online tjänst är immun mot säkerhets brott och säkra Poäng bör inte tolkas som en garanti mot säkerhets brott på något sätt.

## <a name="we-want-to-hear-from-you"></a>Vi vill höra från dig

Om du har några problem kan du meddela oss genom att publicera det i [säkerhets-, integritets &](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community. Vi övervakar communityn och ger hjälp.

## <a name="related-resources"></a>Relaterade resurser

- [Utvärdera säkerhets genom övergå molnet](microsoft-secure-score-improvement-actions.md)
- [Spåra din Microsoft säkra Poäng historik och uppfylla målen](microsoft-secure-score-history-metrics-trends.md)
- [Kommer snart](microsoft-secure-score-whats-coming.md)
- [Nyheter](microsoft-secure-score-whats-new.md)
