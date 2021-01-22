---
title: Hantera säkra länkar
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du hanterar säkra länkar för att skydda företaget från skadliga webbplatser.
ms.openlocfilehash: 1f5b3f61871e8d231029156631031dbb0ef4f2f5
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928028"
---
# <a name="manage-safe-links"></a>Hantera säkra länkar

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft Defender för Office 365 , som tidigare hette Microsoft 365 ATP eller Advanced Threat Protection, hjälper dig att skydda företaget mot skadliga webbplatser när personer klickar på länkar i Office-program.

## <a name="try-it"></a>Prova!

1. Gå till [administrationscentret](https://admin.microsoft.com)och välj **Installation.**
1. Rulla nedåt för **att öka skyddet mot avancerade hot.** Välj **Visa,** **Hantera** och sedan **ATP – säkra länkar.**
1. Under **Principer som gäller för hela** organisationen väljer du **Standardprincip** och sedan **redigeringsikonen.**
1. Ange en URL som du vill blockera.
1. Välj **Använd säkra länkar i Office-appar, Office för iOS och Android.** välj **Spåra inte när användare klickar på säkra länkar**; och välj **Låt inte användare klicka igenom säkra länkar till den ursprungliga URL:en.** De kanske redan är markerade om du har angett standardprincipen. Välj **Spara**.
1. Under **Principer som gäller för specifika mottagare** väljer du **regeln** Rekommenderade säkra länkar och sedan **ikonen** Redigera.
1. Välj **inställningar,** rulla nedåt, ange den URL-adress som du inte vill kontrollera och välj sedan ikonen **Lägg till.**
1. Välj **det du** vill använda på och välj sedan domännamnet. Markera alla ytterligare domäner som du vill att regeln ska tillämpas på. Välj **Lägg till,** **OK** och sedan **Spara.**

ATP – säkra länkar är nu konfigurerade. Det kan ta upp till 30 minuter innan ändringarna verkställs.

När en användare får ett e-postmeddelande med länkar genomsöks länkarna. Om länkarna anses vara säkra går de att klicka på. Men om länken finns med i listan över blockerade ser användarna ett meddelande om att den har blockerats.