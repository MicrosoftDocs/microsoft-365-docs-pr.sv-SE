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
description: Behöver du konfigurera separata administratörer för varje Geo-plats? Lär dig hur du lägger till eller tar bort en geo-administratör i Microsoft 365 multi-geo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9a3d916bfec2c53850f923fb5322298e9ff440ca
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694895"
---
# <a name="add-or-remove-a-geo-administrator-in-microsoft-365-multi-geo"></a><span data-ttu-id="0a854-104">Lägga till eller ta bort en geo-administratör i Microsoft 365 multi-geo</span><span class="sxs-lookup"><span data-stu-id="0a854-104">Add or remove a geo administrator in Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="0a854-105">Du kan konfigurera separata administratörer för varje Geo-plats som du har i klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="0a854-105">You can configure separate administrators for each geo location that you have in your tenant.</span></span> <span data-ttu-id="0a854-106">Dessa administratörer kommer att ha åtkomst till SharePoint Online-och OneDrive-inställningarna som är specifika för deras Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="0a854-106">These administrators will have access to the SharePoint Online and OneDrive settings that are specific to their geo location.</span></span>

<span data-ttu-id="0a854-107">Vissa tjänster-till exempel term lagrings platsen-administreras från central plats och replikeras till satellit platser.</span><span class="sxs-lookup"><span data-stu-id="0a854-107">Some services - such as the term store - are administered from the central location and replicated to satellite locations.</span></span> <span data-ttu-id="0a854-108">Geo-administratören för den centrala platsen har till gång till dessa, medan geo-administratörer för satellit platser inte gör det.</span><span class="sxs-lookup"><span data-stu-id="0a854-108">The geo admin for the central location has access to these, whereas geo admins for satellite locations don't.</span></span>

<span data-ttu-id="0a854-109">Globala administratörer och SharePoint Online-administratörer fortsätter att ha åtkomst till inställningar på Central platsen och alla satellit platser.</span><span class="sxs-lookup"><span data-stu-id="0a854-109">Global administrators and SharePoint Online administrators continue to have access to settings in the central location and all satellite locations.</span></span>

## <a name="configuring-geo-administrators"></a><span data-ttu-id="0a854-110">Konfigurera geo-administratörer</span><span class="sxs-lookup"><span data-stu-id="0a854-110">Configuring geo administrators</span></span>

<span data-ttu-id="0a854-111">Konfigurering av Geo administratörer kräver PowerShell-modulen för SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0a854-111">Configuring geo admins requires SharePoint Online PowerShell module.</span></span>

<span data-ttu-id="0a854-112">Använd [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/Connect-SPOService) för att ansluta till administrations centret för den Geo-plats där du vill lägga till geo-administratören. (Till exempel Connect-SPOService  https://ContosoEUR-admin.sharepoint.com.)</span><span class="sxs-lookup"><span data-stu-id="0a854-112">Use [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/Connect-SPOService) to connect to the admin center of the geo location where you want to add the geo admin. (For example, Connect-SPOService  https://ContosoEUR-admin.sharepoint.com.)</span></span>

<span data-ttu-id="0a854-113">Om du vill visa befintliga geo-administratörer på en plats kör du `Get-SPOGeoAdministrator`</span><span class="sxs-lookup"><span data-stu-id="0a854-113">To view the existing geo admins of a location, run `Get-SPOGeoAdministrator`</span></span>

### <a name="adding-a-user-as-a-geo-admin"></a><span data-ttu-id="0a854-114">Lägga till en användare som geo-administratör</span><span class="sxs-lookup"><span data-stu-id="0a854-114">Adding a user as a geo admin</span></span>

<span data-ttu-id="0a854-115">Om du vill lägga till en användare som geo-administratör kör du `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`</span><span class="sxs-lookup"><span data-stu-id="0a854-115">To add a user as a geo admin, run `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`</span></span>

<span data-ttu-id="0a854-116">Om du vill ta bort en användare som geo-administratör på en plats kör du  `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`</span><span class="sxs-lookup"><span data-stu-id="0a854-116">To remove a user as a Geo Admin of a location, run  `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`</span></span>

### <a name="adding-a-group-as-a-geo-admin"></a><span data-ttu-id="0a854-117">Lägga till en grupp som geo-administratör</span><span class="sxs-lookup"><span data-stu-id="0a854-117">Adding a group as a geo admin</span></span>

<span data-ttu-id="0a854-118">Du kan lägga till en säkerhets grupp eller en e-postaktiverad säkerhets grupp som geo-administratör. (Distributions grupper och Microsoft 365-grupper stöds inte.)</span><span class="sxs-lookup"><span data-stu-id="0a854-118">You can add a security group or a mail-enabled security group as a geo admin. (Distribution groups and Microsoft 365 Groups are not supported.)</span></span>

<span data-ttu-id="0a854-119">Om du vill lägga till en grupp som geo-administratör kör du `Add-SPOGeoAdministrator -GroupAlias <alias>`</span><span class="sxs-lookup"><span data-stu-id="0a854-119">To add a group as a geo administrator, run `Add-SPOGeoAdministrator -GroupAlias <alias>`</span></span>

<span data-ttu-id="0a854-120">Om du vill ta bort en grupp som geo-administratör kör du `Remove-SPOGeoAdministrator -GroupAlias <alias>`</span><span class="sxs-lookup"><span data-stu-id="0a854-120">To remove a group as a geo administrator, run `Remove-SPOGeoAdministrator -GroupAlias <alias>`</span></span>

<span data-ttu-id="0a854-121">Observera att inte alla säkerhets grupper har ett gruppalias.</span><span class="sxs-lookup"><span data-stu-id="0a854-121">Note that not all security groups have a group alias.</span></span> <span data-ttu-id="0a854-122">Om du vill lägga till en säkerhets grupp som inte har ett alias kör du [Get-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/get-msolgroup) för att hämta en lista med grupper, letar reda på säkerhets gruppens ObjectID och kör:</span><span class="sxs-lookup"><span data-stu-id="0a854-122">If you want to add a security group that does not have an alias, run [Get-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/get-msolgroup) to retrieve a list of groups, find your security group's ObjectID, and then run:</span></span>

`Add-SPOGeoAdministrator -ObjectID <ObjectID>`

<span data-ttu-id="0a854-123">Om du vill ta bort en grupp med hjälp av ObjectID kör du `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`</span><span class="sxs-lookup"><span data-stu-id="0a854-123">To remove a group by using the ObjectID, run `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`</span></span>

## <a name="related-topics"></a><span data-ttu-id="0a854-124">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="0a854-124">Related topics</span></span>

[<span data-ttu-id="0a854-125">Add-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="0a854-125">Add-SPOGeoAdministrator</span></span>](https://docs.microsoft.com/powershell/module/sharepoint-online/add-spogeoadministrator)

[<span data-ttu-id="0a854-126">Get-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="0a854-126">Get-SPOGeoAdministrator</span></span>](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spogeoadministrator)

[<span data-ttu-id="0a854-127">Remove-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="0a854-127">Remove-SPOGeoAdministrator</span></span>](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spogeoadministrator)

[<span data-ttu-id="0a854-128">Ange ett alias (smek namn) för en säkerhets grupp</span><span class="sxs-lookup"><span data-stu-id="0a854-128">Set an alias (MailNickName) for a security group</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup)