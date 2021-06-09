---
title: Lägga till eller ta bort en geo-administratör
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords:
- NOCSH
description: Behöver du konfigurera separata administratörer för varje geoplats? Lär dig hur du lägger till eller tar bort en geoadministratör i Microsoft 365 Multi-Geo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 32fe5e934e6a3d6f18c802c3c427974e67c1b454
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905614"
---
# <a name="add-or-remove-a-geo-administrator-in-microsoft-365-multi-geo"></a><span data-ttu-id="e35ef-104">Lägga till eller ta bort en geoadministratör Microsoft 365 i Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="e35ef-104">Add or remove a geo administrator in Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="e35ef-105">Du kan konfigurera separata administratörer för varje geoplats som du har i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="e35ef-105">You can configure separate administrators for each geo location that you have in your tenant.</span></span> <span data-ttu-id="e35ef-106">De här administratörerna har tillgång till de SharePoint Online OneDrive de inställningar som är specifika för deras geografiska position.</span><span class="sxs-lookup"><span data-stu-id="e35ef-106">These administrators will have access to the SharePoint Online and OneDrive settings that are specific to their geo location.</span></span>

<span data-ttu-id="e35ef-107">Vissa tjänster, till exempel termlager, administreras från den centrala platsen och replikeras till satellitplatser.</span><span class="sxs-lookup"><span data-stu-id="e35ef-107">Some services - such as the term store - are administered from the central location and replicated to satellite locations.</span></span> <span data-ttu-id="e35ef-108">Geoadministratören för den centrala platsen har åtkomst till dessa, men geoadministratörer för satellitplatser har det inte.</span><span class="sxs-lookup"><span data-stu-id="e35ef-108">The geo admin for the central location has access to these, whereas geo admins for satellite locations don't.</span></span>

<span data-ttu-id="e35ef-109">Globala administratörer och SharePoint Online-administratörer fortsätter att ha åtkomst till inställningar på den centrala platsen och alla satellitplatser.</span><span class="sxs-lookup"><span data-stu-id="e35ef-109">Global administrators and SharePoint Online administrators continue to have access to settings in the central location and all satellite locations.</span></span>

## <a name="configuring-geo-administrators"></a><span data-ttu-id="e35ef-110">Konfigurera geoadministratörer</span><span class="sxs-lookup"><span data-stu-id="e35ef-110">Configuring geo administrators</span></span>

<span data-ttu-id="e35ef-111">Om du vill konfigurera geoadministratörer SharePoint PowerShell-modulen Online.</span><span class="sxs-lookup"><span data-stu-id="e35ef-111">Configuring geo admins requires SharePoint Online PowerShell module.</span></span>

<span data-ttu-id="e35ef-112">Använd [Anslut-SPOService för](/powershell/module/sharepoint-online/Connect-SPOService) att ansluta till administrationscentret för den geoplats där du vill lägga till geoadministratören. (Till exempel Connect-SPOServicehttps://ContosoEUR-admin.sharepoint.com.)</span><span class="sxs-lookup"><span data-stu-id="e35ef-112">Use [Connect-SPOService](/powershell/module/sharepoint-online/Connect-SPOService) to connect to the admin center of the geo location where you want to add the geo admin. (For example, Connect-SPOService  https://ContosoEUR-admin.sharepoint.com.)</span></span>

<span data-ttu-id="e35ef-113">Om du vill visa befintliga geoadministratörer för en plats kör du `Get-SPOGeoAdministrator`</span><span class="sxs-lookup"><span data-stu-id="e35ef-113">To view the existing geo admins of a location, run `Get-SPOGeoAdministrator`</span></span>

### <a name="adding-a-user-as-a-geo-admin"></a><span data-ttu-id="e35ef-114">Lägga till en användare som geoadministratör</span><span class="sxs-lookup"><span data-stu-id="e35ef-114">Adding a user as a geo admin</span></span>

<span data-ttu-id="e35ef-115">Om du vill lägga till en användare som geoadministratör kör du `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`</span><span class="sxs-lookup"><span data-stu-id="e35ef-115">To add a user as a geo admin, run `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`</span></span>

<span data-ttu-id="e35ef-116">Om du vill ta bort en användare som geoadministratör för en plats kör du  `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`</span><span class="sxs-lookup"><span data-stu-id="e35ef-116">To remove a user as a Geo Admin of a location, run  `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`</span></span>

### <a name="adding-a-group-as-a-geo-admin"></a><span data-ttu-id="e35ef-117">Lägga till en grupp som geoadministratör</span><span class="sxs-lookup"><span data-stu-id="e35ef-117">Adding a group as a geo admin</span></span>

<span data-ttu-id="e35ef-118">Du kan lägga till en säkerhetsgrupp eller en e-postaktiverad säkerhetsgrupp som geoadministratör. (Distributionsgrupper och Microsoft 365-grupper stöds inte.)</span><span class="sxs-lookup"><span data-stu-id="e35ef-118">You can add a security group or a mail-enabled security group as a geo admin. (Distribution groups and Microsoft 365 Groups are not supported.)</span></span>

<span data-ttu-id="e35ef-119">Om du vill lägga till en grupp som geoadministratör kör du `Add-SPOGeoAdministrator -GroupAlias <alias>`</span><span class="sxs-lookup"><span data-stu-id="e35ef-119">To add a group as a geo administrator, run `Add-SPOGeoAdministrator -GroupAlias <alias>`</span></span>

<span data-ttu-id="e35ef-120">Om du vill ta bort en grupp som geoadministratör kör du `Remove-SPOGeoAdministrator -GroupAlias <alias>`</span><span class="sxs-lookup"><span data-stu-id="e35ef-120">To remove a group as a geo administrator, run `Remove-SPOGeoAdministrator -GroupAlias <alias>`</span></span>

<span data-ttu-id="e35ef-121">Observera att inte alla säkerhetsgrupper har ett gruppalias.</span><span class="sxs-lookup"><span data-stu-id="e35ef-121">Note that not all security groups have a group alias.</span></span> <span data-ttu-id="e35ef-122">Om du vill lägga till en säkerhetsgrupp som inte har ett alias kör du [Get-MsolGroup](/powershell/module/msonline/get-msolgroup) för att hämta en lista med grupper, letar reda på säkerhetsgruppens ObjectID och kör sedan:</span><span class="sxs-lookup"><span data-stu-id="e35ef-122">If you want to add a security group that does not have an alias, run [Get-MsolGroup](/powershell/module/msonline/get-msolgroup) to retrieve a list of groups, find your security group's ObjectID, and then run:</span></span>

`Add-SPOGeoAdministrator -ObjectID <ObjectID>`

<span data-ttu-id="e35ef-123">Om du vill ta bort en grupp med hjälp av Objekt-ID:t kör du `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`</span><span class="sxs-lookup"><span data-stu-id="e35ef-123">To remove a group by using the ObjectID, run `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`</span></span>

## <a name="related-topics"></a><span data-ttu-id="e35ef-124">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e35ef-124">Related topics</span></span>

[<span data-ttu-id="e35ef-125">Add-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="e35ef-125">Add-SPOGeoAdministrator</span></span>](/powershell/module/sharepoint-online/add-spogeoadministrator)

[<span data-ttu-id="e35ef-126">Get-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="e35ef-126">Get-SPOGeoAdministrator</span></span>](/powershell/module/sharepoint-online/get-spogeoadministrator)

[<span data-ttu-id="e35ef-127">Remove-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="e35ef-127">Remove-SPOGeoAdministrator</span></span>](/powershell/module/sharepoint-online/remove-spogeoadministrator)

[<span data-ttu-id="e35ef-128">Ange ett alias (MailNickName) för en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="e35ef-128">Set an alias (MailNickName) for a security group</span></span>](/powershell/module/azuread/set-azureadgroup)