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
ms.openlocfilehash: 0fed7df54a21b3696e81915af78e377e855bfd12
ms.sourcegitcommit: fa26da0be667d4be0121c52b05488dc76c5d626c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2020
ms.locfileid: "48794903"
---
# <a name="close-your-account"></a>Avsluta ditt konto

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

När du avslutar kontot hos Microsoft raderas all information som är kopplad till ditt konto. Informationen inkluderar prenumerationer, licenser, betalningsmetoder, användare och användardata. Innan du börjar kan du se till att säkerhetskopiera alla data du vill behålla.

## <a name="step-1-delete-users"></a>Steg 1: ta bort användare

Ta bort alla användare utom den globala administratören som slutför stegen för att avsluta kontot. Innan du kan ta bort katalogen i slutet av processen måste du ta bort alla andra användare.

Om användare synkroniseras från lokal avaktiverar du först synkronisering och tar sedan bort användarna i moln katalogen genom att använda cmdlets för Azure-portalen eller Azure PowerShell.

Information om hur du tar bort användare finns i <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">användar hanterings administratör: ta bort en eller flera användare</a>.

Du kan också använda PowerShell <a href="https://go.microsoft.com/fwlink/?linkid=842230">-cmdleten Remove-MsolUser</a> för att ta bort användare i bulk.

Om din organisation använder Active Directory som synkroniserar med Azure AD kan du i stället ta bort användar kontot från Active Directory. Anvisningar finns i <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Mass borttagning av användare i Azure Active Directory</a>.

## <a name="step-2-cancel-all-active-subscriptions"></a>Steg 2: Avbryt alla aktiva abonnemang

1. Gå till sidan fakturering i administrations centret **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> .

2. Om abonnemangs listan är i **tabellvy** väljer du **kort** till höger.

3. Sök efter en aktiv prenumeration och välj **Avbryt prenumeration** i avsnittet **Inställningar & åtgärder** .

4. Följ anvisningarna för att slutföra processen.

5. Upprepa steg 1 till 4 för att avbryta alla aktiva abonnemang.

## <a name="step-3-delete-all-disabled-subscriptions"></a>Steg 3: ta bort alla inaktiverade abonnemang

1. Gå till sidan fakturering i administrations centret **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> .

2. Om abonnemangs listan är i **tabellvy** väljer du **kort** till höger.

3. Bredvid **prenumerations status** väljer du **inaktive rad** .

4. Hitta en inaktive rad prenumeration och välj **ta bort** i avsnittet **Inställningar & åtgärder** .

5. I dialog rutan **ta bort prenumeration** markerar du kryss rutan **Jag förstår effekt** och väljer sedan **ta bort abonnemang** .

6. Upprepa steg 4 och 5 för varje inaktive rad prenumeration tills alla abonnemang har tagits bort.

## <a name="step-4-disable-multi-factor-authentication"></a>Steg 4: inaktivera multifaktorautentisering

1. Gå till sidan **användare**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">aktiva användare</a> i administrations centret.

2. Välj **multifaktorautentisering** .

3. På sidan multifaktorautentisering avaktiverar du alla konton förutom det globala administratörs konto som du använder för närvarande.

Du kan också <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">använda PowerShell för att inaktivera multifaktorautentisering för flera användare</a>.

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Steg 5: ta bort katalogen i Azure Active Directory

1. Logga in på <a href="https://aad.portal.azure.com/" target="_blank">administrations centret för Azure AD</a> med ett globalt administratörs konto.

2. Välj **Azure Active Directory** .

3. Växla till den organisation som du vill ta bort.

4. Välj **ta bort klient organisation** .

5. Om din organisation inte klarar en eller flera kontroller ser du en länk till mer information om hur du överför checkarna. När du har överfört alla kontrollerna väljer du **ta bort** för att slutföra processen.

När du är klar med det här steget stängs och raderas ditt konto med Microsoft.
