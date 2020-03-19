---
title: Konfigurera policyerna mot skräppost
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 6/9/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 31279431-828d-48bd-b979-20b6de15fa4a
ms.collection:
- M365-security-compliance
description: Skräppostfiltrering aktiveras automatiskt i hela företaget via standardpolicyerna mot skräppost (anslutningsfilter, skräppostfilter och utgående skräppost). Som administratör kan du visa och redigera, men inte ta bort, standardpolicyerna mot skräppost så att de är anpassade för att bäst uppfylla organisationens behov. För större granularitet kan du också skapa anpassade principer och tillämpa dem på angivna användare, grupper eller domäner i organisationen. Som standard har anpassade principer företräde framför standardprincipen, men du kan ändra prioriteten för dina principer.
ms.openlocfilehash: 2ee5833bf476123a84411a7ad645b9f8c5d0b2b8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42805658"
---
# <a name="configure-the-anti-spam-policies"></a>Konfigurera policyerna mot skräppost

Skräppostfiltrering aktiveras automatiskt i hela företaget via standardpolicyerna mot skräppost (anslutningsfilter, skräppostfilter och utgående skräppost). Som administratör kan du visa och redigera, men inte ta bort, standardpolicyerna mot skräppost så att de är anpassade för att bäst uppfylla organisationens behov. För större granularitet kan du också skapa anpassade principer och tillämpa dem på angivna användare, grupper eller domäner i organisationen. Som standard har anpassade principer företräde framför standardprincipen, men du kan ändra prioriteten för dina principer. 
  
Mer information om hur du konfigurerar dina policyer mot skräppost finns i följande avsnitt:
  
[Konfigurera princip för anslutningsfilter](configure-the-connection-filter-policy.md)
  
[Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md)
  
> [!IMPORTANT]
> För fristående EOP-kunder: Som standard skickar EOP-innehållsfiltren skräppostupptäcktmeddelanden till varje mottagares skräppostmapp. För att säkerställa att åtgärden **Flytta meddelande till skräppost** fungerar med lokala postlådor måste du dock konfigurera två Exchange-regler för e-postflöde (kallas även transportregler) på dina lokala servrar för att identifiera skräpposthuvuden som lagts till av EOP. Mer information finns [i Se till att skräppost dirigeras till varje användares skräppostmapp](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). 
  
[Konfigurera principen för skräppost för utgående](configure-the-outbound-spam-policy.md)
  

