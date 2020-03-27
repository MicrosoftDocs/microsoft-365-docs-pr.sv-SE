---
title: Jämföra grupper i Office 365
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: Lär dig mer om de typer av grupper som du kan använda i Office 365.
ms.openlocfilehash: 7d0a18606918884381b0bf7863cfac6cafb29c29
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894605"
---
# <a name="compare-groups"></a>Jämföra grupper

I avsnittet **Grupper** i administrationscentret för Office 365 kan du skapa och hantera följande typer av grupper: 

- **Office 365-grupper** används för samarbete mellan användare, både inom och utanför företaget.
- **Distributionsgrupper** används för att skicka aviseringar till en grupp användare.
- **Säkerhetsgrupper** används för att bevilja åtkomst till resurser som SharePoint-webbplatser.
- **E-postaktiverade säkerhetsgrupper** används för att bevilja åtkomst till resurser som SharePoint och för att skicka e-postmeddelanden till dessa användare.
- **Delade postlådor** används när flera personer behöver åtkomst till samma postlåda, t. ex. företagsinformation och supportens e-postadress.

## <a name="office-365-groups"></a>Office 365-grupper

Office 365-grupper används för samarbete mellan användare, både inom och utanför företaget. Med varje Office 365-grupp får medlemmarna en grupp e-post och en delad arbetsyta för konversationer, filer och kalenderhändelser samt en planerare.

Du kan lägga till personer utanför organisationen i en grupp så länge som detta har [aktiverats av administratören](manage-guest-access-in-groups.md). Du kan också tillåta externa avsändare att skicka e-post till gruppens e-postadress.

Office 365-grupper kan vara [konfigurerade för dynamiskt medlemskap i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type), så att gruppmedlemmarna kan läggas till eller tas bort automatiskt utifrån användarattribut, till exempel avdelning, plats, befattning osv.

Office 365-grupper kan nås via mobilappar, t. ex. Outlook för iOS och Outlook för Android.

Gruppmedlemmar kan skicka som eller skicka för gruppens e-postadress om det har [Aktiverats av administratören](allow-members-to-send-as-or-send-on-behalf-of-group.md).

## <a name="distribution-groups"></a>Distributionsgrupper

[Distributionsgrupper](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) används för att skicka aviseringar till en grupp användare. De kan ta emot externa e-postmeddelanden om de aktiveras av administratören.

Distributionsgrupper passar bäst för situationer där du behöver skicka information till en grupp användare, t. ex. "personer i byggnad A" eller "alla på Contoso".

## <a name="security-groups"></a>Säkerhetsgrupper

[Säkerhetsgrupper](../email/create-edit-or-delete-a-security-group.md) används för att bevilja åtkomst till Office 365-resurser, t. ex. SharePoint. De kan göra administrationen enklare eftersom du bara behöver administrera gruppen i stället för att lägga till användare i varje resurs individuellt.

Säkerhetsgrupper kan innehålla användare och enheter. Om du vill skapa en säkerhetsgrupp för enheter kan du använda tjänster för hantering av mobila enheter, t. ex. Intune.

Säkerhetsgrupper kan vara [konfigurerade för dynamiskt medlemskap i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type), så att gruppmedlemmar eller enheter kan läggas till eller tas bort automatiskt utifrån användarattribut, till exempel avdelning, plats, befattning eller enhetsattribut, t. ex. versionen på operativsystem.

## <a name="mail-enabled-security-groups"></a>E-postaktiverad säkerhetsgrupp

E-postaktiverade säkerhetsgrupper fungerar på samma sätt som vanliga säkerhetsgrupper förutom att de inte kan hanteras dynamiskt i Azure Active Directory och kan inte innehålla enheter.

De innehåller möjligheten att skicka e-post till alla medlemmar i gruppen.

## <a name="shared-mailboxes"></a>Delade postlådor

[Delade postlådor](../email/create-a-shared-mailbox.md) används när flera personer behöver åtkomst till samma postlåda, t. ex. företagsinformation eller supportens e-postadress, receptionen eller andra funktioner som kan delas av flera personer.

Delade postlådor kan ta emot externa e-postmeddelanden om administratören har aktiverat det.

Användare som har behörighet till gruppens postlåda kan skicka som eller skicka för postlådans e-postadress om administratören har gett dig behörighet att göra det. Det här är särskilt användbart för postlådor i hjälp och support eftersom användare kan skicka e-post från "contoso support" eller "Byggnad As reception".

Det är för närvarande inte möjligt att migrera en delad postlåda till en Office 365-grupp. Finns det något du önskar? Berätta för oss. **[Rösta här](https://go.microsoft.com/fwlink/?linkid=871518)**.

## <a name="related-articles"></a>Relaterade artiklar

[Läs om Office 365-grupper](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2)
