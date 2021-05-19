---
title: Hantera betalningsmetoder
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jamitche, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
- commerce_billing
search.appverid: MET150
description: Köp företagsprodukter eller tjänster från Microsoft med hjälp av ett befintligt betalningssätt, eller genom att lägga till en ny i Administrationscenter för Microsoft 365.
ms.date: 04/02/2021
ms.openlocfilehash: bda7eca29b92cdf131c6d3f5a6069ea2be77f6fa
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537325"
---
# <a name="manage-payment-methods"></a>Hantera betalningsmetoder

> [!IMPORTANT]
> Från och med 26 januari 2021 stöds inte längre nya bankkonton för kunder i Belgien, Frankrike, Italien, Luxemburg, Portugal, Spanien och USA. Om du är en befintlig kund i något av dessa länder kan du fortsätta betala för prenumerationen med ett befintligt bankkonto och du kan lägga till nya prenumerationer till det, men bara så länge bankkontot redan är befintligt.

När du köper företagsprodukter eller -tjänster från Microsoft kan du använda en befintlig betalningsmetod eller lägga till en ny. Du kan använda ett kredit- eller betalkort för att betala för det du köper.

Om ditt företagskonto har en faktureringsprofil och du är faktureringsprofilägare eller faktureringsprofildeltagare kan du använda faktureringsprofilen som stöds av ett kreditkort eller fakturabetalning för att göra inköp eller betala fakturor. Om du är faktureringsansvarig kan du bara använda en faktureringsprofil för att betala fakturor. Mer information om faktureringsprofiler och roller finns i [Hantera faktureringsprofiler](manage-billing-profiles.md).

Om ditt företagskonto inte har någon faktureringsprofil kan en global administratör eller faktureringsadministratör hantera och använda alla bankkonton som lagts till i företagskontot. Du kan dock bara hantera eller använda kreditkort som du lägger till.

> [!NOTE]
> Alternativet att betala med ett bankkonto är inte tillgängligt i vissa länder och regioner.
>
> Du måste använda en betalningsmetod som utfärdats från samma land/region som din klientorganisation.

## <a name="before-you-begin"></a>Innan du börjar

Du måste vara global administratör eller faktureringsadministratörer för att kunna utföra åtgärder som beskrivs i den här artikeln. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).

## <a name="add-a-payment-method"></a>Lägg till en betalningsmetod

Att lägga till en betalningsmetod associerar inga prenumerationer till den. Om du vill tilldela en enstaka prenumeration till betalningsmetoden, se [Ändra betalningsmetod för en enstaka prenumeration](#change-a-payment-method-for-a-single-subscription). Om du vill ersätta alla prenumerationer som använder en annan betalningsmetod med den nya, se [Ersätt betalningsmetod](#replace-a-payment-method).

1. I administrationscentret går du till sidan **Fakturering** > **Fakturor och betalningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Betalningsmetoder</a>.
2. Välj **Lägg till en betalningsmetod**.
3. På sidan **Betalningsmetoder** väljer du ett betalningssätt i listrutan. 
4. Ange informationen för det nya kreditkortet eller bankkontot och välj sedan **Lägg till**.

## <a name="update-payment-method-details"></a>Uppdatera information om betalningsmetod

Du kan ändra namnet på kredit- eller betalkortet, faktureringsadressen eller utgångsdatumet för en befintlig betalningsmetod. Men du kan inte ändra kort- eller kontonumret. Om kontonumret har ändrats [ersätter du det med en annan betalningsmetod](#replace-a-payment-method)och tar [bort det gamla](#delete-a-payment-method).

1. I administrationscentret går du till sidan **Fakturering** > **Fakturor och betalningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Betalningsmetoder</a>.
2. Markera raden för betalningsmetoden som ska uppdateras. I det högra fönstret väljer du **Redigera**.
3. Uppdatera information för betalningsmetoden, inklusive namnet på kredit- eller betalkortet, faktureringsadressen eller utgångsdatumet, och välj sedan **Spara**.

## <a name="replace-a-payment-method"></a>Ersätt en betalningsmetod

När du ersätter en betalningsmetod ersätter du den för alla prenumerationer och faktureringsprofiler som använder samma betalningsmetod. När du ersätter en betalningsmetod tas inte den befintliga betalningsmetoden bort. Du kan fortfarande välja och använda den för andra prenumerationer och faktureringsprofiler.

Om du vill ändra betalningsmetoden för en enstaka prenumeration, se [Ändra betalningsmetod för en enstaka prenumeration](#change-a-payment-method-for-a-single-subscription).

1. I administrationscentret går du till sidan **Fakturering** > **Fakturor och betalningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Betalningsmetoder</a>.
2. Markera raden för betalningsmetoden som ska ersättas. I det högra fönstret visas alla faktureringsprofiler och enstaka prenumerationer som använder den valda betalningsmetoden.
3. I det högra fönstret väljer du **Ersätt betalningsmetod för alla objekt**.
4. Om du vill använda en befintlig betalningsmetod väljer du en i listrutan och väljer sedan **Ersätt**.
    > [!NOTE]
    > Om du har prenumerationer som är associerade till en faktureringsprofil kan du bara använda kredit- eller betalkort för att betala för dem. Om du har bankkonton listade på sidan **Betalningsmetoder**, kan de inte väljas i listrutan.
5. Om du vill lägga till en ny betalningsmetod väljer du **Lägg till betalningsmetod**.
6. I fönstret **Lägg till en betalningsmetod** anger du kontoinformationen och väljer sedan **Spara**. Du måste använda en betalningsmetod som utfärdats från samma land/region som din klientorganisation.
7. Den nya betalningsmetoden är redan vald i listrutan. Välj **Ersätt**.

## <a name="change-a-payment-method-for-a-single-subscription"></a>Ändra betalningsmetod för en enstaka prenumeration

Du kan ändra betalningsmetoden som används för att betala för en enstaka prenumeration.

1. I administrationscentret går du till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.
2. På fliken **Produkter** hittar du den prenumeration som du vill betala för med den alternativa betalningsmetoden.
3. Välj de tre punkterna (fler åtgärder) och välj sedan **Ersätt betalningsmetod**.
4. I fönstret **Ersätt betalningsmetod** väljer du i listrutan en annan betalningsmetod eller väljer att lägga till en betalningsmetod.
5. Om du lägger till en betalningsmetod anger du kort- eller kontouppgifterna och väljer sedan **Spara**.
6. Kontrollera att den valda betalningsmetoden är korrekt och välj sedan **Ersätt**.

## <a name="delete-a-payment-method"></a>Ta bort en betalningsmetod

Du kan bara ta bort en betalningsmetod som inte är kopplad till en prenumeration eller faktureringsprofil. Detta gäller för alla prenumerationer, oavsett status.

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a>Ta bort en betalningsmetod utan tillhörande prenumerationer eller faktureringsprofiler

Om din betalningsmetod inte är associerad till några prenumerationer kan du ta bort den direkt.

1. I administrationscentret går du till sidan **Fakturering** > **Fakturor och betalningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Betalningsmetoder</a>.
2. Leta reda på betalningsmetoden du vill ta bort, välj de tre punkterna och välj sedan **Ta bort**.
3. Längst ned i fönstret väljer du **Ta bort**.

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>Ta bort en betalningsmetod med tillhörande prenumerationer eller faktureringsprofiler

Om en betalningsmetod är kopplad till prenumerationer eller faktureringsprofiler ersätter du den först med en befintlig betalningsmetod eller lägger till en ny och tar sedan bort den gamla betalningsmetoden.

1. I administrationscentret går du till sidan **Fakturering** > **Fakturor och betalningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Betalningsmetoder</a>.
2. Markera raden för betalningsmetoden som ska tas bort. I det högra fönstret visas befintliga prenumerationer som använder den betalningsmetoden.
3. I det högra fönstret väljer du **Ta bort**.
4. Om du vill använda en befintlig betalningsmetod väljer du en i listrutan, väljer **Nästa** och väljer sedan **Ta bort**.
    > [!NOTE]
    > Om du har prenumerationer som är associerade till en faktureringsprofil kan du bara använda kreditkort för att betala för dem. Om du har bankkonton listade på sidan **Betalningsmetoder**, kan de inte väljas i listrutan.
5. Om du vill lägga till en ny betalningsmetod väljer du **Lägg till betalningsmetod**.
6. Välj den typ av betalningsmetod som du vill lägga till, ange kontoinformationen och välj sedan **Spara**.
7. Den nya betalningsmetoden är redan vald i listrutan. Välj **Nästa**.
8. Välj **Ta bort**.

## <a name="troubleshoot-payment-methods"></a>Felsöka betalningsmetoder

| Problem | Felsökningssteg |
|:----------|:-----|
|**Jag får ett felmeddelande där det står "Webbläsaren är för tillfället inställd så att den blockerar cookies."** |Konfigurera din webbläsare så att den tillåter cookies från tredje part och försök igen. |
|**Mitt kredit- eller betalkort nekades.** |Om du betalar med kredit- eller betalkort och kortet nekas får du ett e-postmeddelande med information om att Microsoft inte har kunnat bearbeta betalningen. Kontrollera att kortuppgifterna&mdash;kortnummer, utgångsdatum, namn på kortet och adress, inklusive stad, region och postnummer&mdash;visas exakt som de gör på kortet och ditt kontoutdrag. Du kan uppdatera kortuppgifterna och skicka betalningen direkt med hjälp av länken **Reglera saldo** i sektionen **Fakturering** på sidan med prenumerationsinformation. Läs mer i [Vad händer om jag har ett utestående saldo?](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)  <br/><br/>  Om meddelandet om nekat kort fortfarande visas kontaktar du banken. Det är möjligt att kortet inte är aktivt. Om du har nyligen fått kortet via post med ett uppdaterat utgångsdatum kontrollerar du att det är aktiverat. Din bank kan också lämna information om kortet inte är godkänt för onlinetransaktioner, internationella eller återkommande transaktioner. |
|**Jag behöver uppdatera ett kreditkorts- eller bankkontonummer.** |Du kan inte ändra kreditkorts- eller bankkontonumret för en befintlig betalningsmetod. Om ditt kort- eller kontonummer har ändrats [ersätter du det med en annan betalningsmetod](#replace-a-payment-method), vilket flyttar alla aktiva prenumerationer från betalningsmetoden till den nya och sedan [tar du bort den gamla betalningsmetoden](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached). |
|**Jag har bara ett kreditkort eller bankkonto på kontot och vill ta bort det.** |Om du bara har en betalningsmetod måste du [ersätta den med en ny betalningsmetod](#replace-a-payment-method) innan du kan ta bort den. |
|**Jag kan inte lägga till mitt kreditkort eller bankkonto.**  |Du måste använda en betalningsmetod som utfärdats från samma land/region som din klientorganisation. Om du har problem med att ange kreditkorts- eller bankkontoinformation kan du [kontakta supporten](../../business-video/get-help-support.md). |

## <a name="related-content"></a>Relaterat innehåll

[Betala för din företagsprenumeration](pay-for-your-subscription.md) (artikel)\
[Hantera faktureringsprofiler](manage-billing-profiles.md) (artikel)\
[Ändra faktureringsfrekvens för](change-payment-frequency.md) (artikel)
