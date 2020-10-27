---
title: Microsoft 365 SharePoint Online-data borttagning
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
- SPO_Content
f1.keywords:
- NOCSH
description: Lär dig hur data borttagning fungerar i SharePoint Online, till exempel var borttagna innehåll lagras och hur länge.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 888ee807e6cd4ddc435c1df86a63502a617d6cb8
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769048"
---
# <a name="sharepoint-online-data-deletion-in-microsoft-365"></a>SharePoint Online-Databorttagning i Microsoft 365

SharePoint Online lagrar objekt som en upplagrad kod i program databaser. När en användare laddar upp en fil till SharePoint Online assembleras den och omvandlas till program kod och lagras i flera tabeller i flera databaser. I SharePoint Online delas allt innehåll som en kund överföring till delar upp i segment, krypterat (med en eller flera AES 256-bitars nycklar) och fördelas i data centret. 

I SharePoint Online bevaras objekt i 93 dagar från den tid du tar bort dem från den ursprungliga platsen. De stannar i webbplatsens pappers korg hela tiden, såvida inte någon tar bort dem från där eller tömmer pappers korgen. I så fall går objekten till pappers korgen för webbplats samlingen, där de kvarstår för resten av 93 dagar. Information om hur du återställer borttagna objekt finns i [återställa objekt i pappers korgen på en SharePoint-webbplats](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) och [återställa borttagna objekt från webbplats samlingens pappers korg](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b). Bevarande tiden för pappers korgen kan inte konfigureras i SharePoint Online.

När du tar bort en webbplats samling tar du också bort hierarkin över webbplatser i samlingen och allt innehåll i dem:

- Dokument och dokument bibliotek
- Listor och listdata
- Inställningar för webbplats konfiguration
- Roll-och säkerhets information som är relaterad till webbplatsen eller dess under webbplatser
- Under webbplatser till webbplatsen på den översta nivån, deras innehåll och användar information

Om du tar bort en webbplats samling av misstag kan den återställas av en global administratör eller en SharePoint-admin med administrations centret för SharePoint.

Borttagna webbplats samlingar behålls i 93 dagar. Efter 93 dagar raderas webbplatser och allt innehåll och inställningar permanent, inklusive listor, bibliotek, sidor och eventuella underwebbplatser.

Borttagning av filer sker när en användare tar bort borttagna objekt från webbplats samlingens pappers korg när bevarande-och säkerhets kopierings perioden går ut, eller när en administratör raderar en webbplats samling med hjälp av [cmdleten Remove-SPODeletedSite](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps). När en användare tar bort (permanent tar bort) innehåll från SharePoint Online tas alla krypterings nycklar för de borttagna bitarna bort. Blocken på de diskar som tidigare sparade de borttagna bitarna markeras som oanvända och tillgängliga för åter användning.
