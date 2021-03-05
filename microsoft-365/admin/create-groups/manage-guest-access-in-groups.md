---
title: Hantera gäståtkomst i Microsoft 365-grupper
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: Lär dig hur du lägger till gäster i en Microsoft 365-grupp, visar gästanvändare och använder PowerShell för att styra gäståtkomst.
ms.openlocfilehash: 9a713684bb9a2401316dbb3289115be19b220cff
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453663"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Hantera gäståtkomst i Microsoft 365-grupper

Som standard är gäståtkomst för Microsoft 365-grupper aktiverat för din organisation. Administratörer kan styra om de vill tillåta gäståtkomst till grupper för hela organisationen eller för enskilda grupper.

När det är aktiverat kan gruppmedlemmar bjuda in gästanvändare till en Microsoft 365-grupp via Outlook på webben. Inbjudningar skickas till gruppägaren för godkännande.

När gästanvändaren har godkänts läggs den till i katalogen och gruppen.

> [!Note]
> Yammer Enterprise-nätverk som är i inbyggt läge eller [SOM GEO inte](https://go.microsoft.com/fwlink/?linkid=2107357) stöder nätverks gäster.
> Microsoft 365-Yammer-grupper stöder för närvarande inte gäståtkomst, men du kan skapa icke-anslutna, externa grupper i Yammer nätverket. Se [Skapa och hantera externa grupper i Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) för anvisningar.

Gäståtkomst i grupper används ofta som en del av ett bredare scenario som inkluderar SharePoint eller Teams. De här tjänsterna har sina egna inställningar för gästdelning. Fullständiga instruktioner för att konfigurera gästdelning mellan grupper, SharePoint och Teams finns i:

- [Samarbeta med gäster på en webbplats](../../solutions/collaborate-in-site.md)
- [Samarbeta med gäster i ett team](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Hantera gäståtkomst för grupper

Om du vill aktivera eller inaktivera gäståtkomst i grupper kan du göra det i administrationscentret för Microsoft 365.

1. Gå till Visa alla organisationsinställningar **för inställningar** i administrationscentret och välj \>  \>  **Microsoft 365-grupper** på fliken Tjänster. 
  
2. På sidan **Microsoft 365 Grupper** väljer du om du vill låta personer utanför organisationen få åtkomst till gruppresurser eller låta gruppägare lägga till personer utanför organisationen i grupper.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Lägga till gäster i en Microsoft 365-grupp från administrationscentret

Om gästen redan finns i katalogen kan du lägga till dem i dina grupper från administrationscentret för Microsoft 365. (Grupper med dynamiskt medlemskap måste [hanteras i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/enterprise-users/groups-create-rule).)
  
1. Gå till sidan Grupper i  >   administrationscentret.
  
2. Klicka på den grupp som du vill lägga till gästen i och välj **Visa alla och hantera medlemmar** på **fliken** Medlemmar. 
  
4. Välj **Lägg till** medlemmar och välj namnet på gästen som du vill lägga till.
    
5. Välj **Spara**.

Om du vill lägga till en gäst i katalogen direkt kan du lägga [till Azure Active Directory B2B-samarbetsanvändare i Azure Portal.](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)

Om du vill redigera någon gästinformation kan du lägga till eller uppdatera en användares [profilinformation med hjälp av Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

## <a name="see-also"></a>Se även

[Blockera gästanvändare från en viss grupp](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Hantera gruppmedlemskap i administrationscentret för Microsoft 365](add-or-remove-members-from-groups.md)
  
[Åtkomstgranskningar i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
