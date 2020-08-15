---
title: Övervaka Microsoft 365-anslutning
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/4/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 53cdb60c-a6b2-4848-b3ff-e7b75dc3fd1f
description: I den här artikeln får du lära dig mer om verktygen och teknikerna som du kan använda för att övervaka och underhålla Microsoft 365-anslutningar.
ms.openlocfilehash: 7e62bcaae24f9e42fd0514c34c3d7dee764bc271
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694336"
---
# <a name="monitor-microsoft-365-connectivity"></a><span data-ttu-id="84b6d-103">Övervaka Microsoft 365-anslutning</span><span class="sxs-lookup"><span data-stu-id="84b6d-103">Monitor Microsoft 365 connectivity</span></span>

<span data-ttu-id="84b6d-104">När du har distribuerat Microsoft 365 kan du upprätthålla Microsoft 365-anslutningen med några av verktygen och teknikerna nedan.</span><span class="sxs-lookup"><span data-stu-id="84b6d-104">Once you've deployed Microsoft 365, you can maintain Microsoft 365 connectivity using some of the tools and techniques below.</span></span> <span data-ttu-id="84b6d-105">Du vill förstå de offentliga rikt linjerna för [tjänster och kontinuitet](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) samt vår [bästa praxis för att använda Microsoft 365 på ett långsamt nätverk](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span><span class="sxs-lookup"><span data-stu-id="84b6d-105">You'll want to understand the official [Service Health and Continuity](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span> <span data-ttu-id="84b6d-106">Du vill också skaffa [microsoft 365-administratörs programmet](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) och bok märke vår [support för Microsoft 365 för företag – hjälp för administratörer](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span><span class="sxs-lookup"><span data-stu-id="84b6d-106">You'll also want to grab the [Microsoft 365 admin app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) and bookmark our [Microsoft 365 for business - Admin Help](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span></span>
  
## <a name="monitoring-microsoft-365-connectivity"></a><span data-ttu-id="84b6d-107">Övervaka Microsoft 365-anslutningar</span><span class="sxs-lookup"><span data-stu-id="84b6d-107">Monitoring Microsoft 365 Connectivity</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="84b6d-108">**Få meddelanden om nya slut punkter för Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="84b6d-108">**Getting notified of new Microsoft 365 endpoints**</span></span> <br/> |<span data-ttu-id="84b6d-109">Om du [hanterar Microsoft 365-slutpunkter](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), vill du få aviseringar när vi publicerar nya slut punkter, kan du prenumerera på RSS-feeden med din RSS-läsare.</span><span class="sxs-lookup"><span data-stu-id="84b6d-109">If you're [Managing Microsoft 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader.</span></span> <span data-ttu-id="84b6d-110">Så här [abonnerar](https://go.microsoft.com/fwlink/p/?LinkId=532416) du på Outlook eller så kan du [få en RSS-feed uppdaterats via e-post](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span><span class="sxs-lookup"><span data-stu-id="84b6d-110">Here is how to [subscribe via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) or you can [have the RSS feed updates emailed to you](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span></span>  <br/> |
|<span data-ttu-id="84b6d-111">**Använda System Center för att övervaka Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="84b6d-111">**Use System Center to Monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="84b6d-112">Om du använder Microsoft System Center kan du hämta [System Center Management Pack för Office 365](https://www.microsoft.com/download/details.aspx?id=43708) för att börja övervaka Microsoft 365 idag.</span><span class="sxs-lookup"><span data-stu-id="84b6d-112">If you're using Microsoft System Center, you can download the [System Center Management Pack for Office 365](https://www.microsoft.com/download/details.aspx?id=43708) to begin monitoring Microsoft 365 today.</span></span> <span data-ttu-id="84b6d-113">Mer detaljerad information finns i hanterings paketet Operations Guide eller det här blogg inlägget [Office365 övervakning med System Center Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx)</span><span class="sxs-lookup"><span data-stu-id="84b6d-113">For more detailed guidance, please see the management pack operations guide or this blog post [Office365 Monitoring using System Centre Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx)</span></span> <br/> |
|<span data-ttu-id="84b6d-114">**Övervaka hälsa för Azure ExpressRoute**</span><span class="sxs-lookup"><span data-stu-id="84b6d-114">**Monitoring the health of Azure ExpressRoute**</span></span> <br/> |<span data-ttu-id="84b6d-115">Om du ansluter till Microsoft 365 med Azure ExpressRoute för Microsoft 365 bör du kontrol lera att du använder både Microsoft 365 tjänste instrument panel och Azure [Degressiv problemlösnings tid med Azure Resource Health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span><span class="sxs-lookup"><span data-stu-id="84b6d-115">If you are connecting to Microsoft 365 using Azure ExpressRoute for Microsoft 365, you'll want to ensure that you're using both the Microsoft 365 Service Health Dashboard as well as the Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span></span> <br/> |
|<span data-ttu-id="84b6d-116">**Använda Azure AD Connect-hälsa med AD FS**</span><span class="sxs-lookup"><span data-stu-id="84b6d-116">**Using Azure AD Connect Health with AD FS**</span></span> <br/> |<span data-ttu-id="84b6d-117">Om du använder AD FS för enkel inloggning med Microsoft 365 ska du börja [använda Azure AD Connect-tillståndet för att övervaka din AD FS-infrastruktur](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-health-adfs/).</span><span class="sxs-lookup"><span data-stu-id="84b6d-117">If you're using AD FS for Single Sign-On with Microsoft 365, you'll want to begin [using Azure AD Connect Health to monitor your AD FS infrastructure](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-health-adfs/).</span></span>  <br/> |
|<span data-ttu-id="84b6d-118">**Övervaka Microsoft 365 programmatiskt**</span><span class="sxs-lookup"><span data-stu-id="84b6d-118">**Programmatically monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="84b6d-119">Läs vår vägledning om [Microsoft 365 Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span><span class="sxs-lookup"><span data-stu-id="84b6d-119">Refer to our guidance on the [Microsoft 365 Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>  <br/> |

<span data-ttu-id="84b6d-120">Här är en kort länk som du kan använda för att komma tillbaka: [https://aka.ms/monitorconnectivity365](https://aka.ms/monitorconnectivity365)</span><span class="sxs-lookup"><span data-stu-id="84b6d-120">Here's a short link you can use to come back: [https://aka.ms/monitorconnectivity365](https://aka.ms/monitorconnectivity365)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="84b6d-121">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="84b6d-121">Related topics</span></span>

[<span data-ttu-id="84b6d-122">Konfigurera Microsoft 365 Enterprise Services och-program</span><span class="sxs-lookup"><span data-stu-id="84b6d-122">Configure Microsoft 365 Enterprise services and applications</span></span>](configure-services-and-applications.md)
  
[<span data-ttu-id="84b6d-123">Förbered din organisation för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="84b6d-123">Get your organization ready for Microsoft 365 Enterprise</span></span>](get-your-organization-ready-for-office-365.md)
  
[<span data-ttu-id="84b6d-124">Nätverks planering och prestanda justering för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="84b6d-124">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)
  
[<span data-ttu-id="84b6d-125">Microsoft 365-integrering med lokala miljöer</span><span class="sxs-lookup"><span data-stu-id="84b6d-125">Microsoft 365 integration with on-premises environments</span></span>](microsoft-365-integration.md)
  
[<span data-ttu-id="84b6d-126">Hantera slut punkter för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="84b6d-126">Managing Microsoft 365 endpoints</span></span>](managing-office-365-endpoints.md)
