---
title: Avsluta ditt konto
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
search.appverid:
- MET150
description: Lär dig hur du avslutar ditt konto hos Microsoft.
ms.openlocfilehash: bdcf4408ddc9c198fab1d68b4c096fad9059b975
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376323"
---
# <a name="close-your-account"></a>Avsluta ditt konto

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

När du avslutar kontot hos Microsoft raderas all information som är kopplad till ditt konto. Informationen inkluderar prenumerationer, licenser, betalningsmetoder, användare och användardata.

## <a name="before-you-begin"></a>Innan du börjar

Se till att du säkerhetskopierar data som du vill ha kvar innan du påbörjar processen.

Du måste vara global eller fakturerings administratör för att kunna utföra åtgärderna i den här artikeln. Mer information finns i [Om administratörsroller](../admin/add-users/about-admin-roles.md).

## <a name="step-1-delete-users"></a>Steg 1: ta bort användare

Ta bort alla användare utom den globala administratören. Den globala administratören Slutför stegen för att avsluta kontot. Innan du kan ta bort katalogen i slutet av processen måste du ta bort alla andra användare.

Om användare synkroniseras från lokal avaktiverar du först synkronisering och tar sedan bort användarna i moln katalogen genom att använda cmdlets för Azure-portalen eller Azure PowerShell.

Information om hur du tar bort användare finns i <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">användar hanterings administratör: ta bort en eller flera användare</a>.

Du kan också använda PowerShell <a href="https://go.microsoft.com/fwlink/?linkid=842230">-cmdleten Remove-MsolUser</a> för att ta bort användare i bulk.

Om din organisation använder Active Directory som synkroniseras med Microsoft Azure Active Directory (Azure AD) tar du bort användar kontot från Active Directory i stället. Anvisningar finns i <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Mass borttagning av användare i Azure Active Directory</a>.

## <a name="step-2-cancel-all-active-subscriptions"></a>Steg 2: Avbryt alla aktiva abonnemang

1. Gå till sidan fakturering i administrations centret **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> .
2. Hitta en aktiv prenumeration på fliken **produkter** . Välj **fler åtgärder** (tre punkter) och välj sedan **Avbryt prenumeration**.
3. I fönstret **Avsluta prenumeration** väljer du en orsak till varför du avbryter. Du kan också lämna feedback.
4. Välj **Spara**.
5. Upprepa steg 1 till 4 för att avbryta alla aktiva abonnemang.

## <a name="step-3-delete-all-disabled-subscriptions"></a>Steg 3: ta bort alla inaktiverade abonnemang

1. Gå till sidan fakturering i administrations centret **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> .
2. Välj ett inaktiverat abonnemang på fliken **Products** .
3. På sidan prenumerations information, under **prenumerations-och betalnings inställningar** väljer du **ta bort abonnemang**.
4. Välj **ta bort prenumeration** i fönstret **ta bort prenumeration** .
5. I dialog rutan **ta bort prenumeration** väljer du **Ja**.
6. För varje inaktive rad prenumeration upprepar du steg 3 till 5 tills alla abonnemang tas bort.

> [!NOTE]
> Om du inte kan ta bort en inaktive rad prenumeration omedelbart <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">kontaktar du supporten</a>

## <a name="step-4-disable-multi-factor-authentication"></a>Steg 4: inaktivera multifaktorautentisering

1. Logga in i administrations centret med ett globalt administratörs konto. Information om hur du kontrollerar vilka roller du har finns i [kontrol lera administratörs roller i organisationen](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).
2. Gå till sidan **användare**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">aktiva användare</a> .
3. Välj **multifaktorautentisering**.
4. På sidan multifaktorautentisering avaktiverar du alla konton förutom det globala administratörs konto som du använder för närvarande.

Du kan också <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">använda PowerShell för att inaktivera multifaktorautentisering för flera användare</a>.

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Steg 5: ta bort katalogen i Azure Active Directory

1. Logga in på <a href="https://aad.portal.azure.com/" target="_blank">administrations centret för Azure AD</a> med ett globalt administratörs konto.
2. Välj **Azure Active Directory**.
3. Växla till den organisation som du vill ta bort.
4. Välj **ta bort klient organisation**.
5. Om din organisation inte klarar en eller flera kontroller ser du en länk till mer information om hur du överför checkarna. När du har överfört alla kontrollerna väljer du **ta bort** för att slutföra processen.

När du är klar med det här steget stängs och raderas ditt konto med Microsoft.