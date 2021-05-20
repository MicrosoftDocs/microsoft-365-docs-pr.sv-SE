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
description: Lär dig hur du lägger till gäster i Microsoft 365 grupp, visar gästanvändare och använder PowerShell för att styra gäståtkomsten.
ms.openlocfilehash: c52f0094e724040b71d5d72cded049fed57e3969
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571943"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Hantera gäståtkomst i Microsoft 365 grupper

Som standard är gäståtkomst för Microsoft 365 grupper aktiverad för din organisation. Administratörer kan styra om gäståtkomst ska tillåtas till grupper för hela organisationen eller för enskilda grupper.

När den är aktiverad kan gruppmedlemmar bjuda in gästanvändare till en Microsoft 365 grupp via Outlook på webben. Inbjudningar skickas till gruppägaren för godkännande.

När gästanvändaren har godkänts läggs den till i katalogen och gruppen.

> [!Note]
> Yammer Enterprise nätverk som är i inbyggt läge eller [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) inte stöder nätverksgäster.
> Microsoft 365 Anslutna Yammer-grupper har för närvarande inte stöd för gäståtkomst, men du kan skapa icke-anslutna, externa grupper i Yammer nätverk. Se [Skapa och hantera externa grupper i Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) för instruktioner.

Gäståtkomst i grupper används ofta som en del av ett bredare scenario som inkluderar SharePoint eller Teams. Dessa tjänster har sina egna inställningar för gästdelning. Fullständiga instruktioner för hur du konfigurerar gästdelning mellan grupper, SharePoint och Teams finns i:

- [Samarbeta med gäster på en webbplats](../../solutions/collaborate-in-site.md)
- [Samarbeta med gäster i en grupp](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Hantera gäståtkomst för grupper

Om du vill aktivera eller inaktivera gäståtkomst i grupper kan du göra det i Microsoft 365 administrationscenter.

1. Gå till Visa alla  inställningar för Inställningar org och välj Microsoft 365 grupper \>  \>  på **fliken Tjänster.** 
  
2. På sidan **Microsoft 365 grupper** väljer du om du vill låta personer utanför organisationen komma åt gruppresurser eller låta gruppägare lägga till personer utanför organisationen i grupper.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Lägga till gäster i Microsoft 365 grupp från administrationscentret

Om gästen redan finns i din katalog kan du lägga till dem i dina grupper Microsoft 365 administrationscentret. (Grupper med dynamiskt medlemskap [måste hanteras i Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)
  
1. Gå till sidan Gruppera grupper i  >  **administrationscentret.**
  
2. Klicka på den grupp som du vill lägga till gästen i och **välj Visa alla och hantera** medlemmar på **fliken** Medlemmar. 
  
4. Välj **Lägg till** medlemmar och välj namnet på den gäst som du vill lägga till.
    
5. Välj **Spara**.

Om du vill lägga till en gäst i katalogen direkt kan du lägga [till Azure Active Directory B2B-samarbetsanvändare i Azure Portal](/azure/active-directory/b2b/add-users-administrator).

Om du vill redigera någon av gästens information kan du lägga [till eller uppdatera en användares profilinformation med hjälp av Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

## <a name="related-content"></a>Relaterat innehåll

[Blockera gästanvändare från en viss grupp](../../solutions/per-group-guest-access.md) (artikel)

[Hantera gruppmedlemskap i Microsoft 365 administrationscenter](add-or-remove-members-from-groups.md) (artikel)
  
[Azure Active Directory åtkomstrecensioner](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (artikel)

[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (artikel)