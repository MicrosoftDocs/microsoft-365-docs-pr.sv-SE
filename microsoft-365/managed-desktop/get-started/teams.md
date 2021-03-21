---
title: Microsoft Teams
description: Hur Teams installeras på enheter och uppdateras efteråt
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation, appar, verksamhetsbaserade appar, verksamhetsbaserade appar
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
# <a name="microsoft-teams"></a><span data-ttu-id="f530e-104">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f530e-104">Microsoft Teams</span></span>

<span data-ttu-id="f530e-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) är en [meddelandeapp](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) för din organisation som även tillhandahåller en arbetsyta för samarbete och kommunikation i realtid, möten samt fil- och appdelning.</span><span class="sxs-lookup"><span data-stu-id="f530e-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) is a [messaging app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) for your organization that also provides a workspace for real-time collaboration and communication, meetings, and file and app sharing.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="f530e-106">Inledande distribution</span><span class="sxs-lookup"><span data-stu-id="f530e-106">Initial deployment</span></span>

<span data-ttu-id="f530e-107">De flesta maskinvaruleverantörer har ännu inte Teams som en del av sina bilder, så Microsoft Managed Desktop distribuerar Teams till dina enheter med hjälp av Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="f530e-107">Most hardware vendors don't yet include Teams as a part of their images, so Microsoft Managed Desktop deploys Teams to your devices by using Microsoft Intune.</span></span> <span data-ttu-id="f530e-108">Alla hanterade enheter har [Teams .msi-paketet](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) installerat, vilket säkerställer att alla användare som loggar in på en enhet har Microsoft Teams redo att använda.</span><span class="sxs-lookup"><span data-stu-id="f530e-108">All managed devices have the [Teams .msi package](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) installed, ensuring that all users who sign in to a device have Microsoft Teams ready to use.</span></span> <span data-ttu-id="f530e-109">När paketet har installerats klart startas Teams automatiskt och en genväg läggs till på skrivbordet.</span><span class="sxs-lookup"><span data-stu-id="f530e-109">When the package first finishes installing, Teams automatically starts and adds a shortcut to the desktop.</span></span>

### <a name="microsoft-intune-changes"></a><span data-ttu-id="f530e-110">Ändringar i Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f530e-110">Microsoft Intune changes</span></span>

<span data-ttu-id="f530e-111">Microsoft Managed Desktop lägger till två program i din Azure AD-organisation för Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f530e-111">Microsoft Managed Desktop adds two applications to your Azure AD organization for Microsoft Teams.</span></span> <span data-ttu-id="f530e-112">De distribueras till antingen 64- eller 32-bitarsklienter efter behov för enheten:</span><span class="sxs-lookup"><span data-stu-id="f530e-112">They are deployed to either 64-bit or 32-bit clients as appropriate for the device:</span></span>  

- <span data-ttu-id="f530e-113">Modern arbetsplats – Teams Machine Wide Installer x64</span><span class="sxs-lookup"><span data-stu-id="f530e-113">Modern Workplace – Teams Machine Wide Installer x64</span></span>  
- <span data-ttu-id="f530e-114">Modern arbetsplats – Teams Machine Wide Installer x32</span><span class="sxs-lookup"><span data-stu-id="f530e-114">Modern Workplace – Teams Machine Wide Installer x32</span></span>

## <a name="updates"></a><span data-ttu-id="f530e-115">Uppdateringar</span><span class="sxs-lookup"><span data-stu-id="f530e-115">Updates</span></span>

<span data-ttu-id="f530e-116">Teams följer en separat uppdateringssökväg från Microsoft 365-apparna för företag, och själva skrivbordsklienten uppdateras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="f530e-116">Teams follows a separate update path from Microsoft 365 Apps for enterprise and the desktop client updates itself automatically.</span></span> <span data-ttu-id="f530e-117">Teams söker efter uppdateringar efter några timmar, laddar ned dem och väntar sedan på att datorn är inaktiv innan uppdateringen installeras utan att du blir tyst.</span><span class="sxs-lookup"><span data-stu-id="f530e-117">Teams checks for updates every few hours, downloads them, and then waits for the computer to be idle before silently installing the update.</span></span>  

<span data-ttu-id="f530e-118">Teams-produktgruppen tillåter inte att administratörer styr uppdateringar, så Microsoft Managed Desktop använder [standardkanalen för automatisk uppdatering.](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)</span><span class="sxs-lookup"><span data-stu-id="f530e-118">The Teams product group doesn't allow admins to control updates, so Microsoft Managed Desktop uses the [standard automatic update channel](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span></span>

### <a name="manually-updating-teams"></a><span data-ttu-id="f530e-119">Uppdatera Teams manuellt</span><span class="sxs-lookup"><span data-stu-id="f530e-119">Manually updating Teams</span></span>

<span data-ttu-id="f530e-120">Enskilda användare kan också ladda ned uppdateringar genom **att välja** Sök efter uppdateringar i den    \*\*\*\*   nedrullningsbara menyn Profil längst upp till höger i programmet.</span><span class="sxs-lookup"><span data-stu-id="f530e-120">Individual users can also download updates by selecting **Check for updates** on the **Profile** drop-down menu at the top right of the app.</span></span> <span data-ttu-id="f530e-121">Om det finns en uppdatering kommer den att laddas ned och installeras tyst när datorn är inaktiv.</span><span class="sxs-lookup"><span data-stu-id="f530e-121">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

## <a name="delivery-optimization-of-updates"></a><span data-ttu-id="f530e-122">Leveransoptimering av uppdateringar</span><span class="sxs-lookup"><span data-stu-id="f530e-122">Delivery optimization of updates</span></span>

<span data-ttu-id="f530e-123">Leveransoptimering för Teams-uppdateringar är aktiverat som standard och kräver ingen åtgärd från administratörer eller användare.</span><span class="sxs-lookup"><span data-stu-id="f530e-123">Delivery optimization for Teams updates is turned on by default and requires no action from admins or users.</span></span>