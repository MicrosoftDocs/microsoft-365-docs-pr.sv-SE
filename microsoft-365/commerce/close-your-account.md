---
title: Stäng ditt konto
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
ms.custom: ''
search.appverid:
- MET150
description: Läs om hur du stänger ditt konto hos Microsoft.
ms.openlocfilehash: 3a193aea92ff384d53ce320a98cd9043d990b678
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42807497"
---
# <a name="close-your-account"></a>Stäng ditt konto

När du stänger ditt konto hos Microsoft raderas all information som är relaterad till ditt konto. Den här informationen omfattar prenumerationer, licenser, betalningsmetoder, användare och användardata. Innan du startar den här processen måste du säkerhetskopiera alla data som du vill bevara.

## <a name="step-1-delete-users"></a>Steg 1: Ta bort användare

Ta bort alla användare utom en global administratör som slutför stegen för att stänga kontot. Innan du kan ta bort katalogen i slutet av den här processen måste du ta bort alla andra användare.

Om användare synkroniseras från lokalt, inaktiverar först synkroniseringen och tar sedan bort användarna i molnkatalogen med hjälp av Azure-portalen eller Azure PowerShell-cmdlets.

Information om hur du tar bort användare finns i <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">Administratör för användarhantering: Ta bort en eller flera användare</a>.

Du kan också använda <a href="https://go.microsoft.com/fwlink/?linkid=842230">Cmdlet Remove-MsolUser</a> PowerShell för att ta bort användare i grupp.

Om din organisation använder Active Directory som synkroniseras med Azure AD tar du bort användarkontot från Active Directory i stället. Instruktioner finns i <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Massborttagningsanvändare i Azure Active Directory</a>.

## <a name="step-2-cancel-all-active-subscriptions"></a>Steg 2: Avbryt alla aktiva prenumerationer

1. Gå till sidan > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Faktureringsprodukter & tjänster</a> i administrationscentret. **Billing**

2. Om prenumerationslistan finns i **tabellvyn** väljer du **Kort**till höger .

3. Hitta en aktiv prenumeration och välj Avbryt **prenumeration**i avsnittet **Inställningar & åtgärder** .

4. Följ uppmaningarna för att slutföra processen.

5. Upprepa steg 1 till och med 4 för att avbryta alla aktiva prenumerationer.

## <a name="step-3-delete-all-disabled-subscriptions"></a>Steg 3: Ta bort alla inaktiverade prenumerationer

1. Gå till sidan > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Faktureringsprodukter & tjänster</a> i administrationscentret. **Billing**

2. Om prenumerationslistan finns i **tabellvyn** väljer du **Kort**till höger .

3. Välj **Inaktiverad**bredvid **status för prenumeration**.

4. Hitta en inaktiverad prenumeration och välj **Ta bort**i avsnittet Inställningar **& åtgärder.**

5. Markera kryssrutan **Jag förstår effekten** i dialogrutan Ta bort **prenumeration** och välj sedan Ta **bort prenumeration**.

6. För varje inaktiverad prenumeration upprepar du steg 4 och 5 tills alla prenumerationer har tagits bort.

## <a name="step-4-disable-multi-factor-authentication"></a>Steg 4: Inaktivera multifaktorautentisering

1. Gå till sidan **Aktiva** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">användare</a> i administrationscentret.

2. Välj **Multifaktorautentisering**.

3. På sidan multifaktorautentisering inaktiverar du alla konton förutom det globala administratörskonto som du använder för närvarande.

Du kan också <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#use-powershell">använda PowerShell för att inaktivera multifaktorautentisering för flera användare</a>.

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Steg 5: Ta bort katalogen i Azure Active Directory

1. Logga in på <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> med ett globalt administratörskonto.

2. Välj **Azure Active Directory**.

3. Växla till den katalog som du vill ta bort.

4. Välj **Ta bort katalog**.

5. Om katalogen misslyckas med en eller flera kontroller visas en länk till mer information om hur kontrollerna ska utföras. När du har klarat alla kontroller väljer du **Ta bort** för att slutföra processen.

När du har slutfört det sista steget stängs och tas ditt konto med Microsoft bort.
