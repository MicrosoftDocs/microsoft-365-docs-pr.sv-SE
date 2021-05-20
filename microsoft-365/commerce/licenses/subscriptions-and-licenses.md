---
title: Förstå prenumerationer och licenser i Microsoft 365 för företag
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: Vilka program och tjänster som du får beror på vilken produkt Microsoft 365 har köpt, t.ex. Microsoft 365-applikationer för affärsverksamhet.
ms.date: 07/01/2020
ms.openlocfilehash: 4e93a84df106475417289da168ca472ed5a07475
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582734"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>Förstå prenumerationer och licenser i Microsoft 365 för företag

När du köper en prenumeration på Microsoft 365 för företag registrerar du dig för en uppsättning appar och tjänster som du betalar för, antingen per månad eller per år. Vilka program och tjänster som ingår i prenumerationen beror på vilken produkt du har köpt, till exempel Microsoft 365-applikationer för affärsverksamhet eller Microsoft 365 Business Standard. Du kan se vad som medföljer varje produkt [på Microsoft 365 för små och medelstora](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1) företag.

När du köper en prenumeration anger du det antal licenser som du behöver, baserat på hur många personer som finns i organisationen. När du har köpt en prenumeration skapar du konton för personer i organisationen och tilldelar sedan en licens till varje person. Om behoven i din organisation förändras kan du köpa fler licenser för nya användare eller omtilldela licenser till andra användare när någon lämnar organisationen.

Om du har fler än en prenumeration kan du tilldela licenser till olika personer för varje prenumeration. Du kan till exempel tilldela alla dina användare till alla Microsoft 365-program och -tjänster som en del av Microsoft 365 Business Standard prenumeration. Du kan också tilldela en delmängd av användarna till Visio Online via en separat Visio prenumeration.

## <a name="how-many-devices-can-people-install-office-on"></a>Hur många enheter går det att installera Office på?

Om prenumerationen omfattar någon av följande produkter kan varje person installera Office på upp till fem PC- eller Mac-datorer, fem surfplattor och fem telefoner.

:::row:::
   :::column span="":::
        - Microsoft 365-applikationer för affärsverksamhet - Microsoft 365-appar för företag - Microsoft 365 Business Standard - Microsoft 365 Business Premium - Microsoft 365 A3 - Microsoft 365 A5
   :::column-end:::
   :::column span="":::
        - Microsoft 365 E3 - Microsoft 365 E5 - Office 365 A1 Plus - Office 365 A3 - Office 365 A5 - Office 365 E3 - Office 365 E5
   :::column-end:::
:::row-end:::

## <a name="what-happens-when-you-assign-a-license-to-someone"></a>Vad händer när du tilldelar en licens till någon?

I följande tabell anges vad som sker automatiskt när du tilldelar en licens till en person:
  
|**Om prenumerationen har den här tjänsten**|**sker detta automatiskt**|
|:-----|:-----|
|Exchange Online  <br/> |En postlåda skapas för den personen. <br/> Mer information om SLA för att den här uppgiften ska slutföras finns [i "Konfigurera..." meddelanden i Microsoft 365 administrationscenter.](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center) |
|SharePoint Online  <br/> |Personen tilldelas redigeringsbehörigheter på SharePoint Online-standardgruppwebbplatsen.  <br/> |
|Skype för företag - Online  <br/> |Personen har åtkomst till de funktioner som är kopplade till licensen.  <br/> |
|Microsoft 365-applikationer för företag  <br/> |Personen kan ladda ned Office appar på upp till fem Mac- eller PC-datorer, fem surfplattor och fem smartphones.  <br/> |

## <a name="understand-licenses-for-non-user-mailboxes"></a>Allmänt om licenser för postlådor som inte är kopplade till någon användare

Du behöver inte tilldela licenser till resurspostlådor, rumspostlådor och delade postlådor, förutom när de är över sin lagringskvot på 50 GB. Mer information om postlådor som inte är kopplade till någon användare finns i följande artiklar:
  
- [Skapa en delad postlåda](../../admin/email/create-a-shared-mailbox.md)
- [Ta bort en licens från en delad postlåda](../../admin/email/remove-license-from-shared-mailbox.md)
- [Delade postlådor i Exchange Online](/exchange/collaboration-exo/shared-mailboxes) för alla andra Microsoft 365 abonnemang.
- [Skapa och hantera rumspostlådor](/exchange/recipients-in-exchange-online/manage-room-mailboxes)
- [Hantera utrustningspostlådor](/exchange/recipients-in-exchange-online/manage-equipment-mailboxes)

## <a name="who-can-assign-licenses"></a>Vem kan tilldela licenser?

Olika typer av administratörer kan arbeta med licenser på olika sätt beroende på deras respektive roller. I följande tabell finns de vanligaste alternativen. En fullständig lista över administrationsroller och behörigheter finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  
|**Administratörsroller**|**Tilldela en licens**|**Ta bort en licens**|**Köpa fler licenser**|**Ta bort ett konto**|
|:-----|:-----|:-----|:-----|:-----|
|Faktureringsadministratör  <br/> |Nej  <br/> |Nej  <br/> |Ja  <br/> |Nej  <br/> |
|Global administratör  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |
|Licensadministratör <br/> |Ja <br/>|Ja <br/> |Nej <br/> |Nej <br/> |
|Supportadministratör för tjänst  <br/> |Nej  <br/> |Nej  <br/> |Nej  <br/> |Nej  <br/> |
|Användaradministratör  <br/> |Ja  <br/> |Ja  <br/> |Nej  <br/> |Ja  <br/> |

## <a name="related-content"></a>Relaterat innehåll

[Köpa eller ta bort licenser för din företagsprenumeration](buy-licenses.md) (artikel)\
[Tilldela licenser till användare](../../admin/manage/assign-licenses-to-users.md) (artikel)\
[Ta bort tilldelningen av licenser från användare](../../admin/manage/remove-licenses-from-users.md) (artikel)\
[Ta bort en licens från en delad postlåda](../../admin/email/remove-license-from-shared-mailbox.md) (artikel)
