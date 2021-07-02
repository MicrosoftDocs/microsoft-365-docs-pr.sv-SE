---
title: Användning OneDrive Learning verktygskompatibilitet
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Skapa och betygs gradera uppgifter, skapa och hantera kursinnehåll och samarbeta i filer i realtid med den nya appen OneDrive Learning Tools Interoperability App.
ms.openlocfilehash: 0e437ed4b05b9968ee1e853f668787eed5351fb5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53257050"
---
# <a name="use-microsoft-onedrive-lti-with-canvas"></a>Använda Microsoft OneDrive LTI med Canvas

> [!IMPORTANT]
> En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

## <a name="integrate-with-canvas"></a>Integrera med Canvas

Den person som utför den här integrationen bör vara administratör för Canvas och administratör för Microsoft 365 klientorganisationen.

1. Logga in på Microsoft Azure med klientorganisationens administratörskonto. Azure-innehavaradministratören bör också ha rollen Gruppadministratör.

    ![gruppadministratör markerad](../media/lti-media/lti-group-admin.png)

2. Logga in på Microsoft [OneDrive LTI-portalen](https://odltiappnl.azurewebsites.net/admin).

3. Godkänn behörigheterna för att slutföra inloggningen.

    ![acceptera behörigheter](../media/lti-media/lti-permissions.png)

4. Välj **Lägg till LTI-klient.**

     ![lägg till LTI-klient](../media/lti-media/lti-add-tenant.png)

5. Välj **LTI Consumer Platform** som **Canvas** i listrutan.

6. Välj **Arbetsytebas-URL** och välj sedan **Nästa**.

    ![välj Arbetsyta och lägg till bas-URL](../media/lti-media/lti-canvas-base-url.png)

   På nästa skärm visas fält som är konfidentiella.

7. Välj **Nästa** från ?? . KAN GRANSKARE FYLLA I DET TOMMA HÄR?

8. Välj **Nästa** på skärmen som visar information som är konfidentiell.

   Den sista skärmen i Azure-portalen visar nästa steg för att lägga till din Canvas-instans.

9. Kopiera utvecklarnycklarna från den här skärmen. Du kommer att använda när du skapar Canvas-instansen.

## <a name="add-the-canvas-instance"></a>Lägga till Canvas-instansen

1. Avmarkera Administratörsutvecklarenycklar i  >  **Canvas-instansen.**

2. Välj **LTI-nyckel** i listrutan på **Utvecklarnyckel**.

   ![Hämta LTI-utvecklarnycklarna](../media/lti-media/lti-developer-keys.png)

3. Klistra in utvecklarnycklarna här.

     ![Klistra in utvecklarnycklarna](../media/lti-media/lti-developer-keys.png)

   Nyckeln skapas i **AV-läge**

   ![Utvecklarnycklarna som skapats i läget Av](../media/lti-media/lti-copy-developer-keys.png)

4. Kopiera den markerade texten.
    Det här fungerar som klient-ID Microsoft OneDrive LTI-portalen.

5. Klistra in texten i fältet **Klient-ID** i Microsoft OneDrive LTI-portalen och välj **sedan Nästa.**

6. Välj **Spara**.

7. Visa inställningarna genom att välja **Visa LTI-klientorganisation.**
