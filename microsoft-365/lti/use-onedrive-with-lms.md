---
title: Använda utbildningskompatibilitet med OneDrive-utbildningsverktyg
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
description: Skapa och betyg sätt uppgifter, skapa och hantera kursinnehåll och samarbeta i filer i realtid med den nya appen OneDrive Learning Tools Interoperability.
ms.openlocfilehash: 97baf3e524e483e879d00f5e0c8495b450e13c92
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327804"
---
# <a name="use-microsoft-onedrive-with-your-learning-management-system"></a>Använda Microsoft OneDrive med ditt system för utbildningshantering

> [!IMPORTANT]
> En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

Lär dig fördelarna med att använda Microsoft OneDrive med ditt LMS (Learning Management System).

**Tar Microsoft Office 365 direkt till dina arbetsflöden**

Appen Microsoft OneDrive Learning Tools Interoperability (LTI) integreras med LMS så att Microsoft OneDrive och Microsoft Office 365 kan integreras direkt i dina viktigaste arbetsflöden som inkluderar:

- Bifoga resurser och ordna innehåll.
- Starta samarbetsdokument.
- Skapa och betygsätta uppgifter.

**Säker och helt kompatibel med de senaste LTI-standarderna**

Microsoft OneDrive LTI-appen är kompatibel med LTI 1.3 och LTI Advantage. Den här fördelen ger en mycket säker och tätt integrerad användarupplevelse.

**Modern och rik användarupplevelse**

Med Microsoft OneDrive LTI-appen får du det bästa från Microsoft direkt i LMS-upplevelsen. Vi förbättrar den befintliga Office 365-integreringen i LMS genom att tillhandahålla en modernare användarupplevelse, komplett med en ny och utökad Filväljare i Microsoft OneDrive och fler redigeringsupplevelser för Office-filer. Microsoft kommer även att äga hela Microsoft OneDrive LTI-appen från och med nu, vilket innebär att du alltid får det senaste och bästa från Microsoft automatiskt.

Med Microsoft OneDrive LTI-appen kan du:

- Bifoga Office 365-filer, inklusive Word-dokument, PowerPoint-presentationer och Excel från RTF-redigeraren.

- Distribuera Office 365-molnuppgifter.

- Visa och ordna dina personliga filer och kurs i Microsoft OneDrive-filer.

- Skapa samarbeten där kursmedlemmarna kan arbeta tillsammans med delade dokument i realtid.

- Få åtkomst till flera Microsoft OneDrive-konton, inklusive personliga konton och skolkonton.

- Integrera Office 365-filer med kursmodulerna.

- Använd ditt Microsoft-konto för enkel inloggning med ditt LMS.

## <a name="integrate-with-canvas"></a>Integrera med Canvas

Den person som utför den här integrationen bör vara administratör för Canvas och administratör för Microsoft 365-klientorganisationen.

1. Logga in på Microsoft Azure-portalen med klientorganisationens administratörskonto. Azure-innehavaradministratören bör också ha rollen Gruppadministratör.

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
    Det här fungerar som klient-ID på Microsoft OneDrive LTI-portalen.

5. Klistra in texten i fältet **Klient-ID** i Microsoft OneDrive LTI-portalen och välj **sedan Nästa.**

6. Välj **Spara**.

7. Visa inställningarna genom att välja **Visa LTI-klientorganisation.**
