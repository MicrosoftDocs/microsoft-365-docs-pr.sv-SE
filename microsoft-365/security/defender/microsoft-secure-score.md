---
title: Microsoft Secure Score
description: Här beskrivs Microsoft Secure Score Microsoft 365 säkerhetscenter, hur du kan förbättra säkerheten och vilka säkerhetsadministratörer kan förvänta sig.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center, improvement actions
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
ms.openlocfilehash: 4a2c220cab15751671b9b38c3bb2fda3db12c9e1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245383"
---
# <a name="microsoft-secure-score"></a>Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft Secure Score är ett mått på en organisations säkerhetssäkerhet, med ett högre tal som anger fler förbättringsåtgärder som vidtas. Den finns på Microsoft 365 https://security.microsoft.com/securescore [Säkerhetscenter.](overview-security-center.md)

Om du följer rekommendationerna för Secure Score kan du skydda organisationen från hot. Från en centraliserad instrumentpanel i Microsoft 365 säkerhetscenter kan organisationer övervaka och arbeta med säkerheten för sina Microsoft 365 identiteter, appar och enheter.

Secure Score hjälper organisationer att:  

* Rapport om den aktuella statusen för organisationens säkerhetsstatus.
* Förbättra säkerheten genom att tillhandahålla förutsägbarhet, synlighet, vägledning och kontroll.  
* Jämför med riktvärden och skapa KPI:er (Key Performance Indicators).

Organisationer får tillgång till robusta visualiseringar av mätvärden och trender, integrering med andra Microsoft-produkter, resultatjämförelse med liknande organisationer och mycket mer. Poängen kan också återspegla när lösningar från tredje part har åtgärdat rekommenderade åtgärder.

![Startsida för Secure Score](../../media/secure-score/secure-score-home-page.png)

## <a name="how-it-works"></a>Så här fungerar det

Du får poäng för följande åtgärder:

- Konfigurera rekommenderade säkerhetsfunktioner
- Utföra säkerhetsrelaterade uppgifter
- Åtgärda förbättringsåtgärden i ett program eller en programvara från tredje part, eller en alternativ minskning

Vissa förbättringsåtgärder ger endast poäng när de är slutförda. Vissa ger delpunkter om de är slutförda för vissa enheter eller användare. Om du inte kan eller inte vill utföra någon av förbättringsåtgärderna kan du välja att acceptera risken eller återstående risk.

Om du har en licens för någon av De Microsoft-produkter som stöds visas rekommendationer för dessa produkter. Vi visar dig alla tänkbara förbättringar för en produkt, oavsett licensversion, prenumeration eller abonnemang. På så sätt kan du förstå metodtips för säkerhet och förbättra ditt resultat. Din absolut säkerhet som representeras av Secure Score förblir densamma oavsett vilka licenser din organisation äger för en viss produkt. Kom ihåg att säkerheten bör balanseras med användbarheten, och alla rekommendationer kan inte fungera för din miljö.

Poängen uppdateras i realtid för att återspegla informationen som presenteras på visualiserings- och förbättringsåtgärdssidorna. Secure Score synkroniseras också dagligen för att ta emot systemdata om dina uppnåde poäng för varje åtgärd.

### <a name="key-scenarios"></a>Viktiga scenarier

- [Kontrollera ditt aktuella poängresultat](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [Jämför poäng med organisationer som ditt](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [Visa förbättringsåtgärder och bestäm en handlingsplan](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [Initiera arbetsflöden att undersöka eller implementera](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a>Så här poängas förbättringsåtgärder

Varje förbättringsåtgärd är värd 10 punkter eller mindre och de flesta poängs på binärt sätt. Om du implementerar förbättringsåtgärden, till exempel skapar en ny princip eller aktiverar en viss inställning, får du 100 % av punkterna. För andra förbättringsåtgärder anges punkter som procent av den totala konfigurationen.

En förbättringsåtgärd ger dig till exempel 10 poäng genom att skydda alla användare med multifaktorautentisering. Du har bara 50 av 100 totala användare skyddade, så du får en partiell poäng på 5 poäng (50 skyddade / 100 totalt * 10 max pts = 5 pts).

### <a name="products-included-in-secure-score"></a>Produkter som ingår i Secure Score

Det finns för närvarande rekommendationer för följande produkter:

- Microsoft 365 (inklusive Exchange Online)
- Azure Active Directory
- Microsoft Defender för Endpoint
- Microsoft Defender for Identity
- Cloud App Security
- Microsoft Teams

Rekommendationer för andra säkerhetsprodukter kommer snart. Rekommendationerna täcker inte alla attackytor som är kopplade till varje produkt, men de är en bra baslinje. Du kan också markera de förbättringsåtgärder som omfattas av en tredje part eller en alternativ minskning.

### <a name="security-defaults"></a>Standardinställningar för säkerhet

Microsoft Secure Score har uppdaterat förbättringsåtgärder för att stödja säkerhetsstandarder i [Azure Active Directory,](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)vilket gör det enklare att skydda organisationen med förkonfigurerade säkerhetsinställningar för vanliga attacker.

Om du aktiverar säkerhetsstandardvärden tilldelas du fullständiga poäng för följande förbättringsåtgärder:

- Se till att alla användare kan slutföra multifaktorautentisering för säker åtkomst (9 punkter)
- Kräv MFA för administrativa roller (10 poäng)
- Aktivera princip för att blockera äldre autentisering (7 punkter)

>[!IMPORTANT]
>Säkerhetsstandarder omfattar säkerhetsfunktioner som ger liknande säkerhet som förbättringsåtgärderna "inloggningsriskpolicy" och "användarriskpolicy". I stället för att konfigurera dessa principer ovanpå säkerhetsstandardvärdena rekommenderar vi att du uppdaterar deras status till "Löst genom alternativ minskning".

## <a name="required-permissions"></a>Behörighet som krävs

För att ha behörighet att komma åt Microsoft Secure Score måste du tilldelas en av följande roller i Azure Active Directory.

### <a name="read-and-write-roles"></a>Läs- och skrivroller

Med läs- och skrivåtkomst kan du göra ändringar och interagera direkt med Secure Score. Du kan också tilldela skrivskyddsåtkomst till andra användare.

* Global administratör
* Säkerhetsadministratör
* Exchange-administratör
* SharePoint-administratör
* Kontoadministratör

### <a name="read-only-roles"></a>Skrivskyddade roller

Med skrivskydd kan du inte redigera status eller anteckningar för en förbättringsåtgärd, redigera poängzoner eller redigera anpassade jämförelser.

* Helpdesk-administratör
* Användaradministratör
* Tjänstadministratör
* Säkerhetsläsare
* Säkerhetsoperatör
* Global läsare

## <a name="risk-awareness"></a>Riskmedvetande

Microsoft Secure Score är en numerisk sammanfattning av din säkerhetskonfiguration baserad på systemkonfigurationer, användarbeteende och andra säkerhetsrelaterade mått. Det är inte ett absolut mått på hur troligt det är att ditt system eller dina data bryts. Den representerar i stället den utsträckning som du har infört säkerhetskontroller i din Microsoft-miljö som kan hjälpa till att uppväga risken för intrång. Ingen onlinetjänst är en del av säkerhetsbrister och säkra poäng ska inte tolkas som en garanti för säkerhetsbrister på något sätt.

## <a name="we-want-to-hear-from-you"></a>Vi vill höra från dig

Om du har problem kan du meddela oss genom att publicera i communityn [säkerhet, & sekretess och](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) efterlevnad. Vi övervakar communityn och kommer att hjälpa dig.

## <a name="related-resources"></a>Relaterade resurser

- [Utvärdera din säkerhetsstatus](microsoft-secure-score-improvement-actions.md)
- [Spåra din Microsoft Secure Score-historik och nå dina mål](microsoft-secure-score-history-metrics-trends.md)
- [Kommer snart](microsoft-secure-score-whats-coming.md)
- [Vad är det senaste](microsoft-secure-score-whats-new.md)