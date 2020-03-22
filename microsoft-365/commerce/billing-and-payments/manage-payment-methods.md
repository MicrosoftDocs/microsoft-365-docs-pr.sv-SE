---
title: Hantera betalningsmetoder
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: Läs om hur du hanterar dina betalningsmetoder i administrationscentret för Microsoft 365.
ms.openlocfilehash: 997b957bb28d32402e17eb855bc891ed07e5f27f
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894847"
---
# <a name="manage-payment-methods"></a>Hantera betalningsmetoder

När du köper företagsprodukter eller tjänster från Microsoft kan du använda en befintlig betalningsmetod eller lägga till en ny. Du kan använda ett kredit- eller betalkort eller bankkonto för att betala för det du köper. Men du kan bara hantera betalningsmetoder som du lägger till.

> [!NOTE]
> Alternativet att betala med ett bankkonto är inte tillgängligt i vissa länder eller regioner.
>
> Du måste använda en betalningsmetod som utfärdats från samma land som din klient.

## <a name="add-a-payment-method"></a>Lägga till en betalningsmetod

Om du lägger till en betalningsmetod kopplas inga prenumerationer till den. Information om hur du tilldelar en enskild prenumeration till betalningsmetoden finns i [Ändra en betalningsmetod för en enskild prenumeration](#change-a-payment-method-for-a-single-subscription). Information om hur du ersätter alla prenumerationer som använder en annan betalningsmetod med den nya finns i [Ersätta en betalningsmetod](#replace-a-payment-method).

1. Gå till sidan > **Faktureringsfakturor &** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">betalningsmetoder</a> i administrationscentret. **Billing**
2. Välj **Lägg till en betalningsmetod**.
3. På sidan **Betalningsmetoder** väljer du ett betalningssätt i listrutan. 
4. Ange informationen för det nya kortet eller bankkontot och välj sedan **Lägg till**.

## <a name="update-payment-method-details"></a>Uppdatera information om betalningsmetod

Du kan ändra namnet på kredit- eller betalkortet, faktureringsadressen eller utgångsdatumet för en befintlig betalningsmetod. Du kan dock inte ändra kortet eller kontonumret. Om kontonumret har ändrats [ersätter du det med en annan betalningsmetod](#replace-a-payment-method)och tar sedan bort det [gamla](#delete-a-payment-method).

1. Gå till sidan > **Faktureringsfakturor &** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">betalningsmetoder</a> i administrationscentret. **Billing**
2. Markera raden för den betalningsmetod som ska uppdateras. Välj **Redigera**i den högra rutan .
3. Uppdatera din betalningsmetodsinformation (namn på kredit- eller betalkort, faktureringsadress eller utgångsdatum) och välj sedan **Spara**.

## <a name="replace-a-payment-method"></a>Ersätta en betalningsmetod

När du ersätter en betalningsmetod ersätter du den för alla prenumerationer och faktureringsprofiler som använder samma betalningsmetod. Om du ersätter en betalningsmetod tas inte den befintliga betalningsmetoden bort. Den är fortfarande tillgänglig för dig att välja och använda för andra prenumerationer och faktureringsprofiler.

Information om hur du ändrar betalningsmetoden för en enskild prenumeration finns i [Ändra en betalningsmetod för en enskild prenumeration](#change-a-payment-method-for-a-single-subscription).

1. Gå till sidan > **Faktureringsfakturor &** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">betalningsmetoder</a> i administrationscentret. **Billing**
2. Markera raden för den betalningsmetod som ska ersättas. I den högra rutan visas alla faktureringsprofiler och enskilda prenumerationer som använder den valda betalningsmetoden.
3. Välj Ersätt betalningsmetod **för alla artiklar**i den högra rutan .
4. Om du vill använda en befintlig betalningsmetod väljer du en i listrutan och väljer sedan **Ersätt**.
    > [!NOTE]
    > Om du har prenumerationer kopplade till en faktureringsprofil kan du bara använda ett kredit- eller betalkort för att betala för dem. Om du har bankkonton listade på sidan **Betalningsmetoder** är de inte tillgängliga att välja i listrutan.
5. Om du vill lägga till en ny betalningsmetod väljer du **Lägg till betalningsmetod**.
6. I fönstret **Lägg till en betalningsmetod** anger du kontoinformationen och väljer sedan **Spara**. Du måste använda en betalningsmetod från samma land som din klient.
7. Den nya betalningsmetoden har redan valts i listrutan. Välj **Ersätt**.

## <a name="change-a-payment-method-for-a-single-subscription"></a>Ändra en betalningsmetod för en enskild prenumeration

Du kan ändra betalningsmetoden som används för att betala för en enskild prenumeration.

1. Gå till sidan **Faktureringsprodukter** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">& tjänster</a> i administrationscentret.
2. På fliken **Prenumerationer** väljer du den prenumeration som du vill betala för med den alternativa betalningsmetoden. 
3. Välj **Billing** **Redigera**bredvid betalningsmetoden.
4. Välj Ändra **bredvid**din befintliga betalningsmetod .
5. Välj en alternativ betalningsmetod i listrutan eller välj att lägga till en betalningsmetod.
6. Om du lägger till en betalningsmetod anger du kort- eller kontouppgifterna och väljer sedan **Spara**.
7. Kontrollera att den valda betalningsmetoden är korrekt och välj sedan **Spara**.

## <a name="delete-a-payment-method"></a>Ta bort en betalningsmetod

Du kan bara ta bort en betalningsmetod som inte är kopplad till en prenumeration eller faktureringsprofil. Detta gäller alla prenumerationer, oavsett deras status.

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a>Ta bort en betalningsmetod utan prenumerationer eller faktureringsprofiler kopplade

Om en betalningsmetod inte är kopplad till prenumerationer eller faktureringsprofiler kan du omedelbart ta bort den.

1. Gå till sidan > **Faktureringsfakturor &** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">betalningsmetoder</a> i administrationscentret. **Billing**
2. Leta reda på betalningsmetoden som ska tas bort, markera de tre punkterna och välj sedan **Ta bort**.
3. Längst ned i den högra rutan väljer du **Ta bort**.

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>Ta bort en betalningsmetod med prenumerationer eller faktureringsprofiler kopplade

Om en betalningsmetod är kopplad till prenumerationer eller faktureringsprofiler ersätter du den först med en befintlig betalningsmetod eller lägger till en ny och tar sedan bort den gamla betalningsmetoden.

1. Gå till sidan > **Faktureringsfakturor &** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">betalningsmetoder</a> i administrationscentret. **Billing**
2. Markera raden för betalningsmetoden som ska tas bort. I den högra rutan visas befintliga prenumerationer som använder den betalningsmetoden.
3. Välj **Ta bort**i den högra rutan .
4. Om du vill använda en befintlig betalningsmetod väljer du en i listrutan, väljer **Nästa**och väljer sedan **Ta bort**.
    > [!NOTE]
    > Om du har prenumerationer kopplade till en faktureringsprofil kan du bara använda ett kreditkort för att betala för dem. Om du har bankkonton listade på sidan **Betalningsmetoder** är de inte tillgängliga att välja i listrutan.
5. Om du vill lägga till en ny betalningsmetod väljer du **Lägg till betalningsmetod**.
6. Välj den typ av betalningsmetod som du vill lägga till, ange kontoinformationen och välj sedan **Spara**.
7. Den nya betalningsmetoden har redan valts i listrutan. Välj **Nästa**.
8. Välj **Ta bort**.

## <a name="troubleshoot-payment-methods"></a>Felsöka betalningsmetoder

|**Problem**|**Felsökningssteg**|
|:----------|:-----|
|**Jag får ett felmeddelande som säger: "Webbläsaren är för närvarande inställd på att blockera cookies."** |Konfigurera din webbläsare så att den tillåter cookies från tredje part och försök igen. |
|**Mitt kredit- eller betalkort avvisades.** |Om du betalar med kredit- eller betalkort och kortet avvisas får du ett e-postmeddelande där det står att Microsoft inte kunde behandla betalningen. Dubbelkolla att &mdash; kortnummer, utgångsdatum, namn på kortet och adress, inklusive ort, delstat och postnummer , visas precis som de gör på kortet och ditt utdrag. Du kan uppdatera din kortinformation och omedelbart skicka betalningen med hjälp av länken **Kvitta saldo** i avsnittet **Fakturering** på sidan Prenumerationsinformation. Mer information finns i [Vad händer om mitt kreditkort avvisades och min betalning förfaller till betalning?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)  <br/><br/>  Om meddelandet om nekat kort fortfarande visas kontaktar du banken. Det är möjligt att ditt kort inte är aktivt. Om du nyligen har fått kortet med ett uppdaterat utgångsdatum kontrollerar du att det är aktiverat. Din bank kan också berätta om ditt kort inte är godkänt för online-, internationella eller återkommande transaktioner. |
|**Jag vill uppdatera ett kort- eller bankkontonummer.** |Du kan inte ändra kortet eller kontonumret på en befintlig betalningsmetod. Om ditt kort- eller kontonummer har ändrats [ersätter du det med en annan betalningsmetod](#replace-a-payment-method), som flyttar alla aktiva prenumerationer från betalningsmetoden till den nya och sedan tar bort den gamla [betalningsmetoden](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached). |
|**Jag har bara ett kort eller bankkonto på mitt konto och jag vill ta bort det.** |Om du bara har en betalningsmetod måste du [ersätta den med en ny betalningsmetod](#replace-a-payment-method) innan du kan ta bort den. |
|**Jag kan inte lägga till mitt kort eller bankkonto.**  |Du måste använda en betalningsmetod som utfärdats från samma land som din klient. Om du har problem med att ange kort- eller bankkontoinformation kan du [kontakta supporten](../../admin/contact-support-for-business-products.md). |

## <a name="related-articles"></a>Relaterade artiklar

[Betala för din företagsprenumeration](pay-for-your-subscription.md)

[Hantera faktureringsprofiler](manage-billing-profiles.md)

[Ändra din betalningsfrekvens](change-payment-frequency.md)