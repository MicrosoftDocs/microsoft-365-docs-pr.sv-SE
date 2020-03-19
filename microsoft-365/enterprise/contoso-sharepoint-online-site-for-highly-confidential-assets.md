---
title: SharePoint-webbplats för mycket konfidentiella digitala tillgångar i Contoso Corporation
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
description: 'Sammanfattning: Hur Contoso implementerade en SharePoint-webbplats för starkt reglerade data för enklare samarbete mellan sina forskargrupper.'
ms.openlocfilehash: a1ffb336e85eb6eb850b53ed14adf947b56642cc
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42807628"
---
# <a name="sharepoint-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>SharePoint-webbplats för mycket konfidentiella digitala tillgångar i Contoso Corporation

Contosos mest värdefulla tillgångar är dess immateriella rättigheter i form av affärshemligheter, såsom egenutvecklade tillverkningstekniker, och designspecifikationer för produkter som är under utveckling. Dessa tillgångar var i digital form, ursprungligen lagras som filer på en SharePoint Server 2016 webbplats. När Contoso distribuerade Microsoft 365 Enterprise ville de överlåta sina lokala digitala tillgångar till molnet för enklare åtkomst och mer öppet samarbete mellan forskargrupper i Paris, Moskva, New York, Peking och Bangalore. 
  
På grund av sin känsliga natur måste dock tillgången till dessa filer vara:

- Begränsad till uppsättningen personer som är tillåtna tillgång till dem. 
- Skyddad med en DLP-princip (Data Loss Prevention) för att förhindra att användare distribuerar dem utanför webbplatsen.
- Krypterad och skyddad med behörigheter för att förhindra att obehöriga användare kommer åt deras innehåll, även om de distribueras utanför webbplatsen.

Säkerhets- och SharePoint-administratörer på Contosos IT-avdelning har beslutat att använda en [SharePoint-webbplats för starkt reglerade data](teams-sharepoint-online-sites-highly-regulated-data.md).
  
Contoso använde dessa steg för att skapa och säkra en SharePoint-gruppwebbplatser för sina forskargrupper.

## <a name="step-1-created-a-private-sharepoint-team-site"></a>Steg 1: Skapade en privat SharePoint-gruppwebbplats

För att skydda åtkomsten till SharePoint-webbplatsen konfigurerade Contoso IT de [rekommenderade SharePoint-åtkomstprinciperna](sharepoint-file-access-policies.md).

Därefter sammanställt Contoso IT-administratörer en lista över användarkonton för forskarna i deras Kontor i Paris, Moskva, New York, Peking och Bangalore. 

Därefter skapade en Contoso IT-administratör en ny privat teamwebbplats med namnet **Research** och lade till alla användarkonton för sina forskare.

Sedan konfigurerade de ytterligare behörighetsinställningar för webbplatsen för att förhindra att forskare delar åtkomst till webbplatsen och för att förhindra att icke-forskare begär åtkomst till webbplatsen.

## <a name="step-2-configured-the-site-for-a-restrictive-dlp-policy"></a>Steg 2: Konfigurerade platsen för en restriktiv DLP-princip

Först tillämpade Contoso-administratörer den befintliga lagringsetiketten **Highly Confidential** Office 365 på mappen Dokument på **forskningswebbplatsen.**

Därefter skapade de en ny DLP-princip för Office 365 med namnet **Forskning** som:

- Använder lagringsetiketten **Mycket konfidentiell** Office 365. 
- Blockerar användare när de försöker dela en digital tillgång på **forskningswebbplatsen** utanför Contoso.

Information om konfigurationen finns i [Skydda SharePoint-filer med kvarhållningsetiketter och DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).

## <a name="step-3-created-an-office-365-sensitivity-sublabel-for-the-site"></a>Steg 3: Skapade en underetikett för Office 365-känslighet för webbplatsen

Contoso-administratörer skapade en ny underetikett med Office 365-känslighet med namnet **Forskargrupper** för etiketten **Mycket konfidentiellt** som:

- Kräver kryptering.
- Tillåter behörigheter för samtidig redigering för **gruppen Research** Office 365
- Gäller **för gruppen Research** Office 365

Här är den resulterande konfigurationen av **forskningsgruppens** webbplats för mycket konfidentiella tillgångar.

![Den resulterande konfigurationen av forskningsgruppens webbplats för mycket konfidentiella tillgångar](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

Filer i mappar på **forskningswebbplatsen** skyddas av:

- Webbplatsbehörigheterna, som endast tillåter åtkomst till medlemmar i gruppen **Research** Office 365.
- **Policyn För DLP för forskning,** som använder etiketten **Mycket konfidentiell** lagring och inställningar som förhindrar att filen delas med externa användare.
- **Underetiketten För forskarkänslighet,** med kryptering och behörigheter som färdas med filen om den flyttas eller kopieras från **forskningswebbplatsen.**

Här är ett exempel på en fil som lagras på **forskningswebbplatsen** med underetiketten **Research Teams** känslighet tilldelad.

![Den resulterande konfigurationen av forskningsgruppens webbplats för mycket konfidentiella tillgångar](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config-example-file.png)


## <a name="step-4-migrated-the-on-premises-sharepoint-research-data"></a>Steg 4: Migrerade lokala SharePoint-forskningsdata

Contoso-administratörer flyttade alla lokala forskningsfiler på den lokala SharePoint Server 2016-webbplatsen till mappar på den nya **Research** SharePoint-webbplatsen.

## <a name="step-5-trained-their-researchers"></a>Steg 5: Utbildade sina forskare

Contosos säkerhetspersonal utbildade medlemmarna i **research** office 365-gruppen i en obligatorisk kurs som gick igenom dem:

- Hur man kommer åt den nya **forskningswebbplatsen** och dess befintliga filer.
- Så här skapar du nya filer på webbplatsen och laddar upp nya filer som lagras lokalt.
- En demonstration av hur **Research** DLP-principen blockerar filer från att delas externt.
- Så här märker du filer med **underetiketten Forskningsteams** känslighet.
- En demonstration av hur **underetiketten research teams** skyddar en fil även när den läcker ut från platsen.

Slutresultatet är en säker miljö där forskarna kan samarbeta över Contoso i en säker miljö på filer som innehåller forskningsinformation. 

Om ett forskningsdokument med underetiketten **Forskargrupper** lämnar **forskningswebbplatsen** krypteras och är det endast tillgängligt för medlemmar i gruppen **Research** Office 365 med giltiga användarkonton.

## <a name="next-step"></a>Nästa steg

[Distribuera](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise i organisationen.

## <a name="see-also"></a>Se även

[Produktivitetsbibliotek i Microsoft 365](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)
