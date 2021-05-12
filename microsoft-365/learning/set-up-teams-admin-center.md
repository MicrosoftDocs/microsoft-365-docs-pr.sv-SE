---
title: Konfigurera Microsoft Viva Learning (förhandsversion) i administrationscentret för Teams
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/12/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Lär dig hur du konfigurerar Microsoft Viva Learning (förhandsversion) i administrationscentret för Teams.
ms.openlocfilehash: 40e659796b22097f42515c0cbb704bdaa4ccc972
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333524"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a>Konfigurera Microsoft Viva Learning (förhandsversion) i administrationscentret för Teams

> [!NOTE]
> Informationen i den här artikeln gäller en förhandsversion av en produkt som kan komma att ändras väsentligt innan den släpps till kommersiellt bruk. 

Teams-administratören installerar Viva Learning (förhandsversion) och tillämpar behörighetsprinciper via administrationscentret för Teams.

## <a name="manage-settings-for-viva-learning-preview"></a>Hantera inställningar för Viva Learning (förhandsversion)

Du måste vara administratör i administrationscentret för Teams för att utföra de här uppgifterna.

Gör Viva Learning (förhandsversion) tillgängligt för användare i organisationen genom att följa de här stegen:

1. I det vänstra navigeringsfältet i administrationscentret för Teams går du till  >  **Teams-appar Hantera appar**.

   ![Vänster navigering i administrationscentret för Teams med teams-appar och avsnittet Hantera appar.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. På sidan **Hantera appar** skriver du *Viva learning* i sökrutan och väljer sedan **Viva Learning (förhandsversion).**

   ![Sidan Hantera appar i administrationscentret för Teams med sökrutan.](../media/learning/learning-app-teams-manage-apps-page.png)

3. På **sidan Viva Learning (förhandsversion):**

   1. Under **Status** väljer du **Tillåts** att aktivera Viva Learning (förhandsversion).

   2. På fliken **Inställningar,** under **Appinställningar, går** du till administrationscentret för Microsoft 365 för att [konfigurera källor för utbildningsinnehåll.](content-sources-365-admin-center.md)

   ![Sidan Utbildning i administrationscentret för Teams som visar avsnittet Status och Appinställningar.](../media/learning/learning-app-teams-learning-page.png)

4. När **du har hanterat appinställningarna** går du till Behörighetsprinciper och Konfigurationsprinciper för att ge behörighet till anställda som bör ha tillgång till Viva Learning (förhandsversion) som en del av organisationens deltagande i förhandsgranskningen.  

> [!NOTE]
>  Om din organisation har Ring 4.0 som en del av Teams TAP100-program kan du behöva aktivera godkända användare i Ring 3.0 för att få åtkomst till Viva Learning (förhandsversion). <br><br>Som en del av förhandsversionen släpps Viva Learning (förhandsversion) i Ring 3.0. Om din organisation har Ring 4.0 ser du inte Viva Learning (förhandsversion) på **sidan Hantera** appar. Om du vill testa appen måste du skapa en behörighetsprincip för anpassade appar, ange Tillåt alla appar och tilldela den till Ring 3.0-godkända användare. <br><br>   ![TAP-AppsPermission-Plcy-sidan med Tillåt alla appar markerade.](../media/learning/learning-app-tap-appspermission-plcy.png)

## <a name="next-step"></a>Nästa steg

[Konfigurera utbildningsinnehållskällor för Viva Learning (förhandsversion) i administrationscentret för Microsoft 365](content-sources-365-admin-center.md)