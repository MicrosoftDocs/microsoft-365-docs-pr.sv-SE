---
title: Förutsättningar för gästkonton
description: Konfigurationsriktlinjer för gästkonton och hur du justerar dem
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: bbf679a01716fc48d37b241d69740f50a985f048
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574613"
---
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="aafbb-104">Förutsättningar för gästkonton</span><span class="sxs-lookup"><span data-stu-id="aafbb-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="aafbb-105">För Microsoft Managed Desktop krävs följande inställningar i Azure AD-organisationen för gästkontoåtkomst.</span><span class="sxs-lookup"><span data-stu-id="aafbb-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="aafbb-106">Du kan justera de här inställningarna i [Azure-portalen](https://portal.azure.com) under **Externa identiteter/externt samarbete:**</span><span class="sxs-lookup"><span data-stu-id="aafbb-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration**:</span></span>

-   <span data-ttu-id="aafbb-107">**Administratörer och användare med rollen som gäst inbjudna kan bjuda in inställda** på **Ja**</span><span class="sxs-lookup"><span data-stu-id="aafbb-107">**Admins and users in the guest inviter role can invite** set to **Yes**</span></span>
-   <span data-ttu-id="aafbb-108">Välj **något av följande** alternativ för Begränsningar för samarbete:</span><span class="sxs-lookup"><span data-stu-id="aafbb-108">For **Collaboration restrictions**, choose any of these options:</span></span>
    -   <span data-ttu-id="aafbb-109">Om du väljer **Tillåt att inbjudningar skickas till valfri domän (mest inkluderande)** krävs ingen annan konfiguration.</span><span class="sxs-lookup"><span data-stu-id="aafbb-109">If you select **Allow invitations to be sent to any domain (most inclusive)**, no other configuration required.</span></span>
    -   <span data-ttu-id="aafbb-110">Om du väljer **Neka inbjudningar till** de angivna domänerna kontrollerar du att Microsoft.com inte finns i måldomänerna.</span><span class="sxs-lookup"><span data-stu-id="aafbb-110">If you select **Deny invitations to the specified domains**, make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="aafbb-111">Om du väljer Tillåt endast inbjudningar till de angivna domänerna **(mest restriktiva)** kontrollerar du att Microsoft.com *visas* i måldomänerna.</span><span class="sxs-lookup"><span data-stu-id="aafbb-111">If you select **Allow invitations only to the specified domains (most restrictive)**, make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="aafbb-112">Om du anger begränsningar som interagerar med de här inställningarna ska du se till att utesluta Azure Active Directory **Modern Workplace-tjänstkonton.**</span><span class="sxs-lookup"><span data-stu-id="aafbb-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="aafbb-113">Om du till exempel har en princip för villkorsstyrd åtkomst som förhindrar gästkonton från att komma åt Intune-portalen ska du utesluta gruppen **Tjänstkonton** för modern arbetsplats från den här principen.</span><span class="sxs-lookup"><span data-stu-id="aafbb-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="aafbb-114">Steg för att förbereda dig</span><span class="sxs-lookup"><span data-stu-id="aafbb-114">Steps to get ready</span></span>

1. <span data-ttu-id="aafbb-115">Granska [kraven för Microsoft Managed Desktop](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="aafbb-115">Review [prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="aafbb-116">Använda [utvärderingsverktyg för beredskap .](readiness-assessment-tool.md)</span><span class="sxs-lookup"><span data-stu-id="aafbb-116">Use [readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. <span data-ttu-id="aafbb-117">[Krav för gästkonton](guest-accounts.md) (den här artikeln)</span><span class="sxs-lookup"><span data-stu-id="aafbb-117">[Prerequisites for guest accounts](guest-accounts.md) (This article)</span></span>
4. [<span data-ttu-id="aafbb-118">Nätverks konfiguration för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="aafbb-118">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="aafbb-119">Förbereda certifikat och nätverks profiler för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="aafbb-119">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="aafbb-120">Förbereda lokala resurser till gång för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="aafbb-120">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="aafbb-121">Appar på Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="aafbb-121">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="aafbb-122">Förbereda mappade enheter för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="aafbb-122">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="aafbb-123">Förbereda skrivarresurser för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="aafbb-123">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)