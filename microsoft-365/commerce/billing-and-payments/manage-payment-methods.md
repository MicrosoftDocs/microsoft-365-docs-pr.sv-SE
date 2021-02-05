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
description: Lär dig hur du hanterar dina betalningsmetoder i administrationscentret för Microsoft 365.
ms.date: ''
ms.openlocfilehash: 6cba5e33ba99212cb6e67a90d1535120ccac3c38
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114855"
---
# <a name="manage-payment-methods"></a>Hantera betalningsmetoder

::: moniker range="o365-21vianet"
> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).
::: moniker-end

När du köper företagsprodukter eller -tjänster från Microsoft kan du använda en befintlig betalningsmetod eller lägga till en ny. Du kan använda ett kreditkort eller bankkort eller bankkonto för att betala för det du köper.

Om ditt företagskonto har en faktureringsprofil och du är faktureringsprofilägare eller faktureringsprofilsdeltagare kan du använda faktureringsprofilen som backas upp med kreditkorts- eller fakturabetalning för att göra inköp eller betala räkningar. Om du är fakturahanterare för fakturering kan du bara använda en faktureringsprofil för att betala fakturor. Mer information om faktureringsprofiler och roller finns i [Hantera faktureringsprofiler.](manage-billing-profiles.md)

Om ditt företagskonto inte har någon faktureringsprofil kan alla globala administratörer eller faktureringsadministratörer hantera och använda alla bankkonton som lagts till i företagskontot. Du kan dock bara hantera eller använda kreditkort som du lägger till.

> [!NOTE]
> Alternativet att betala med ett bankkonto är inte tillgängligt i vissa länder eller regioner.
>
> Du måste använda en betalningsmetod som utfärdats från samma land som din klientorganisation.

## <a name="before-you-begin"></a>Innan du börjar

Du måste vara global administratör eller faktureringsadministratör för att kunna utföra uppgifterna i den här artikeln. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).

## <a name="add-a-payment-method"></a>Lägg till en betalningsmetod

När du lägger till en betalningsmetod kopplas inga prenumerationer till den. Information om hur du tilldelar en enskild prenumeration till betalningsmetoden finns i [Ändra en betalningsmetod för en enskild prenumeration.](#change-a-payment-method-for-a-single-subscription) Om du vill ersätta alla prenumerationer som använder en annan betalningsmetod med den nya, se [Ersätt en betalningsmetod.](#replace-a-payment-method)

1. I administrationscentret går du till sidan  >  **Faktureringsfakturor &**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">betalningssätt.</a>
2. Välj **Lägg till en betalningsmetod**.
3. På sidan **Betalningsmetoder** väljer du ett betalningssätt i listrutan. 
4. Ange information för det nya kortet eller bankkontot och välj sedan Lägg **till.**

## <a name="update-payment-method-details"></a>Uppdatera information om betalningsmetod

Du kan ändra namnet på kreditkortet eller betalkortet, faktureringsadressen eller förfallodatumet för en befintlig betalningsmetod. Du kan dock inte ändra kort- eller kontonumret. Om kontonumret har ändrats [ersätter du det med en annan betalningsmetod](#replace-a-payment-method)och tar sedan bort den [gamla.](#delete-a-payment-method)

1. I administrationscentret går du till sidan  >  **Faktureringsfakturor &**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">betalningssätt.</a>
2. Markera raden för betalningsmetoden som ska uppdateras. Välj Redigera i det högra **fönstret.**
3. Uppdatera informationen om betalningsmetoden, inklusive namnet på kreditkortet eller betalkortet, faktureringsadressen eller utgångsdatumet, och välj sedan **Spara.**

## <a name="replace-a-payment-method"></a>Ersätta ett betalningssätt

När du ersätter en betalningsmetod ersätter du den för alla prenumerationer och faktureringsprofiler som använder samma betalningsmetod. När du ersätter en betalningsmetod tas inte den befintliga betalningsmetoden bort. Det är fortfarande tillgängligt för dig att välja och använda för andra prenumerationer och faktureringsprofiler.

Information om hur du ändrar betalningsmetod för en enskild prenumeration finns i [Ändra en betalningsmetod för en enskild prenumeration.](#change-a-payment-method-for-a-single-subscription)

1. I administrationscentret går du till sidan  >  **Faktureringsfakturor &**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">betalningssätt.</a>
2. Markera raden för den betalningsmetod du vill ersätta. I det högra fönstret visas alla faktureringsprofiler och enskilda prenumerationer som använder den valda betalningsmetoden.
3. I den högra rutan väljer du **Ersätt betalningsmetod för alla objekt.**
4. Om du vill använda en befintlig betalningsmetod väljer du en betalningsmetod i listrutan och sedan **Ersätt.**
    > [!NOTE]
    > Om du har prenumerationer kopplade till en faktureringsprofil kan du bara använda ett kreditkort eller betalkort för att betala för dem. Om du har bankkonton listade **på sidan Betalningsmetoder** är de inte tillgängliga att välja i listrutan.
5. Välj Lägg till betalningsmetod om du vill **lägga till en ny betalningsmetod.**
6. I fönstret **Lägg till en betalningsmetod** anger du kontoinformationen och väljer sedan **Spara.** Du måste använda en betalningsmetod från samma land som din klientorganisation.
7. Den nya betalningsmetoden är redan vald i listrutan. Välj **Ersätt.**

## <a name="change-a-payment-method-for-a-single-subscription"></a>Ändra en betalningsmetod för en enskild prenumeration

Du kan ändra betalningsmetoden som används för att betala för en enskild prenumeration.

1. Gå till sidan Fakturering för dina  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">produkter i administrationscentret.</a>
2. Leta upp **prenumerationen** som du vill betala för med den alternativa betalningsmetoden på fliken Produkter.
3. Välj **Fler åtgärder** (tre punkter) och välj sedan Ersätt **betalningsmetod.**
4. I fönstret **Ersätt betalningsmetod** väljer du en alternativ betalningsmetod i listrutan eller väljer att lägga till en betalningsmetod.
5. Om du lägger till en betalningsmetod anger du kort- eller kontouppgifterna och väljer sedan **Spara.**
6. Kontrollera att den valda betalningsmetoden är korrekt och välj sedan **Ersätt.**

## <a name="delete-a-payment-method"></a>Ta bort en betalningsmetod

Du kan bara ta bort en betalningsmetod som inte är kopplad till en prenumeration eller faktureringsprofil. Det här gäller för alla prenumerationer, oavsett status.

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a>Ta bort en betalningsmetod utan prenumerationer eller faktureringsprofiler bifogade

Om en betalningsmetod inte är kopplad till några prenumerationer eller faktureringsprofiler kan du ta bort den direkt.

1. I administrationscentret går du till sidan  >  **Faktureringsfakturor &**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">betalningssätt.</a>
2. Leta reda på betalningsmetoden du vill ta bort, välj de tre punkterna och välj sedan **Ta bort.**
3. Välj Ta bort längst ned i det högra **fönstret.**

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>Ta bort en betalningsmetod med prenumerationer eller faktureringsprofiler bifogade

Om en betalningsmetod bifogas till en prenumeration eller faktureringsprofiler ersätter du först den med en befintlig betalningsmetod eller lägger till en ny och tar sedan bort den gamla betalningsmetoden.

1. I administrationscentret går du till sidan  >  **Faktureringsfakturor &**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">betalningssätt.</a>
2. Markera raden för betalningsmetoden som ska tas bort. I det högra fönstret visas befintliga prenumerationer som använder den betalningsmetoden.
3. Välj Ta bort i det högra **fönstret.**
4. Om du vill använda en befintlig betalningsmetod väljer du en betalningsmetod i listrutan, **väljer Nästa** och sedan **Ta bort.**
    > [!NOTE]
    > Om du har prenumerationer kopplade till en faktureringsprofil kan du bara använda ett kreditkort för att betala för dem. Om du har bankkonton listade **på sidan Betalningsmetoder** är de inte tillgängliga att välja i listrutan.
5. Välj Lägg till betalningsmetod om du vill **lägga till en ny betalningsmetod.**
6. Välj den typ av betalningsmetod du vill lägga till, ange kontoinformationen och välj sedan **Spara.**
7. Den nya betalningsmetoden är redan vald i listrutan. Välj **Nästa**.
8. Välj **Ta bort.**

## <a name="troubleshoot-payment-methods"></a>Felsöka betalningsmetod

| Problem | Felsökningssteg |
|:----------|:-----|
|**Jag får ett felmeddelande där det står "Webbläsaren är för närvarande inställd på att blockera cookies".** |Konfigurera din webbläsare så att den tillåter cookies från tredje part och försök igen. |
|**Mitt kreditkort eller betalkort nekades.** |Om du betalar med kreditkort eller betalkort och kortet nekas får du ett e-postmeddelande om att Microsoft inte kunde bearbeta betalningen. Kontrollera att kortnumret med kortinformation, utgångsdatum, namn på kortet och adress, inklusive stad och postnummer, visas exakt som de gör på kortet och ditt &mdash; &mdash; kontoutdrag. Du kan uppdatera kortinformationen och skicka betalningen  direkt med hjälp av länken Betala saldo i avsnittet Fakturering **på** sidan prenumerationsinformation. Mer information finns i Vad [gör jag om jag har ett utestående saldo?](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)  <br/><br/>  Om meddelandet om nekat kort fortfarande visas kontaktar du banken. Det är möjligt att kortet inte är aktivt. Om du nyligen har fått kortet via e-post med ett uppdaterat utgångsdatum kontrollerar du att det är aktiverat. Din bank kan också tala om för dig om kortet inte är godkänt för onlinetransaktioner, internationella eller återkommande transaktioner. |
|**Jag vill uppdatera ett kort- eller bankkontonummer.** |Du kan inte ändra kort- eller kontonumret för en befintlig betalningsmetod. Om kortet eller kontonumret [](#replace-a-payment-method)har ändrats ersätter du det med en annan betalningsmetod som flyttar alla aktiva prenumerationer från betalningsmetoden till den nya och tar sedan bort den [gamla betalningsmetoden.](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached) |
|**Jag har bara ett kort eller bankkonto på mitt konto och jag vill ta bort det.** |Om du bara har en betalningsmetod måste du ersätta [den med en ny betalningsmetod innan](#replace-a-payment-method) du kan ta bort den. |
|**Jag kan inte lägga till mitt kort eller bankkonto.**  |Du måste använda en betalningsmetod som utfärdats från samma land som din klientorganisation. Om du har problem med att ange kort- eller bankkontoinformation kan [du kontakta supporten.](../../admin/contact-support-for-business-products.md) |

## <a name="related-content"></a>Relaterat innehåll

[Betala för din företagsprenumeration](pay-for-your-subscription.md) (artikel)\
[Hantera faktureringsprofiler](manage-billing-profiles.md) (artikel)\
[Ändra faktureringsfrekvensen](change-payment-frequency.md) (artikel)
