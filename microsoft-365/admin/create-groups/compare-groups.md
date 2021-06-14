---
title: Jämföra grupper
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: Gruppmedlemmar i Microsoft 365 en grupp-e-post och en delad arbetsyta för konversationer, filer och kalenderhändelser, Stream samt en Planner.
ms.openlocfilehash: 038c4b9f6d9d28e62c0fb9b8f117db96ac42ddfb
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903846"
---
# <a name="compare-groups"></a>Jämföra grupper

I avsnittet **Grupper** i administrationscentret för Office 365 kan du skapa och hantera följande typer av grupper: 

- **Microsoft 365-grupper** (tidigare Office 365-grupper) används för samarbete mellan användare, både inom och utanför företaget.
- **Distributionsgrupper** används för att skicka e-postaviseringar till en grupp personer.
- **Säkerhetsgrupper** används för att bevilja åtkomst till resurser som SharePoint-webbplatser.
- **E-postaktiverade säkerhetsgrupper** används för att bevilja åtkomst till resurser som SharePoint och för att skicka e-postmeddelanden till dessa användare.
- **Delade postlådor** används när flera personer behöver åtkomst till samma postlåda, t. ex. företagsinformation och supportens e-postadress.

## <a name="microsoft-365-groups"></a>Microsoft 365-grupper

Microsoft 365-grupper används för samarbete mellan användare, både inom och utanför företaget. Med varje Microsoft 365-grupp får medlemmarna en grupp-e-post och en delad arbetsyta för konversationer, filer och kalenderhändelser, Stream samt en planerare.

Du kan lägga till personer utanför organisationen i en grupp så länge som detta har [aktiverats av administratören](manage-guest-access-in-groups.md). Du kan också tillåta externa avsändare att skicka e-post till gruppens e-postadress.

Microsoft 365-grupper kan vara [konfigurerade för dynamiskt medlemskap i Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type), så att gruppmedlemmarna kan läggas till eller tas bort automatiskt utifrån användarattribut, till exempel avdelning, plats, befattning osv.

Microsoft 365-grupper kan nås via mobilappar, t. ex. Outlook för iOS och Outlook för Android.

Gruppmedlemmar kan skicka som eller skicka för gruppens e-postadress om det har [Aktiverats av administratören](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md).

## <a name="distribution-groups"></a>Distributionsgrupper

[Distributionsgrupper](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) används för att skicka aviseringar till en grupp användare. De kan ta emot externa e-postmeddelanden om de aktiveras av administratören.

Distributionsgrupper passar bäst för situationer där du behöver skicka information till en grupp användare, t. ex. "personer i byggnad A" eller "alla på Contoso".

Distributionsgrupper kan [uppgraderas till Microsoft 365-grupper](../manage/upgrade-distribution-lists.md).

Distributionsgrupper kan läggas till i ett team i Microsoft Teams.

## <a name="security-groups"></a>Säkerhetsgrupper

[Säkerhetsgrupper](../email/create-edit-or-delete-a-security-group.md) används för att bevilja åtkomst till Microsoft 365-resurser, t.ex. SharePoint. De kan göra administrationen enklare eftersom du bara behöver administrera gruppen i stället för att lägga till användare i varje resurs individuellt.

Säkerhetsgrupper kan innehålla användare eller enheter. Du kan använda en säkerhetsgrupp för enheter med hanteringstjänster för mobila enheter, till exempel Intune.

Säkerhetsgrupper kan vara [konfigurerade för dynamiskt medlemskap i Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type), så att gruppmedlemmar eller enheter kan läggas till eller tas bort automatiskt utifrån användarattribut, till exempel avdelning, plats, befattning eller enhetsattribut, t. ex. versionen på operativsystem.

Säkerhetsgrupper kan läggas till i ett team.

## <a name="mail-enabled-security-groups"></a>E-postaktiverad säkerhetsgrupp

E-postaktiverade säkerhetsgrupper fungerar på samma sätt som vanliga säkerhetsgrupper förutom att de inte kan hanteras dynamiskt i Azure Active Directory och kan inte innehålla enheter.

De innehåller möjligheten att skicka e-post till alla medlemmar i gruppen.

E-postaktiverade säkerhetsgrupper kan läggas till i ett team.

## <a name="shared-mailboxes"></a>Delade postlådor

[Delade postlådor](../email/create-a-shared-mailbox.md) används när flera personer behöver åtkomst till samma postlåda, t. ex. företagsinformation eller supportens e-postadress, receptionen eller andra funktioner som kan delas av flera personer.

Delade postlådor kan ta emot externa e-postmeddelanden om administratören har aktiverat det.

I delade postlådor finns en kalender som kan användas för samarbete.

Användare som har behörighet till gruppens postlåda kan skicka som eller skicka för postlådans e-postadress om administratören har gett dig behörighet att göra det. Det här är särskilt användbart för postlådor i hjälp och support eftersom användare kan skicka e-post från "contoso support" eller "Byggnad As reception".

Det är inte möjligt att migrera en delad postlåda till en Microsoft 365-grupp. 

## <a name="related-content"></a>Relaterat innehåll

[Läs mer om Microsoft 365-grupper](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2) (artikel)\
[Varför du bör uppgradera dina distributionslistor till grupper i Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188) (artikel)
