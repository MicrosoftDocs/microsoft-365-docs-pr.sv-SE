---
title: Efterlevnadsalternativ för Microsoft 365 grupper, Teams och SharePoint samarbete
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
description: Läs mer om kompatibilitetsalternativ för Microsoft 365 grupper, Teams och SharePoint samarbete.
ms.openlocfilehash: a9a94f0c1886ac5b60292f5f4d4b9b9d6d84380c
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241682"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Efterlevnadsalternativ för Microsoft 365 grupper, Teams och SharePoint samarbete

Microsoft 365 finns en komplett uppsättning verktyg för att upprätthålla efterlevnad allt eftersom användarna samarbetar. Gå igenom de här alternativen och fundera på hur de kan mappa till dina affärsbehov, dina datas känslighet och vilka personer som användarna behöver samarbeta med.

Följande tabell innehåller en snabbreferens för de efterlevnadskontroller som finns i Microsoft 365. Ytterligare information ges i följande avsnitt.

|Kategori|Beskrivning|Referens|
|:-------|:----------|:--------|
|Informationsbevarande|||
||Behålla e-post och innehåll SharePoint grupper|[Läs mer om bevarandeprinciper för SharePoint och OneDrive](../compliance/retention-policies-sharepoint.md)|
||Behålla chatt och meddelanden|[Läs mer om bevarandeprinciper för Microsoft Teams](../compliance/retention-policies-teams.md)|
|Informationsklassificering|||
||Klassificera grupper och team|[Använd känslighetsetiketter för att skydda innehåll i Microsoft Teams, Microsoft 365-grupper och SharePoint-webbplatser](../compliance/sensitivity-labels-teams-groups-sites.md)|
||Klassificera känsligt innehåll automatiskt|[Använda en känslighetsetikett för innehåll automatiskt](../compliance/apply-sensitivity-label-automatically.md)|
||Kryptera känsligt innehåll|[Begränsa åtkomst till innehåll med hjälp av känslighetsetiketter för att tillämpa kryptering](../compliance/encryption-sensitivity-labels.md)|
|Informationsskydd|||
||Förhindra förlust av känslig information|[Mer information om skydd mot dataförlust](../compliance/dlp-learn-about-dlp.md)|
||Skydda känslig information i chatten.|[Skydd mot dataförlust och Microsoft Teams](../compliance/dlp-microsoft-teams.md)|
||Definiera känslig information för din organisation|[Vanliga typer av känslig information](../compliance/sensitive-information-type-learn-about.md)|
|Användarsegmentering|||
||Begränsa kommunikationen mellan användarsegment|[Informationsbarriärer](../compliance/information-barriers.md)|
|Datahem|||
||Lagra data på specifika geoplatser|[Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)|

## <a name="information-retention"></a>Informationsbevarande

Bevarandeprinciper är tillgängliga för att behålla eller ta bort objekt som används för samarbete i grupper och grupper, inklusive filer, meddelanden och e-post. Principer kan ställas in på att behålla och ta bort, endast behålla eller ta bort. Information som omfattas av en bevarandeprincip skyddas om gruppen eller gruppen upphör att gälla eller tas bort på annat sätt.

Om du konfigurerar en bevarandeprincip för Microsoft 365 grupper omfattar detta grupppostlådan och den SharePoint webbplatsen och filerna.

- [Läs mer om bevarandeprinciper för SharePoint och OneDrive](../compliance/retention-policies-sharepoint.md)

Bevarandeprinciper för Teams behålla chatt- och kanalmeddelanden. Chatt- och kanalmeddelanden lagras i Exchange, men de påverkas inte av Exchange bevarandeprinciper. Du måste ange att bevarandeprinciper ska gälla Teams chattar och Teams kanalmeddelanden. 

Användarchattar behålls på obestämd tid även om ett användarkonto tas bort. Om du inte vill behålla dessa data på obestämd tid kan du använda en bevarandeprincip för att ta bort användarchattar efter en angiven tid eller ta med den här borttagningen i borttagningsprocessen för användare.

- [Läs mer om bevarandeprinciper för Microsoft Teams](../compliance/retention-policies-teams.md)

- [Bevarandeprinciper i Microsoft Teams](/microsoftteams/retention-policies)

En enda bevarandeprincip kan ställas in så att den gäller Teams chatta och Teams kanalmeddelanden. 

Fler resurser:

- [Lär dig mer om kvarhållningsprinciper](../compliance/retention.md)

- [Bevarandetaggar och bevarandeprinciper](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) i Exchange

## <a name="information-classification"></a>Informationsklassificering

Du kan använda känslighetsetiketter för att styra gäståtkomst, grupp- och teamsekretess och åtkomst via ohanterade enheter för grupper och team. Om du använder etiketten konfigureras de här inställningarna automatiskt enligt etikettinställningarna.

- [Använd känslighetsetiketter för att skydda innehåll i Microsoft Teams, Microsoft 365-grupper och SharePoint-webbplatser](../compliance/sensitivity-labels-teams-groups-sites.md)

Du kan konfigurera Microsoft 365 att automatiskt tillämpa känslighetsetiketter på filer och e-postmeddelanden baserat på de villkor du anger, inklusive identifiering av typer av känslig information eller mönstermatchning med utbildande klassificerare.

- [Använda en känslighetsetikett för innehåll automatiskt](../compliance/apply-sensitivity-label-automatically.md)

Du kan använda känslighetsetiketter för att kryptera filer, så att bara de med behörighet kan dekryptera och läsa dem.

- [Begränsa åtkomst till innehåll med hjälp av känslighetsetiketter för att tillämpa kryptering](../compliance/encryption-sensitivity-labels.md)

- [Konfigurera ett team med säkerhetsisolering](./secure-teams-security-isolation.md)

Fler resurser:

- [Lär dig mer om känslighetsetiketter](../compliance/sensitivity-labels.md)


## <a name="information-protection"></a>Informationsskydd

DLP-principer kan förhindra att känslig information oavsiktligt delas mellan olika SharePoint, Exchange och Teams. Du kan skapa principer som anger åtgärder som ska vidtas (t.ex. blockera åtkomst) baserat på en uppsättning regler.

- [Mer information om skydd mot dataförlust](../compliance/dlp-learn-about-dlp.md)

Med DLP i Teams kan du skydda känslig information i Teams och kanalmeddelanden genom att ta bort meddelanden som innehåller känslig information.

- [Skydd mot dataförlust och Microsoft Teams](../compliance/dlp-microsoft-teams.md)

Om du har känslig information som är unik för din organisation, t.ex. projektkodsnamn, kan du skapa egna typer av känslig information och tillämpa dem på DLP-principer för att skydda innehåll i grupper, grupper och SharePoint.

- [Vanliga typer av känslig information](../compliance/sensitive-information-type-learn-about.md)

## <a name="user-segmentation"></a>Användarsegmentering

Om det finns informationsbarriärer kan du segmentera dina data och användare för att begränsa oönskad kommunikation och samarbete mellan grupper och undvika intressekonflikter i organisationen. Informationsbarriärer gör att du kan skapa principer för att tillåta eller förhindra filsamarbete, chatt, samtal eller mötesinbjudningar mellan grupper av personer i din organisation.

- [Informationsbarriärer](../compliance/information-barriers.md)

- [Informationsbarriärer i Microsoft Teams](/microsoftteams/information-barriers-in-teams)

- [Använd informationsbarriärer med SharePoint](/sharepoint/information-barriers)

## <a name="data-residency"></a>Datahem

Med Microsoft 365 Multi-Geo kan du tillhandahålla och lagra data i vila på de geoplatser som du har valt att uppfylla krav för datalagring. I en Multi-Geo-miljö består Microsoft 365-klientorganisationen av en central plats (där Microsoft 365-prenumerationen ursprungligen skapades) och en eller flera satellitplatser där du kan lagra data.

- [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)

- [Planera för Microsoft 365 Multi-Geo](/microsoft-365/enterprise/plan-for-multi-geo)

## <a name="related-topics"></a>Relaterade ämnen

[Planering av samarbetsstyrning steg för steg](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Skapa din plan för samarbetesstyrning](collaboration-governance-first.md)

[Säkerhet och efterlevnad för Exchange Online](/exchange/security-and-compliance/security-and-compliance)

[Skydda information](../compliance/information-protection.md)
