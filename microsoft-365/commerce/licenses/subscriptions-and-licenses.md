---
title: Förstå prenumerationer och licenser i Microsoft 365 för företag
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Läs mer om prenumerationer och licenser i Microsoft 365 för företag.
ms.date: 07/01/2020
ms.openlocfilehash: 9f8576b00b942c4b38d6192770bd2128afb4b104
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015965"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>Förstå prenumerationer och licenser i Microsoft 365 för företag

När du köper en prenumeration på Microsoft 365 för företag registrerar du dig för en uppsättning appar och tjänster som du betalar för antingen månadsvis eller årsvis. Vilka program och tjänster du får som en del av prenumerationen beror på vilken produkt du har köpt, till exempel Microsoft 365 Apps for business eller Microsoft 365 Business Standard. Du kan se vad som medföljer varje produkt på [sidan Microsoft 365 för små och medelstora företag.](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1)

När du köper en prenumeration anger du det antal licenser som du behöver, baserat på hur många personer som finns i organisationen. När du har köpt en prenumeration skapar du konton för personer i organisationen och tilldelar sedan en licens till varje person. När dina organisationsbehov ändras kan du köpa fler licenser för att anpassa nya personer eller tilldela om licenser till andra användare när någon lämnar organisationen.

Om du har mer än en prenumeration kan du tilldela licenser till olika personer för varje prenumeration. Du kan till exempel tilldela alla användare till alla Microsoft 365-program och -tjänster som en del av en Microsoft 365 Business Standard-prenumeration. Du kan också tilldela en delmängd användare till Visio Online via en separat Visio-prenumeration.

## <a name="how-many-devices-can-people-install-office-on"></a>Hur många enheter går det att installera Office på?

Om din prenumeration innehåller någon av följande produkter kan varje person installera Office på upp till fem datorer eller Mac, fem surfplattor och fem telefoner.

:::row:::
   :::column span="":::
        - Microsoft 365 Apps för företag – Microsoft 365 Apps for enterprise – Microsoft 365 Business Standard – Microsoft 365 Business Premium – Microsoft 365 A3 - Microsoft 365 A5
   :::column-end:::
   :::column span="":::
        - Microsoft 365 E3 - Microsoft 365 E5 - Office 365 A1 Plus - Office 365 A3 - Office 365 A5 - Office 365 E3 - Office 365 E5
   :::column-end:::
:::row-end:::

## <a name="what-happens-when-you-assign-a-license-to-someone"></a>Vad händer när du tilldelar en licens till någon?

I följande tabell anges vad som sker automatiskt när du tilldelar en licens till en person:
  
|**Om prenumerationen har den här tjänsten**|**sker detta automatiskt**|
|:-----|:-----|
|Exchange Online  <br/> |En postlåda skapas för den personen. <br/> Mer information om serviceavtalet för den här uppgiften finns i ["Ställa in..." meddelanden i Microsoft 365 admin center](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center). |
|SharePoint Online  <br/> |Personen tilldelas redigeringsbehörigheter på SharePoint Online-standardgruppwebbplatsen.  <br/> |
|Skype för företag - Online  <br/> |Personen har tillgång till de funktioner som är associerade med licensen.  <br/> |
| Microsoft 365 Apps för företag  <br/> |Personen kan ladda ned Office-appar på upp till fem Mac-datorer eller datorer, fem surfplattor och fem smartphones.  <br/> |

## <a name="understand-licenses-for-non-user-mailboxes"></a>Allmänt om licenser för postlådor som inte är kopplade till någon användare

You don't need to assign licenses to resource mailboxes, room mailboxes, and shared mailboxes, except when they are over their storage quota of 50 gigabytes (GB). For more about non-user mailboxes, see the following articles:
  
- [Skapa en delad postlåda](../../admin/email/create-a-shared-mailbox.md)
- [Ta bort en licens från en delad postlåda](../../admin/email/remove-license-from-shared-mailbox.md)
- [Delade postlådor i Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes) för alla andra Microsoft 365-abonnemang.
- [Skapa och hantera rumspostlådor](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-room-mailboxes)
- [Hantera utrustningspostlådor](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-equipment-mailboxes)

## <a name="who-can-assign-licenses"></a>Vem kan tilldela licenser?

Different types of admins can work with licenses in different ways, depending on their roles. The following table lists the most common options. For a complete list of admin roles and privileges, see [About admin roles](../../admin/add-users/about-admin-roles.md).
  
|**Administratörsroller**|**Tilldela en licens**|**Ta bort tilldelning av en licens**|**Köp fler licenser**|**Ta bort ett konto**|
|:-----|:-----|:-----|:-----|:-----|
|Faktureringsadministratör  <br/> |Nej  <br/> |Nej  <br/> |Ja  <br/> |Nej  <br/> |
|Global administratör  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |
|Licensadministratör <br/> |Ja <br/>|Ja <br/> |Nej <br/> |Nej <br/> |
|Administration av servicesupport  <br/> |Nej  <br/> |Nej  <br/> |Nej  <br/> |Nej  <br/> |
|Användaradministratör  <br/> |Ja  <br/> |Ja  <br/> |Nej  <br/> |Ja  <br/> |

## <a name="related-content"></a>Relaterat innehåll

[Köpa eller ta bort licenser för din företagsprenumeration](buy-licenses.md) (artikel)\
[Tilldela licenser till användare](../../admin/manage/assign-licenses-to-users.md) (artikel)\
[Ta bort tilldelning av licenser från användare](../../admin/manage/remove-licenses-from-users.md) (artikel)\
[Ta bort en licens från en delad postlåda](../../admin/email/remove-license-from-shared-mailbox.md) (artikel)