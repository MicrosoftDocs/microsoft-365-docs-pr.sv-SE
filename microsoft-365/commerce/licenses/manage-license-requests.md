---
title: Hantera licens förfrågningar
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- commerce
ms.custom: MACBillingLicensesRequests
search.appverid:
- MET150
description: Lär dig att granska och godkänna eller avvisa licens förfrågningar från användare för din Microsoft 365 för företag-prenumeration.
ms.date: 08/07/2020
ms.openlocfilehash: cbcdc5550d404278832cc702560ac55f6ace8a44
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597664"
---
# <a name="manage-license-requests"></a>Hantera licens förfrågningar

> [!NOTE]
> Informationen i den här artikeln gäller endast självbetjänings köps produkter. Mer information finns i [vanliga frågor och svar om inköp](../subscriptions/self-service-purchase-faq.md).

Om du inaktiverar självbetjänings köp i din organisation kan du använda licens förfrågningar för att hantera processen för licenser för användare. När en användare försöker göra en självbetjänings köp för en produkt som du har blockerat kan de skicka en begäran om en licens till dig, administratören. När de gör en begäran kan de lägga till namnen på andra användare som också behöver licenser för produkten.

> [!NOTE]
> Om du spärrar användare från att göra självbetjänings köp skickar Microsoft inte ut reklam för e-post. Om de använder en utvärderings version av en produkt visas inga uppmaningar att köpa den. Mer information finns i [Hantera självbetjänings köp (administratör)](../subscriptions/manage-self-service-purchases-admins.md).

För att se och hantera licens förfrågningar använder administratören fliken **begär Anden** på sidan **licensiering** . I listan visas namnet på den efterfrågade produkten, namnet på den person som begär en licens, datum och status för begäran. Administratörer kan filtrera listan för att Visa begär Anden som väntar eller slutförts. Förfrågningar sparas i 30 dagar.

## <a name="before-you-begin"></a>Innan du börjar

Du måste vara global administratör för att utföra åtgärderna i den här artikeln. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).

## <a name="use-your-own-request-process"></a>Använd din egen begäran

Om din organisation har en egen förfrågnings process kan du använda den istället. Du skapar ett meddelande som visas för användarna när de efterfrågar en licens.

> [!IMPORTANT]
> Om du använder din egen begär ande process visas inga förfrågningar på fliken **begär** Anden. befintliga förfrågningar från innan du lade till ditt meddelande visas tills du godkänner eller tackar nej.

1. I administrations centret går du till sidan **fakturerings**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenser</a> och väljer sedan fliken **begär Anden** .
2. Välj **Använd din befintliga förfrågan i stället**.
3. I den högra rutan, i rutan **meddelande** , skriver du det meddelande som du vill att användarna ska se när de efterfrågar en licens. Om du även vill inkludera en länk till din organisations princip eller annan dokumentation anger du URL-adressen i text rutan **länk till Documentation (valfritt)** .
4. Välj **Spara**.

När du går tillbaka till listan **förfrågningar** ser du det meddelande **som du använder för din egen licens förfrågnings process**. Om du vill göra ändringar i meddelandet som skickas till användarna väljer du **Använd din befintliga förfrågan i stället**.

## <a name="stop-using-your-own-request-process"></a>Sluta använda din egen begäran

1. I administrations centret går du till sidan **fakturerings**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenser</a> och väljer sedan fliken **begär Anden** .
2. Välj **Använd din befintliga förfrågan i stället**.
3. I den högra rutan avmarkerar du kryss rutan **Använd min organisations begärans process** .
4. Välj **Spara**.

## <a name="approve-or-deny-a-license-request"></a>Godkänna eller neka en licens ansökan

1. I administrations centret går du till sidan **fakturerings**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenser</a> och väljer sedan fliken **begär Anden** .
2. Markera raden som innehåller den begäran du vill granska. I det högra fönstret visas information om vilka användare som har licenser för produkten.
3. Om du vill neka hela begäran väljer du **Godkänn inte**och väljer **Godkänn inte**i dialog rutan.
4. För att neka vissa användare åt begäran, men Godkänn andra, Välj X efter namnet på de användare som du vill ta bort. Deras namn flyttas under **tilldela inte dessa användare**.
5. Om du har fler än en produkt väljer du den du vill använda för att tilldela licenser under **Välj en produkt**.
6. För att neka användare åtkomst till vissa appar och tjänster expanderar du **Aktivera och inaktivera program och tjänster**och avmarkerar sedan kryss rutorna för de som du vill undanta.
7. Skriv ett valfritt meddelande i text rutan längst ned i fönstret.
8. Välj **Godkänn**när du är klar. I det högra fönstret visas information om begäran.
9. Stänga fönstret till höger.
    Användare får ett e-postmeddelande om att begäran har godkänts eller nekats.

## <a name="related-content"></a>Relaterat innehåll

[Tilldela licenser till användare](../../admin/manage/assign-licenses-to-users.md) (artikel) \
[Flytta användare till en annan prenumeration](../subscriptions/move-users-different-subscription.md) (artikel) \
[Köpa eller ta bort prenumerations licenser](buy-licenses.md) (artikel)