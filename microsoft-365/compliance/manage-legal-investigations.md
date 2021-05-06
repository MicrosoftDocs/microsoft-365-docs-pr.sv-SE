---
title: Hantera juridiska undersökningar i Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e
ms.custom:
- seo-marvel-apr2020
description: Använd eDiscovery-ärenden i Säkerhets- & efterlevnadscenter i Office 365 för att hantera organisationens juridiska undersökning.
ms.openlocfilehash: c052daab8de33e21cccc3c638ab4995a007f60fb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161848"
---
# <a name="manage-legal-investigations-in-microsoft-365"></a>Hantera juridiska undersökningar i Microsoft 365

Organisationer har många skäl att besvara ett juridiskt ärende som rör vissa chefer eller andra anställda i organisationen. Det här kan innefatta att snabbt hitta och behålla för vidare undersökningsspecifik information i e-postmeddelanden, dokument, snabbmeddelandekonversationer och andra innehållsplatser som används av personer i deras dagliga arbetsuppgifter. Du kan utföra dessa och många andra liknande aktiviteter med hjälp av eDiscovery-fallverktygen i säkerhets- och efterlevnadscentret.
  
**Vill du veta hur Microsoft hanterar sina eDiscovery-undersökningar?** Här är en teknisk [informationsartikel](https://go.microsoft.com/fwlink/?linkid=852161) som förklarar hur vi använder samma sök- och undersökningsverktyg för att hantera vårt interna eDiscovery-arbetsflöde.

## <a name="manage-legal-investigations-with-ediscovery-cases"></a>Hantera juridiska undersökningar med eDiscovery-ärenden

Med eDiscovery-ärenden kan du styra vem som kan skapa, komma åt och hantera eDiscovery-ärenden i organisationen. Använd ärenden för att lägga till medlemmar och kontrollera vilka typer av åtgärder de kan utföra, skapa ett väntande på innehållsplatser som är relevanta för juridiska ärenden och använd verktyget Innehållssökning för att söka efter innehåll som kan svara på ditt ärende på platser som är väntande. Sedan kan du också exportera och ladda ned resultaten för ytterligare undersökning av externa granskare.
  
- [Hantera ditt eDiscovery-arbetsflöde](./get-started-core-ediscovery.md) genom att skapa och använda eDiscovery-ärenden för varje juridisk undersökning som din organisation måste utföra.

- [Tilldela eDiscovery-behörigheter](assign-ediscovery-permissions.md) för att styra vem som kan skapa och hantera eDiscovery-ärenden i organisationen.

- [Konfigurera efterlevnadsgränser för](set-up-compliance-boundaries.md) att styra användarinnehållsplatser som eDiscovery-hanterare kan söka i.

- [Sök efter innehåll](search-for-content.md) i din organisation.

### <a name="use-scripts-for-advanced-scenarios"></a>Använda skript för avancerade scenarier

Precis som i föregående avsnitt där skript för innehållssökningsscenarier visas har vi också skapat vissa PowerShell-skript för säkerhets- och efterlevnadscenter för &-efterlevnadscenter som hjälper dig att hantera eDiscovery-ärenden.
  
- [Skapa en eDiscovery-rapport som](create-a-report-on-holds-in-ediscovery-cases.md) innehåller information om alla innehåll som är kopplade till eDiscovery-ärenden i organisationen.

- [Lägg till postlådor OneDrive platser för](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) en lista över användare i ett eDiscovery-lager.
  
## <a name="manage-legal-investigations-with-the-advanced-ediscovery-solution-in-microsoft-365"></a>Hantera juridiska undersökningar med Advanced eDiscovery lösning i Microsoft 365

The Advanced eDiscovery solution in Microsoft 365 builds on the existing eDiscovery and analytics capabilities in Office 365. Den här nya lösningen, som kallas *Advanced eDiscovery,* ger ett end-to-end-arbetsflöde för att bevara, samla in, granska, analysera och exportera innehåll som svarar på organisationens interna och externa undersökningar. Det gör också att juridiska grupper kan hantera hela arbetsflödet för aviseringar om juridiska frågor och kommunicera med dokumenter som är inblandade i ett ärende.

Advanced eDiscovery krävs en E5-prenumeration för din Microsoft 365 eller Office 365 organisation. Mer information om licensiering finns i [Konfigurera Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).

Här är en snabb överblick över det inbyggda arbetsflödet i Advanced eDiscovery. Mer information finns i [Hantera Advanced eDiscovery arbetsflöde.](create-and-manage-advanced-ediscoveryv2-case.md#manage-the-workflow)

- [Skapa ett ärende](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case) för att komma igång.

- [Hantera brevlådor](managing-custodians.md) genom att lägga till dem i ett ärende och sätta ett juridiskt värde på innehåll i postlådan, OneDrive konto och skapa Microsoft Teams de är medlemmar i.

- [Hantera kommunikation med](managing-custodian-communications.md) biblioteks uppringare genom att automatisera processen för att skapa juridiska meddelanden.

- [Indexerade data och](processing-data-for-case.md) korrigera indexeringsfel så att du effektivt kan samla in data för dina undersökningar.

- [Samla in data](collecting-data-for-ediscovery.md) för ett ärende och lägg [till dem i en granskning för](collecting-data-for-ediscovery.md#add-search-results-to-a-review-set) ytterligare undersökning.

- [Visa](view-documents-in-review-set.md) dokument, [frågedata](review-set-search.md) och [tagga](tagging-documents.md) objekt i en granskningsuppsättning.

- [Analysera falldata](analyzing-data-in-review-set.md) med avancerade analysverktyg.

- [Exportera ärendedata](exporting-data-ediscover20.md) för granskning av utomstående jurister.

- [Hantera långvariga jobb i](managing-jobs-ediscovery20.md) Advanced eDiscovery.