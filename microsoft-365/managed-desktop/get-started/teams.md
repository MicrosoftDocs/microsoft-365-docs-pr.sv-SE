---
title: Microsoft Teams
description: Hur Teams installeras på enheter och uppdateras efteråt
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation, appar, verksamhetsbaserade appar, verksamhetsbaserade appar
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: 01a3adc7829bbb94f36649f69ba6ef15dbe6b3c2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920662"
---
# <a name="microsoft-teams"></a><span data-ttu-id="9491f-104">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9491f-104">Microsoft Teams</span></span>

<span data-ttu-id="9491f-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) är en [meddelandeapp](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) för din organisation som även tillhandahåller en arbetsyta för samarbete och kommunikation i realtid, möten, fil- och appdelning.</span><span class="sxs-lookup"><span data-stu-id="9491f-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) is a [messaging app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) for your organization that also provides a workspace for real-time collaboration and communication, meetings, and file and app sharing.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="9491f-106">Inledande distribution</span><span class="sxs-lookup"><span data-stu-id="9491f-106">Initial deployment</span></span>

<span data-ttu-id="9491f-107">De flesta maskinvaruleverantörer har ännu inte några Teams som en del av sina bilder, så Microsoft Hanterat skrivbord distribuerar Teams till dina enheter med hjälp av Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="9491f-107">Most hardware vendors don't yet include Teams as a part of their images, so Microsoft Managed Desktop deploys Teams to your devices by using Microsoft Intune.</span></span> <span data-ttu-id="9491f-108">Alla hanterade enheter har [Teams .msi installerat,](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) vilket säkerställer att alla användare som loggar in på en enhet Microsoft Teams redo att använda.</span><span class="sxs-lookup"><span data-stu-id="9491f-108">All managed devices have the [Teams .msi package](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) installed, ensuring that all users who sign in to a device have Microsoft Teams ready to use.</span></span> <span data-ttu-id="9491f-109">När paketet har installerats klart startas Teams och en genväg läggs till på skrivbordet.</span><span class="sxs-lookup"><span data-stu-id="9491f-109">When the package first finishes installing, Teams automatically starts and adds a shortcut to the desktop.</span></span>

### <a name="microsoft-intune-changes"></a><span data-ttu-id="9491f-110">Microsoft Intune ändringar</span><span class="sxs-lookup"><span data-stu-id="9491f-110">Microsoft Intune changes</span></span>

<span data-ttu-id="9491f-111">Microsoft Hanterat skrivbord lägger till två program i Azure AD-organisationen för Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9491f-111">Microsoft Managed Desktop adds two applications to your Azure AD organization for Microsoft Teams.</span></span> <span data-ttu-id="9491f-112">De distribueras till antingen 64- eller 32-bitarsklienter efter behov för enheten:</span><span class="sxs-lookup"><span data-stu-id="9491f-112">They are deployed to either 64-bit or 32-bit clients as appropriate for the device:</span></span>  

- <span data-ttu-id="9491f-113">Modern workplace – Teams Machine Wide Installer x64</span><span class="sxs-lookup"><span data-stu-id="9491f-113">Modern Workplace – Teams Machine Wide Installer x64</span></span>  
- <span data-ttu-id="9491f-114">Modern workplace – Teams Machine Wide Installer x32</span><span class="sxs-lookup"><span data-stu-id="9491f-114">Modern Workplace – Teams Machine Wide Installer x32</span></span>

## <a name="updates"></a><span data-ttu-id="9491f-115">Uppdateringar</span><span class="sxs-lookup"><span data-stu-id="9491f-115">Updates</span></span>

<span data-ttu-id="9491f-116">Teams följer en separat uppdateringssökväg från Microsoft 365-appar för företag och själva skrivbordsklienten uppdateras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="9491f-116">Teams follows a separate update path from Microsoft 365 Apps for enterprise and the desktop client updates itself automatically.</span></span> <span data-ttu-id="9491f-117">Teams söker efter uppdateringar efter några timmar, laddar ned dem och väntar sedan på att datorn ska vara inaktiv innan uppdateringen installeras utan att du gör en tyst installation.</span><span class="sxs-lookup"><span data-stu-id="9491f-117">Teams checks for updates every few hours, downloads them, and then waits for the computer to be idle before silently installing the update.</span></span>  

<span data-ttu-id="9491f-118">Produktgruppen Teams inte tillåter att administratörer styr uppdateringarna, så det Microsoft Hanterat skrivbord standardkanalen [för automatisk uppdatering.](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)</span><span class="sxs-lookup"><span data-stu-id="9491f-118">The Teams product group doesn't allow admins to control updates, so Microsoft Managed Desktop uses the [standard automatic update channel](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span></span>

### <a name="manually-updating-teams"></a><span data-ttu-id="9491f-119">Uppdatera Teams</span><span class="sxs-lookup"><span data-stu-id="9491f-119">Manually updating Teams</span></span>

<span data-ttu-id="9491f-120">Enskilda användare kan också ladda ned uppdateringar genom **att välja** Sök efter uppdateringar i den    \*\*\*\*   nedrullningsbara menyn Profil längst upp till höger i programmet.</span><span class="sxs-lookup"><span data-stu-id="9491f-120">Individual users can also download updates by selecting **Check for updates** on the **Profile** drop-down menu at the top right of the app.</span></span> <span data-ttu-id="9491f-121">Om det finns en uppdatering kommer den att laddas ned och installeras tyst när datorn är inaktiv.</span><span class="sxs-lookup"><span data-stu-id="9491f-121">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

## <a name="delivery-optimization-of-updates"></a><span data-ttu-id="9491f-122">Leveransoptimering av uppdateringar</span><span class="sxs-lookup"><span data-stu-id="9491f-122">Delivery optimization of updates</span></span>

<span data-ttu-id="9491f-123">Leveransoptimering för Teams är aktiverat som standard och kräver ingen åtgärd från administratörer eller användare.</span><span class="sxs-lookup"><span data-stu-id="9491f-123">Delivery optimization for Teams updates is turned on by default and requires no action from admins or users.</span></span>