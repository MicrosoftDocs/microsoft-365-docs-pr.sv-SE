---
title: Avsluta ditt konto
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
description: Läs om hur du avslutar ditt konto hos Microsoft.
ms.openlocfilehash: a92b9f2053d9acf4e8233bee7a42047f51288943
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44898927"
---
# <a name="close-your-account"></a>Avsluta ditt konto

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

När du avslutar kontot hos Microsoft raderas all information som är kopplad till ditt konto. Informationen inkluderar prenumerationer, licenser, betalningsmetoder, användare och användardata. Innan du påbörjar den här processen måste du säkerhetskopiera alla data som du vill bevara.

## <a name="step-1-delete-users"></a>Steg 1: Ta bort användare

Ta bort alla användare utom en global administratör som slutför stegen för att stänga kontot. Innan du kan ta bort katalogen i slutet av den här processen måste du ta bort alla andra användare.

Om användare synkroniseras från lokala, stäng först av synkronisering och ta sedan bort användarna i molnkatalogen med hjälp av Azure-portalen eller Azure PowerShell-cmdletar.

Information om hur du tar bort användare finns i <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">Användarhanteringsadministratör: Ta bort en eller flera användare</a>.

Du kan också använda cmdleten <a href="https://go.microsoft.com/fwlink/?linkid=842230">Ta bort MsolUser</a> PowerShell för att ta bort användare i grupp.

Om din organisation använder Active Directory som synkroniseras med Azure AD tar du bort användarkontot från Active Directory i stället. Instruktioner finns <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">i Massborttagning av användare i Azure Active Directory</a>.

## <a name="step-2-cancel-all-active-subscriptions"></a>Steg 2: Avbryta alla aktiva prenumerationer

1. Gå till sidan **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Faktureringsprodukter</a> i administrationscentret.

2. Om prenumerationslistan finns i **tabellvyn** väljer du **Kort**till höger .

3. Hitta en aktiv prenumeration och välj **Avbryt prenumeration**i avsnittet Inställningar **& åtgärder** .

4. Följ anvisningarna för att slutföra processen.

5. Upprepa steg 1 till och med 4 för att avbryta alla aktiva prenumerationer.

## <a name="step-3-delete-all-disabled-subscriptions"></a>Steg 3: Ta bort alla inaktiverade prenumerationer

1. Gå till sidan **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Faktureringsprodukter</a> i administrationscentret.

2. Om prenumerationslistan finns i **tabellvyn** väljer du **Kort**till höger .

3. Välj **Inaktiverad bredvid** **Prenumerationsstatus**.

4. Hitta en inaktiverad prenumeration och välj **Ta bort**i avsnittet Inställningar **& åtgärder** .

5. Markera kryssrutan **Jag förstår fliken Påverkan i** dialogrutan Ta bort **prenumeration** och välj sedan Ta **bort prenumeration**.

6. Upprepa steg 4 och 5 för varje inaktiverad prenumeration tills alla prenumerationer har tagits bort.

## <a name="step-4-disable-multi-factor-authentication"></a>Steg 4: Inaktivera multifaktorautentisering

1. Gå till sidan Aktiva användare i **administrationscentret.**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>

2. Välj **Multifaktorautentisering**.

3. På sidan multifaktorautentisering inaktiverar du alla konton utom det globala administratörskonto som du för närvarande använder.

Du kan också <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">använda PowerShell för att inaktivera multifaktorautentisering för flera användare</a>.

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Steg 5: Ta bort katalogen i Azure Active Directory

1. Logga in på <a href="https://aad.portal.azure.com/" target="_blank">Azure AD-administrationscentret</a> med ett globalt administratörskonto.

2. Välj **Azure Active Directory**.

3. Växla till den katalog som du vill ta bort.

4. Välj **Ta bort katalog**.

5. Om katalogen misslyckas med en eller flera kontroller visas en länk till mer information om hur du skickar kontrollerna. När du har klarat alla kontroller väljer du **Ta bort** för att slutföra processen.

När du har slutfört det här sista steget stängs kontot hos Microsoft och tas bort.
