---
title: Microsoft 365 Yammer Enterprise Access-kontroller
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
description: Den här artikeln innehåller en kort sammanfattning av företags åtkomst kontroller för Yammer i produktions miljön.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b7e1ceae1b7ddda4c2eac96cd581a612768f1461
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332670"
---
# <a name="yammer-enterprise-access-controls"></a>Kontroller för Yammer Enterprise Access 

Fysisk och logisk åtkomst till Yammer-produktions miljön begränsas till en mindre uppsättning människor (infrastruktur och tjänster). Precis som med andra Microsoft 365-tekniker har Yammer-tekniker ingen ständig åtkomst till kunddata. Åtkomst måste begäras med hjälp av ett godkännande baserat inloggnings system som liknar låsning med ett begränsat antal god kännare. God kännare verifiera begäran (till exempel kontrollerar de om begäran är legitim baserat på behov, affärs fråga, tid etc.) och Godkänn eller avvisa begäran. Om begäran godkänns ges JIT-åtkomst under en definierad och begränsad tid. När åtkomst tiden har överskridits förfaller Access automatiskt.

Precis som med andra Microsoft 365-tjänster använder multi-factority all åtkomst till produktions miljön för Yammer. Alla Access-och kommando historik skrivs till en användare, och loggas och granskas regelbundet av Yammer-säkerhetsgruppen.

Mer information om Yammer-administration och-hantering finns i [Hjälp för Yammer-administratörer](https://docs.microsoft.com/yammer/yammer-landing-page).