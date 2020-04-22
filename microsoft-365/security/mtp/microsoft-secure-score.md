---
title: Microsoft Secure Score
description: I artikeln beskrivs Microsoft Secure Score i säkerhetscentret Microsoft 365, hur information beräknas och vilka säkerhetsadministratörer som kan förvänta sig.
keywords: säkerhet, malware, Microsoft 365, M365, säker poäng, säkerhetscenter, förbättringsåtgärder
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
ms.openlocfilehash: c15f0b30dbf377da4e01ba199852f02bd7a003ff
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637110"
---
# <a name="microsoft-secure-score"></a>Microsoft Secure Score

Microsoft Secure Score är ett mått på en organisations säkerhetsposition, med ett högre antal som anger fler förbättringsåtgärder som vidtas. Om du följer rekommendationerna om säkerhetsresultat kan du skydda din organisation från hot. Från en centraliserad instrumentpanel i Microsoft 365-säkerhetscentret kan organisationer övervaka och arbeta med säkerheten för sina Microsoft 365-identiteter, data, appar, enheter och infrastruktur.

Secure Score hjälper organisationer:

* Rapport om det aktuella läget för organisationens säkerhetsposition.
* Förbättra deras säkerhetsposition genom att tillhandahålla upptäckbarhet, synlighet, vägledning och kontroll.  
* Jämför med riktmärken och fastställ nyckeltal.

Organisationer får tillgång till robusta visualiseringar av mått och trender, integrering med andra Microsoft-produkter, poängjämlikhet med liknande organisationer och mycket mer. Poängen kan också återspegla när tredjepartslösningar har åtgärdat rekommenderade åtgärder.

Dessutom kan du komma åt dina rekommendationer och poäng via [Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api). Läs mer om [resurstypen Säker poäng](https://go.microsoft.com/fwlink/?linkid=2092996).

## <a name="how-it-works"></a>Så här fungerar det

Du får poäng för att konfigurera rekommenderade säkerhetsfunktioner, utföra säkerhetsrelaterade uppgifter (till exempel visa rapporter) eller åtgärda förbättringsåtgärden med ett program eller en programvara från tredje part. Vissa förbättringsåtgärder ger bara poäng när de är helt slutförda, och vissa ger partiella poäng om de slutförs för vissa enheter eller användare.

Vi visar dig alla möjliga förbättringar, oavsett licens, så att du kan förstå bästa praxis för säkerhet och förbättra dina poäng. Din absoluta säkerhetsposition representeras av Secure Score, som förblir densamma oavsett vilka produktlicenser din organisation äger. Tänk på att säkerheten bör vara balanserad med användbarhet, och inte varje rekommendation kan fungera för din miljö.

Din poäng uppdateras i realtid för att återspegla den information som presenteras i visualiseringar och förbättring åtgärd sidor. Secure Score synkroniserar också dagligen för att ta emot systemdata om dina uppnådda poäng för varje åtgärd.

### <a name="how-improvement-actions-are-scored"></a>Hur förbättringsåtgärder görs

De flesta görs på ett binärt sätt - om du genomför förbättringsåtgärden, som att skapa en ny princip eller aktivera en viss inställning, får du 100% av poängen. För andra förbättringsåtgärder anges punkter som en procentandel av den totala konfigurationen. Till exempel, om förbättringen åtgärd stater du får 30 poäng genom att skydda alla dina användare med multifaktorautentisering och du bara har 5 av 100 totala användare skyddade, skulle du få en partiell poäng på cirka 2 poäng (5 skyddade / 100 totalt * 30 max poäng = 2 poäng partiell poäng).

### <a name="products-included-in-secure-score"></a>Produkter som ingår i Secure Score

För närvarande finns det rekommendationer för bland annat SharePoint Online, Exchange Online, OneDrive för företag, Microsoft Information Protection med mera), Azure AD och Cloud App Security. Rekommendationer för andra säkerhetsprodukter, som Azure ATP och Microsoft Defender ATP, kommer snart. Rekommendationerna kommer inte att omfatta alla angreppsytor som är associerade med varje produkt, men de är en bra baslinje. Du kan också markera förbättringsåtgärderna som omfattas av en tredje part.

## <a name="required-permissions"></a>Nödvändiga behörigheter

Om du vill ha behörighet att komma åt Microsoft Secure Score måste du tilldelas en av följande roller i Azure Active Directory.

### <a name="read-and-write-roles"></a>Läs- och skrivroller

Med läs- och skrivåtkomst kan du göra ändringar och interagera direkt med Secure Score. Du kan också tilldela skrivskyddad åtkomst till andra användare.

* Global administratör
* Säkerhetsadministratör
* Exchange-administratör
* SharePoint-administratör

### <a name="read-only-roles"></a>Skrivskyddade roller

Med skrivskyddad åtkomst kan du inte redigera status eller anteckningar för en förbättringsåtgärd, redigera poängzoner eller redigera anpassade jämförelser.

* Helpdesk-administratör
* Användaradministratör
* Tjänstadministratör
* Säkerhetsläsare
* Säkerhetsoperatör
* Global läsare

### <a name="graph-api"></a>Api för diagram

Om du vill komma åt Graph API måste du ha något av följande scope utöver en roll:

* SecurityEvents.Read.All (för skrivskyddad roll)
* SecurityEvents.ReadWrite.All (för läs- och skrivroll)

## <a name="gain-visibility-into-your-security-posture"></a>Få insyn i din säkerhetsposition

För att hjälpa dig den information du behöver snabbare är Microsofts förbättringsåtgärder organiserade i grupper:

* Identitet (Azure AD-konton & roller)
* Data (Microsofts informationsskydd)
* Enhet (inga förbättringsåtgärder för tillfället)
* App (e-post- och molnappar, inklusive Office 365 och Microsoft Cloud App Security)
* Infrastruktur (inga förbättringsåtgärder för tillfället)

På översiktssidan för Microsoft Secure Score kan du se hur poäng delas mellan dessa grupper och vilka punkter som är tillgängliga. Översiktssidan är också platsen för att få en helhetsbild av den totala poängen, historisk trend för din säkra poäng med jämförelsemål och prioriterade förbättringsåtgärder som kan vidtas för att förbättra din poäng.

![Startsida](../../media/secure-score/homepage-original.png)
för säker poäng*Bild 1: Översiktssida för Microsoft Secure Score*

## <a name="take-action-to-improve-your-score"></a>Vidta åtgärder för att förbättra din poäng

På fliken Förbättringsåtgärder visas de säkerhetsrekommendationer som åtgärdar möjliga angreppsytor, tillsammans med deras status (slutförd, inte slutförd, löst via tredje part och ignoreras). Du kan söka, filtrera och gruppera alla förbättringsåtgärder.

### <a name="ranking"></a>Ranking

Rankningen baseras på antalet återstående poäng kvar att uppnå, implementeringssvårigheter, användarpåverkan och komplexitet. De högst rankade förbättringsåtgärderna har ett stort antal punkter kvar med låg svårighet, användarpåverkan och komplexitet.

### <a name="actions"></a>Åtgärder

Åtgärder som är märkta som [Ej poängsatta] spåras inte av Microsoft Secure Score. Du kan fortfarande vidta åtgärder, men att slutföra dem kommer inte att påverka din poäng. Om en åtgärd spåras av Microsoft Secure Score i framtiden och du redan har slutfört den, återspeglar din säkra poäng automatiskt ändringen.

När du väljer en specifik förbättringsåtgärd visas en utfällning. För att slutföra åtgärden har du några alternativ:

1. Välj **Visa inställningar** för att gå till konfigurationsskärmen och göra ändringen. Du får sedan de punkter som åtgärden är värd, synlig på toppen av flugan ut. Det kan ta upp till 24 timmar att uppdatera poäng.

2. Välj **Lös via tredje part** eftersom förbättringsåtgärden redan har åtgärdats av ett program eller en programvara från tredje part. Du får de poäng som åtgärden är värd, så din säkra poäng bättre återspeglar din totala säkerhet hållning. Om en tredje part inte längre täcker kontrollen kan du markera förbättringsåtgärden som inte slutförd. Tänk på att Microsoft inte har någon insyn i om poängkraven har uppfyllts om förbättringsåtgärden markeras som löst via tredje part.

3. Välj **Ignorera** eftersom du har bestämt dig för att acceptera risken och inte anta förbättringsåtgärden. När du ignorerar en förbättringsåtgärd minskas det totala antalet säkra poäng du kan uppnå. Du kan visa den här åtgärden i historiken eller ångra den när som helst.

4. Välj **Granska** eftersom förbättringsåtgärden kräver att du regelbundet granskar en del av din miljö för att få och behålla poäng. Regler för vidarebefordran av postlådor bör till exempel granskas varje vecka för att se till att data inte exfilteras från nätverket. Du behöver inte göra några ändringar, men en åtgärd måste utföras. Om du regelbundet granskar reglerna får du poängen. Om inte, är poängen minskas.

![Exempel på förbättring av säker poäng](../../media/secure-score/secure-score1x450.png) ![Exempel på förbättringsåtgärd för säker poänggranskning](../../media/secure-score/secure-score2x450.png)

*Figurerna 2 & 3: Utfällbara förbättringsåtgärder*

## <a name="monitor-improvements-over-time"></a>Övervaka förbättringar över tid

Du kan visa ett diagram över organisationens poäng över tid på fliken **Historik.** Under diagrammet finns en lista över alla åtgärder som vidtagits i det valda tidsintervallet och deras attribut, till exempel resulterande poäng och kategori. Du kan anpassa ett datumintervall och filtrera efter kategori.

## <a name="risk-awareness"></a>Riskmedvetenhet

Microsoft Secure Score är en numerisk sammanfattning av din säkerhetsposition baserat på systemkonfigurationer, användarbeteende och andra säkerhetsrelaterade mätningar. Det är inte ett absolut mått på hur sannolikt ditt system eller data kommer att brytas. Snarare är det i vilken utsträckning du har antagit säkerhetskontroller i din Microsoft-miljö som kan bidra till att kompensera risken för att brytas. Ingen onlinetjänst är helt immun mot säkerhetsöverträdelser, och säker poäng bör inte tolkas som en garanti mot säkerhetsöverträdelse på något sätt.

## <a name="whats-new"></a>Vad är nytt?

För att göra Microsoft Secure Score till en bättre representant för din säkerhetsposition har vi gjort vissa ändringar. Mer information om planerade ändringar finns [i Vad finns i Microsoft Secure Score?](microsoft-secure-score-whats-coming.md)

### <a name="january---march-2020"></a>Januari - mars 2020

#### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>Stöd för säkerhetsstandarder för Azure AD-förbättringsåtgärder

Microsoft Secure Score uppdaterar förbättringsåtgärder för att stödja [säkerhetsstandarder i Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), vilket gör det enklare att skydda din organisation med förkonfigurerade säkerhetsinställningar för vanliga attacker.

Det kommer att påverka följande förbättringsåtgärder:

- Se till att alla användare kan slutföra multifaktorautentisering för säker åtkomst
- Kräv MFA för administrativa roller
- Aktivera princip för att blockera äldre autentisering

#### <a name="removed-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Borttagna förbättringsåtgärder som inte uppfyller förväntningarna för tillförlitlig mätning eller inte ger en användbar representation av säkerhetsposition

För att säkerställa att Microsoft Secure Score är meningsfull och att varje förbättringsåtgärd är mätbar och tillförlitlig tar vi bort följande förbättringsåtgärder.

- Lagra användardokument i OneDrive för företag
- Konfigurera principer för säker bilaga till Office 365 ATP
- Konfigurera säkra Office 365-länkar för att verifiera webbadresser
- Tillåt inte postlådedelegering
- Tillåt anonyma gästdelningslänkar för webbplatser och dokument
- Aktivera Säkerhetskonsolen för Molnappar
- Konfigurera förfallotid för externa delningslänkar
- Aktivera registrering av granskningsdata
- Upptäck riskfyllda och icke-kompatibla skugg-IT-program
- Granska behörigheter & blockera riskfyllda OAuth-program som är anslutna till din miljö
- Konfigurera versionshantering på SharePoint onlinedokumentbibliotek
- Ta bort/blockera konton som inte använts under de senaste 30 dagarna
- Utse färre än 5 globala administratörer

#### <a name="removed-not-scored-improvement-actions"></a>Borttagna förbättringsåtgärder som inte gjorts

En av principerna för Secure Score är att poängen ska vara standardiserade och lätta att relatera till. Att ha förbättringsåtgärder som inte är mätbara eller genomförbara har orsakat förvirring. Microsoft Secure Score är bara meningsfullt när varje rekommendation kan ha en tydlig effekt på poängen. Inte poängsatt förbättringsåtgärder är inte mätbara.  

Av dessa skäl har alla förbättringsåtgärder som inte har gjorts tagits bort. Inga åtgärder behövs från din sida.

#### <a name="removed-device-improvement-actions"></a>Åtgärder för att förbättra enheten har tagits bort

Efter en utvärdering av microsoft secure score-enhetskategorin för förbättringsåtgärder fastställdes att dessa åtgärder för närvarande utvärderar principtillståndet och inte konfigurationstillståndet för enheter. Eftersom konfigurationen är direkt knuten till säkerhetspositionen, var de befintliga enhetsåtgärderna fast beslutna att inte helt representera organisationshållning.  Vi kommer att ta bort de aktuella åtgärderna i enhetskategorin när vi arbetar med att tillhandahålla en uppsättning rekommendationer som direkt använder diagnostikdata för att mer fullständigt representera enhetens säkerhetshållning.

Följande förbättringsåtgärder har tagits bort:

- Aktivera Hantering av Mobila enheter för Microsoft Intune
- Skapa en efterlevnadsprincip för Microsoft Intune för Android
- Skapa en efterlevnadsprincip för Microsoft Intune för Android for Work
- Skapa en Microsoft Intune App Protection Policy för Android
- Skapa en Microsoft Intune-appskyddsprincip för iOS
- Markera enheter utan Microsoft Intune-efterlevnadsprincip som inte är kompatibla
- Skapa en Microsoft Intune-efterlevnadsprincip för iOS
- Skapa en efterlevnadsprincip för Microsoft Intune för macOS
- Skapa en Microsoft Intune-efterlevnadsprincip för Windows
- Skapa en konfigurationsprofil för Microsoft Intune för Android
- Skapa en konfigurationsprofil för Microsoft Intune för Android for Work
- Skapa en konfigurationsprofil för Microsoft Intune för macOS
- Skapa en konfigurationsprofil för Microsoft Intune för iOS
- Skapa en konfigurationsprofil för Microsoft Intune för Windows
- Aktivera förbättrad jailbreak-identifiering i Microsoft Intune
- Kräva att alla enheter ska korrigeras, ha anti-virus och brandväggar aktiverade
- Aktivera Windows Defender ATP-integrering i Microsoft Intune
- Skapa en informationsskyddsprincip för Microsoft Intune Windows
- Kräv att alla enheter har avancerade säkerhetskonfigurationer
- Granska rapporter om blockerade enheter varje vecka

#### <a name="mfa-improvement-action-updates"></a>Uppdateringar av förbättringsåtgärder för MFA

För att återspegla behovet av företag att säkerställa den högsta säkerheten när de tillämpar principer som fungerar med deras verksamhet, har Microsoft Secure Score tagit bort tre förbättringsåtgärder centrerade kring multifaktorautentisering och lagt till två.

Borttagna förbättringsåtgärder:

- Registrera alla användare för multifaktorautentisering
- Kräv MFA för alla användare
- Kräv MFA för Azure AD-privilegierade roller

Lade till förbättringsåtgärder:

- Se till att alla användare kan slutföra multifaktorautentisering för säker åtkomst
- Kräv MFA för administrativa roller

 Dessa nya förbättringsåtgärder kräver registrering av användare eller administratörer för MFA (Multi factor Authentication) i katalogen och upprätta rätt uppsättning principer som passar dina organisationsbehov. Huvudmålet är att ha flexibilitet samtidigt som alla användare och administratörer kan autentisera med flera faktorer eller riskbaserade uppmaningar om identitetsverifiering. Det kan ta formen av flera principer som tillämpar begränsade beslut eller anger säkerhetsstandarder (som kommer den 16 mars) som låter Microsoft bestämma när användare ska utmanas för MFA.

#### <a name="removed-review-improvement-actions"></a>Borttagna "granska" förbättringsåtgärder

En av principerna för Secure Score är att poängen ska vara standardiserade och lätta att relatera till. Att ha förbättringsåtgärder som inte är mätbara eller genomförbara har orsakat förvirring. En Microsoft Secure Score är bara meningsfullt när varje rekommendation kan ha en tydlig effekt på poängen. Granskningsåtgärder mäts inte enligt samma standard som andra förbättringsåtgärder.  

Av dessa skäl har alla förbättringsåtgärder som krävde en granskningskadens tillfälligt tagits bort. Inga åtgärder behövs från din sida.

### <a name="preview-features"></a>Förhandsgranskningsfunktioner

Följande funktioner kommer att ingå i [förhandsversionen:](microsoft-secure-score-preview.md)

* Alla nya statistik- och trendersvyer för CISO- och leadnivådiskussioner
* Nya sätt att spåra och jämföra din poäng
* Bättre spårning och övervakning för poängregressioner
* Filtrera, tagga, söka och gruppera förbättringsåtgärder
* Hantera mot dina framtida mål med hjälp av resultatprognoser och planerade åtgärder
* Förenkling av poängsystemet
* Och mer!

## <a name="we-want-to-hear-from-you"></a>Vi vill höra från dig

Om du har några problem, vänligen meddela oss genom att publicera i [security, privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community. Vi övervakar samhället och kommer att ge hjälp.
