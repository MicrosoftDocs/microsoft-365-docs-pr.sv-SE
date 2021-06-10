---
title: Tenant Isolation i Office 365 Video
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: I den här artikeln finns en förklaring av hur innehavarisolering håller varje innehavare lagrade videor separerade i Office 365 Video.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fc67b17aa40b3bca9ce6d73ebb7e18319e780339
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918936"
---
# <a name="tenant-isolation-in-office-365-video"></a>Tenant Isolation i Office 365 Video

> [!NOTE]
> Office 365 Videon kommer att ersättas av Microsoft Stream. Mer information om den nya företagsvideotjänsten som tillhandahåller information för videosamarbete och lära dig mer om övergångsplaner för aktuella Microsoft 365 Video-kunder finns i Office 365 Videoövergång till Översikt över [Microsoft Stream.](/stream/migrate-from-office-365)

## <a name="introduction"></a>Introduktion

Azure Storage används för att lagra data för flera Office 365 tjänster, inklusive Office 365 Video och Sway. Azure Storage innehåller Blob-lagring, som är en restbaserad, REST-baserad molnobjektlagring som används för lagring av ostrukturerade data. Azure Storage använder en enkel åtkomstkontrollmodell. varje Azure-prenumeration kan skapa en eller flera Storage Konton. Varje Storage konto har en enda hemlig nyckel som används för att kontrollera åtkomsten till alla data i Storage konto. Det här stöder ett vanligt scenario där lagring är associerat med program och dessa program har fullständig kontroll över associerade data. Till exempel Sway lagrar innehåll i Azure Storage. Allt kundinnehåll för Sway lagras i delade Azure-lagringskonton. Varje användares innehåll finns i ett separat katalogträd med blobbar i Azure-lagringen.

De system som hanterar åtkomst till kundmiljöer (t.ex. Azure-portalen, SMAPI osv.) isoleras inom ett Azure-program som drivs av Microsoft. Detta skiljer logiskt kundåtkomstinfrastrukturen från kundprogrammen och lagringslagret.

## <a name="tenant-isolation-in-office-365-video"></a>Tenant Isolation i Office 365 Video

[Office 365 Video](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) är en företagsportal som ger organisationer en mycket säker och företagsomfattande destination för publicering, delning och upptäckt videoinnehåll. I Office 365 Video hålls varje klientorganisations videor isolerade och krypterade på alla platser, och är bara tillgängliga för autentiserade användare som har åtkomst till och behörighet till organisationens videor. Office 365 Video använder en kombination av tekniker för att uppnå detta:

- SharePoint Online används för att lagra videofilen och metadata (videotitel, beskrivning osv.). Det ger också säkerhets- och efterlevnadslager (inklusive autentisering) och sökfunktioner.
- Azure Media Services tillhandahåller transcoding, adaptiv direktuppspelning, säker leverans (med AES-kryptering) och miniatyrfunktioner.

[Azure Media Services](https://azure.microsoft.com/services/media-services/) är en plattform som tjänst för att möjliggöra end-to-end-mediearbetsflöden i molnet. Plattformen ger ett REST API för uppladdning, kodning, kryptering (med PlayReady) och leverans av media via Azure-datacenter över hela världen.

Alla uppladdningar för Office 365-video sker via HTTPS. När en videofil överförs lagras den i SharePoint Online och en kopia av filen skickas via en krypterad kanal till Azure Media Services. Azure Media Services omkodar videon till flera format som är optimerade för visning (t.ex. mobil, låg bandbredd, hög bandbredd osv.). Dessa filer, tillsammans med den ursprungliga filen som köptes vid överföringen, lagras i Azure Blob-lagring. Filerna krypteras med AES 128 enligt algoritmen för MPEG Common Encryption-paketering (eller en tidigare PlayReady-version) för uppspelning och krypteras med AES 256-lagringskryptering innan de lagras i Blob-lagring i Azure. (Med hjälp Azure Media Services Client SDK kan kunder styra vilken kryptering som används. En kund kan till exempel använda Azure Media Services-lagringskryptering (AES 256) på en medienivå innan den laddas upp med Azure Blob-lagring.)

Azure Media Services en miniatyr av videon som skickas tillsammans med miniatyrmetadata till SharePoint Online via en krypterad kanal.