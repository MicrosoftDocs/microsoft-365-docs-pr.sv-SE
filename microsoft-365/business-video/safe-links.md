---
title: Hantera säkra länkar
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du hanterar säkra länkar för att skydda företaget från skadliga webbplatser.
ms.openlocfilehash: ce0c1ba6e4099b6eaf4ec974938170020b8a5892
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580636"
---
# <a name="manage-safe-links"></a>Hantera säkra länkar

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft Defender för Office 365 – kallades tidigare Microsoft 365 ATP eller Advanced Threat Protection – för att skydda företaget mot skadliga webbplatser när användare klickar på länkar i Office-appar.

## <a name="try-it"></a>Prova!

1. Gå till [administrationscentret](https://admin.microsoft.com)och välj **Konfigurera**.
1. Rulla nedåt till **Öka skyddet mot avancerade hot**. Välj **Visa**, **Hantera** och sedan **ATP – säkra länkar.**
1. Under **Principer som gäller för hela organisationen** väljer du **Standardprincip** och sedan **redigeringsikonen.**
1. Ange en URL-adress som du vill blockera.
1. Välj **Använd säkra länkar i Office-appar, Office för iOS och Android**. välj **Spåra inte när användare klickar på säkra länkar**; och välj **Låt inte användare klicka sig igenom säkra länkar till den ursprungliga URL:en.** De kanske redan är markerade om du har ställt in standardprincipen. Välj **Spara**.
1. Under **Principer som gäller för specifika mottagare** väljer du **Rekommenderad regel för säkra** länkar och sedan **redigeringsikonen.**
1. Välj **inställningar**, rulla nedåt, ange den URL-adress som du inte vill kontrollera och välj sedan ikonen **Lägg till.**
1. Välj **tillämpas på** och välj sedan ditt domännamn. Markera alla ytterligare domäner som du vill att regeln ska tillämpas på. Välj **lägg** till , **OK** och sedan **Spara**.

AtP – säkra länkar är nu konfigurerade. Det kan ta upp till 30 minuter innan ändringarna verkställs.

När en användare får ett e-postmeddelande med länkar genomsöks länkarna. Om länkarna anses vara säkra går de att klicka på. Men om länken finns med i listan över blockerade länkar visas ett meddelande om att länken har blockerats.