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
description: Lär dig hur du stänger ditt konto hos Microsoft.
ms.openlocfilehash: 44428654946d31ad249bfd3e7a3609da3e3634a6
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860553"
---
# <a name="close-your-account"></a>Avsluta ditt konto

När du avslutar kontot hos Microsoft raderas all information som är kopplad till ditt konto. Informationen inkluderar prenumerationer, licenser, betalningsmetoder, användare och användardata.

## <a name="before-you-begin"></a>Innan du börjar

Se till att du säkerhetskopierar data som du vill ha kvar innan du påbörjar processen.

Du måste vara global administratör eller faktureringsadministratörer för att kunna utföra åtgärder som beskrivs i den här artikeln. Mer information finns i [Om administratörsroller](../admin/add-users/about-admin-roles.md).

## <a name="step-1-delete-users"></a>Steg 1: Ta bort användare

Ta bort alla användare utom en global administratör. Den globala administratören slutför stegen för att stänga kontot. Innan du kan ta bort katalogen i slutet av den här processen måste du ta bort alla andra användare.

Om användarna synkroniseras från en lokal miljö inaktiverar du först synkroniseringen och tar sedan bort användarna i molnkatalogen med hjälp av Azure-portalen eller Azure PowerShell-cmdlets.

Information om hur du tar bort användare <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">finns i Användarhanteringsadministratör: Ta bort en eller flera användare</a>.

Du kan också använda <a href="https://docs.microsoft.com/powershell/module/msonline/remove-msoluser">PowerShell-cmdleten Remove-MsolUser</a> för att massborttagning av användare.

Om din organisation använder Active Directory som synkroniserar med Microsoft Azure Active Directory (Azure AD) ska du ta bort användarkontot från Active Directory i stället. Instruktioner finns i <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">Massborttagning av användare i Azure Active Directory.</a>

## <a name="step-2-cancel-all-active-subscriptions"></a>Steg 2: Avbryt alla aktiva prenumerationer

1. I administrationscentret går du till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.
2. På fliken **Produkter** hittar du en aktiv prenumeration. Välj **Fler åtgärder** (tre punkter) och välj sedan **Avbryt prenumeration**.
3. I fönstret **Avbryt prenumeration** väljer du en anledning till varför du avbryter prenumerationen. Alternativt kan du ge valfri feedback.
4. Välj **Spara**.
5. Upprepa steg 1 till 4 för att avbryta alla aktiva prenumerationer.

## <a name="step-3-delete-all-disabled-subscriptions"></a>Steg 3: Ta bort alla inaktiverade prenumerationer

1. I administrationscentret går du till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.
2. Välj en **inaktiverad** prenumeration på fliken Produkter.
3. Välj Ta bort prenumeration i avsnittet **Prenumerations- och betalningsinställningar** på sidan **prenumerationsinformation.**
4. I fönstret **Ta bort prenumeration** väljer du Ta bort **prenumeration.**
5. Välj **Ja i** dialogrutan Ta bort **prenumeration.**
6. Upprepa steg 3 till 5 för varje inaktiverad prenumeration tills alla prenumerationer har tagits bort.

> [!NOTE]
> Om du inte kan ta bort en inaktiverad prenumeration direkt kontaktar <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">du supporten</a>

## <a name="step-4-disable-multi-factor-authentication"></a>Steg 4: Inaktivera multifaktorautentisering

1. Logga in på administrationscentret med ett globalt administratörskonto. Du kan kontrollera vilka roller du har i [Kontrollera administratörsroller i din organisation.](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)
2. Gå till **sidan Användare**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">aktiva</a> användare.
3. Välj **Multifaktorautentisering**.
4. På sidan Multifaktorautentisering inaktiverar du alla konton utom för det globala administratörskonto som du använder för närvarande.

Du kan också <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">använda PowerShell för att inaktivera multifaktorautentisering för flera användare.</a>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Steg 5: Ta bort katalogen i Azure Active Directory

1. Logga in på <a href="https://aad.portal.azure.com/" target="_blank">administrationscentret för Azure AD med</a> ett globalt administratörskonto.
2. Välj **Azure Active Directory.**
3. Växla till den organisation som du vill ta bort.
4. Välj **Ta bort klientorganisation.**
5. Om din organisation misslyckas med en eller flera kontroller visas en länk till mer information om hur du gör för att överföra kontrollerna. När du har slutfört alla kontroller väljer **du Ta** bort för att slutföra processen.

När du är klar med det här sista steget stängs ditt konto hos Microsoft och tas bort.