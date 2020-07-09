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
ms.openlocfilehash: 44c9992be3fe0e6919a498fea0ee1b480a30a2bb
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086685"
---
# <a name="microsoft-secure-score"></a>Microsoft Secure Score

Microsoft Secure Score är ett mått på en organisations säkerhetsposition, med ett högre antal som anger fler förbättringsåtgärder som vidtas. Den finns https://security.microsoft.com/securescore på i Microsoft [365 security center](overview-security-center.md).

Om du följer rekommendationerna för säker poäng kan du skydda din organisation från hot. Från en centraliserad instrumentpanel i Microsoft 365-säkerhetscentret kan organisationer övervaka och arbeta med säkerheten för sina Microsoft 365-identiteter, data, appar, enheter och infrastruktur.

Secure Score hjälper organisationer:  

* Rapport om det aktuella läget för organisationens säkerhetsposition.
* Förbättra deras säkerhetsposition genom att tillhandahålla upptäckbarhet, synlighet, vägledning och kontroll.  
* Jämför med riktmärken och fastställ nyckeltal.

Organisationer får tillgång till robusta visualiseringar av mått och trender, integrering med andra Microsoft-produkter, poängjämlikhet med liknande organisationer och mycket mer. Poängen kan också återspegla när tredjepartslösningar har åtgärdat rekommenderade åtgärder.

## <a name="how-it-works"></a>Så här fungerar det

Du får poäng för att konfigurera rekommenderade säkerhetsfunktioner, utföra säkerhetsrelaterade uppgifter eller åtgärda förbättringsåtgärden med ett program eller program från tredje part, eller en alternativ begränsning. Vissa förbättringsåtgärder ger bara poäng när de är helt slutförda, och vissa ger partiella poäng om de slutförs för vissa enheter eller användare. Om du inte kan eller inte vill anta någon av förbättringsåtgärderna kan du välja att acceptera risken eller den återstående risken.

Vi visar dig alla möjliga förbättringar, oavsett licens, så att du kan förstå bästa praxis för säkerhet och förbättra dina poäng. Din absoluta säkerhetsposition representeras av Secure Score, som förblir densamma oavsett vilka produktlicenser din organisation äger. Tänk på att säkerheten bör balanseras med användbarhet, och inte varje rekommendation kan fungera för din miljö.

Din poäng uppdateras i realtid för att återspegla den information som presenteras i visualiseringar och förbättring åtgärd sidor. Secure Score synkroniserar också dagligen för att ta emot systemdata om dina uppnådda poäng för varje åtgärd.

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

## <a name="gain-visibility-into-your-security-posture"></a>Få insyn i din säkerhetsposition

För att hjälpa dig den information du behöver snabbare är Microsofts förbättringsåtgärder organiserade i grupper:

* Identitet (Azure AD-konton & roller)
* Data (Microsofts informationsskydd)
* Enhet (Microsoft Defender ATP, känd som [konfigurationspoäng)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configuration-score)
* App (e-post- och molnappar, inklusive Office 365 och Microsoft Cloud App Security)
* Infrastruktur (inga förbättringsåtgärder för tillfället)

>[!NOTE]
>I den senaste versionen av Microsoft Secure Score har en förbättrad poängsättningsmodell släppts som gjorde Microsoft Secure Score tillfälligt inkompatibelt med Identity Secure Score och Graph API. [Visa information](microsoft-secure-score.md#incompatibility-with-identity-secure-score-and-graph-api)

På översiktssidan för Microsoft Secure Score kan du se hur poäng delas mellan dessa grupper och vilka punkter som är tillgängliga. Översiktssidan är också platsen för att få en helhetsbild av den totala poängen, historisk trend för din säkra poäng med jämförelsemål och prioriterade förbättringsåtgärder som kan vidtas för att förbättra din poäng.

![Startsida för säkra poäng](../../media/secure-score/secure-score-homepage-new.png)

## <a name="take-action-to-improve-your-score"></a>Vidta åtgärder för att förbättra din poäng

På fliken **Förbättringsåtgärder** visas de säkerhetsrekommendationer som åtgärdar möjliga angreppsytor, tillsammans med deras status (för att ta itu med, planerade, risk accepterade, lösas via tredje part, lösas genom alternativ begränsning och slutförd). Du kan söka, filtrera och gruppera alla förbättringsåtgärder.  

### <a name="ranking"></a>Ranking (ranking)

Rankningen baseras på antalet återstående poäng kvar att uppnå, implementeringssvårigheter, användarpåverkan och komplexitet. De högst rankade förbättringsåtgärderna har ett stort antal punkter kvar med låg svårighet, användarpåverkan och komplexitet.

### <a name="view-improvement-action-details"></a>Visa information om förbättringsåtgärder

När du väljer en viss förbättringsåtgärd visas ett utfällbart utfällbart helsidesutfällbart resultat.  

![Utfällbart exempel på förbättringsåtgärd ](../../media/secure-score/secure-score-improvement-action-details.png)
 *Bild 2: Exempel på utfällbara förbättringar*

För att slutföra åtgärden har du några alternativ:

* Välj **Hantera** om du vill gå till konfigurationsskärmen och göra ändringen. Du kommer då att få de poäng som åtgärden är värd, synlig i flyga ut. Poäng tar i allmänhet ca 24 timmar att uppdatera.

* Välj **Dela** om du vill kopiera den direkta länken till förbättringsåtgärden eller välj den plattform som du vill dela länken som e-post, Microsoft Teams, Microsoft Planner eller ServiceNow. Genom att välja ServiceNow kan du skapa en ändringsbiljett som visas i ServiceNow och Microsoft 365 security center home. Mer information finns i [Microsoft 365 Security Center och ServiceNow-integrering](tickets-security-center.md).

### <a name="choose-an-improvement-action-status"></a>Välj status för förbättringsåtgärder

Välj alla statusar och spela in anteckningar som är specifika för förbättringsåtgärden. De statyer du kan välja är följande:

* **För att ta itu med** - Du inser att förbättringen åtgärder är nödvändiga och planerar att ta itu med det någon gång i framtiden. Det här tillståndet gäller även åtgärder som identifieras som delvis, men inte helt slutförda.
* **Planerad** – Det finns konkreta planer för att slutföra förbättringsåtgärderna.
* **Risk accepteras** - Säkerhet bör alltid balanseras med användbarhet, och inte varje rekommendation kommer att fungera för din miljö. När så är fallet kan du välja att acceptera risken, eller den återstående risken, och inte anta förbättringsåtgärden. Du kommer inte att få några poäng, men åtgärden kommer inte längre att vara synlig i listan över förbättringsåtgärder. Du kan visa den här åtgärden i historiken eller ångra den när som helst.
* **Löst via tredje part** och **löst genom alternativ begränsning** – Förbättringsåtgärden har redan åtgärdats av ett program eller program från tredje part, eller ett internt verktyg. Du kommer att få de poäng som åtgärden är värd, så din poäng bättre återspeglar din totala säkerhet hållning. Om en tredje part eller ett internt verktyg inte längre täcker kontrollen kan du välja en annan status. Tänk på att Microsoft inte har någon insyn i implementeringens fullständighet om förbättringsåtgärden markeras som någon av dessa statusar.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Åtgärder för förbättring av hot & sårbarhetshantering

För förbättringsåtgärder i kategorin "Enhet" kan du inte välja status. I stället dirigeras du till den tillhörande [& säkerhetsproblemshantering (TVM) i](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) för att vidta åtgärder. Det undantag du väljer och motiveringen som du skriver är specifikt för portalen och finns inte på portalen Microsoft Secure Score.

#### <a name="completed-improvement-actions"></a>Slutförda förbättringsåtgärder

Förbättringsåtgärder har en "slutförd" status när alla möjliga punkter för förbättringsåtgärderna har uppnåtts. Slutförda förbättringsåtgärder bekräftas genom Microsoft-data och du kommer inte att kunna ändra status.

### <a name="assess-information-and-review-user-impact"></a>Utvärdera information och granska användarnas påverkan

I avsnittet **Vid en överblick** visas kategorin, attacker som den kan skydda mot och produkten.

**Användareffekten** visar vad användarna kommer att uppleva om förbättringsåtgärden har antagits och **användare som påverkas** visar vem som kommer att uppleva det.

### <a name="implement-the-improvement-action"></a>Genomföra förbättringsåtgärderna

Avsnittet **Implementering** visar eventuella förutsättningar, steg för steg nästa steg för att slutföra förbättringsåtgärden, den aktuella implementeringsstatusen för förbättringsåtgärden och eventuella fler länkar.

Förutsättningar kommer att vara alla licenser som måste erhållas eller åtgärder som måste slutföras innan förbättringsåtgärden åtgärdas. Se till att du har tillräckligt med platser i din licens för att slutföra förbättringsåtgärden och att dessa licenser tillämpas på nödvändiga användare.  

## <a name="track-your-score-history-and-meet-goals"></a>Spåra din poänghistorik och uppnå mål

Du kan visa ett diagram över organisationens poäng över tid på fliken **Historik.** Under diagrammet finns en lista över alla åtgärder som vidtagits i det valda tidsintervallet och deras attribut, till exempel resulterande poäng och kategori. Du kan anpassa ett datumintervall och filtrera efter kategori.

På fliken **Mått & trender** finns det flera diagram som ger dig större insyn i trender och sätta upp mål. Du kan ange datumintervallet för hela sidan med visualiseringar. Visualiseringarna inkluderar:

* **Zonen Secure Score** – Anpassad baserat på organisationens mål och definitioner av bra, okej och dåliga resultatintervall.
* **Regressionstrend** – En tidslinje med punkter som har gått tillbaka på grund av konfiguration, användar- eller enhetsändringar.  
* **Jämförelsetrend** – Hur organisationens säkra resultat kan jämföras med andras över tid. Den här vyn kan innehålla rader som representerar poänggenomsnittet för organisationer med liknande platsantal och en anpassad jämförelsevy som du kan ange.
* **Risk acceptans trend** - Tidslinje för förbättringsåtgärder markerade som "risk accepteras."
* **Poängändringar** – Antalet uppnådda poäng, poäng som gått tillbaka, tillsammans med den efterföljande poängändringen, i det angivna datumintervallet.

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

