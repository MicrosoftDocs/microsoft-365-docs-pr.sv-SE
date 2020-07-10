---
title: Microsoft Secure Score
description: I artikeln beskrivs Microsoft Secure Score i säkerhetscentret Microsoft 365, hur du kan förbättra säkerhetspositionen och vad säkerhetsadministratörer kan förvänta sig.
keywords: säkerhet, skadlig kod, Microsoft 365, M365, säker poäng, säkerhetscenter, förbättringsåtgärder
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 212cefebfa3b4954f30d114419f82a5862e98a4f
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094804"
---
# <a name="microsoft-secure-score"></a>Microsoft Secure Score

Microsoft Secure Score är ett mått på en organisations säkerhetsposition, med ett högre antal som anger fler förbättringsåtgärder som vidtas. Den finns https://security.microsoft.com/securescore på i Microsoft [365 security center](overview-security-center.md).

Om du följer rekommendationerna för säker poäng kan du skydda din organisation från hot. Från en centraliserad instrumentpanel i Microsoft 365-säkerhetscentret kan organisationer övervaka och arbeta med säkerheten för sina Microsoft 365-identiteter, data, appar, enheter och infrastruktur.

Secure Score hjälper organisationer:  

* Rapport om det aktuella läget för organisationens säkerhetsposition.
* Förbättra deras säkerhetsposition genom att tillhandahålla upptäckbarhet, synlighet, vägledning och kontroll.  
* Jämför med riktmärken och fastställ nyckeltal.

Organisationer får tillgång till robusta visualiseringar av mått och trender, integrering med andra Microsoft-produkter, poängjämlikhet med liknande organisationer och mycket mer. Poängen kan också återspegla när tredjepartslösningar har åtgärdat rekommenderade åtgärder.

![Startsida för säkra poäng](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>Så här fungerar det

Du får poäng för att konfigurera rekommenderade säkerhetsfunktioner, utföra säkerhetsrelaterade uppgifter eller åtgärda förbättringsåtgärden med ett program eller program från tredje part, eller en alternativ begränsning. Vissa förbättringsåtgärder ger bara poäng när de är helt slutförda, och vissa ger partiella poäng om de slutförs för vissa enheter eller användare. Om du inte kan eller inte vill anta någon av förbättringsåtgärderna kan du välja att acceptera risken eller den återstående risken.

Vi visar dig alla möjliga förbättringar, oavsett licens, så att du kan förstå bästa praxis för säkerhet och förbättra dina poäng. Din absoluta säkerhetsposition representeras av Secure Score, som förblir densamma oavsett vilka produktlicenser din organisation äger. Tänk på att säkerheten bör balanseras med användbarhet, och inte varje rekommendation kan fungera för din miljö.

Din poäng uppdateras i realtid för att återspegla den information som presenteras i visualiseringar och förbättring åtgärd sidor. Secure Score synkroniserar också dagligen för att ta emot systemdata om dina uppnådda poäng för varje åtgärd.

### <a name="key-scenarios"></a>Viktiga scenarier

- [Kontrollera din aktuella poäng](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [Jämför dina poäng med organisationer som din](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [Visa förbättringsåtgärder och bestäm en handlingsplan](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [Initiera arbetsflöden för att undersöka eller implementera](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [Microsoft 365 säkerhetscenter och ServiceNow-integrering](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a>Hur förbättringsåtgärder görs

Varje förbättringsåtgärd är värd 10 poäng eller mindre. De flesta görs på ett binärt sätt - om du genomför förbättringsåtgärden, som att skapa en ny princip eller aktivera en viss inställning, får du 100% av poängen. För andra förbättringsåtgärder anges punkter som en procentandel av den totala konfigurationen. Till exempel, om förbättringen åtgärd stater du får 10 poäng genom att skydda alla dina användare med multifaktorautentisering och du bara har 50 av 100 totala användare skyddade, skulle du få en partiell poäng på 5 poäng (50 skyddade / 100 totalt * 10 max poäng = 5 poäng partiell poäng).

### <a name="products-included-in-secure-score"></a>Produkter som ingår i Secure Score

För närvarande finns det rekommendationer för Microsoft 365 (inklusive Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP och Cloud App Security. Rekommendationer för andra säkerhetsprodukter kommer snart. Rekommendationerna kommer inte att täcka alla angreppsytor som är associerade med varje produkt, men de är en bra baslinje. Du kan också markera förbättringsåtgärderna som omfattas av en tredje part eller alternativ begränsning.

### <a name="security-defaults"></a>Standardinställningar för säkerhet

Microsoft Secure Score har uppdaterade förbättringsåtgärder för att stödja [säkerhetsstandarder i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), vilket gör det enklare att skydda din organisation med förkonfigurerade säkerhetsinställningar för vanliga attacker.

Om du aktiverar standardvärden för säkerhet får du fullständiga poäng för följande förbättringsåtgärder:

- Se till att alla användare kan slutföra multifaktorautentisering för säker åtkomst (9 poäng)
- Kräv MFA för administrativa roller (10 poäng)
- Aktivera principen för att blockera äldre autentisering (7 poäng)

>[!IMPORTANT]
>Standardinställningar för säkerhet omfattar säkerhetsfunktioner som ger liknande säkerhet som förbättringsåtgärderna för "inloggningsrisk" och "användarriskprincip". I stället för att ställa in dessa principer ovanpå säkerhetsinställningarna rekommenderar vi att de uppdateras till "Löst genom alternativ begränsning".

## <a name="required-permissions"></a>Nödvändiga behörigheter

Om du vill ha behörighet att komma åt Microsoft Secure Score måste du tilldelas en av följande roller i Azure Active Directory.

### <a name="read-and-write-roles"></a>Läs- och skrivroller

Med läs- och skrivåtkomst kan du göra ändringar och interagera direkt med Secure Score. Du kan också tilldela skrivskyddad åtkomst till andra användare.

* Global administratör
* Säkerhetsadministratör
* Exchange-administratör
* SharePoint-administratör
* Kontoadministratör

### <a name="read-only-roles"></a>Skrivskyddade roller

Med skrivskyddad åtkomst kan du inte redigera status eller anteckningar för en förbättringsåtgärd, redigera poängzoner eller redigera anpassade jämförelser.

* Helpdesk-administratör
* Användaradministratör
* Tjänstadministratör
* Säkerhetsläsare
* Säkerhetsoperatör
* Global läsare

## <a name="risk-awareness"></a>Riskmedvetenhet

Microsoft Secure Score är en numerisk sammanfattning av din säkerhetsposition baserat på systemkonfigurationer, användarbeteende och andra säkerhetsrelaterade mätningar. Det är inte ett absolut mått på hur sannolikt ditt system eller data kommer att brytas. Snarare är det i vilken utsträckning du har antagit säkerhetskontroller i din Microsoft-miljö som kan bidra till att kompensera risken för att brytas. Ingen onlinetjänst är helt immun mot säkerhetsöverträdelser, och säker poäng bör inte tolkas som en garanti mot säkerhetsöverträdelse på något sätt.

## <a name="whats-new"></a>Vad är nytt? 

För att göra Microsoft Secure Score till en bättre representant för din säkerhetsposition har vi gjort vissa ändringar. Mer information om planerade ändringar finns [i Vad som kommer i Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).

### <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Inkompatibilitet med Identity Secure Score och Graph API

I den senaste versionen av Microsoft Secure Score har en förbättrad poängsättningsmodell släppts. Dessa ändringar möjliggör en mer flexibel och korrekt bild av din säkerhetsposition. Dessa uppdateringar har dock gjort Microsoft Secure Score tillfälligt inkompatibelt med Identity Secure Score och Graph API.

Med tiden antar Identity Secure Score och Graph API den nya bedömningsmodellen. Fram till dess ser kunderna skillnader i poängen som rapporteras av Microsoft Secure Score, Identity Secure Score och Graph API. Vi ber om ursäkt för eventuella besvär detta orsakar, och arbetar för att säkerställa dessa erfarenheter är mer kompatibla i framtiden.

### <a name="updated-improvement-actions"></a>Uppdaterade förbättringsåtgärder

- Lade till förbättringarsåtgärder för Azure Active Directory
- Lade till Azure Advanced Threat Protection improvement-åtgärder
- Stöd för säkerhetsrekommendationer för Microsoft Defender ATP [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
    - Alla utgivna säkerhetsrekommendationer från TVM finns nu tillgängliga

### <a name="updated-interface-and-functionality"></a>Uppdaterat gränssnitt och funktionalitet

* Alla nya statistik- och trendersvyer för CISO- och leadnivådiskussioner
* Nya sätt att spåra och jämföra din poäng
* Bättre spårning och förståelse för poängregressioner
* Filtrera, tagga, söka och gruppera förbättringsåtgärder
* Hantera mot dina framtida mål med hjälp av resultatprognoser och planerade åtgärder
* Och mer!

### <a name="june-2020"></a>Juni 2020

#### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Borttagen förbättringsåtgärd för Microsoft Defender Advanced Threat Protection

* Aktivera regler för minskning av attackytan

#### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Lade till förbättringsåtgärder för Microsoft Defender Advanced Threat Protection

* Blockera Adobe Reader från att skapa underordnade processer
* Använd avancerat skydd mot ransomware
* Blockera alla Office-program från att skapa underordnade processer
* Blockera Office-program från att skapa körbart innehåll
* Blockera JavaScript eller VBScript från att starta nedladdat körbart innehåll
* Blockera körning av potentiellt fördunklade skript
* Blockera körbart innehåll från e-postklient och webbmail
* Blockera Office-kommunikationsprogram från att skapa underordnade processer
* Blockera ej betrodda och osignerade processer som körs från USB
* Blockera persistens genom WMI-händelseprenumeration
* Blockera Office-program från att injicera kod i andra processer
* Blockera körbara filer från att köras om de inte uppfyller ett prevalens-, ålders- eller tillförlitligt listkriterium
* Blockera processskapanden från PSExec- och WMI-kommandon
* Blockera stöld av autentiseringsuppgifter från undersystemet Windows lokala säkerhetsmyndighet (lsass.exe)
* Blockera Win32 API-anrop från Office-makron

## <a name="we-want-to-hear-from-you"></a>Vi vill höra från dig

Om du har några problem, vänligen meddela oss genom att publicera i [security, privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community. Vi övervakar samhället och kommer att ge hjälp.

## <a name="related-resources"></a>Relaterade resurser

- [Få insyn i din säkerhetsposition](microsoft-secure-score-improvement-actions.md)
- [Spåra din Microsoft Secure Score-historik och uppnå mål](microsoft-secure-score-history-metrics-trends.md)
- [Kommer snart](microsoft-secure-score-whats-coming.md)
