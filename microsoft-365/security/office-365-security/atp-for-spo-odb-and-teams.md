---
title: Office 365 ATP för SharePoint, OneDrive och Microsoft-team
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
description: Utöka Office 365 Advanced Threat Protection till filer i SharePoint Online, OneDrive för företag och Microsoft Teams för att möjliggöra säkrare samarbete för din organisation.
ms.openlocfilehash: 3105a9443ddab483bc5ac4037e5260b354d64de9
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811854"
---
# <a name="office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Office 365 ATP för SharePoint, OneDrive och Microsoft-team

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Översikt över Office 365 ATP för SharePoint, OneDrive och Microsoft Teams

Andra delar regelbundet filer och samarbetar med SharePoint, OneDrive och Microsoft Teams. Med [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kan din organisation samarbeta på ett säkrare sätt. ATP hjälper till att identifiera och blockera filer som identifieras som skadliga på gruppwebbplatser och dokumentbibliotek.

## <a name="how-it-works"></a>Så här fungerar det

När en fil i SharePoint Online, OneDrive för företag och Microsoft Teams har identifierats som skadlig integreras ATP direkt med filarkivet för att låsa filen. Följande bild visar ett exempel på en skadlig fil som har upptäckts i ett bibliotek.

![Filer i OneDrive för företag med en upptäckt som skadlig](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Även om den blockerade filen fortfarande finns med i dokumentbiblioteket och webb-, mobil- eller skrivbordsprogrammen kan den blockerade filen inte öppnas, kopieras, flyttas eller delas. Andra kan dock ta bort en blockerad fil. Här är ett exempel på hur det ser ut på en användares mobila enhet:

![Ta bort en blockerad fil från OneDrive för företag från Mobilappen OneDrive](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

Beroende på hur Office 365 är konfigurerat kan det hända att personer kan hämta en blockerad fil eller inte. Så här ser det ut att ladda ned en blockerad fil på en användares mobila enhet:

![Hämta en blockerad fil i OneDrive för företag](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

Mer information finns [i Aktivera Office 365 ATP för SharePoint, OneDrive och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

## <a name="keep-these-points-in-mind"></a>Tänk på dessa punkter

- ATP söker inte igenom varenda fil i SharePoint Online, OneDrive för företag eller Microsoft Teams. Detta är avsiktligt. Filer skannas asynkront, genom en process som använder delning och gästaktivitetshändelser tillsammans med smarta heuristik er och hotsignaler för att identifiera skadliga filer.

- Kontrollera att dina SharePoint-webbplatser är konfigurerade för att använda den [moderna upplevelsen](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience). När en fil identifieras som skadlig och blockerad kan personer se att detta har inträffat i den moderna upplevelsen, men inte i vyn Klassisk. ATP-skydd gäller om modern erfarenhet eller den klassiska vyn används; Visuella indikatorer på att en fil är blockerad finns dock endast i modern erfarenhet.

- Filer som identifieras som skadliga i SharePoint Online, OneDrive för företag eller Microsoft Teams visas i [rapporter för Office 365 Advanced Threat Protection](view-reports-for-atp.md) och i Explorer [(och realtidsidentifieringar)](threat-explorer.md).

- ATP är en del av organisationens övergripande strategi för skydd av hot, som omfattar skydd mot skräppost och skadlig kod, samt säkra länkar och säkra bilagor. Mer information finns i [Skydda mot hot i Office 365](protect-against-threats.md).

- En SharePoint Online-administratör kan avgöra om andra ska kunna hämta filer som identifieras som skadliga. Detta görs genom att köra Cmdlet Set-SPOTenant PowerShell med en parameter DisallowInfectedFileDownload (se [Aktivera Office 365 ATP för SharePoint, OneDrive och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).

## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a>Karantän i ATP för SharePoint Online, OneDrive för företag och Microsoft Teams

 Från och med slutet av maj 2018 utökas [karantänfunktionerna](quarantine-email-messages.md) i Security &amp; Compliance Center till ATP för SharePoint Online, OneDrive för företag och Microsoft Teams.

När en fil i SharePoint Online, OneDrive för företag eller Microsoft Teams identifieras som skadlig, förutom att ATP blockerar filen från att öppnas eller delas, inkluderas filen i en lista över objekt i karantän. (I Security &amp; Compliance Center går du till **Threat management** \> **Review** \> **Quarantine** och filter för **innehåll**.)

Om du är en del av organisationens Säkerhetsteam för Office 365 och har de behörigheter som krävs [i Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md)kan du hämta, publicera, rapportera och ta bort filer som identifieras som skadliga av ATP från karantän.

- **Om du släpper och rapporterar** en fil tas ATP-blocket bort på filen på respektive gruppwebbplats eller dokumentbibliotek för SharePoint, OneDrive eller Microsoft Teams. Användarna kan sedan öppna, dela och ladda ned filen. Och när alternativet **Skicka till Microsoft** är markerat rapporteras filen som ett falskt positivt för Microsoft.

- **Om du tar bort en fil** tas filen bort från karantänen. Filen är dock fortfarande blockerad från att öppnas eller delas. Filen måste också tas bort i respektive dokumentbibliotek eller gruppwebbplats (SharePoint Online, OneDrive för företag eller Microsoft Teams).

- **Genom att hämta en fil** kan du hämta och analysera filen för falska positiva identifieringar.

## <a name="next-steps"></a>Nästa steg

1. [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)

2. [Visa information om skadliga filer som upptäckts i SharePoint- eller OneDrive- eller Microsoft-teams](malicious-files-detected-in-spo-odb-or-teams.md)

