---
title: Hantera gäståtkomst i Microsoft 365 grupper
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
description: Lär dig hur du lägger till gäster Microsoft 365 grupp, visar gästanvändare och använder PowerShell för att styra gäståtkomst.
ms.openlocfilehash: 00a6353f02ae7f3675961c3ee2ee31e3715652f2
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635768"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Hantera gäståtkomst i Microsoft 365 grupper

Som standard är gäståtkomst för Microsoft 365 grupper aktiverat för din organisation. Administratörer kan styra om de vill tillåta gäståtkomst till grupper för hela organisationen eller för enskilda grupper.

När det är aktiverat kan gruppmedlemmar bjuda in gästanvändare till en Microsoft 365 via Outlook på webben. Inbjudningar skickas till gruppägaren för godkännande.

När den har godkänts läggs gästanvändaren till i katalogen och gruppen.

> [!Note]
> Yammer Enterprise nätverk som är i inbyggt läge eller [som GEO inte](/yammer/manage-security-and-compliance/manage-data-compliance) har stöd för nätverksgäster.
> Microsoft 365 Anslutna Yammer grupper stöder för närvarande inte gäståtkomst, men du kan skapa icke-anslutna, externa grupper i ditt Yammer nätverk. Instruktioner [finns i Skapa och hantera externa grupper Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) grupper.

Gäståtkomst i grupper används ofta som en del av ett bredare scenario som omfattar SharePoint eller Teams. De här tjänsterna har egna inställningar för gästdelning. Fullständiga instruktioner för hur du inställningar gästdelning mellan grupper, SharePoint och Teams finns i:

- [Samarbeta med gäster på en webbplats](../../solutions/collaborate-in-site.md)
- [Samarbeta med gäster i en grupp](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Hantera gäståtkomst i grupper

Om du vill aktivera eller inaktivera gäståtkomst i grupper kan du göra det Microsoft 365 administrationscentret.

1. I administrationscentret går du till Visa **Inställningar** organisationsinställningar och på fliken \>  \>  **Tjänster** väljer du **Microsoft 365 grupper.**
  
2. På sidan **Microsoft 365 grupper** väljer du om du vill låta personer utanför organisationen få åtkomst till gruppresurser eller låta gruppägare lägga till personer utanför organisationen i grupper.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Lägga till gäster i Microsoft 365 grupp från administrationscentret

Om gästen redan finns i katalogen kan du lägga till dem i grupperna från Microsoft 365 administrationscentret. (Grupper med dynamiskt medlemskap måste [hanteras i Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)
  
1. Gå till sidan Grupper i **administrationscentret.**  >  
  
2. Klicka på den grupp som du vill lägga till gästen i och **välj Visa alla och hantera** medlemmar på **fliken** Medlemmar. 
  
4. Välj **Lägg till** medlemmar och välj namnet på gästen som du vill lägga till.
    
5. Välj **Spara**.

Om du vill lägga till en gäst i katalogen direkt kan du lägga [till Azure Active Directory B2B-samarbetsanvändare i Azure Portal.](/azure/active-directory/b2b/add-users-administrator)

Om du vill redigera någon gästinformation kan du lägga till eller uppdatera en användares [profilinformation med hjälp av Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

## <a name="related-content"></a>Relaterat innehåll

[Blockera gästanvändare från en viss grupp](../../solutions/per-group-guest-access.md) (artikel)\
[Hantera gruppmedlemskap i Microsoft 365 administrationscenter](add-or-remove-members-from-groups.md) (artikel)\
[Azure Active Directory granskningar av åtkomst](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (artikel)\
[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (artikel)