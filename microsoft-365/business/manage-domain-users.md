---
title: Synkronisera domänanvändare med Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Synkronisera domänstyrda användare med Microsoft 365 för företag.
ms.openlocfilehash: b477b8a1f35a790d6c49937c973c141ad9f90ad4
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578416"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="7f7da-103">Synkronisera domänanvändare med Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7f7da-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="7f7da-104">1. Förbereda katalogsynkronisering</span><span class="sxs-lookup"><span data-stu-id="7f7da-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="7f7da-105">Innan du synkroniserar användare och datorer från den lokala Active Directory-domänen bör du läsa [Förbereda för katalogsynkronisering Microsoft 365](../enterprise/prepare-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="7f7da-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](../enterprise/prepare-for-directory-synchronization.md).</span></span> <span data-ttu-id="7f7da-106">Framförallt:</span><span class="sxs-lookup"><span data-stu-id="7f7da-106">In particular:</span></span>

   - <span data-ttu-id="7f7da-107">Kontrollera att det inte finns några dubbletter i katalogen för följande attribut: **mail,** **proxyAddresses** och **userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="7f7da-107">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="7f7da-108">Dessa värden måste vara unika och eventuella dubbletter måste tas bort.</span><span class="sxs-lookup"><span data-stu-id="7f7da-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="7f7da-109">Vi rekommenderar att du konfigurerar **attributet userPrincipalName** (UPN) för varje lokalt användarkonto så att det matchar den primära e-postadressen som motsvarar den licensierade Microsoft 365 användaren.</span><span class="sxs-lookup"><span data-stu-id="7f7da-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="7f7da-110">Till exempel: *mary.shelley@contoso.com* inte *mary@contoso.local*</span><span class="sxs-lookup"><span data-stu-id="7f7da-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="7f7da-111">Om Active [Directory-domänen](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)slutar med ett icke-dirigerbart suffix som *.local* eller *.lan* i stället för ett dirigerbart internetsuffix, till exempel *.com* eller *.org,* justerar du UPN-suffixet för de lokala användarkontona först enligt beskrivningen i Förbereda en icke-dirigerbar domän för katalogsynkronisering.</span><span class="sxs-lookup"><span data-stu-id="7f7da-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span> 

<span data-ttu-id="7f7da-112">Med **Kör IdFix** i steg fyra (4) nedan ser du också till att din lokala Active Directory är redo för katalogsynkronisering.</span><span class="sxs-lookup"><span data-stu-id="7f7da-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for directory synchronization.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="7f7da-113">2. Installera och konfigurera Azure AD-Anslut</span><span class="sxs-lookup"><span data-stu-id="7f7da-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="7f7da-114">Om du vill synkronisera användare, grupper och kontakter från den lokala Active Directory Azure Active Directory du genom Azure Active Directory Anslut konfigurera katalogsynkronisering.</span><span class="sxs-lookup"><span data-stu-id="7f7da-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="7f7da-115">I [administrationscentret väljer](https://go.microsoft.com/fwlink/p/?linkid=2024339)du **Inställningar i** det vänstra navigeringsfältet.</span><span class="sxs-lookup"><span data-stu-id="7f7da-115">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="7f7da-116">Under **Inloggning och säkerhet väljer** du **Visa** under Synkronisera användare **från organisationens katalog.**</span><span class="sxs-lookup"><span data-stu-id="7f7da-116">Under **Sign-in and security**, choose **View**  under **Sync users from your org's directory**.</span></span>

 3. <span data-ttu-id="7f7da-117">På sidan **Synkronisera användare från organisationens katalog väljer** du Komma **igång.**</span><span class="sxs-lookup"><span data-stu-id="7f7da-117">On the **Sync users from your org's directory** page, choose **Get started**.</span></span>

 4. <span data-ttu-id="7f7da-118">I det första steget ska du köra IdFix-verktyget för att förbereda katalogsynkronisering.</span><span class="sxs-lookup"><span data-stu-id="7f7da-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="7f7da-119">Följ anvisningarna i guiden för att ladda ned Azure AD Anslut och använda det för att synkronisera dina domänstyrda användare till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7f7da-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="7f7da-120">Mer [information finns i Konfigurera Microsoft 365](../enterprise/set-up-directory-synchronization.md) för användare.</span><span class="sxs-lookup"><span data-stu-id="7f7da-120">See [Set up directory synchronization for Microsoft 365](../enterprise/set-up-directory-synchronization.md) to learn more.</span></span>

<span data-ttu-id="7f7da-121">När du konfigurerar alternativen för Azure AD Anslut rekommenderar vi att du aktiverar lösenordssynkronisering, sömlös enkel inloggning och återskrivningsfunktionen för lösenord, som också stöds i Microsoft 365 för företag. </span><span class="sxs-lookup"><span data-stu-id="7f7da-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="7f7da-122">Det finns några ytterligare steg för tillbakaskrivning av lösenord utöver kryssrutan i Azure AD Anslut.</span><span class="sxs-lookup"><span data-stu-id="7f7da-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="7f7da-123">Mer information finns i Så [här gör du för att: konfigurera tillbakaskrivning av lösenord.](/azure/active-directory/authentication/howto-sspr-writeback)</span><span class="sxs-lookup"><span data-stu-id="7f7da-123">For more information, see [How-to: configure password writeback](/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="7f7da-124">Om du även vill hantera domänaktiverade Windows 10-enheter kan du gå till Aktivera domänkoppling för [Windows 10-enheter](manage-windows-devices.md) så att de hanteras av Microsoft 365 Business Premium och konfigurera en hybrid-Azure AD Join.</span><span class="sxs-lookup"><span data-stu-id="7f7da-124">If you also want to manage domain-joined Windows 10 devices, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span>