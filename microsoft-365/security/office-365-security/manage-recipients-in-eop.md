---
title: Hantera mottagare i EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 2921f544-8257-4bae-8e3a-ce9250e9f162
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig mer om e-postmottagare som stöds av Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: eb2855f93083c88725492be2691799c3521bbf8f
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036155"
---
# <a name="manage-recipients-in-eop"></a><span data-ttu-id="d0b3c-103">Hantera mottagare i EOP</span><span class="sxs-lookup"><span data-stu-id="d0b3c-103">Manage recipients in EOP</span></span>

<span data-ttu-id="d0b3c-104">Microsoft Exchange Online Protection (EOP) erbjuder flera sätt att hantera dina e-postmottagare.</span><span class="sxs-lookup"><span data-stu-id="d0b3c-104">Microsoft Exchange Online Protection (EOP) offers several ways to manage your mail recipients.</span></span> <span data-ttu-id="d0b3c-105">Som administratör kan du utföra vissa hanteringsuppgifter i Administrationscenter för Exchange (EAC) eller använda fjärrdata Windows PowerShell och verifiera andra hanteringsuppgifter som utförs i Microsoft 365-administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="d0b3c-105">As an administrator, you can perform certain management tasks within the Exchange admin center (EAC) or using remote Windows PowerShell, and verify other management tasks performed in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="d0b3c-106">EOP stöder följande typer av mottagare:</span><span class="sxs-lookup"><span data-stu-id="d0b3c-106">EOP supports the following types of recipients:</span></span>

- <span data-ttu-id="d0b3c-107">**E-postanvändare:** E-postanvändare är mottagare i dina EOP-hanterade domäner.</span><span class="sxs-lookup"><span data-stu-id="d0b3c-107">**Mail Users**: Mail users are recipients in your EOP managed domains.</span></span> <span data-ttu-id="d0b3c-108">Dessa mottagare har inloggningsuppgifter i organisationen, men de har externa e-postadresser, vilket innebär att deras mottagarpostlådor finns utanför din molnorganisation.</span><span class="sxs-lookup"><span data-stu-id="d0b3c-108">These recipients have logon credentials in your organization, but they have external email addresses, meaning that their recipient mailboxes are located outside of your cloud organization.</span></span>

  <span data-ttu-id="d0b3c-109">Du kan lägga till e-postanvändare så att de kan ta emot e-post och du kan också skapa regler för e-postflöde (kallas även transportregler) för specifika användare.</span><span class="sxs-lookup"><span data-stu-id="d0b3c-109">You can add mail users so that they can receive mail and you can also create mail flow rules (also known as transport rules) for specific users.</span></span> <span data-ttu-id="d0b3c-110">Du kan också tilldela roller till e-postanvändare i organisationen. användare med behörighet för hanteringsrollgrupp kan komma åt Administrationscenter för Exchange (EAC) och utföra vissa hanteringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="d0b3c-110">You can also assign roles to mail users in your organization; users with management role group privileges can access the Exchange admin center (EAC) and perform certain management tasks.</span></span> <span data-ttu-id="d0b3c-111">Mer information om användarroller och hur du tilldelar användarroller i EOP finns [i Hantera administratörsrollgruppbehörigheter i EOP](manage-admin-role-group-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="d0b3c-111">To learn more about user roles and how to assign user roles in EOP, see [Manage admin role group permissions in EOP](manage-admin-role-group-permissions-in-eop.md).</span></span>

  <span data-ttu-id="d0b3c-112">Mer information om hur du hanterar e-postanvändare i EOP finns [i Hantera e-postanvändare i EOP](manage-mail-users-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="d0b3c-112">For more information about managing mail users in EOP, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

- <span data-ttu-id="d0b3c-113">**Grupper**: E-postanvändare kan grupperas tillsammans i distributionsgrupper eller säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="d0b3c-113">**Groups**: Mail users can be grouped together into distribution groups or security groups.</span></span>

<span data-ttu-id="d0b3c-114">Mer information om hur du hanterar grupper i EOP finns [i Hantera grupper i EOP](manage-groups-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="d0b3c-114">For more information about managing groups in EOP, see [Manage groups in EOP](manage-groups-in-eop.md).</span></span>
