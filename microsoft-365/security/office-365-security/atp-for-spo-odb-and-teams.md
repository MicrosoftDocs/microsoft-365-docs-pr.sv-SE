---
title: ATP för SharePoint, OneDrive och Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 03/19/2019
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
description: Lär dig mer om avancerat skydd mot Office 365 för filer i SharePoint Online, OneDrive för företag och Microsoft Teams.
ms.openlocfilehash: 90e84f0a4393e5097fb59b93693862a21d6d9f2f
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44031454"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a>ATP för SharePoint, OneDrive och Microsoft Teams

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Översikt över Office 365 ATP för SharePoint, OneDrive och Microsoft Teams

Personer delar regelbundet filer och samarbetar med SharePoint, OneDrive och Microsoft Teams. Med [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kan din organisation samarbeta på ett säkrare sätt. ATP hjälper till att identifiera och blockera filer som identifieras som skadliga på gruppwebbplatser och dokumentbibliotek.

## <a name="how-it-works"></a>Så här fungerar det

När en fil i SharePoint Online, OneDrive för företag och Microsoft Teams har identifierats som skadlig integreras ATP direkt med filarkiven för att låsa filen. Följande bild visar ett exempel på en skadlig fil som har identifierats i ett bibliotek.

![Filer i OneDrive för företag med en som har identifierats som skadlig](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Även om den blockerade filen fortfarande finns med i dokumentbiblioteket och webb-, mobil- eller skrivbordsprogrammen kan den blockerade filen inte öppnas, kopieras, flyttas eller delas. Andra kan dock ta bort en blockerad fil. Här är ett exempel på hur det ser ut på en användares mobila enhet:

![Ta bort en blockerad fil från OneDrive för företag från OneDrive-mobilappen](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

Beroende på hur Microsoft 365 är konfigurerat kan det hända att personer kan hämta en blockerad fil eller inte. Så här ser det ut att hämta en blockerad fil på en användares mobila enhet:

![Hämta en blockerad fil i OneDrive för företag](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

Mer information finns i [Aktivera Office 365 ATP för SharePoint, OneDrive och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

## <a name="keep-these-points-in-mind"></a>Tänk på dessa punkter

- ATP söker inte igenom varenda fil i SharePoint Online, OneDrive för företag eller Microsoft Teams. Detta är avsiktligt. Filer skannas asynkront, genom en process som använder delnings- och gästaktivitetshändelser tillsammans med smarta heuristik och hotsignaler för att identifiera skadliga filer.

- Kontrollera att dina SharePoint-webbplatser är konfigurerade för att använda den [moderna upplevelsen](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience). När en fil identifieras som skadlig och blockerad kan andra se att detta har inträffat i den moderna upplevelsen, men inte den klassiska vyn. ATP-skydd gäller oavsett om den moderna upplevelsen eller den klassiska vyn används. Visuella indikatorer som en fil är blockerad finns dock bara i den moderna upplevelsen.

- Filer som identifieras som skadliga i SharePoint Online, OneDrive för företag eller Microsoft Teams visas i [rapporter för avancerat skydd mot office 365](view-reports-for-atp.md) och i [Explorer (och realtidsidentifieringar).](threat-explorer.md)

- ATP är en del av organisationens övergripande strategi för skydd av hot, som omfattar skydd mot skräppost och skadlig kod, samt säkra länkar och säkra bilagor. Mer information finns [i Skydda mot hot i Office 365](protect-against-threats.md).

- En SharePoint Online-administratör kan avgöra om personer ska kunna hämta filer som identifieras som skadliga. Detta görs genom att köra cmdleten Set-SPOTenant PowerShell med parametern DisallowInfectedFileDownload (se [Aktivera Office 365 ATP för SharePoint, OneDrive och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).

## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a>Karantän i ATP för SharePoint Online, OneDrive för företag och Microsoft Teams

 Från och med slutet av maj 2018 utökas [karantänfunktionerna](quarantine-email-messages.md) i Security &amp; Compliance Center till ATP för SharePoint Online, OneDrive för företag och Microsoft Teams.

När en fil i SharePoint Online, OneDrive för företag eller Microsoft Teams identifieras som skadlig, förutom att ATP blockerar filen från att öppnas eller delas, inkluderas filen i en lista över objekt i karantän. (I Security &amp; Compliance Center går du till **Karantän för granskning av hothantering** \> **Review** \> **och** filtrerar efter **filer**.)

Om du ingår i organisationens Microsoft 365 för företagssäkerhetsteam och har de behörigheter som krävs [tilldelade i Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)kan du hämta, släppa, rapportera och ta bort filer som identifieras som skadliga av ATP från karantänen.

- **Om du släpper och rapporterar** en fil tas ATP-blocket bort på filen på respektive gruppwebbplats eller dokumentbibliotek för SharePoint, OneDrive eller Microsoft Teams. Användarna kan sedan öppna, dela och ladda ned filen. Och när alternativet **Skicka rapport till Microsoft** är markerat rapporteras filen som falskt positivt för Microsoft.

- **Om du tar bort en fil** tas filen bort från karantänen. Filen är dock fortfarande blockerad från att öppnas eller delas. Filen måste också tas bort i respektive dokumentbibliotek eller gruppwebbplats (SharePoint Online, OneDrive för företag eller Microsoft Teams).

- **Genom att hämta en fil** kan du hämta och analysera filen för eventuella falska positiva identifieringar.

## <a name="next-steps"></a>Nästa steg

 - [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)

 - [Visa information om skadliga filer som upptäckts i SharePoint, OneDrive eller Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)

