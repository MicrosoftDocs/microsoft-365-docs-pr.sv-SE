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
ms.openlocfilehash: d29b9d6bdc30d981b273d95925ba740bc92304c4
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694251"
---
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="a7061-104">Förutsättningar för gästkonton</span><span class="sxs-lookup"><span data-stu-id="a7061-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="a7061-105">Microsoft Hanterat skrivbord kräver följande inställningar i Azure AD-organisationen för gästkontoåtkomst.</span><span class="sxs-lookup"><span data-stu-id="a7061-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="a7061-106">Du kan justera de här inställningarna i [Azure-portalen](https://portal.azure.com) under **Externa identiteter/inställningar för externt samarbete:**</span><span class="sxs-lookup"><span data-stu-id="a7061-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration settings**:</span></span>

-   <span data-ttu-id="a7061-107">För **begränsningar av gäst inbjudningar** som angetts för medlemsanvändare och användare som tilldelats specifika administratörsroller kan du bjuda in **gästanvändare, bland annat gäster med medlemsbehörigheter**</span><span class="sxs-lookup"><span data-stu-id="a7061-107">For **Guest invite restrictions** set to **Member users and users assigned to specific admin roles can invite guest users including guests with member permissions**</span></span>
-   <span data-ttu-id="a7061-108">Välj **något av följande** alternativ för Begränsningar för samarbete:</span><span class="sxs-lookup"><span data-stu-id="a7061-108">For **Collaboration restrictions**, choose any of these options:</span></span>
    -   <span data-ttu-id="a7061-109">Om du väljer **Tillåt att inbjudningar skickas till valfri domän (mest inkluderande)** krävs ingen annan konfiguration.</span><span class="sxs-lookup"><span data-stu-id="a7061-109">If you select **Allow invitations to be sent to any domain (most inclusive)**, no other configuration required.</span></span>
    -   <span data-ttu-id="a7061-110">Om du väljer **Neka inbjudningar till** de angivna domänerna kontrollerar du att Microsoft.com inte finns i måldomänerna.</span><span class="sxs-lookup"><span data-stu-id="a7061-110">If you select **Deny invitations to the specified domains**, make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="a7061-111">Om du väljer Tillåt endast inbjudningar till de angivna domänerna **(mest restriktiva)** kontrollerar du att Microsoft.com *visas* i måldomänerna.</span><span class="sxs-lookup"><span data-stu-id="a7061-111">If you select **Allow invitations only to the specified domains (most restrictive)**, make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="a7061-112">Om du anger begränsningar som interagerar med de här inställningarna ska du se till att utesluta Azure Active Directory **för den moderna arbetsplatsen-tjänsten.**</span><span class="sxs-lookup"><span data-stu-id="a7061-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="a7061-113">Om du till exempel har en princip för villkorsstyrd åtkomst som förhindrar gästkonton från att komma åt Intune-portalen ska du utesluta gruppen **Tjänstkonton** för modern arbetsplats från den här principen.</span><span class="sxs-lookup"><span data-stu-id="a7061-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="a7061-114">Steg för att förbereda dig</span><span class="sxs-lookup"><span data-stu-id="a7061-114">Steps to get ready</span></span>

1. <span data-ttu-id="a7061-115">Läs [Förutsättningar för Microsoft Hanterat skrivbord](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="a7061-115">Review [prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="a7061-116">Använd [verktygen för beredskapsbedömning](readiness-assessment-tool.md).</span><span class="sxs-lookup"><span data-stu-id="a7061-116">Use [readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. <span data-ttu-id="a7061-117">[Krav för gästkonton](guest-accounts.md) (den här artikeln)</span><span class="sxs-lookup"><span data-stu-id="a7061-117">[Prerequisites for guest accounts](guest-accounts.md) (This article)</span></span>
4. [<span data-ttu-id="a7061-118">Nätverkskonfiguration för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="a7061-118">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="a7061-119">Förbereda certifikat och nätverksprofiler för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="a7061-119">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="a7061-120">Förbereda åtkomst till lokala resurser för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="a7061-120">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="a7061-121">Appar i Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="a7061-121">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="a7061-122">Förbereda mappade enheter för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="a7061-122">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="a7061-123">Förbereda utskriftsresurser för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="a7061-123">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)
