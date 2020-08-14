---
title: Alternativ för kompatibilitet för Microsoft 365-grupper, team och SharePoint-samarbete
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Läs om alternativ för kompatibilitet för Microsoft 365-grupper,-team och SharePoint-samarbete.
ms.openlocfilehash: cc8f7391b03cc65ba66cca6cf010137e3843ab05
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662865"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Alternativ för kompatibilitet för Microsoft 365-grupper, team och SharePoint-samarbete

Microsoft 365 erbjuder en mängd olika verktyg som gör att användarna kan samar beta. Granska de här alternativen och fundera på hur de kan mappa till dina företags behov, känsligheten hos dina data och omfattningen på de personer som användarna måste samar beta med.

Följande tabell innehåller en snabb referens för de kontroll kontroller som finns tillgängliga i Microsoft 365. Mer information finns i följande avsnitt.

|Kategori|Beskrivning|Entitetsreferens|
|:-------|:----------|:--------|
|Informations lagring|||
||Behåll gruppens e-post-och SharePoint-innehåll|[Läs mer om bevarande principer för SharePoint och OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)|
||Bevara chatt och meddelanden|[Läs mer om bevarande principer för Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)|
|Informations klassificering|||
||Klassificera grupper och team|[Använd känslighets etiketter för att skydda innehåll i Microsoft Teams, Microsoft 365-grupper och SharePoint-webbplatser](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Automatiskt klassificera känsligt innehåll|[Använda en känslighetsetikett för innehåll automatiskt](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)|
||Kryptera känsligt innehåll|[Begränsa åtkomst till innehåll med hjälp av känslighetsetiketter för att tillämpa kryptering](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)|
|Informationsskydd|||
||Förhindra förlust av känslig information|[Översikt över skydd mot data förlust](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)|
||Skydda känslig information i chatten.|[Förhindra data förlust och Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)|
||Definiera känslig information för din organisation|[Vanliga typer av känslig information](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)|
|Användar segmentering|||
||Begränsa kommunikationen mellan användar segment|[Informationsbarriärer](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)|

## <a name="information-retention"></a>Informations lagring

Bevarande principer är tillgängliga för att behålla eller ta bort objekt som används för att samar beta i grupper och team, inklusive filer, meddelanden och e-post. Principer kan anges för att behålla och ta bort, endast för att behålla eller ta bort. Information som omfattas av en bevarande princip är skyddad i händelse av att gruppen eller teamet upphör eller på annat sätt raderas.

Konfigurering av en bevarande princip för Microsoft 365-grupper täcker gruppens post låda och tillhör ande SharePoint-webbplats och filer.

- [Läs mer om bevarande principer för SharePoint och OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)

Bevarande principer för Teams behåller chatt-och kanal meddelanden. När chatt och kanal meddelanden lagras i Exchange-postlådor påverkas de inte av Exchange bevarande principer. Du måste ställa in bevarande principer så att de gäller för Teams-chatt och Teams-kanal meddelanden:

- [Läs mer om bevarande principer för Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

- [Bevarande principer i Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies)

En enda bevarande princip kan ställas in så att den gäller för Microsoft 365-grupper, teams-chatt och Team kanal meddelanden. 

Fler resurser:

- [Lär dig mer om kvarhållningsprinciper](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

- [Bevarande märkning och bevarande principer](https://docs.microsoft.com/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) i Exchange

## <a name="information-classification"></a>Informations klassificering

Du kan använda känslighets etiketter för att reglera gäst åtkomst, grupp-och team integritet och åtkomst via ohanterade enheter för grupper och team. Genom att använda etiketten konfigureras dessa inställningar automatiskt enligt inställningarna för etikett.

- [Använd känslighets etiketter för att skydda innehåll i Microsoft Teams, Microsoft 365-grupper och SharePoint-webbplatser](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Du kan konfigurera Microsoft 365 för att automatiskt tillämpa känslighets etiketter på filer och e-postmeddelanden baserat på de villkor du anger, inklusive identifiering av känslig information och mönster matchning med tågens klassificerare.

- [Använda en känslighetsetikett för innehåll automatiskt](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)

Du kan använda känslighets etiketter för att kryptera filer, så att endast de som har behörighet att dekryptera och läsa dem.

- [Begränsa åtkomst till innehåll med hjälp av känslighetsetiketter för att tillämpa kryptering](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)

- [Konfigurera en team med säkerhetsisolering](https://docs.microsoft.com/microsoft-365/solutions/secure-teams-security-isolation)

Fler resurser:

- [Lär dig mer om känslighetsetiketter](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)


## <a name="information-protection"></a>Informationsskydd

DLP-principer kan förhindra oavsiktlig delning av känslig information i SharePoint, Exchange och Teams. Du kan skapa principer som anger vilka åtgärder som ska vidtas (till exempel att blockera åtkomst) baserat på en uppsättning regler.

- [Översikt över skydd mot data förlust](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)

Med DLP i Teams kan du skydda känslig information i chatt-och kanal meddelanden genom att ta bort meddelanden som innehåller känslig information.

- [Förhindra data förlust och Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)

Om du har känslig information som är unik för din organisation, till exempel projekt kod namn, kan du skapa egna känsliga informations typer och tillämpa dem på DLP-principer för att skydda innehållet i grupper, team och SharePoint.

- [Vanliga typer av känslig information](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)

## <a name="user-segmentation"></a>Användar segmentering

Med informations hinder kan du dela med dig av dina data och användare för att begränsa oönskad kommunikation och samarbete mellan grupper och undvika intresse konflikter i organisationen. Med informations hinder kan du skapa principer för att tillåta eller förhindra fil samarbete, chatta, ringa eller Mötes inbjudningar mellan grupper med personer i organisationen.

- [Informationsbarriärer](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)

- [Informations hinder i Microsoft Teams](https://docs.microsoft.com/microsoftteams/information-barriers-in-teams)

- [Använda informations hinder med SharePoint](https://docs.microsoft.com/sharepoint/information-barriers)

## <a name="related-topics"></a>Relaterade ämnen

[Säkerhet och efterlevnad för Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance)

[Skydda information](https://docs.microsoft.com/microsoft-365/compliance/protect-information)


