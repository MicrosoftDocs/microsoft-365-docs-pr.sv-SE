---
title: Konfigurera Microsoft Viva Learning (förhandsversion) i Teams administrationscenter
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/24/2021
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
ms.openlocfilehash: a96a2f3ecf7d4e1ee0c136ae155868218f08aaf4
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636140"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a>Konfigurera Microsoft Viva Learning (förhandsversion) i Teams administrationscenter

> [!NOTE]
> Informationen i den här artikeln gäller en förhandsversion av en produkt som kan komma att ändras väsentligt innan den släpps till kommersiellt bruk. 

Administratören Teams viva Learning (förhandsversion) och tillämpar behörighetsprinciper via Teams administrationscenter.

1. För Viva Learning (förhandsversion) måste du först ställa in uppdateringsprincipen i Teams. Mer information finns i Microsoft Teams [förhandsgranskning.](/MicrosoftTeams/public-preview-doc-updates)

    1. Logga in Teams administrationscentret.

    2. Välj **Teams**  >  **Uppdatera principer**.

    3. Välj **Lägg till**. 

    4. Namnge uppdateringsprincipen, lägg till en princip och aktivera Visa **förhandsgranskningsfunktioner.**

2. Administratören måste meddela användarna om principuppdateringen så att de flyttar sin version till den offentliga förhandsversionen för Teams. 

    1. Användarna måste välja sin profilbild > **om**  >  **offentlig förhandsversion**.
   
        ![Övre navigeringsfältet i Teams visar användarens profil](../media/learning/learning-app-select-profile-teams.png)
    
    2. Användarna måste godkänna **villkoren för** den offentliga förhandsversionen.

        ![Växla till offentlig förhandsversion](../media/learning/learning-app-switch-to-public-preview.png)
 
3. För organisationer som har restriktiva principer och behöver aktivera Viva Learning (förhandsversion) följer du processen i nästa avsnitt.

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
