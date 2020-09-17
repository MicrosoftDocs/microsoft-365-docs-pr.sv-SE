---
title: Microsoft Teams
description: Hur team är installerat på enheter och uppdateras efteråt
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation, appar, branschspecifika appar, LOB-appar
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: ea2ef7637a8d360e3b598aec4852425d977ae4ec
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950961"
---
# <a name="microsoft-teams"></a><span data-ttu-id="577ac-104">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="577ac-104">Microsoft Teams</span></span>

<span data-ttu-id="577ac-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) är ett [meddelande program](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) för din organisation som också tillhandahåller en arbets yta för samarbete och kommunikation i real tid, möten och fil-och program delning.</span><span class="sxs-lookup"><span data-stu-id="577ac-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) is a [messaging app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) for your organization that also provides a workspace for real-time collaboration and communication, meetings, and file and app sharing.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="577ac-106">Inledande distribution</span><span class="sxs-lookup"><span data-stu-id="577ac-106">Initial deployment</span></span>

<span data-ttu-id="577ac-107">De flesta maskin varu leverantörer inkluderar inte team som en del av bilderna, så Microsoft Managed Desktop distribuerar Teams till dina enheter med hjälp av Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="577ac-107">Most hardware vendors don't yet include Teams as a part of their images, so Microsoft Managed Desktop deploys Teams to your devices by using Microsoft Intune.</span></span> <span data-ttu-id="577ac-108">Alla hanterade enheter har [Teams. MSI-paketet](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) installerat, så att alla användare som loggar in på en enhet kan använda Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="577ac-108">All managed devices have the [Teams .msi package](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) installed, ensuring that all users who sign in to a device have Microsoft Teams ready to use.</span></span> <span data-ttu-id="577ac-109">När paketet först slutar installeras startar Teams automatiskt och lägger till en genväg på Skriv bordet.</span><span class="sxs-lookup"><span data-stu-id="577ac-109">When the package first finishes installing, Teams automatically starts and adds a shortcut to the desktop.</span></span>

### <a name="microsoft-intune-changes"></a><span data-ttu-id="577ac-110">Ändringar i Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="577ac-110">Microsoft Intune changes</span></span>

<span data-ttu-id="577ac-111">Microsoft Managed Desktop lägger till två program i din Azure AD-organisation för Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="577ac-111">Microsoft Managed Desktop adds two applications to your Azure AD organization for Microsoft Teams.</span></span> <span data-ttu-id="577ac-112">De distribueras till antingen 64-bitars-eller 32-bitars klienter enligt vad som är lämpligt för enheten:</span><span class="sxs-lookup"><span data-stu-id="577ac-112">They are deployed to either 64-bit or 32-bit clients as appropriate for the device:</span></span>  

- <span data-ttu-id="577ac-113">Modern arbets plats – Teams Machine wide installations program x64</span><span class="sxs-lookup"><span data-stu-id="577ac-113">Modern Workplace – Teams Machine Wide Installer x64</span></span>  
- <span data-ttu-id="577ac-114">Modern arbets plats – Teams Machine wide Installer x32</span><span class="sxs-lookup"><span data-stu-id="577ac-114">Modern Workplace – Teams Machine Wide Installer x32</span></span>

## <a name="updates"></a><span data-ttu-id="577ac-115">Uppdateringar</span><span class="sxs-lookup"><span data-stu-id="577ac-115">Updates</span></span>

<span data-ttu-id="577ac-116">Teams följer en separat uppdaterings väg från Microsoft 365-appar för företag och Station ära klient uppdateringar automatiskt.</span><span class="sxs-lookup"><span data-stu-id="577ac-116">Teams follows a separate update path from Microsoft 365 Apps for enterprise and the desktop client updates itself automatically.</span></span> <span data-ttu-id="577ac-117">Teams söker efter uppdateringar med några timmars mellanrum, laddar ned dem och väntar sedan på att datorn ska vara inaktiv innan den installeras.</span><span class="sxs-lookup"><span data-stu-id="577ac-117">Teams checks for updates every few hours, downloads them, and then waits for the computer to be idle before silently installing the update.</span></span>  

<span data-ttu-id="577ac-118">Teams produkt gruppen tillåter inte att administratörer styr uppdateringar, så Microsoft Managed Desktop använder standard ikonen för [Automatisk uppdatering](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span><span class="sxs-lookup"><span data-stu-id="577ac-118">The Teams product group doesn't allow admins to control updates, so Microsoft Managed Desktop uses the [standard automatic update channel](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span></span>

### <a name="manually-updating-teams"></a><span data-ttu-id="577ac-119">Uppdatera Teams manuellt</span><span class="sxs-lookup"><span data-stu-id="577ac-119">Manually updating Teams</span></span>

<span data-ttu-id="577ac-120">Enskilda användare kan också ladda ner uppdateringar genom att välja **Sök efter uppdateringar**   på den **Profile**   nedrullningsbara menyn profil längst upp till höger i appen.</span><span class="sxs-lookup"><span data-stu-id="577ac-120">Individual users can also download updates by selecting **Check for updates** on the **Profile** drop-down menu at the top right of the app.</span></span> <span data-ttu-id="577ac-121">Om det finns en uppdatering hämtas den och installeras tyst när datorn är inaktiv.</span><span class="sxs-lookup"><span data-stu-id="577ac-121">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

## <a name="delivery-optimization-of-updates"></a><span data-ttu-id="577ac-122">Leverans optimering för uppdateringar</span><span class="sxs-lookup"><span data-stu-id="577ac-122">Delivery optimization of updates</span></span>

<span data-ttu-id="577ac-123">Leverans optimering för Teams-uppdateringar är aktiverat som standard och kräver ingen åtgärd från administratörer eller användare.</span><span class="sxs-lookup"><span data-stu-id="577ac-123">Delivery optimization for Teams updates is turned on by default and requires no action from admins or users.</span></span> 