---
title: Hantera gäst åtkomst i Microsoft 365-grupper
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Lär dig hur du lägger till gäster i en Microsoft 365-grupp, visar gäst användare och använder PowerShell för att kontrol lera gäst åtkomst.
ms.openlocfilehash: 640a35cbb1a3eb395453b224cadcf0d0db82fab8
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326525"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Hantera gäst åtkomst i Microsoft 365-grupper

Gäst åtkomst för Microsoft 365-grupper är aktive rad som standard för din organisation. Administratörer kan kontrol lera om gäst åtkomst ska tillåtas till grupper för hela organisationen eller för enskilda grupper.

När den är aktive rad kan grupp medlemmar bjuda in gäst användare till en Microsoft 365-grupp via Outlook på webben. Inbjudningar skickas till gruppens ägare för godkännande.

När gäst användaren har godkänts läggs den till i katalogen och i gruppen.

> [!Note]
> Yammer Enterprise-nätverk i enhetligt läge eller [EU geo](https://go.microsoft.com/fwlink/?linkid=2107357) stöder inte nätverks gäster.
> Microsoft 365 anslöt Yammer-grupper stöder för närvarande inte gäst åtkomst, men du kan skapa icke anslutna externa grupper i Yammer-nätverket. Se [skapa och hantera externa grupper i Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) för instruktioner.

Gäst åtkomst i grupper används ofta som en del av ett bredare scenario som innehåller SharePoint eller teams. Dessa tjänster har sina egna inställningar för gäst delning. Fullständiga anvisningar för hur du konfigurerar gäst delning i grupper, SharePoint och Teams finns i:

- [Samar beta med gäster på en webbplats](../../solutions/collaborate-in-site.md)
- [Samar beta med gäster i ett team](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Hantera grupper gäst åtkomst

Om du vill aktivera eller inaktivera gäst åtkomst i grupper kan du göra det i administrations centret för Microsoft 365.

1. I administrations centret går du till **Visa alla** \> **Inställningar** \> **organisations inställningar** och väljer **Microsoft 365 Groups**på fliken **tjänster** .
  
2. På sidan **Microsoft 365-grupper** väljer du om du vill låta personer utanför organisationen komma åt grupp resurserna eller låta grupp ägarna lägga till personer utanför organisationen till grupper.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Lägga till gäster i en Microsoft 365-grupp från administrations centret

Om gästen redan finns i katalogen kan du lägga till den i dina grupper från administrations centret för Microsoft 365.
  
1. Gå till sidan grupper i administrations centret **Groups**  >  **Groups** .
  
2. Klicka på den grupp där du vill lägga till gästen och välj **Visa alla och hantera medlemmar** på fliken **medlemmar** . 
  
4. Välj **Lägg till medlemmar**och välj namnet på den gäst du vill lägga till.
    
5. Välj **Spara**.

Om du vill lägga till en gäst i katalogen direkt kan du [lägga till användare i Azure Active Directory B2B-samarbete i Azure-portalen](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).

Om du vill redigera ett gäst konto kan du [lägga till eller uppdatera en användares profil information med Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

## <a name="see-also"></a>Se även

[Blockera gäst användare i en viss grupp](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Hantera grupp medlemskap i administrations centret för Microsoft 365](add-or-remove-members-from-groups.md)
  
[Åtkomst granskning för Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
