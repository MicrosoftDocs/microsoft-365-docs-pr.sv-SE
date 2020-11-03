---
title: Synkronisera domänanvändare med Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
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
description: Synkronisera domänbaserade användare med Microsoft 365 för företag.
ms.openlocfilehash: b40a995a1723808d2fd171c534e9131a891840ba
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841368"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="c4525-103">Synkronisera domänanvändare med Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c4525-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="c4525-104">1. förbereda för Active Directory-synkronisering</span><span class="sxs-lookup"><span data-stu-id="c4525-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="c4525-105">Innan du synkroniserar användare och datorer från den lokala Active Directory-domänen bör du kontrol lera [förbereda för Active Directory-synkronisering till Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="c4525-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="c4525-106">Särskilt:</span><span class="sxs-lookup"><span data-stu-id="c4525-106">In particular:</span></span>

   - <span data-ttu-id="c4525-107">Kontrol lera att det inte finns några dubbletter i katalogen för följande attribut: **mail** , **proxyAddresses** och **userPrincipalName** .</span><span class="sxs-lookup"><span data-stu-id="c4525-107">Make sure that no duplicates exist in your directory for the following attributes: **mail** , **proxyAddresses** , and **userPrincipalName** .</span></span> <span data-ttu-id="c4525-108">Dessa värden måste vara unika och dubbletter måste tas bort.</span><span class="sxs-lookup"><span data-stu-id="c4525-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="c4525-109">Vi rekommenderar att du konfigurerar **userPrincipalName** -attributet (UPN) för varje lokalt användar konto så att det stämmer överens med den primära e-postadressen som motsvarar den licensierade Microsoft 365-användaren.</span><span class="sxs-lookup"><span data-stu-id="c4525-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="c4525-110">Till exempel: *Mary.Shelley@contoso.com* i stället för *Mary@contoso. local*</span><span class="sxs-lookup"><span data-stu-id="c4525-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="c4525-111">Om Active Directory-domänen slutar på ett icke-dirigerbart till exempel *. local* eller *. LAN* , kan du i stället för ett dirigerbart Internet *-suffix som. com* eller *. org* justera UPN-suffixet för de lokala användar kontona enligt beskrivningen i [förbereda en icke-dirigerbart domän för Active Directory-synkronisering](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="c4525-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan* , instead of an internet routable suffix such as *.com* or *.org* , adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

<span data-ttu-id="c4525-112">**Kör IdFix** i steg fyra (4) nedan kontrollerar också att den lokala Active Directory är klar för profilsynkronisering.</span><span class="sxs-lookup"><span data-stu-id="c4525-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for directory synchronization.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="c4525-113">2. Installera och konfigurera Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="c4525-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="c4525-114">Om du vill synkronisera dina användare, grupper och kontakter från den lokala Active Directory i Azure Active Directory installerar du Azure Active Directory Connect och konfigurera katalog synkronisering.</span><span class="sxs-lookup"><span data-stu-id="c4525-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="c4525-115">I [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2024339)väljer du **Inställningar** i det vänstra navigerings fältet.</span><span class="sxs-lookup"><span data-stu-id="c4525-115">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="c4525-116">Under **inloggning och säkerhet** väljer du **Visa**  under **synkronisera användare i organisationens katalog** .</span><span class="sxs-lookup"><span data-stu-id="c4525-116">Under **Sign-in and security** , choose **View**  under **Sync users from your org's directory** .</span></span>

 3. <span data-ttu-id="c4525-117">På sidan **synkronisera användare från organisationens katalog** sida väljer du **komma igång** .</span><span class="sxs-lookup"><span data-stu-id="c4525-117">On the **Sync users from your org's directory** page, choose **Get started** .</span></span>

 4. <span data-ttu-id="c4525-118">I det första steget Kör IdFix verktyg för att förbereda för katalog synkronisering.</span><span class="sxs-lookup"><span data-stu-id="c4525-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="c4525-119">Följ stegen i guiden för att ladda ned Azure AD Connect och Använd den för att synkronisera domän kontrollerade användare till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c4525-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="c4525-120">Mer information finns i [Konfigurera katalog-synkronisering för Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) .</span><span class="sxs-lookup"><span data-stu-id="c4525-120">See [Set up directory synchronization for Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) to learn more.</span></span>

<span data-ttu-id="c4525-121">När du konfigurerar alternativen för Azure AD Connect rekommenderar **vi att du aktiverar Lösenordssynkronisering** , **sömlös enkel inloggning** och funktionen för att ändra **lösen ord** , som också stöds i Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="c4525-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization** , **Seamless Single Sign-On** , and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="c4525-122">Det finns ytterligare anvisningar för att ångra lösen ordet utöver kryss rutan i Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="c4525-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="c4525-123">Mer information finns i [så här konfigurerar du tillbakaskrivning av lösen ord](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span><span class="sxs-lookup"><span data-stu-id="c4525-123">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="c4525-124">Om du även vill hantera domänanslutna Windows 10-enheter kan du läsa [Aktivera domän anslutna Windows 10-enheter som hanteras av Microsoft 365 Business Premium](manage-windows-devices.md) för att konfigurera en hybrid Azure AD-anslutning.</span><span class="sxs-lookup"><span data-stu-id="c4525-124">If you also want to manage domain-joined Windows 10 devices, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span> 