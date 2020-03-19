---
title: Team för ett topphemligt projekt av Contoso Corporation
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
ms.openlocfilehash: 58d381751db3e94f35a0c1b8f7a14c191918e754
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811498"
---
# <a name="team-for-a-top-secret-project-of-the-contoso-corporation"></a>Team för ett topphemligt projekt av Contoso Corporation

Efter en verkställande offsite, beställde Contoso VD utvecklingen av en ny svit av produkter och tjänster som kan fördubbla Contoso vinst under de kommande fem åren. Det topphemliga projektet för att utveckla affärs-, ingenjörs- och marknadsplanen utsågs till **Project 2X** och nyckelpersonal i hela företaget rekryterades. 

Tidslinjerna för forskning och utveckling var snäva, vilket innebar att samarbetet måste vara effektivt och ge säkra möten, pågående samtal och fillagring.

De resulterande slutprodukter för Project 2X var affärsplaner, produkt- och teknikspecifikationer samt marknadsföringsmaterial och scheman i form av Word-, Excel- och PowerPoint-filer. 

På grund av sin känsliga natur var tillgången till dessa filer:

- Begränsad till Project 2X-gruppmedlemmar.
- Skyddas med en DLP-princip (Data Loss Prevention) för att förhindra att Project 2X-gruppmedlemmar delar dem utanför teamet.
- Krypterad och skyddad med behörighet för att endast tillåta åtkomst till Project 2X-gruppmedlemmar, även om filerna distribuerades utanför Contoso.

Contoso [IT-personal](secure-teams-highly-regulated-data-scenario.md) använde ett team för starkt reglerade data för Project 2X och dessa steg.

## <a name="step-1-created-a-private-team-and-locked-down-the-underlying-sharepoint-site"></a>Steg 1: Skapade ett privat team och låste den underliggande SharePoint-webbplatsen

För att skydda åtkomsten till den underliggande SharePoint-webbplatsen för teamet har Contoso IT-administratörer konfigurerat de [rekommenderade SharePoint-åtkomstprinciperna](sharepoint-file-access-policies.md).

Därefter skapade en Contoso IT-administratör ett nytt privat team som heter Project 2X och lade till användarkontona för Project 2X-personal som medlemmar.

Därefter har de konfigurerat ytterligare behörighetsinställningar för webbplatsen för att förhindra att Project 2X delar åtkomst till webbplatsen och för att förhindra att andra begär åtkomst till webbplatsen.

Information om konfigurationen finns i [SharePoint-inställningar för ett starkt reglerat team](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).

## <a name="step-2-configured-a-dlp-policy-and-the-underlying-site-for-a-retention-label"></a>Steg 2: Konfigurerade en DLP-princip och den underliggande platsen för en bevarandeetikett 

För det första tillämpade Contoso-administratörer den befintliga lagringsetiketten **highly Confidential** Office 365 på avsnittet **Dokument** på den underliggande SharePoint-webbplatsen i Project 2X-teamet.

Därefter skapade de en ny Office 365 DLP-princip med namnet **Project 2X** som:

- Använder lagringsetiketten Mycket konfidentiell Office 365.
- Blockerar användare när de försöker dela en fil i Project 2X-teamet utanför Contoso.

Information om konfigurationen [finns i Skydda filer i team med kvarhållningsetiketter och DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).

## <a name="step-3-created-an-office-365-sensitivity-label-for-the-project-2x-team"></a>Steg 3: Skapade en känslighetsetikett för Office 365 för Project 2X-teamet

Contoso-administratörer skapade en ny Office 365-känslighetsetikett med namnet **Project 2X** som:

- Kräver kryptering.
- Tillåter samredigeringsbehörigheter för gruppen Project 2X Office 365.

Här är den resulterande konfigurationen av Project 2X-teamet.

![Den resulterande konfigurationen av Project 2X-teamet](../media/contoso-team-for-highly-confidential-assets/final-config.png)
 
Filerna i avsnittet Dokument på den underliggande Project 2X SharePoint-webbplatsen skyddades av:

- Webbplatsbehörigheterna, som endast tillåter åtkomst till medlemmar i gruppen Project 2X Office 365.
- Etiketten Mycket konfidentiell lagring, som automatiskt tilldelas nya filer.
- En DLP-princip som använder etiketten Mycket konfidentiell lagring och inställningar som blockerar filen från att delas med externa användare.
- Etiketten för project 2x-känslighet med kryptering och behörigheter som färdas med filen om den flyttas eller kopieras från webbplatsen.

Här är ett exempel på en fil som lagras på den underliggande Project 2X-platsen med den högreglerade retentionsetiketten och etiketten Project 2X-känslighet tilldelad.

![Ett exempel på en fil som lagras på den underliggande Project 2X-platsen](../media/contoso-team-for-highly-confidential-assets/final-config-example-file.png)
 
## <a name="step-4-trained-project-2x-team-members"></a>Steg 4: Utbildade Project 2X-teammedlemmar

Contosos säkerhetspersonal utbildade Project 2X-teammedlemmarna i en obligatorisk kurs som klev igenom dem:

- Så här öppnar du det nya Project 2X-teamet, använder möten och chattar och hur du samarbetar i gruppfiler.
- Så här skapar du nya filer i teamet och laddar upp nya filer som skapats lokalt.
- En demonstration av hur DLP-principen blockerar filer från att delas externt.
- Så här märker du filer med känslighetsetiketten Project 2X.
- En demonstration av hur Project 2X-etiketten skyddar en fil även när den lämnar teamet.

Slutresultatet blev en säker miljö där Project 2X-gruppmedlemmar samarbetade i en säker miljö för chattar, möten och filer.

I ett par instanser hämtade Project 2X-gruppmedlemmar filer som skyddas av Project 2X-etiketten till en lokal enhet för offlinearbete. Men efter att ha uppmanats för autentiseringsuppgifter när de öppnade dem, insåg de sitt misstag och raderade dem.

På grund av samarbetsmiljön för Teams och säkerhetsfunktionerna i Microsoft 365 hölls informationen om Project 2X hemlig under projektets gång. Contoso tillkännagav sina planer och håller på att rulla ut de nya produkterna och tjänsterna till glädje för sina kunder och investerare och förtret för sina konkurrenter.

## <a name="next-step"></a>Nästa steg

[Distribuera](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise i organisationen.

## <a name="see-also"></a>Se även

[Produktivitetsbibliotek i Microsoft 365](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)
