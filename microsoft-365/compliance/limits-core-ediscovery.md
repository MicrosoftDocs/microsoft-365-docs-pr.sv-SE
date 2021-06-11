---
title: Begränsningar i grundläggande e-dataidentifieringsfall
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: I den här artikeln beskrivs gränserna för grundläggande e-dataidentifieringsfall i Microsoft 365.
ms.openlocfilehash: e7b1013abd9fd94748baf3b83dd04efbc3831a1d
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311430"
---
# <a name="limits-in-core-ediscovery"></a>Begränsningar i bas-e-dataidentifiering

I följande tabell finns begränsningar för grundläggande eDiscovery-ärenden och kvarstående information som är kopplade till ett grundläggande eDiscovery-ärende. Mer information om bas-eDiscovery finns i [Översikt över bas-eDiscovery.](./get-started-core-ediscovery.md)
    
  | Beskrivning av gräns | Gräns |
  |:-----|:-----|
  |Maximalt antal ärenden för en organisation.  <br/> |Ingen gräns  <br/> |
  |Maximalt antal spärrade ärende för en organisation.  <br/> |10 000  <br/> |
  |Maximalt antal postlådor för ett enskilt ärende håll. Den här gränsen omfattar totalt antal användarpostlådor och postlådorna som är kopplade Microsoft 365 grupper, Microsoft Teams och Yammer grupper.  <br/> |1 000  <br/> |
  |Maximalt antal webbplatser i ett enskilt ärende. Den här gränsen omfattar det totala antalet OneDrive för företag, SharePoint webbplatser och webbplatser som är kopplade till grupper Microsoft 365, Microsoft Teams och Yammer grupper.  <br/> |100  <br/> |
  |Maximalt antal ärenden som visas på eDiscovery-huvudsidan och det maximala antalet objekt som visas på flikarna Spärrar, Sökningar och Exportera i ett ärende. <sup>1</sup> |1 000|
  |||

   > [!NOTE]
   > <sup>1</sup> Om du vill visa en lista över mer än 1 000 ärenden, som sätts i, sätts i sökningar eller exporteras kan du använda motsvarande PowerShell-Office 365-cmdlets för säkerhet och &- och efterlevnad:
   > 
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)

Mer information om begränsningar relaterade till sökningar och exporter som är kopplade till en bas-e-dataidentifieringsfall finns i Begränsningar för innehållssökning och [bas-eDiscovery.](limits-for-content-search.md)