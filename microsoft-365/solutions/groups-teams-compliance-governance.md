---
title: Efterlevnadsalternativ för Microsoft 365-grupper, Teams och SharePoint-samarbete
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Läs mer om kompatibilitetsalternativ för Microsoft 365-grupper, Teams och SharePoint-samarbete.
ms.openlocfilehash: f68381ab45e74b9b7c8f44465387add82bd4150a
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838657"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Efterlevnadsalternativ för Microsoft 365-grupper, Teams och SharePoint-samarbete

Microsoft 365 erbjuder en komplett uppsättning verktyg för att upprätthålla efterlevnad allt eftersom användarna samarbetar. Gå igenom de här alternativen och fundera på hur de kan mappa till dina affärsbehov, dina datas känslighet och vilka personer som användarna behöver samarbeta med.

Följande tabell innehåller en snabbreferens för de efterlevnadskontroller som är tillgängliga i Microsoft 365. Ytterligare information ges i följande avsnitt.

|Kategori|Beskrivning|Referens|
|:-------|:----------|:--------|
|Informationsbevarande|||
||Behålla e-post och SharePoint-innehåll för grupper|[Läs mer om bevarandeprinciper för SharePoint och OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)|
||Behålla chatt och meddelanden|[Läs mer om bevarandeprinciper för Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)|
|Informationsklassificering|||
||Klassificera grupper och team|[Använda känslighetsetiketter för att skydda innehåll i Microsoft Teams, Microsoft 365-grupper och SharePoint-webbplatser](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Klassificera känsligt innehåll automatiskt|[Använda en känslighetsetikett för innehåll automatiskt](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)|
||Kryptera känsligt innehåll|[Begränsa åtkomst till innehåll med hjälp av känslighetsetiketter för att tillämpa kryptering](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)|
|Informationsskydd|||
||Förhindra förlust av känslig information|[Översikt över dataförlustskydd](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)|
||Skydda känslig information i chatten.|[Skydd mot dataförlust och Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)|
||Definiera känslig information för din organisation|[Vanliga typer av känslig information](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)|
|Användarsegmentering|||
||Begränsa kommunikationen mellan användarsegment|[Informationsbarriärer](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)|

## <a name="information-retention"></a>Informationsbevarande

Bevarandeprinciper är tillgängliga för att behålla eller ta bort objekt som används för samarbete i grupper och grupper, inklusive filer, meddelanden och e-post. Principer kan ställas in på att behålla och ta bort, endast behålla eller ta bort. Information som omfattas av en bevarandeprincip skyddas om gruppen eller gruppen upphör att gälla eller tas bort på annat sätt.

Konfigurering av en bevarandeprincip för Microsoft 365 Grupper omfattar grupppostlådan och den tillhörande SharePoint-webbplatsen och tillhörande filer.

- [Läs mer om bevarandeprinciper för SharePoint och OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)

Bevarandeprinciper för Teams bevarar chatt- och kanalmeddelanden. Chatt- och kanalmeddelanden lagras i Exchange-postlådor, men de påverkas inte av Exchange-kvarhållningsprinciper. Du måste ange att bevarandeprinciper ska gälla för Chattar i Teams och meddelanden i Teams-kanalen. 

Användarchattar behålls på obestämd tid även om ett användarkonto tas bort. Om du inte vill behålla dessa data på obestämd tid kan du använda en bevarandeprincip för att ta bort användarchattar efter en angiven tid eller ta med den här borttagningen i borttagningsprocessen för användare.

- [Läs mer om bevarandeprinciper för Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

- [Bevarandeprinciper i Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies)

En enda bevarandeprincip kan ställas in att gälla för Microsoft 365-grupper, Teams-chatt och Teams-kanalmeddelanden. 

Fler resurser:

- [Lär dig mer om kvarhållningsprinciper](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

- [Bevarandetaggar och bevarandeprinciper](https://docs.microsoft.com/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) i Exchange

## <a name="information-classification"></a>Informationsklassificering

Du kan använda känslighetsetiketter för att styra gäståtkomst, grupp- och teamsekretess och åtkomst via ohanterade enheter för grupper och team. Om du använder etiketten konfigureras de här inställningarna automatiskt enligt etikettinställningarna.

- [Använda känslighetsetiketter för att skydda innehåll i Microsoft Teams, Microsoft 365-grupper och SharePoint-webbplatser](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Du kan konfigurera Microsoft 365 så att känslighetsetiketter tillämpas automatiskt i filer och e-postmeddelanden baserat på de villkor du anger, inklusive identifiering av typer av känslig information eller mönstermatchning med utbildande klassificerare.

- [Använda en känslighetsetikett för innehåll automatiskt](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)

Du kan använda känslighetsetiketter för att kryptera filer, så att bara de med behörighet kan dekryptera och läsa dem.

- [Begränsa åtkomst till innehåll med hjälp av känslighetsetiketter för att tillämpa kryptering](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)

- [Konfigurera en team med säkerhetsisolering](https://docs.microsoft.com/microsoft-365/solutions/secure-teams-security-isolation)

Fler resurser:

- [Lär dig mer om känslighetsetiketter](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)


## <a name="information-protection"></a>Informationsskydd

DLP-principer kan förhindra att känslig information delas av misstag i SharePoint, Exchange och Teams. Du kan skapa principer som anger åtgärder som ska vidtas (t.ex. blockera åtkomst) baserat på en uppsättning regler.

- [Översikt över dataförlustskydd](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)

Med DLP i Teams kan du skydda känslig information i Teams chatt- och kanalmeddelanden genom att ta bort meddelanden som innehåller känslig information.

- [Skydd mot dataförlust och Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)

Om du har känslig information som är unik för din organisation, t.ex. projektkodsnamn, kan du skapa egna typer av känslig information och tillämpa dem på DLP-principer för att skydda innehåll i grupper, grupper och SharePoint.

- [Vanliga typer av känslig information](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)

## <a name="user-segmentation"></a>Användarsegmentering

Om det finns informationsbarriärer kan du segmentera dina data och användare för att begränsa oönskad kommunikation och samarbete mellan grupper och undvika intressekonflikter i organisationen. Informationsbarriärer gör att du kan skapa principer för att tillåta eller förhindra filsamarbete, chatt, samtal eller mötesinbjudningar mellan grupper av personer i din organisation.

- [Informationsbarriärer](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)

- [Informationsbarriärer i Microsoft Teams](https://docs.microsoft.com/microsoftteams/information-barriers-in-teams)

- [Använd informationsbarriärer med SharePoint](https://docs.microsoft.com/sharepoint/information-barriers)

## <a name="related-topics"></a>Relaterade ämnen

[Planering av samarbetsstyrning steg för steg](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Skapa din plan för samarbetesstyrning](collaboration-governance-first.md)

[Säkerhet och efterlevnad för Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance)

[Skydda information](https://docs.microsoft.com/microsoft-365/compliance/protect-information)
