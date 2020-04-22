---
title: Team för ett topphemligt projekt på Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/18/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Sammanfattning: Hur Contoso använde ett team för starkt reglerade data för ett topphemligt projekt för att utveckla en ny uppsättning produkter och tjänster.'
ms.openlocfilehash: 310ef33d4add7d71616aee8808515ca90536d8c1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636504"
---
# <a name="team-for-a-top-secret-project-of-the-contoso-corporation"></a>Team för ett topphemligt projekt på Contoso Corporation

Efter en verkställande offsite, Contoso VD beställde utvecklingen av en ny svit av produkter och tjänster som kan fördubbla Contoso vinst under de kommande fem åren. Det topphemliga projektet för att utveckla affärs-, ingenjörs- och marknadsplanen fick namnet **Project 2X** och nyckelpersonal i hela företaget rekryterades. 

Tidslinjerna för forskning och utveckling var snäva, vilket innebar att samarbetet måste vara effektivt och ge säkra möten, pågående samtal och fillagring.

De resulterande slutprodukterna för Project 2X var affärsplaner, produkt- och teknikspecifikationer samt marknadsföringsmaterial och scheman i form av Word-, Excel- och PowerPoint-filer. 

På grund av deras känsliga karaktär, tillgång till dessa filer var:

- Begränsad till Project 2X-gruppmedlemmar.
- Skyddad med en DLP-princip (Data Loss Prevention) för att förhindra att Project 2X-gruppmedlemmar delar dem utanför teamet.
- Krypterad och skyddad med behörighet att endast tillåta åtkomst till Project 2X-gruppmedlemmar, även om filerna distribuerades utanför Contoso.

Contoso [IT-personal](secure-teams-highly-regulated-data-scenario.md) använde ett team för starkt reglerade data för Project 2X och dessa steg.

## <a name="step-1-created-a-private-team-and-locked-down-the-underlying-sharepoint-site"></a>Steg 1: Skapade ett privat team och låste den underliggande SharePoint-webbplatsen

För att skydda åtkomsten till den underliggande SharePoint-webbplatsen för teamet konfigurerade Contoso IT-administratörer de [rekommenderade SharePoint-åtkomstprinciperna](sharepoint-file-access-policies.md).

Därefter skapade en Contoso IT-administratör ett nytt privat team med namnet Project 2X och lade till användarkontona för Project 2X-personal som medlemmar.

Därefter konfigurerade de ytterligare behörighetsinställningar för webbplatsen för att förhindra att Project 2X delar åtkomst till webbplatsen och för att förhindra att andra begär åtkomst till webbplatsen.

Konfigurationsinformation finns i [SharePoint-inställningar för ett starkt reglerat team](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).

## <a name="step-2-configured-a-dlp-policy-and-the-underlying-site-for-a-retention-label"></a>Steg 2: Konfigurerade en DLP-princip och den underliggande platsen för en kvarhållningsetikett 

Först tillämpade Contoso-administratörer den befintliga **mycket konfidentiella** lagringsetiketten **Documents** på dokumentavsnittet på den underliggande SharePoint-webbplatsen för Project 2X-teamet.

Därefter skapade de en ny DLP-princip med namnet **Project 2X** som:

- Använder etiketten Mycket konfidentiell kvarhållning.
- Blockerar användare när de försöker dela en fil i Project 2X-teamet utanför Contoso.

Konfigurationsinformation finns [i Skydda filer i team med kvarhållningsetiketter och DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).

## <a name="step-3-created-a-sensitivity-label-for-the-project-2x-team"></a>Steg 3: Skapade en känslighetsetikett för Project 2X-teamet

Contoso-administratörer skapade en ny känslighetsetikett med namnet **Project 2X** som:

- Kräver kryptering.
- Tillåter samtidiga redigeringsbehörigheter för gruppen Project 2X Microsoft 365.

Här är den resulterande konfigurationen av Project 2X-teamet.

![Den resulterande konfigurationen av Project 2X-teamet](../media/contoso-team-for-highly-confidential-assets/final-config.png)
 
Filerna i avsnittet Dokument på den underliggande Project 2X SharePoint-webbplatsen skyddades av:

- Webbplatsbehörigheterna, som endast ger åtkomst till medlemmar i Gruppen Project 2X Microsoft 365.
- Den mycket konfidentiella kvarhållningsetiketten, som automatiskt tilldelas nya filer.
- En DLP-princip som använder etiketten Mycket konfidentiell kvarhållning och inställningar som blockerar filen från att delas med externa användare.
- Känslighetsetiketten För Project 2X, med kryptering och behörigheter som färdas med filen om den flyttas eller kopieras från webbplatsen.

Här är ett exempel på en fil som lagras i den underliggande Project 2X-platsen med den starkt reglerade kvarhållningsetiketten och känslighetsetiketten Project 2X tilldelad.

![Ett exempel på en fil som lagras på den underliggande Project 2X-platsen](../media/contoso-team-for-highly-confidential-assets/final-config-example-file.png)
 
## <a name="step-4-trained-project-2x-team-members"></a>Steg 4: Utbildade Project 2X-gruppmedlemmar

Contoso säkerhetspersonal utbildade Project 2X-teammedlemmarna i en obligatorisk kurs som klev igenom dem:

- Så här kommer du åt det nya Project 2X-teamet, använder möten och chattar och hur du samarbetar i gruppfiler.
- Så här skapar du nya filer i teamet och laddar upp nya filer som skapats lokalt.
- En demonstration av hur DLP-principen blockerar filer från att delas externt.
- Så här märker du filer med känslighetsetiketten För Project 2X.
- En demonstration av hur Project 2X-etiketten skyddar en fil även när den lämnar teamet.

Slutresultatet blev en säker miljö där Project 2X-gruppmedlemmar samarbetade i en säker miljö för chattar, möten och filer.

I ett par fall hämtade Project 2X-gruppmedlemmar filer som skyddas av Project 2X-etiketten till en lokal enhet för offlinearbete. Men efter att ha uppmanats om autentiseringsuppgifter när de öppnades, insåg de sitt misstag och tog bort dem.

På grund av teamens samarbetsmiljö och säkerhetsfunktionerna i Microsoft 365 hölls detaljerna i Project 2X hemliga under hela projektet. Contoso tillkännagav sina planer och håller på att rulla ut de nya produkterna och tjänsterna till glädje för sina kunder och investerare och förtret för sina konkurrenter.

## <a name="next-step"></a>Nästa steg

[Distribuera](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise i din organisation.

## <a name="see-also"></a>Snabbreferens

[Produktivitetsbiblioteket för Microsoft 365](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)
