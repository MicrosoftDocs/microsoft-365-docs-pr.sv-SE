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
description: Synkronisera domänkontrollerade användare med Microsoft 365 för företag.
ms.openlocfilehash: af9cb7c9b2b639edc2375679a73ab41c4cf6de71
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080065"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="c5d7d-103">Synkronisera domänanvändare med Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c5d7d-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="c5d7d-104">1. Förbered för katalogsynkronisering</span><span class="sxs-lookup"><span data-stu-id="c5d7d-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="c5d7d-105">Innan du synkroniserar användare och datorer från den lokala Active Directory-domänen läser du [Förbered för katalogsynkronisering med Microsoft 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="c5d7d-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="c5d7d-106">I synnerhet gäller följande:</span><span class="sxs-lookup"><span data-stu-id="c5d7d-106">In particular:</span></span>

   - <span data-ttu-id="c5d7d-107">Kontrollera att det inte finns några dubbletter i katalogen för följande attribut: **e-post**, **proxyAdresser**och **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="c5d7d-107">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="c5d7d-108">Dessa värden måste vara unika och eventuella dubbletter måste tas bort.</span><span class="sxs-lookup"><span data-stu-id="c5d7d-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="c5d7d-109">Vi rekommenderar att du konfigurerar attributet **userPrincipalName** (UPN) för varje lokalt användarkonto så att det matchar den primära e-postadressen som motsvarar den licensierade Microsoft 365-användaren.</span><span class="sxs-lookup"><span data-stu-id="c5d7d-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="c5d7d-110">Till exempel: *mary.shelley@contoso.com* i stället *för mary@contoso.local*</span><span class="sxs-lookup"><span data-stu-id="c5d7d-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="c5d7d-111">Om Active Directory-domänen slutar i ett suffix som inte är dirigerbart som *.local* eller *.lan*i stället för ett internetrdigerbart suffix som *.com* eller *.org*justerar du UPN-suffixet för de lokala användarkontona först enligt beskrivningen i [Förbered en icke-dirigerbar domän för katalogsynkronisering](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="c5d7d-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

<span data-ttu-id="c5d7d-112">**Run IdFix** i steg fyra (4) nedan, kommer också att se till att din lokala Active Directory är redo för dir-synkronisering.</span><span class="sxs-lookup"><span data-stu-id="c5d7d-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for dir sync.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="c5d7d-113">2. Installera och konfigurera Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="c5d7d-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="c5d7d-114">Om du vill synkronisera användare, grupper och kontakter från den lokala Active Directory till Azure Active Directory installerar du Azure Active Directory Connect och konfigurerar katalogsynkronisering.</span><span class="sxs-lookup"><span data-stu-id="c5d7d-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="c5d7d-115">Välj Inställningar i den vänstra navigeringscentralen i administrationscentret vid <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> administrationscentret. **Setup**</span><span class="sxs-lookup"><span data-stu-id="c5d7d-115">In the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="c5d7d-116">Under **Logga in och säkerhet**väljer du **Visa** under Synkronisera användare **från organisationens katalog**.</span><span class="sxs-lookup"><span data-stu-id="c5d7d-116">Under **Sign-in and security**, choose **View**  under **Sync users from your org's directory**.</span></span>

 3. <span data-ttu-id="c5d7d-117">På **synkroniseringsanvändarna från organisationens katalogsida** väljer du **Kom igång**.</span><span class="sxs-lookup"><span data-stu-id="c5d7d-117">On the **Sync users from your org's directory** page, choose **Get started**.</span></span>

 4. <span data-ttu-id="c5d7d-118">I det första steget kör IdFix-verktyget för att förbereda för katalogsynkronisering.</span><span class="sxs-lookup"><span data-stu-id="c5d7d-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="c5d7d-119">Följ guidestegen för att hämta Azure AD Connect och använda den för att synkronisera dina domänkontrollerade användare till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c5d7d-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="c5d7d-120">Mer information finns i [Konfigurera katalogsynkronisering för Microsoft 365.](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)</span><span class="sxs-lookup"><span data-stu-id="c5d7d-120">See [Set up directory synchronization for Microsoft 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) to learn more.</span></span>

<span data-ttu-id="c5d7d-121">När du konfigurerar dina alternativ för Azure AD Connect rekommenderar vi att du aktiverar **lösenordssynkronisering**, **Sömlös enkel inloggning**och **tillbakaskrivningsfunktionen** för lösenord, som också stöds i Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="c5d7d-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="c5d7d-122">Det finns ytterligare några steg för återställning av lösenord utanför kryssrutan i Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="c5d7d-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="c5d7d-123">Mer information finns i [Så här konfigurerar du tillbaka lösenordet](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span><span class="sxs-lookup"><span data-stu-id="c5d7d-123">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="c5d7d-124">Om du också vill hantera domänanslutna Windows 10-enheter läser du [Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 Business Premium](manage-windows-devices.md) för att konfigurera en hybrid-Azure AD-koppling.</span><span class="sxs-lookup"><span data-stu-id="c5d7d-124">If you want to manage domain-joined Windows 10 devices also, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span> 