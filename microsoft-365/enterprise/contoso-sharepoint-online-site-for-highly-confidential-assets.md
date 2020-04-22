---
title: SharePoint-webbplats för högst konfidentiella digitala tillgångar i Contoso Corporation
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
ms.openlocfilehash: 0a4bc2f685cf015611da62ebbed000218f37f31e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634258"
---
# <a name="sharepoint-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>SharePoint-webbplats för högst konfidentiella digitala tillgångar i Contoso Corporation

Contosos mest värdefulla tillgångar är dess immateriella rättigheter i form av affärshemligheter, såsom egenutvecklade tillverkningstekniker, och designspecifikationer för produkter som är under utveckling. Dessa tillgångar var i digital form, ursprungligen lagras som filer på en SharePoint Server 2016-webbplats. När Contoso distribuerade Microsoft 365 Enterprise ville de överföra sina lokala digitala tillgångar till molnet för enklare åtkomst och mer öppet samarbete mellan forskargrupper i Paris, Moskva, New York, Peking och Bangalore. 
  
På grund av sin känsliga karaktär måste dock tillgången till dessa filer vara:

- Begränsad till den uppsättning personer som får åtkomst till dem. 
- Skyddad med en DLP-princip (Data Loss Prevention) för att förhindra att användare distribuerar dem utanför webbplatsen.
- Krypterad och skyddad med behörigheter för att förhindra att obehöriga användare kommer åt sitt innehåll, även om de distribueras utanför webbplatsen.

Säkerhets- och SharePoint-administratörer på Contosos IT-avdelning har beslutat att använda en [SharePoint-webbplats för starkt reglerade data](teams-sharepoint-online-sites-highly-regulated-data.md).
  
Contoso använde dessa steg för att skapa och säkra en SharePoint-gruppwebbplatser för sina forskargrupper.

## <a name="step-1-created-a-private-sharepoint-team-site"></a>Steg 1: Skapade en privat SharePoint-gruppwebbplats

Contoso IT konfigurerade de [rekommenderade SharePoint-åtkomstprinciperna](sharepoint-file-access-policies.md)för att skydda åtkomsten till SharePoint-webbplatsen .

Därefter sammanställde Contoso IT-administratörer en lista över användarkonton för forskarna i deras Kontor i Paris, Moskva, New York, Peking och Bangalore. 

Därefter skapade en Contoso IT-administratör en ny privat gruppwebbplats med namnet **Forskning** och lade till alla användarkonton för sina forskare.

Sedan konfigurerade de ytterligare behörighetsinställningar för webbplatsen för att förhindra att forskare delar åtkomst till webbplatsen och för att förhindra att icke-forskare begär åtkomst till webbplatsen.

## <a name="step-2-configured-the-site-for-a-restrictive-dlp-policy"></a>Steg 2: Konfigurerade platsen för en restriktiv DLP-princip

Först tillämpade Contoso-administratörer den befintliga **mycket konfidentiella** lagringsetiketten på mappen Dokument på **forskningswebbplatsen.**

Därefter skapade de en ny DLP-princip med namnet **Forskning** som:

- Använder etiketten **Mycket konfidentiell** kvarhållning. 
- Blockerar användare när de försöker dela en digital tillgång på **forskningswebbplatsen** utanför Contoso.

Konfigurationsinformation finns i [Skydda SharePoint-filer med kvarhållningsetiketter och DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).

## <a name="step-3-created-a-sensitivity-sublabel-for-the-site"></a>Steg 3: Skapade ett känslighetsundermärke för platsen

Contoso-administratörer skapade ett nytt känslighetsundermärke med namnet **Research Teams** på etiketten **Mycket konfidentiellt** som:

- Kräver kryptering.
- Tillåter samtidiga redigeringsbehörigheter för gruppen **Research** Microsoft 365
- Gäller för **gruppen Research** Microsoft 365

Här är den resulterande konfigurationen av **forskningsgruppens** webbplats för mycket konfidentiella tillgångar.

![Den resulterande konfigurationen av forskningsgruppsplatsen för mycket konfidentiella tillgångar](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

Filer i mappar på **forskningswebbplatsen** skyddas av:

- Webbplatsbehörigheterna, som endast ger åtkomst till medlemmar i gruppen **Research** Microsoft 365.
- **DLP-principen För forskning,** som använder etiketten **Mycket konfidentiell** kvarhållning och inställningar som förhindrar att filen delas med externa användare.
- **Underabeln Forsknings teams** känslighet, med kryptering och behörigheter som färdas med filen om den flyttas eller kopieras från **forskningswebbplatsen.**

Här är ett exempel på en fil som lagras på **forskningsplatsen** med underabeln **Forskningsteamens** känslighetstilldelade.

![Den resulterande konfigurationen av forskningsgruppsplatsen för mycket konfidentiella tillgångar](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config-example-file.png)


## <a name="step-4-migrated-the-on-premises-sharepoint-research-data"></a>Steg 4: Migrerade lokala SharePoint-forskningsdata

Contoso-administratörerna flyttade alla lokala forskningsfiler på den lokala SharePoint Server 2016-webbplatsen till mappar på den nya Webbplatsen För Forskningsresurserpoint. **Research**

## <a name="step-5-trained-their-researchers"></a>Steg 5: Tränade sina forskare

Contoso säkerhetspersonal utbildade medlemmarna i **Gruppen Research** Microsoft 365 i en obligatorisk kurs som klev dem igenom:

- Så här kommer du åt den nya **forskningswebbplatsen** och dess befintliga filer.
- Hur man skapar nya filer på webbplatsen och laddar upp nya filer som lagras lokalt.
- En demonstration av hur **DLP-principen för forskning** blockerar filer från att delas externt.
- Så här märker du filer med undermärket **Forskningsteamens** känslighet.
- En demonstration av hur underetiketten **Research Teams** skyddar en fil även när den läcker ut från webbplatsen.

Slutresultatet är en säker miljö där forskarna kan samarbeta över Contoso i en säker miljö på filer som innehåller forskningsinformation. 

Om ett forskningsdokument med undermärket **Research Teams** lämnar webbplatsen **Research** krypteras det och är endast tillgängligt för medlemmar i gruppen **Research** Microsoft 365 med giltiga kontouppgifter.

## <a name="next-step"></a>Nästa steg

[Distribuera](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise i din organisation.

## <a name="see-also"></a>Snabbreferens

[Produktivitetsbiblioteket för Microsoft 365](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)
