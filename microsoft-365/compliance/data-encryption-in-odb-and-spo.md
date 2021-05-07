---
title: Data Encryption in OneDrive for Business and SharePoint Online
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: Förstå de grundläggande krypteringselementen för datasäkerhet i OneDrive för företag och SharePoint Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ca93d04fa21487ad054cd9cb924dff1fc15abfbd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162187"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a>Data Encryption in OneDrive for Business and SharePoint Online

Förstå de grundläggande krypteringselementen för datasäkerhet i OneDrive för företag och SharePoint Online.
  
## <a name="security-and-data-encryption-in-office-365"></a>Säkerhet och datakryptering i Office 365

Microsoft 365 är en mycket säker miljö som erbjuder omfattande skydd i flera lager: fysisk säkerhet på datacenter, nätverkssäkerhet, åtkomstsäkerhet, programsäkerhet och datasäkerhet. Den här artikeln fokuserar specifikt på krypteringssidan för datasäkerhet under överföring och OneDrive för företag och SharePoint Online.
  
Se hur datakryptering fungerar i följande video.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a>Kryptering av data som överförs

I OneDrive för företag och SharePoint Online finns det två scenarier där data matas in i och lämnar datacenter.
  
- **Klientkommunikation med servern** Kommunikation till OneDrive för företag över Internet använder SSL-/TLS-anslutningar. Alla SSL-anslutningar upprättas med 2048-bitarsnycklar.

- **Dataförflyttning mellan datacenter** Den främsta orsaken till att flytta data mellan datacenter är för georeplikering för att möjliggöra katastrofåterställning. Till exempel SQL Server transaktionsloggar och blob-lagringss deltan färdas längs den här ledning. Även om dessa data redan överförs genom ett privat nätverk skyddas de ytterligare med förstklassig kryptering. 

## <a name="encryption-of-data-at-rest"></a>Kryptering av data i vila

Kryptering i vila består av två komponenter: BitLocker kryptering på disknivå och kryptering per fil för kundinnehåll.
  
BitLocker distribueras för OneDrive för företag och SharePoint Online i tjänsten. Per filkryptering finns också i OneDrive för företag och SharePoint Online i Microsoft 365 med flera innehavare och nya dedikerade miljöer som bygger på teknik för flera innehavare.
  
Medan BitLocker krypterar alla data på en disk går krypteringen per fil ännu längre genom att en unik krypteringsnyckel för varje fil inkluderas. Varje uppdatering av varje fil krypteras dessutom med en egen krypteringsnyckel. Innan de lagras lagras nycklar till det krypterade innehållet på en fysiskt separat plats från innehållet. Varje steg i den här krypteringen använder AES (Advanced Encryption Standard) med 256-bitarsnycklar och är FIPS (Federal Information Processing Standard) 140-2-kompatibel. Det krypterade innehållet fördelas över ett antal behållare i datacentret och varje behållare har unika autentiseringsuppgifter. Autentiseringsuppgifterna lagras på en separat fysisk plats från innehållet eller innehållsnycklarna.
  
Mer information om efterlevnad med FIPS 140-2 finns i Efterlevnad för [FIPS 140-2.](/previous-versions/sql/sql-server-2008-r2/bb326611(v=sql.105))
  
Kryptering på filnivå i vila utnyttjar blob-lagring för att tillhandahålla virtuellt obegränsad lagringstillväxt och aktivera skydd av miljön. Allt kundinnehåll i OneDrive för företag och SharePoint Online migreras till blob-lagring. Så här skyddas dessa data:
  
1. Allt innehåll krypteras, potentiellt med flera nycklar, och distribueras över datacentret. Varje fil som ska lagras delas upp i en eller flera delar, beroende på dess storlek. Därefter krypteras varje segment med en egen unik nyckel. Uppdateringar hanteras på samma sätt: uppsättningen ändringar, eller deltan, som skickas av en användare är uppdelad i delar och var och en krypteras med en egen nyckel.

2. Alla delar – filer, delar av filer och uppdateringss delta – lagras som blobbar i vår blob-butik. De är också slumpmässigt fördelade över flera blob-behållare.

3. Den "karta" som används för att sammanställa filen från dess komponenter lagras i innehållsdatabasen.

4. Varje blob-behållare har sina egna unika autentiseringsuppgifter per åtkomsttyp (läsa, skriva, räkna upp och ta bort). Varje uppsättning autentiseringsuppgifter hålls i det säkra nyckelarkivet och uppdateras regelbundet.

Det finns med andra ord tre olika typer av butiker som ingår i per filkryptering i vila, var och en med en särskild funktion:
  
- Innehållet lagras som krypterade blobbar i blob-butiken. Nyckeln till varje del av innehållet krypteras och lagras separat i innehållsdatabasen. Själva innehållet innehåller ingen ledtråd om hur det kan dekrypteras.

- Innehållsdatabasen är en SQL Server databas. Den innehåller den mappning som krävs för att hitta och sätta ihop allt innehåll som blobbar som finns i blob Store samt de nycklar som krävs för att dekryptera dessa blobbar.

Var och en av de här tre lagringskomponenterna – blob-lagringen, innehållsdatabasen och nyckellagringslagret – är fysiskt separat. Informationen som finns i någon av komponenterna är oanvändbar på egen hand. Detta ger en säkerhetsnivå. Utan åtkomst till alla tre går det inte att hämta nycklarna i segmenten, dekryptera nycklarna så att de kan användas, associera nycklarna med motsvarande delar, dekryptera något segment eller återskapa ett dokument från dess beståndsdelar.