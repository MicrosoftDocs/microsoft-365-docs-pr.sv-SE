---
title: Hantera betalningsmetoder
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: Lär dig hur du hanterar dina betalnings metoder i administrations centret för Microsoft 365.
ms.date: ''
ms.openlocfilehash: 81c7509fb2f3be982890ec6b68dafb83ff0c1876
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324240"
---
# <a name="manage-payment-methods"></a>Hantera betalningsmetoder

::: moniker range="o365-21vianet"
> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).
::: moniker-end

När du köper affärs produkter och-tjänster från Microsoft kan du använda en befintlig betalnings metod eller lägga till en ny. Du kan använda ett kredit-eller betalkort eller bank konto för att betala för det du köper.

Om ditt företags konto har en fakturerings profil och du är ägare till en fakturerings profil eller en fakturerings profil, kan du använda den betalnings profil som du har fått av ett kredit kort eller en faktura betalning för att göra inköp eller betala räkningar. Om du är fakturerings faktura chef kan du bara använda en fakturerings profil för att betala räkningar. Mer information om fakturerings profiler och-roller finns i [hantera fakturerings profiler](manage-billing-profiles.md).

Om ditt företags konto inte har någon fakturerings profil kan en global eller fakturerings administratör hantera och använda eventuella bank konton som läggs till i företags kontot. Men du kan bara hantera eller använda kredit kort som du lägger till.

> [!NOTE]
> Alternativet att betala med ett bank konto är inte tillgängligt i vissa länder eller regioner.
>
> Du måste använda en betalnings metod som utfärdats från samma land som din klient organisation.

## <a name="before-you-begin"></a>Innan du börjar

Du måste vara global eller fakturerings administratör för att kunna utföra åtgärderna i den här artikeln. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).

## <a name="add-a-payment-method"></a>Lägg till en betalningsmetod

Om du lägger till en betalnings metod kopplas inga abonnemang till den. Om du vill tilldela ett enda abonnemang till betalnings metoden läser du [ändra en betalnings metod för en enda prenumeration](#change-a-payment-method-for-a-single-subscription). Om du vill ersätta alla abonnemang som använder en annan betalnings metod med den nya, se [ersätta en betalnings metod](#replace-a-payment-method).

1. I administrations centret går du till **Billing**  >  sidan betalnings metoder för **& betalning**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> .
2. Välj **Lägg till en betalningsmetod**.
3. På sidan **Betalningsmetoder** väljer du ett betalningssätt i listrutan. 
4. Ange informationen för det nya kortet eller bank kontot och välj sedan **Lägg till**.

## <a name="update-payment-method-details"></a>Uppdatera betalnings metod uppgifter

Du kan ändra namnet på kredit-eller betalkort, fakturerings adress eller utgångs datum för en befintlig betalnings metod. Men du kan inte ändra kort eller konto nummer. Om konto numret har ändrats [ersätter du det med en annan betalnings metod](#replace-a-payment-method)och [tar sedan bort den gamla](#delete-a-payment-method).

1. I administrations centret går du till **Billing**  >  sidan betalnings metoder för **& betalning**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> .
2. Välj raden för betalnings metoden att uppdatera. I det högra fönstret väljer du **Redigera**.
3. Uppdatera din betalnings metod, inklusive namnet på kredit-eller betalkort, fakturerings adress eller utgångs datum och välj sedan **Spara**.

## <a name="replace-a-payment-method"></a>Ersätta en betalnings metod

När du ersätter en betalnings metod ersätter du den för alla abonnemang och fakturerings profiler som använder samma betalnings metod. Att ersätta en betalnings metod tar inte bort den befintliga betalnings metoden. Det är fortfarande tillgängligt för dig att välja och använda för andra prenumerationer och fakturerings profiler.

Om du vill ändra betalnings metod för en enda prenumeration läser du [ändra en betalnings metod för en enda prenumeration](#change-a-payment-method-for-a-single-subscription).

1. I administrations centret går du till **Billing**  >  sidan betalnings metoder för **& betalning**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> .
2. Välj raden för betalnings metoden som du vill ersätta. I det högra fönstret visas alla fakturerings profiler och enskilda abonnemang med den valda betalnings metoden.
3. I det högra fönstret väljer du **Ersätt betalnings metod för alla objekt**.
4. Om du vill använda en befintlig betalnings metod väljer du en i list rutan och väljer sedan **Ersätt**.
    > [!NOTE]
    > Om du har abonnemang kopplade till en fakturerings profil kan du bara använda ett kredit-eller betalkort för att betala för dem. Om du har bank konton som visas på sidan **betalnings sätt** kan de inte väljas i list rutan.
5. Om du vill lägga till en ny betalnings metod väljer du **Lägg till betalnings metod**.
6. Ange konto informationen i fönstret **Lägg till betalnings metod** och välj sedan **Spara**. Du måste använda en betalnings metod från samma land som din klient organisation.
7. Den nya betalnings metoden har redan valts i list rutan. Välj **Ersätt**.

## <a name="change-a-payment-method-for-a-single-subscription"></a>Ändra betalnings metod för ett enda abonnemang

Du kan ändra betalnings metod som används för att betala för en enda prenumeration.

1. Gå till sidan fakturering i administrations centret **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> .
2. På fliken **produkter** letar du upp den prenumeration som du vill betala för med den alternativa betalnings metoden.
3. Välj **fler åtgärder** (tre punkter) och välj sedan **Ersätt betalnings metod**.
4. I rutan **Ersätt betalnings metod** i list rutan väljer du en alternativ betalnings metod eller väljer att lägga till en betalnings metod.
5. Om du lägger till en betalnings metod anger du kort-eller konto informationen och väljer sedan **Spara**.
6. Kontrol lera att den valda betalnings metoden stämmer och välj sedan **Ersätt**.

## <a name="delete-a-payment-method"></a>Ta bort en betalnings metod

Du kan bara ta bort en betalnings metod som inte är kopplad till ett abonnemang eller en fakturerings profil. Detta gäller alla abonnemang oavsett deras status.

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a>Ta bort en betalnings metod utan några prenumerationer eller betalnings profiler kopplade

Om en betalnings metod inte är kopplad till några abonnemang eller fakturerings profiler kan du ta bort den omedelbart.

1. I administrations centret går du till **Billing**  >  sidan betalnings metoder för **& betalning**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> .
2. Klicka på de tre punkterna och välj sedan **ta bort**.
3. Välj **ta bort**längst ned till höger.

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>Ta bort en betalnings metod med abonnemang eller fakturerings profiler kopplade

Om en betalnings metod är kopplad till alla abonnemang eller fakturerings profiler ska du först ersätta den med en befintlig betalnings metod eller lägga till en ny och sedan ta bort den gamla betalnings metoden.

1. I administrations centret går du till **Billing**  >  sidan betalnings metoder för **& betalning**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> .
2. Markera raden för den betalnings metod som du vill ta bort. I det högra fönstret visas befintliga abonnemang med denna betalnings metod.
3. Välj **ta bort**i den högra rutan.
4. Om du vill använda en befintlig betalnings metod väljer du en i list rutan, väljer **Nästa**och väljer sedan **ta bort**.
    > [!NOTE]
    > Om du har abonnemang kopplade till en fakturerings profil kan du bara använda kredit kort för att betala för dem. Om du har bank konton som visas på sidan **betalnings sätt** är de inte tillgängliga att välja i list rutan.
5. Om du vill lägga till en ny betalnings metod väljer du **Lägg till betalnings metod**.
6. Välj den betalnings metod som du vill lägga till, ange konto informationen och välj sedan **Spara**.
7. Den nya betalnings metoden har redan valts i list rutan. Välj **Nästa**.
8. Välj **ta bort**.

## <a name="troubleshoot-payment-methods"></a>Felsöka betalningsmetod

|**Problem**|**Felsökningssteg**|
|:----------|:-----|
|**Jag får ett fel meddelande som säger "webbläsaren är för tillfället inställd på att blockera cookies."** |Konfigurera din webbläsare så att den tillåter cookies från tredje part och försök igen. |
|**Mitt kredit-eller betalkort nekades.** |Om du betalar med kredit eller betalkort, och ditt kort nekas, får du ett e-postmeddelande om att Microsoft inte kunde hantera betalningen. Dubbel kontrol lera att kort numret, &mdash; utgångs datumet, namnet på kortet och adressen, inklusive ort, delstat och post nummer &mdash; visas exakt som på kortet och på ditt konto utdrag. Du kan uppdatera kort informationen och omedelbart skicka betalningen med hjälp av länken **likvidera** i avsnittet **fakturering** på sidan abonnemangs information. Om du vill ha mer information kan du läsa [om mitt kredit kort nekades och min betalning förfaller.](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)  <br/><br/>  Om meddelandet om nekat kort fortfarande visas kontaktar du banken. Det är möjligt att ditt kort inte är aktivt. Om du har tagit emot kortet i e-postmeddelandet med ett uppdaterat utgångs datum kontrollerar du att det är aktiverat. Din bank kan också berätta om ditt kort inte är godkänt för online-, internationella eller återkommande transaktioner. |
|**Jag vill uppdatera ett kort-eller bankkonto nummer.** |Du kan inte ändra kort-eller konto numret på en befintlig betalnings metod. Om ditt kort eller konto nummer har ändrats [ersätter du det med en annan betalnings metod](#replace-a-payment-method), som flyttar alla aktiva abonnemang från betalnings metoden till den nya och [tar sedan bort den gamla betalnings metoden](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached). |
|**Jag har bara ett kort eller bank konto på mitt konto och jag vill ta bort det.** |Om du bara har en betalnings metod måste du [ersätta den med en ny betalnings metod](#replace-a-payment-method) innan du kan ta bort den. |
|**Jag kan inte lägga till mitt kort eller bank konto.**  |Du måste använda en betalnings metod som utfärdats från samma land som din klient organisation. Om du har problem med att skriva in kort-eller bank konto information kan du [kontakta supporten](../../admin/contact-support-for-business-products.md). |

## <a name="related-content"></a>Relaterat innehåll

[Betala för ditt företags abonnemang](pay-for-your-subscription.md) (artikel) \
[Hantera betalnings profiler](manage-billing-profiles.md) (artikel) \
[Ändra fakturerings frekvensen](change-payment-frequency.md) (artikel)