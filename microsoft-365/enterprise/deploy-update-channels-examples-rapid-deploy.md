---
title: Exempel på en bred distribution för de senaste versionerna
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
ms.custom: ''
description: Hur en organisation som distribuerar den senaste versionen använder kanaler för Windows 10-och Microsoft 365-appar.
ms.openlocfilehash: fd1d8ddd342b2781470378c879ef70d2ba304316
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686172"
---
# <a name="example-of-broad-deployment-for-the-latest-releases"></a>Exempel på en bred distribution för de senaste versionerna

Detta konfigurations exempel för kanaler är för en organisation som använder snabb distribution av de senaste versionerna för att få plats med dessa affärs prioriteringar:

- Säkerställ företags kontinuitet med Microsoft-program och-tjänster.
- Maximera enhets-, tjänst-och data säkerheten med de senaste funktionerna och korrigeringarna från Microsoft.
- Maximera användarproduktiviteten med de senaste funktionerna från Microsoft.

Syftet är att översätta till IT-aktiviteten för att hitta saldot mellan snabb distribution av produktion och tidiga vetting med en representativ del uppsättning användare och enheter att validera i funktion före bred distribution.

Våra exempel organisationer har 5 000 anställda i byggnader i världen i Europa, Afrika, Asien och Amerika. 70% av medarbetarna använder Microsoft 365 E3 och resten av organisationen använder Microsoft 365 E5.

>[!Note]
>I det här exemplet ser du hur du kan använda distributions faser och-grupper, som kan användas i organisationer med många olika typer och storlekar.
>

Organisationens IT-infrastruktur: 

- Är i stort sett homogent, med Windows, Microsoft 365-appar och Microsofts moln tjänster som innehåller 60% av den installerade bas versionen. Några äldre system finns kvar efter en intensiv arbetskraft för att förenkla och strömlinjeforma IT-infrastrukturen.
- Upprätthålls av en mycket erfaren anställd och med uppgifter som gör att användarna kan vara produktiva och säkra med att följa Microsofts bly i sina versioner.

## <a name="deployment-and-update-stages"></a>Steg för distribution och uppdatering

I det här exemplet använder vi en distributions process i två steg baserat på snabba distributions mål för den senaste versionen.

1. **Använda en förhands granskning eller distribution av pilotprojekt:** validera och iterera med tidiga efterföljare, IT-personal, användare med representativa konfigurationer och utbildnings personal. 

   Tidiga medarbetare, IT-personal och användare med representativa konfigurationer, kan validera funktioner med andra program och på enheter innan de nya funktionerna distribueras till resten av organisationen.

   Ändra chefer har tidig till gång till nya funktioner före omfattande lansering och kan planera meddelande hantering och lansering.

   Utbildnings personal kan planera nya interna kurser eller uppdatera befintliga kurser för nya funktioner före omfattande lansering.

2. **Produktions distribution:** ut för alla återstående användare efter region, avdelning eller annan distributions metod.

## <a name="deployment-configuration-for-windows-10"></a>Distributions konfiguration för Windows 10

Det övergripande målet är att göra en bred distribution av den senaste halvårs fri lanseringen efter validering av frisläppnings kanaler för förhands granskning av en grupp representativa användare och deras enheter.

Mer information om distributions metoder och strategier för Windows 10 finns i [distribution av Windows 10](https://docs.microsoft.com/windows/deployment/).

| Fas | Kanal | Distributions grupp |
|:-------|:-------|:-----|
| Pilot |  **Frisläpp för hands version**  <ul><li>Syfte: distribution av funktions uppdateringar för IT-personal och tidiga inför verifiering för representativa enheter och konfigurationer (språk, program från 3:e part). </li><li> Län: är helt kompatibla med och stöds inte för kommersiella kunder och det räknas inte mot dina support avtal. </li></ul> | **Win10ReleasePreviewChannel** (exempel namn) <br><br> Medlemmar är grupper som innehåller: <ul><li> Windows-entusiaster på olika avdelningar och platser </li><li> Personal med konfigurationer som behöver verifieras </li><li> IT-administratörer och IT-personal </li><li> Ändra chefer </li><li> Intern utbildnings personal </li></ul> |
| Produktion |  **Halvårskanal**  <ul><li>Syfte: omfattande distribution av de senaste funktions uppdateringarna till resten av organisationen. </li><li> State: fullständigt kompatibla och stöds. </li></ul> | **Win10SemiAnnualChannel** (exempel namn) <br><br> Medlemmar är alla användare som inte finns i gruppen Win10ReleasePreviewChannel. |
||||

Med den här organisationens bästa metod för distribution av versionen av för hands versionen av för hands versionen av kanaler på samma sätt som de använder halvårs kanal släpningar, t. ex. Windows Update eller Windows Server Update Services, och att de tillämpar samma principer för uppdateringar av båda kanalerna.

Pågående uppdaterings processen:

1. Släpp förhands gransknings kanal ändringarna distribueras till distributions gruppen Win10ReleasePreviewChannel (exempel namn).
2. Medlemmar i Win10ReleasePreviewChannel-gruppen bekräftar att de släppta ändringarna för förhands granskning av kanaler fungerar för IT-personal. vem som kan ge feedback till Microsoft och vänta på nästa version av Preview-kanalen ändras för ytterligare verifiering.
3. Halvårs byten för kanal funktioner distribueras till distributions gruppen Win10SemiAnnualChannel. 

>[!Note]
>Även om den årliga kanalen är den rekommenderade kanalen bör IT-avdelningen använda sina hanterings verktyg och bestämma när den senaste halvårs versionen av kanalen ska distribueras i organisationen och sedan sammanställa den i vågor.
>

## <a name="deployment-configuration-for-microsoft-365-apps"></a>Distributions konfiguration för Microsoft 365-appar

Det övergripande målet är att utföra en bred distribution av den senaste aktuella kanal versionen när du har verifierat den aktuella kanalen (för hands version).

Se [distribution av Microsoft 365-appar](https://docs.microsoft.com/deployoffice/plan-office-365-proplus) mer information om distributions metoder och strategier för Microsoft 365-appar.

| Fas | Kanal | Distributions grupp |
|:-------|:-------|:-----|
| Pilot |  **Aktuell kanal (förhandsversion)** <ul><li> Syfte: {ge en grupp representativa användare en titt på de nya Microsoft 365 Apps-apparna} distribution av funktions uppdateringar så snart de har testats med aktuell kanal (för hands version) och är Product Ready. </li><li> State: fullständigt kompatibla och stöds.</li><li> Hur ofta: uppdaterar 2-3 gånger per månad. </li></ul> | **AppsCurrentChannelPreview** (exempel namn) <br><br> Medlemmar är grupper som innehåller: <ul><li> Office-appar entusiaster över avdelningar och platser </li><li> Personal med konfigurationer som behöver verifieras </li><li> IT-administratörer och IT-personal </li><li> Ändra chefer </li><li> Intern utbildnings personal </li></ul>|
| Produktion | **Aktuell kanal** <ul><li> Syfte: omfattande distribution av de senaste funktions uppdateringarna till resten av organisationen. </li><li> State: fullständigt kompatibla och stöds. </li></ul> |  **AppsCurrentChannel** (exempel namn) <br><br> Medlemmar är alla användare som inte finns i gruppen AppsCurrentChannelPreview. |
|||

Pågående uppdaterings processen:

1. Aktuell kanal (förhandsversion) distribueras till distributions gruppen AppsCurrentChannelPreview.
2. Medlemmar i AppsCurrentChannelPreview-gruppen bekräftar att aktuell kanal (förhandsversion) fungerar för IT-personal, som kan ge feedback till Microsoft och vänta på nästa aktuella kanal (förhandsversion) för ytterligare verifiering.
3. Aktuella kanal ändringar distribueras till distributions gruppen AppsCurrentChannel. 

## <a name="visual-summary"></a>Visuell sammanfattning

Här är de produkter, deras kanaler, och de distributions grupper som används i den här exempel organisationen. 

![Distributions grupper för omfattande distribution av de senaste versionerna](../media/deploy-update-channels-examples-rapid-deploy/group-summary.png)

## <a name="see-also"></a>Se även

[Distribution och uppdatering av kanalkonfigurationer](deploy-update-channels-examples.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Testlabbguider](m365-enterprise-test-lab-guides.md)
