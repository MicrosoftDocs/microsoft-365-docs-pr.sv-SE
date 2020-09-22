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
- seo-marvel-jun2020
description: Lär dig mer om Office 365 Avancerat skydd för filer i SharePoint Online, OneDrive för företag och Microsoft Teams.
ms.openlocfilehash: 9831b61fafc7cb4696fbad3d569f061612f85fe1
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199045"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a>ATP för SharePoint, OneDrive och Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Översikt över Office 365 ATP för SharePoint, OneDrive och Microsoft Teams

Folk delar regelbundet filer och samarbetar med SharePoint, OneDrive och Microsoft Teams. Med [Office 365 Avancerat skydd](office-365-atp.md) (ATP) kan din organisation samar beta på ett säkrare sätt. ATP hjälper till att upptäcka och blockera filer som identifieras som skadliga på grupp webbplatser och dokument bibliotek.

## <a name="how-office-365-atp-operates"></a>Så fungerar Office 365 ATP

När en fil i SharePoint Online, OneDrive för företag och Microsoft Teams har identifierats som skadlig, integreras ATP direkt med fil arkiven för att låsa den filen. Följande bild visar ett exempel på en skadlig fil som identifieras i ett bibliotek.

![Filer i OneDrive för företag med en identifierad som skadlig](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Även om den blockerade filen fortfarande visas i dokument biblioteket och webb-, mobil-eller Skriv bords program går det inte att öppna, kopiera, flytta eller dela den blockerade filen. Det går att ta bort en blockerad fil. Här är ett exempel på vad som ser ut på en användares mobila enhet:

![Ta bort en blockerad fil från OneDrive för företag från OneDrive-mobilappen](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

Beroende på hur Microsoft 365 har kon figurer ATS kan folk eller kanske inte kunna ladda ned en blockerad fil. Så här laddar du ned en blockerad fil på en användares mobila enhet:

![Ladda ned en blockerad fil i OneDrive för företag](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

Mer information finns i [Aktivera Office 365 ATP för SharePoint, OneDrive och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

## <a name="keep-these-points-in-mind"></a>Tänk på följande saker

- ATP kommer inte att söka igenom alla filer i SharePoint Online, OneDrive för företag eller Microsoft Teams. Detta är avsiktligt. Filer skannas asynkront, genom en process där delnings-och gäst aktivitets händelser används tillsammans med smarta heuristik och hot signaler.

- Kontrol lera att dina SharePoint-webbplatser är konfigurerade för att använda den [moderna upplevelsen](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience). När en fil identifieras som skadlig och blockerad kan andra se att det har hänt med den moderna upplevelsen, men inte i klassiskt läge. ATP-skydd gäller om den moderna upplevelsen eller vyn Klassisk används; visuella indikatorer som en fil är blockerade är bara att presentera i den moderna upplevelsen.

- Filer som identifieras som skadliga i SharePoint Online, OneDrive för företag eller Microsoft Teams visas i [rapporter för Office 365 Avancerat skydd för hotet](view-reports-for-atp.md) och i [Utforskaren (och i real tid)](threat-explorer.md).

- ATP är en del av organisationens övergripande hot skydds strategi, som inkluderar skydd mot skräp post samt säkra länkar och säkra bifogade filer. Mer information finns i [skydda mot hot i Office 365](protect-against-threats.md).

- En SharePoint Online-administratör kan bestämma om andra ska kunna hämta filer som identifieras som skadliga. Det gör du genom att köra PowerShell-cmdleten Set-SPOTenant med hjälp av en DisallowInfectedFileDownload-parameter (se [aktivera Office 365 ATP för SharePoint, OneDrive och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).

## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a>Karantän i ATP för SharePoint Online, OneDrive för företag och Microsoft Teams

 Från [och med](quarantine-email-messages.md) den här inledningen kan 2018 i säkerhets &amp; Center utökas till ATP för SharePoint Online, OneDrive för företag och Microsoft Teams.

När en fil i SharePoint Online, OneDrive för företag eller Microsoft Teams identifieras som skadlig är det förutom ATP som blockerar filen från att öppnas eller delas, den filen ingår i en lista över objekt i karantän. (I säkerhets &amp; Compliance Center, gå till **Threat Management** \> **Granska** \> **karantän** och filtrera efter **filer**.)

Om du är en del av säkerhets gruppen Microsoft 365 för företag och har de behörigheter som krävs [för säkerhets &amp; kontroll Center](permissions-in-the-security-and-compliance-center.md)kan du ladda ned, släppa, rapportera och ta bort filer som identifieras som skadligt för ATP från karantän.

- Om du **släpper och rapporterar** en fil tas spärr blocket för ATP bort från filen på respektive grupp webbplats eller dokument bibliotek för SharePoint, OneDrive eller Microsoft Teams. Då kan användarna öppna, dela och ladda ned filen. Och när alternativet **Skicka rapport till Microsoft** är markerat rapporteras filen som falsk till Microsoft.

- Om du **tar bort en fil** tas filen bort från karantänen. filen är dock fortfarande förhindrad att öppnas eller delas. Filen måste också tas bort i sitt respektive dokument bibliotek eller på en grupp webbplats (SharePoint Online, OneDrive för företag eller Microsoft Teams).

- Om du **laddar ned en fil** kan du ladda ned och analysera filen för alla falska positiva positiv.

## <a name="next-steps"></a>Nästa steg

 - [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)

 - [Visa information om skadliga filer som identifieras i SharePoint, OneDrive eller Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)

