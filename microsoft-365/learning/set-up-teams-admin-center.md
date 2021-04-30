---
title: Konfigurera Microsoft Viva Learning (förhandsversion) i Teams administrationscenter
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 04/30/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Lär dig hur du konfigurerar Microsoft Viva Learning (förhandsversion) Teams administrationscentret.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: c1427ae9fceab38046b53b31540e08d726815bda
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52101095"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a>Konfigurera Microsoft Viva Learning (förhandsversion) i Teams administrationscenter

> [!NOTE]
> Informationen i den här artikeln gäller en förhandsversion av en produkt som kan komma att ändras väsentligt innan den släpps till kommersiellt bruk. 

Administratören Teams viva Learning (förhandsversion) och tillämpar behörighetsprinciper via Teams administrationscenter.

## <a name="manage-settings-for-viva-learning-preview"></a>Hantera inställningar för Viva Learning (förhandsversion)

Du måste vara administratör i administrationscentret Teams utföra de här uppgifterna.

Gör Viva Learning (förhandsversion) tillgängligt för användare i organisationen genom att följa de här stegen:

1. I det vänstra navigeringsfältet i Teams administrationscenter går du till Teams   >  **Hantera appar**.

   ![Vänster navigering i Teams administrationscenter som visar Teams program och avsnittet Hantera appar.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. På sidan **Hantera appar** skriver du *Viva learning* i sökrutan och väljer sedan **Viva Learning (förhandsversion).**

   ![Sidan Hantera appar i Teams administrationscenter som visar sökrutan.](../media/learning/learning-app-teams-manage-apps-page.png)

3. På **sidan Viva Learning (förhandsversion):**

   1. Under **Status** väljer du **Tillåts** att aktivera Viva Learning (förhandsversion).

   2. På fliken **Inställningar,** under **Appinställningar,** går du till administrationscentret för Microsoft 365 för [att konfigurera källor för utbildningsinnehåll.](content-sources-365-admin-center.md)

   ![Sidan Utbildning i Teams visar avsnittet Status och Appinställningar.](../media/learning/learning-app-teams-learning-page.png)

4. När **du har hanterat appinställningarna** går du till Behörighetsprinciper och Konfigurationsprinciper för att ge behörighet till anställda som bör ha tillgång till Viva Learning (förhandsversion) som en del av organisationens deltagande i förhandsgranskningen.  

> [!NOTE]
>  Om din organisation har Ring 4.0 som en del av Teams TAP100-programmet kan du behöva aktivera godkända användare i Ring 3.0 för att få åtkomst till Viva Learning (förhandsversion). <br><br>Som en del av förhandsversionen släpps Viva Learning (förhandsversion) i Ring 3.0. Om din organisation har Ring 4.0 ser du inte Viva Learning (förhandsversion) på **sidan Hantera** appar. Om du vill testa appen måste du skapa en behörighetsprincip för anpassade appar, ange Tillåt alla appar och tilldela den till Ring 3.0-godkända användare. <br><br>   ![TAP-AppsPermission-Plcy-sidan med Tillåt alla appar markerade.](../media/learning/learning-app-tap-appspermission-plcy.png)

## <a name="next-step"></a>Nästa steg

[Konfigurera utbildningsinnehållskällor för Viva Learning (förhandsversion) Microsoft 365 administrationscentret](content-sources-365-admin-center.md)