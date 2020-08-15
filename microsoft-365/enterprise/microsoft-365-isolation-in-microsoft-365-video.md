---
title: Klient isolering i Office 365 Video
ms.author: josephd
author: JoeDavies-MSFT
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
description: I den här artikeln finns en förklaring av hur klient isolering behåller varje klient organisations lagrade videor i Office 365-Video.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3f46812bb2bf9432252c2de6bb46fbb47cb71221
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694649"
---
# <a name="tenant-isolation-in-office-365-video"></a>Klient isolering i Office 365 Video

> [!NOTE]
> Office 365-videon ersätts av Microsoft Stream. Om du vill veta mer om den nya företags video tjänsten som lägger till intelligens i video samarbete och mer information om över gången abonnemang för aktuella Microsoft 365-videosamtal, se [Office 365 Video över gång till Microsoft Stream-översikt](https://docs.microsoft.com/stream/migrate-from-office-365).

## <a name="introduction"></a>Introduktion

Azure Storage används för att lagra data för flera Office 365-tjänster, inklusive Office 365-Video och Sway. Azure Storage inkluderar Blob Storage, som är en skalbar, REST-baserad, moln objekt lagring som används för att lagra ostrukturerade data. Azure-lagring använder en enkel åtkomst kontroll modell; varje Azure-prenumeration kan skapa ett eller flera lagrings konton. Varje lagrings konto har en hemlig nyckel som används för att kontrol lera åtkomsten till alla data på det lagrings kontot. Detta stöder det typiska scenario där lagring är kopplad till program och att dessa program har fullständig kontroll över tillhör ande data; Sway lagrar till exempel innehåll i Azure-lagring. Allt kund innehåll för Sway lagras i delade Azure Storage-konton. Varje användares innehåll är i ett separat katalog träd med blobbar i Azure-lagring.

De system som hanterar åtkomst till kund miljöer (till exempel Azure Portal, SMAPI etc.) är isolerade i ett Azure-program som drivs av Microsoft. Det här skiljer sig logiskt från Customer Access Infrastructure från Customer Applications och lagrings lagret.

## <a name="tenant-isolation-in-office-365-video"></a>Klient isolering i Office 365 Video

[Office 365 Video](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) är en Enterprise Portal som ger organisationer med ett mycket säkert, organisations mål för att anslå, dela och hitta video innehåll. I Office 365-Video är varje klient organisation isolerad och krypterad på alla platser och är bara tillgänglig för autentiserade användare som har åtkomst och behörighet till organisationens videor. I Office 365-Video används en kombination av teknologier för att åstadkomma detta:

- SharePoint Online används för att lagra video filen och metadata (video rubrik, beskrivning osv.). Det ger också säkerhets-och kompatibilitetstillstånd (inklusive verifikation) och Sök funktioner.
- Med Azure Media Services kan du avkoda, anpassa direkt uppspelning, säker leverans (använda AES-kryptering) och miniatyr funktioner.

[Azure Media Services](https://azure.microsoft.com/services/media-services/) är en plattform-as-service-erbjudande för att aktivera medie flöden från slut punkt till slut punkt i molnet. Plattformen tillhandahåller ett REST API för överföring, kodning, kryptering (med PlayReady) och leverans av media via Azure-datacentrer världen över.

Alla uppladdningar för Office 365-Video uppträder via HTTPS. När en videofil laddas upp lagras den i SharePoint Online och en kopia av filen skickas via en krypterad kanal till Azure Media Services. Azure Media Services kodar videon i flera format som är optimerade för visning (till exempel mobil, låg bandbredd, höghastighets samtal osv.). Dessa filer, tillsammans med den ursprungliga filen som erhölls under uppladdning, lagras i Azure Blob Storage. Filerna är krypterade med AES 128 per den MPEG common Encryption-algoritm (eller en tidigare PlayReady-version) som ska spelas upp och krypterad med AES 256 lagrings kryptering innan den lagras i Azure Blob Storage. (Med hjälp av Azure Media Services Client SDK kan kunderna kontrol lera vilken kryptering som används. En kund kan till exempel använda Azure Media Services Storage Encryption (AES 256) till en medie till gång med hög värde innan den laddar upp Azure Blob Storage.)

I Azure Media Services skapas också en miniatyr bild för videon som skickas tillsammans med miniatyrer till SharePoint Online via en krypterad kanal.
