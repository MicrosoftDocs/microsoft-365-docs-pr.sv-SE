---
title: Se till att skräppost dirigeras till varje användares skräppostmapp
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 7/16/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur du dirigerar skräppost till mappar för skräppost från användare i Exchange Online Protection.
ms.openlocfilehash: 6d1fd625669e8b638a408b2db1993f45fa653ffb
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42810739"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Se till att skräppost dirigeras till varje användares skräppostmapp

> [!IMPORTANT]
> Det här avsnittet gäller endast För Exchange Online Protection (EOP) kunder som är värdar för postlådor lokalt i en hybriddistribution. Exchange Online-kunder vars postlådor är fullt värd i Office 365 behöver inte köra dessa kommandon.

Standardåtgärden mot skräppost för EOP-kunder är att flytta skräppost till mottagarnas skräppostmapp. För att den här åtgärden ska fungera med lokala postlådor måste du konfigurera Exchange-regler för e-postflöde (kallas även transportregler) på dina lokala Edge- eller Hub-servrar för att identifiera skräpposthuvuden som lagts till av EOP. Dessa regler för e-postflöde anger den scl-nivå (Spam Confidence Level) som används av egenskapen SclJunkThreshold för cmdlet Set-OrganizationConfig för att flytta skräppost till mappen Skräppost i varje postlåda.

### <a name="to-add-mail-flow-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a>Så här lägger du till regler för e-postflöde för att säkerställa att skräppost flyttas till mappen Skräppost med hjälp av Windows PowerShell

1. Öppna Exchange Management Shell för din lokala Exchange-server. Mer information om hur du öppnar Exchange Management Shell i din lokala Exchange-organisation finns **i Öppna Shell**.

2. Kör följande kommando för att dirigera innehållsfiltrerade skräppostmeddelanden till mappen Skräppost:

   ```Powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
   ```

   Där _NameForRule_ är namnet på den nya regeln, till exempel JunkContentFilteredMail.

3. Kör följande kommando för att dirigera meddelanden som markerats som skräppost innan innehållsfiltret når mappen Skräppost:

   ```Powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
   ```

   Där _NameForRule_ är namnet på den nya regeln, till exempel JunkMailBeforeReachingContentFilter.

4. Kör följande kommando för att säkerställa att meddelanden från avsändare i en blockeringslista i skräppostfilterprincipen, till exempel **blockeringslistan av avsändare,** dirigeras till mappen Skräppost:

   ```Powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
   ```

   Där _NameForRule_ är namnet på den nya regeln, till exempel JunkMailInSenderBlockList.

Om du inte vill använda åtgärden **Flytta meddelande till skräppostmapp** kan du välja en annan åtgärd i innehållsfilterprinciperna i administrationscentret för Exchange. Mer information finns i [Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md). Mer information om dessa fält i meddelandehuvudet finns i [Rubriker för skräppostmeddelanden](anti-spam-message-headers.md).

> [!TIP]
> Om du inte vill använda åtgärden **Flytta meddelande till skräppostmapp** kan du välja en annan åtgärd i innehållsfilterprinciperna i administrationscentret för Exchange. Mer information finns i [Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md). Mer information om dessa fält i meddelandehuvudet finns i [Rubriker för skräppostmeddelanden](anti-spam-message-headers.md).

## <a name="see-also"></a>Se även

[Ny-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)
