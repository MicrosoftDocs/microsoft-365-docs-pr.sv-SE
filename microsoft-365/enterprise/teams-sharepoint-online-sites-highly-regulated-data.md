---
title: SharePoint-webbplatser för strikt reglerade data
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- SPO_Content
ms.custom: ''
description: Skapa en säker SharePoint-gruppwebbplats för att lagra värdefulla och känsliga filer.
ms.openlocfilehash: 97a01275d1d45cb02e66e88f82c95311bcb6fe70
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636717"
---
# <a name="sharepoint-sites-for-highly-regulated-data"></a>SharePoint-webbplatser för strikt reglerade data

*Det här scenariot gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*

Microsoft 365 Enterprise innehåller en komplett uppsättning molnbaserade tjänster så att du kan skapa, lagra, skydda och hantera strikt reglerade data som lagras i filer. Det inkluderar data som:

- Lyder under regionala bestämmelser.
- Är de mest värdefulla data för din organisation, t.ex. affärshemligheter, ekonomisk information och personalinformation samt organisationens strategi.

>[!Note]
> Ett liknande scenario med Microsoft Teams finns [här](secure-teams-highly-regulated-data-scenario.md).
>

Ett molnbaserat scenario för Microsoft 365 Enterprise som uppfyller detta affärsbehov kräver att du:

- Lagrar filer (dokument, bildspel, kalkylblad osv.) på en SharePoint-gruppwebbplats.
- Lås webbplatsen för att förhindra:
  - Åtkomst av användare som inte är medlemmar i webbplatsens Microsoft 365-grupp.
  - Webbplatsmedlemmarna från att ge andra personer åtkomst.
  - Icke-medlemmar av webbplatsen från att begära åtkomst till webbplatsen.
- Konfigurera en kvarhållningsetikett för dina SharePoint-webbplatser som ett standardsätt att hindra användare från att skicka filer utanför organisationen.
- Kryptera de känsligaste filerna på webbplatsen med kryptering som följer med filen.
- Lägg till behörigheter för de känsligaste filerna så att giltiga inloggningsuppgifter för ett användarkonto som har behörighet måste anges även om de delas utanför webbplatsen.

I följande tabell beskrivs kraven i det här scenariot för en funktion i Microsoft 365 Enterprise.

|||
|:-------|:-----|
| **Krav** | **Microsoft 365 Enterprise-funktion** |
| Lagra filer | SharePoint-gruppwebbplatser |
| Lås webbplatsen | Microsoft 365-grupper och behörigheter för SharePoint-gruppwebbplats |
| Etikettera filerna på webbplatsen | Microsoft 365-kvarhållningsetiketter |
| Blockera användare från att skicka filer utanför organisationen | DLP-principer (dataförlustskydd) |
| Kryptera alla filer på webbplatsen | Microsoft 365-känslighetsetiketter eller underetiketter |
| Lägg till behörigheter för webbplatsens filer | Microsoft 365-känslighetsetiketter eller underetiketter |
|||

Här är ett exempel på en konfiguration för en säker SharePoint-webbplats.

![Scenario för SharePoint-webbplatser för strikt reglerade data](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

Det här scenariot kräver att du redan har distribuerat:

- Fasen [Identitet](identity-infrastructure.md) och steg 1 och 2 av fasen [Informationsskydd](infoprotect-infrastructure.md) i den grundläggande infrastrukturen. 
- [SharePoint](sharepoint-online-onedrive-workload.md).

I följande faser får du stegvisa instruktioner om hur du utformar, konfigurerar och driver på användningen av SharePoint-webbplatser för strikt reglerade data.

<a name="poster"></a> En sammanfattning på en sida finns på [affischen SharePoint-webbplatser för strikt reglerade data](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf).

[![SharePoint-webbplatser för strikt reglerade data (affisch)](../media/teams-sharepoint-online-sites-highly-regulated-data/sharepoint-sites-highly-regulated-data-poster.png)](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)

Du kan också ladda ned den här affischen i [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)- eller [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePoint-Sites-Highly-Regulated-Data.pptx)-format och skriva ut den i pappersstorleken letter, legal eller tabloid (11 x 17).


## <a name="identity-and-device-access-prerequisites"></a>Villkor för identitet och enhetsåtkomst

För att skydda åtkomsten till SharePoint-webbplatsen ska du se till att du har konfigurerat [principer för identitet och enhetsåtkomst](identity-access-policies.md) och de rekommenderade [principerna för SharePoint-åtkomst](sharepoint-file-access-policies.md).

## <a name="phase-1-design"></a>Fas 1: Utformning

När du vill skapa en SharePoint-webbplats för strikt reglerade data måste du först identifiera syftet med den. En forsknings- och utvecklingsavdelning i en tillverkningsorganisation kan till exempel behöva en SharePoint-webbplats för att lagra aktuella specifikationer för befintliga produkter och en plats för samarbete om nya produkter. Bara medlemmar på forsknings- och utvecklingsavdelningen och utvalda chefer får åtkomst till webbplatsen.

Syftet avgör viktiga konfigurationselement som:

- Kvarhållningsetiketten som tilldelas dokumentavsnittet på webbplatsen och DLP-principerna för etiketten
- Inställningarna för en underetikett för känslighet som användare tillämpar på mycket känsliga filer som lagras på webbplatsen

När du har fastställt detta använder du inställningarna för att konfigurera webbplatsen i fas 2. 

### <a name="step-1-microsoft-365-retention-labels-and-dlp-policies"></a>Steg 1 Microsoft 365-kvarhållningsetiketter och DLP-principer

Kvarhållningsetiketter som tillämpas på dokumentavsnittet på SharePoint-gruppwebbplatsen är en standardmetod för att klassificera alla filer som lagras på webbplatsen.
 
För SharePoint-webbplatser för strikt reglerade data måste du avgöra vilken kvarhållningsetikett som ska användas.

Information om utformning av etiketter finns i [Klassificering och etiketter för Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).

Använd DLP-principer för att skydda känslig information och förhindra att den avslöjas oavsiktligt eller avsiktligt. Mer information finns i denna [översikt](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).

För SharePoint-webbplatser måste du konfigurera en DLP-princip för kvarhållningsetiketten som tilldelats webbplatsen så att användare förhindras att dela filer med externa användare. 

### <a name="step-2-your-microsoft-365-sensitivity-sublabel"></a>Steg 2: Din Microsoft 365-underetikett för känslighet

För att tillhandahålla kryptering och en uppsättning behörigheter till de känsligaste filerna måste användarna använda en känslighetsetikett eller underetikett. En underetikett finns under en befintlig etikett. 

Använd en känslighetsetikett när du behöver ett litet antal etiketter för både global användning och enskilda privata team. Använd en underetikett för känslighet när du har ett stort antal etiketter eller vill ordna etiketter för säkra webbplatser under den strikt reglerade etiketten. 

Inställningarna för etiketten eller underetiketten följer med filen. Även om den läcks utanför webbplatsen kan bara autentiserade användarkonton som har behörighet öppna den.

### <a name="design-results"></a>Resultat av utformningen

Du har fastställt följande:

- Lämplig kvarhållningsetikett och DLP-principen som associeras med etiketten
- Inställningarna för underetiketten för känslighet som inkluderar kryptering och behörigheter

## <a name="phase-2-configure"></a>Fas 2: Konfigurera

I den här fasen tar du inställningarna som fastställts i fas 1 och använder dem för att skapa en SharePoint-webbplats för strikt reglerade data.

### <a name="step-1-create-a-private-sharepoint-team-site-with-owners-and-members-of-the-corresponding-microsoft-365-group"></a>Steg 1: Skapa en privat SharePoint-gruppwebbplats med ägare och medlemmar i motsvarande Microsoft 365-grupp

Skapa en privat SharePoint-gruppwebbplats genom att följa [dessa instruktioner]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8).

### <a name="step-2-configure-additional-permissions-settings-for-the-sharepoint-team-site"></a>Steg 2: Konfigurera ytterligare behörighetsinställningar för SharePoint-gruppwebbplatsen

Konfigurera dessa behörighetsinställningar på SharePoint-webbplatsen.

1. Klicka på inställningsikonen i verktygsfältet och klicka sedan på **Webbplatsbehörigheter**.
2. I fönstret **Webbplatsbehörigheter** under **Delningsinställningar** klickar du på **Ändra delningsinställningar**.
3. Under **Delningsbehörigheter** väljer du **Endast webbplatsägare kan dela filer, mappar och webbplats**.
4. Inaktivera **Tillåt åtkomstbegäranden** och klicka sedan på **Spara**.

Med dessa inställningar inaktiveras funktionen för webbplatsgruppens medlemmar att dela webbplatsen med andra medlemmar eller för icke-medlemmar att begära åtkomst till webbplatsen.

### <a name="step-3-configure-the-site-for-a-retention-label"></a>Steg 3: Konfigurera webbplatsen för en kvarhållningsetikett

Följ anvisningarna i [Skydda SharePoint-filer med etiketter och DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) när du:

1. Skapar och publicerar en kvarhållningsetikett för strikt reglerade data (om det behövs).
2. Konfigurerar webbplatsen för kvarhållningsetiketten som skapats i steg 1.
3. Skapar en DLP-princip för strikt reglerade data som använder kvarhållningsetiketten som skapats i steg 2 och hindrar användare från att skicka filer utanför organisationen

#### <a name="step-4-create-a-sensitivity-sublabel-for-the-site"></a>Steg 4: Skapa en underetikett för känslighet för webbplatsen

Till skillnad från en känslighetsetikett för strikt reglerade data som alla kan tillämpa på valfri fil behöver en säker webbplats en egen underetikett så att filer som tilldelas underetiketten:

- krypteras och krypteringen följer med filen,
- innehåller anpassade behörigheter så att bara medlemmar i webbplatsgruppen kan öppna den.

För att åstadkomma den här extra säkerhetsnivån för filer på webbplatsen måste du konfigurera en ny känslighetsetikett eller en underetikett för den allmänna etiketten för strikt reglerade filer. Endast gruppmedlemmarna på webbplatsen ser den i listan med underetiketter för etiketten för strikt reglerade data.

Följ anvisningarna [här](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) när du vill konfigurera en etikett eller en underetikett för etiketten som du använder för strikt reglerade filer med följande inställningar:

- Namnet på etiketten eller underetiketten innehåller namnet på webbplatsen för enkel koppling när etiketten eller underetiketten tilldelas en fil.
- Kryptering är aktiverat.
- Webbplatsgruppen har samredigeringsbehörighet.

### <a name="configuration-results"></a>Konfigurationsresultat

Du har konfigurerat följande:

- Striktare behörighetsinställningar på SharePoint-webbplatsen
- En kvarhållningsetikett som tilldelats dokumentavsnittet på SharePoint-webbplatsen
- En DLP-princip för kvarhållningsetiketten
- En känslighetsetikett eller en underetikett som användare kan tillämpa på de känsligaste filerna som lagras på webbplatsen. Den krypterar filer och tillåter bara samtidig redigering för medlemmar i webbplatsgruppen. 

Här är en konfiguration som använder en underetikett av etiketten för strikt reglerade data.

![Scenario för SharePoint-webbplatser för strikt reglerade data](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

Här är ett exempel på en användare som har tilldelat en underetikett till en fil som lagras på webbplatsen.

![Scenario för SharePoint-webbplatser för strikt reglerade data](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-example-file.png)


## <a name="phase-3-drive-user-adoption"></a>Fas 3: Driva på användningen

En SharePoint-webbplats för strikt reglerade data kan bara skydda data om den används konsekvent för lagring och åtkomst till känsliga filer. Det här är den svåraste fasen eftersom den förlitar sig på att användarna ändrar sina vanor och inställningar. 

Anställda som till exempel lagrar känsliga filer på USB-enheter eller i privata molnbaserade lagringslösningar måste nu enbart lagra dem på en SharePoint-webbplats för strikt reglerade data.

### <a name="step-1-train-your-users"></a>Steg 1: Utbilda dina användare

När du har slutfört konfigurationen bör du utbilda användarna som är medlemmar av webbplatsen:

- Om vikten av att använda den nya webbplatsen för att skydda värdefulla filer och konsekvenserna av en läcka av strikt reglerade data, till exempel juridiska aspekter, tillsynsböter, utpressningstrojaner eller förlust av konkurrensfördelar.
- Om åtkomst till webbplatsen och dess filer.
- Hur man skapar nya filer på webbplatsen och laddar upp nya filer som lagras lokalt.
- Hur DLP-principen förhindrar dem från att dela filer externt.
- Hur man förser de känsligaste filerna med etiketten eller underetiketten för webbplatsen.
- Hur etiketten eller underetiketten skyddar filer även när de läcker från webbplatsen.

I den här utbildningen ska det ingå praktiska övningar så att användarna kan prova funktionerna och se deras resultat.

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a>Steg 2: Utföra regelbundna granskningar av användning och filer

Under veckorna efter utbildningen kan SharePoint-administratören för SharePoint-webbplatsen:

- Analysera webbplatsens användning och jämföra med den förväntade användningen.
- Kontrollera att strikt reglerade filer har etiketterats korrekt med känslighetsetiketten eller underetiketten.

  Du kan se vilka filer som har tilldelats en etikett genom att visa en mapp i SharePoint och lägga till kolumnen **Känslighet** genom alternativet **Visa/dölj kolumner** i **Lägg till kolumn**.


Vidareutbilda dina användare efter behov.

### <a name="user-adoption-results"></a>Användningsresultat

Strikt reglerade filer lagras enbart på SharePoint-webbplatser för strikt reglerade data och de känsligaste filerna har tilldelats känslighetsetiketten eller underetiketten för webbplatsen.

## <a name="how-the-contoso-corporation-used-a-sharepoint-site-for-highly-regulated-data"></a>Så här använde Contoso Corporation en SharePoint-webbplats för strikt reglerade data

Contoso Corporation är ett fiktivt men representativt globalt tillverkningskonglomerat. Se hur Contoso skapade, konfigurerade och införde användningen av en [säker SharePoint-webbplats](contoso-sharepoint-online-site-for-highly-confidential-assets.md) för forskningsteamen i Paris, Moskva, New York, Beijing och Bangalore. 

## <a name="see-also"></a>Se även

[Teams för strikt reglerade data](secure-teams-highly-regulated-data-scenario.md)

[Arbetsbelastningar och scenarier i Microsoft 365 Enterprise](deploy-workloads.md)

[Produktivitetsbiblioteket för Microsoft 365](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)

[Distributionsguide](deploy-microsoft-365-enterprise.md)
