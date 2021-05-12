---
title: Hantera licensbegäranden
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- MACBillingLicensesRequests
- AdminSurgePortfolio
- commerce_licensing
search.appverid: MET150
description: Läs om hur du granskar och godkänner eller nekar licensbegäranden från användare för Microsoft 365 för företag-prenumerationen.
ms.date: 08/07/2020
ms.openlocfilehash: 06ee210b39c19c1f2c8a2041c463568e55001b6e
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331556"
---
# <a name="manage-license-requests"></a>Hantera licensbegäranden

> [!NOTE]
> Informationen i den här artikeln gäller endast självbetjäningsprodukter som köpts. Mer information finns i Vanliga frågor [och svar om självbetjäning för köp.](../subscriptions/self-service-purchase-faq.md)

Om du inaktiverar självbetjäning för köp i organisationen kan du använda licensförfrågningar för att hantera licensbegäran för användarna. När en användare försöker göra ett självbetjäningsköp för en produkt som du har blockerat kan han/hon skicka en begäran om en licens till dig som administratör. När de gör en begäran kan de lägga till namnen på andra användare som också behöver licenser för produkten.

> [!NOTE]
> Om du blockerar användare från att göra köp via självbetjäning skickar Microsoft inte marknadsföringsmeddelanden till dem. Om de använder en utvärderingsversion av en produkt ser de heller inte uppmaningarna att köpa den. Mer information finns i [Hantera självbetjäning för köp (administratör)](../subscriptions/manage-self-service-purchases-admins.md).

För att visa och hantera licensbegäranden använder administratören **fliken** Begäranden på **sidan** Licensiering. Listan visar namnet på den produkt som begärs, namnet på den person som begär en licens, begärt datum och status för begäran. Administratörer kan filtrera listan för att visa väntande eller slutförda begäranden. Begäranden hålls i 30 dagar.

## <a name="before-you-begin"></a>Innan du börjar

Du måste vara global administratör för att utföra uppgifterna i den här artikeln. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).

## <a name="use-your-own-request-process"></a>Använd din egen process för förfrågan

Om din organisation har en egen process för begäran kan du använda den i stället. Du skapar ett meddelande som visas för användarna när de begär en licens.

> [!IMPORTANT]
> Om du använder en egen begärandeprocess visas inga begäranden på **fliken Begäranden.** Befintliga förfrågningar från innan du lagt till meddelandet fortsätter att visas tills du godkänner eller avböjer dem.

1. I administrationscentret går du till sidan  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Faktureringslicenser</a> och väljer sedan **fliken Begäranden.**
2. Välj **Använd din befintliga begärandeprocess i stället**.
3. I det högra fönstret, i rutan **Meddelande,** skriver du det meddelande som du vill att användare ska se när de begär en licens. Om du även vill ta med en länk till organisationens policy eller annan dokumentation anger du URL-adressen i textrutan **Länka** till dokumentation (valfritt).
4. Välj **Spara**.

När du återgår **till listan** Begäranden visas meddelandet Du använder din egen process **för licensbegäran.** Om du vill ändra meddelandet som skickas till användarna väljer du Använd **din befintliga begäran i stället.**

## <a name="stop-using-your-own-request-process"></a>Sluta använda din egen process för begäran

1. I administrationscentret går du till sidan  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Faktureringslicenser</a> och väljer sedan **fliken Begäranden.**
2. Välj **Använd din befintliga begärandeprocess i stället**.
3. I det högra fönstret avmarkerar **du kryssrutan Använd organisationens** begärandeprocess.
4. Välj **Spara**.

## <a name="approve-or-deny-a-license-request"></a>Godkänna eller neka en licensbegäran

1. I administrationscentret går du till sidan  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Faktureringslicenser</a> och väljer sedan **fliken Begäranden.**
2. Markera raden som innehåller den begäran du vill granska. I fönstret till höger visas information om vilka användare som vill ha licenser för produkten.
3. Om du vill neka hela begäran **väljer du Godkänn inte** och i dialogrutan väljer du Godkänn **inte.**
4. Om du vill neka vissa användare för begäran, men godkänna andra, väljer du X vid namnet på de användare som du vill ta bort. Deras namn flyttas under **Tilldela inte till dessa användare.**
5. Om du har fler än en produkt **väljer** du den produkt som du vill använda för att tilldela licenser för under Välj en produkt.
6. Om du vill neka användare åtkomst till vissa appar och tjänster expanderar du Aktivera eller inaktivera appar och tjänster och avmarkerar sedan kryssrutorna för de du vill utesluta.
7. Skriv ett meddelande (valfritt) i textrutan längst ned i fönstret.
8. När du är klar väljer du **Godkänn**. I det högra fönstret visas information om begäran.
9. Stäng det högra fönstret.
    Användarna får ett e-postmeddelande om att begäran har godkänts eller nekats.

## <a name="related-content"></a>Relaterat innehåll

[Tilldela licenser till användare](../../admin/manage/assign-licenses-to-users.md) (artikel)\
[Flytta användare till en annan prenumeration](../subscriptions/move-users-different-subscription.md) (artikel)\
[Köpa eller ta bort prenumerationslicenser](buy-licenses.md) (artikel)
