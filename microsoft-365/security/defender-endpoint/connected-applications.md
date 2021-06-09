---
title: Anslutna program i Microsoft Defender för Slutpunkt
ms.reviewer: ''
description: Visa anslutna partnerprogram som använder OAuth 2.0-standardprotokoll för att autentisera och ange token som ska användas med Microsoft Defender för slutpunkts-API:er.
keywords: partner, program, tredje part, anslutningar, sentinelone, lookout, bitdefender, corrata, morphisec, paloalto, ziften, bättre mobil
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 06ef716e9deee7b20e8615bd22c93130ee18b77f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845588"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="cc417-104">Anslutna program i Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="cc417-104">Connected applications in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cc417-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="cc417-105">**Applies to:**</span></span>
- [<span data-ttu-id="cc417-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="cc417-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cc417-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc417-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="cc417-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="cc417-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cc417-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="cc417-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="cc417-110">Anslutna program integreras med Defender för slutpunktsplattformen med API:er.</span><span class="sxs-lookup"><span data-stu-id="cc417-110">Connected applications integrates with the Defender for Endpoint platform using APIs.</span></span> 

<span data-ttu-id="cc417-111">Program använder standard-OAuth 2.0-protokollet för att autentisera och tillhandahålla token för användning med Microsoft Defender för slutpunkts-API:er.</span><span class="sxs-lookup"><span data-stu-id="cc417-111">Applications use standard OAuth 2.0 protocol to authenticate and provide tokens for use with Microsoft Defender for Endpoint APIs.</span></span>  <span data-ttu-id="cc417-112">Dessutom tillåter Azure Active Directory (Azure AD) att innehavaradministratörer kan ställa in explicit kontroll över vilka API:er som kan nås med hjälp av motsvarande app.</span><span class="sxs-lookup"><span data-stu-id="cc417-112">In addition, Azure Active Directory (Azure AD) applications allow tenant admins to set explicit control over which APIs can be accessed using the corresponding app.</span></span>
 
<span data-ttu-id="cc417-113">Du måste följa de här [anvisningarna för att](/microsoft-365/security/defender-endpoint/apis-intro) använda API:erna med det anslutna programmet.</span><span class="sxs-lookup"><span data-stu-id="cc417-113">You'll need to follow [these steps](/microsoft-365/security/defender-endpoint/apis-intro) to use the APIs with the connected application.</span></span>
 
## <a name="access-the-connected-application-page"></a><span data-ttu-id="cc417-114">Öppna sidan för det anslutna programmet</span><span class="sxs-lookup"><span data-stu-id="cc417-114">Access the connected application page</span></span>
<span data-ttu-id="cc417-115">I den vänstra navigeringsmenyn väljer du **Partners & API:er**  >  **anslutna AAD-program.**</span><span class="sxs-lookup"><span data-stu-id="cc417-115">From the left navigation menu, select **Partners & APIs** > **Connected AAD applications**.</span></span>

 
## <a name="view-connected-application-details"></a><span data-ttu-id="cc417-116">Visa information om anslutna program</span><span class="sxs-lookup"><span data-stu-id="cc417-116">View connected application details</span></span>
<span data-ttu-id="cc417-117">Sidan Anslutna program innehåller information om de Azure AD-program som är anslutna till Microsoft Defender för Slutpunkt i din organisation.</span><span class="sxs-lookup"><span data-stu-id="cc417-117">The Connected applications page provides information about the Azure AD applications connected to Microsoft Defender for Endpoint in your organization.</span></span> <span data-ttu-id="cc417-118">Du kan granska användningen av anslutna program: senast sedd, antal begäranden under de senaste 24 timmarna och begär trender under de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="cc417-118">You can review the usage of the connected applications: last seen, number of requests in the past 24 hours, and request trends in the last 30 days.</span></span>

![Bild på anslutna appar](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a><span data-ttu-id="cc417-120">Redigera, konfigurera om eller ta bort ett anslutet program</span><span class="sxs-lookup"><span data-stu-id="cc417-120">Edit, reconfigure, or delete a connected application</span></span>
<span data-ttu-id="cc417-121">Länken **Öppna programinställningar** öppnar motsvarande sida för Hantering av Azure AD-program i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="cc417-121">The **Open application settings** link opens the corresponding Azure AD application management page in the Azure portal.</span></span> <span data-ttu-id="cc417-122">Från Azure Portal kan du hantera behörigheter, konfigurera om eller ta bort anslutna program.</span><span class="sxs-lookup"><span data-stu-id="cc417-122">From the Azure portal, you can manage permissions, reconfigure, or delete the connected applications.</span></span>
