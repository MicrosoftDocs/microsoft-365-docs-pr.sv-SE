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
description: Synkronisera domänstyrda användare med Microsoft 365 för företag.
ms.openlocfilehash: 1c939dec7229f02991b15f08c48f184efecaddb0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913263"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="8d16c-103">Synkronisera domänanvändare med Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8d16c-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="8d16c-104">1. Förbereda katalogsynkronisering</span><span class="sxs-lookup"><span data-stu-id="8d16c-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="8d16c-105">Innan du synkroniserar användare och datorer från den lokala Active Directory-domänen bör du läsa Förbereda [katalogsynkronisering till Microsoft 365.](../enterprise/prepare-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="8d16c-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](../enterprise/prepare-for-directory-synchronization.md).</span></span> <span data-ttu-id="8d16c-106">Framförallt:</span><span class="sxs-lookup"><span data-stu-id="8d16c-106">In particular:</span></span>

   - <span data-ttu-id="8d16c-107">Kontrollera att det inte finns några dubbletter i katalogen för följande attribut: **mail,** **proxyAddresses** och **userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="8d16c-107">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="8d16c-108">Dessa värden måste vara unika och eventuella dubbletter måste tas bort.</span><span class="sxs-lookup"><span data-stu-id="8d16c-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="8d16c-109">Vi rekommenderar att du konfigurerar **attributet userPrincipalName** (UPN) för varje lokalt användarkonto så att det matchar den primära e-postadress som motsvarar den licensierade Microsoft 365-användaren.</span><span class="sxs-lookup"><span data-stu-id="8d16c-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="8d16c-110">Till exempel: *mary.shelley@contoso.com* inte *mary@contoso.local*</span><span class="sxs-lookup"><span data-stu-id="8d16c-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="8d16c-111">Om Active [Directory-domänen](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)slutar med ett icke-dirigerbart suffix som *.local* eller *.lan* i stället för ett dirigerbart internetsuffix, till exempel *.com* eller *.org,* justerar du UPN-suffixet för de lokala användarkontona först enligt beskrivningen i Förbereda en icke-dirigerbar domän för katalogsynkronisering.</span><span class="sxs-lookup"><span data-stu-id="8d16c-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span> 

<span data-ttu-id="8d16c-112">Med **Kör IdFix** i steg fyra (4) nedan ser du också till att din lokala Active Directory är redo för katalogsynkronisering.</span><span class="sxs-lookup"><span data-stu-id="8d16c-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for directory synchronization.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="8d16c-113">2. Installera och konfigurera Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="8d16c-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="8d16c-114">Installera Azure Active Directory Connect och konfigurera katalogsynkronisering om du vill synkronisera användare, grupper och kontakter från den lokala Active Directory i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8d16c-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="8d16c-115">I [administrationscentret väljer](https://go.microsoft.com/fwlink/p/?linkid=2024339)du **Inställningar i** det vänstra navigeringsfältet.</span><span class="sxs-lookup"><span data-stu-id="8d16c-115">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="8d16c-116">Under **Inloggning och säkerhet väljer** du **Visa** under Synkronisera användare **från organisationens katalog.**</span><span class="sxs-lookup"><span data-stu-id="8d16c-116">Under **Sign-in and security**, choose **View**  under **Sync users from your org's directory**.</span></span>

 3. <span data-ttu-id="8d16c-117">På sidan **Synkronisera användare från organisationens katalog väljer** du Komma **igång.**</span><span class="sxs-lookup"><span data-stu-id="8d16c-117">On the **Sync users from your org's directory** page, choose **Get started**.</span></span>

 4. <span data-ttu-id="8d16c-118">I det första steget ska du köra IdFix-verktyget för att förbereda katalogsynkronisering.</span><span class="sxs-lookup"><span data-stu-id="8d16c-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="8d16c-119">Följ anvisningarna i guiden för att ladda ned Azure AD Connect och använda det för att synkronisera dina domänstyrda användare till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8d16c-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="8d16c-120">Mer [information finns i Konfigurera katalogsynkronisering för Microsoft 365.](../enterprise/set-up-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="8d16c-120">See [Set up directory synchronization for Microsoft 365](../enterprise/set-up-directory-synchronization.md) to learn more.</span></span>

<span data-ttu-id="8d16c-121">När du konfigurerar alternativen för Azure AD Connect rekommenderar vi att du aktiverar  lösenordssynkronisering, sömlös enkel inloggning och återskrivningsfunktionen för lösenord, som också stöds i Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="8d16c-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="8d16c-122">Det finns några ytterligare steg för tillbakaskrivning av lösenord utöver kryssrutan i Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="8d16c-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="8d16c-123">Mer information finns i Så [här gör du för att: konfigurera tillbakaskrivning av lösenord.](/azure/active-directory/authentication/howto-sspr-writeback)</span><span class="sxs-lookup"><span data-stu-id="8d16c-123">For more information, see [How-to: configure password writeback](/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="8d16c-124">Om du även vill hantera domänaktiverade Windows 10-enheter kan du gå till Aktivera domän anslutna [Windows 10-enheter](manage-windows-devices.md) så att de hanteras av Microsoft 365 Business Premium och konfigurera en Azure AD-hybridkoppling.</span><span class="sxs-lookup"><span data-stu-id="8d16c-124">If you also want to manage domain-joined Windows 10 devices, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span>