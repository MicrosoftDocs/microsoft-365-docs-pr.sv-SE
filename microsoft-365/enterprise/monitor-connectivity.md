---
title: Övervaka Microsoft 365 anslutning
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
description: I den här artikeln får du lära dig mer om de verktyg och tekniker du kan använda för att övervaka och Microsoft 365 anslutning.
ms.openlocfilehash: dfba158085e6642856049d7894b4156f42353236
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538813"
---
# <a name="monitor-microsoft-365-connectivity"></a><span data-ttu-id="e6780-103">Övervaka Microsoft 365 anslutning</span><span class="sxs-lookup"><span data-stu-id="e6780-103">Monitor Microsoft 365 connectivity</span></span>

<span data-ttu-id="e6780-104">När du har distribuerat Microsoft 365 kan du upprätthålla Microsoft 365 med några av verktygen och teknikerna nedan.</span><span class="sxs-lookup"><span data-stu-id="e6780-104">Once you've deployed Microsoft 365, you can maintain Microsoft 365 connectivity using some of the tools and techniques below.</span></span> <span data-ttu-id="e6780-105">Du bör förstå riktlinjerna [](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) för tjänstens hälsa och kontinuitet samt våra metodtips för att [använda Microsoft 365 i ett långsamt nätverk.](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)</span><span class="sxs-lookup"><span data-stu-id="e6780-105">You'll want to understand the official [Service Health and Continuity](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span> <span data-ttu-id="e6780-106">Ta även tag i appen Microsoft 365 [och bokmärk](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) vårt [Microsoft 365 för företag – hjälp för administratörer.](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)</span><span class="sxs-lookup"><span data-stu-id="e6780-106">You'll also want to grab the [Microsoft 365 admin app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) and bookmark our [Microsoft 365 for business - Admin Help](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span></span>
  
## <a name="monitoring-microsoft-365-connectivity"></a><span data-ttu-id="e6780-107">Övervaka Microsoft 365 anslutning</span><span class="sxs-lookup"><span data-stu-id="e6780-107">Monitoring Microsoft 365 Connectivity</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e6780-108">**Få ett meddelande om nya Microsoft 365 slutpunkter**</span><span class="sxs-lookup"><span data-stu-id="e6780-108">**Getting notified of new Microsoft 365 endpoints**</span></span> <br/> |<span data-ttu-id="e6780-109">Om du [](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)hanterar Microsoft 365-slutpunkter får du aviseringar när vi publicerar nya slutpunkter, så kan du prenumerera på vår RSS-feed med hjälp av din favorit RSS-läsare.</span><span class="sxs-lookup"><span data-stu-id="e6780-109">If you're [Managing Microsoft 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader.</span></span> <span data-ttu-id="e6780-110">Så här prenumererar du [via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) eller så kan du få [RSS-feeduppdateringarna e-postade till dig.](https://go.microsoft.com/fwlink/p/?LinkId=532417)</span><span class="sxs-lookup"><span data-stu-id="e6780-110">Here is how to [subscribe via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) or you can [have the RSS feed updates emailed to you](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span></span>  <br/> |
|<span data-ttu-id="e6780-111">**Använda System Center för att övervaka Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="e6780-111">**Use System Center to Monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="e6780-112">Om du använder Microsoft System Center kan du ladda ned [System Center Management Pack](https://www.microsoft.com/download/details.aspx?id=43708) för att Office 365 börja övervaka Microsoft 365 dag.</span><span class="sxs-lookup"><span data-stu-id="e6780-112">If you're using Microsoft System Center, you can download the [System Center Management Pack for Office 365](https://www.microsoft.com/download/details.aspx?id=43708) to begin monitoring Microsoft 365 today.</span></span> <span data-ttu-id="e6780-113">Mer detaljerad vägledning finns i guiden för hanteringspaket.</span><span class="sxs-lookup"><span data-stu-id="e6780-113">For more detailed guidance, please see the management pack operations guide.</span></span> <br/> |
|<span data-ttu-id="e6780-114">**Övervaka Azure ExpressRoute**</span><span class="sxs-lookup"><span data-stu-id="e6780-114">**Monitoring the health of Azure ExpressRoute**</span></span> <br/> |<span data-ttu-id="e6780-115">Om du ansluter till Microsoft 365 med hjälp av Azure ExpressRoute för Microsoft 365 bör du säkerställa att du använder både Microsoft 365-instrumentpanelen för tjänstens hälsa och Azure-minska felsökningstiden med Status för [Azure-resurser](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span><span class="sxs-lookup"><span data-stu-id="e6780-115">If you are connecting to Microsoft 365 using Azure ExpressRoute for Microsoft 365, you'll want to ensure that you're using both the Microsoft 365 Service Health Dashboard as well as the Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span></span> <br/> |
|<span data-ttu-id="e6780-116">**Använda Azure AD Anslut Health med AD FS**</span><span class="sxs-lookup"><span data-stu-id="e6780-116">**Using Azure AD Connect Health with AD FS**</span></span> <br/> |<span data-ttu-id="e6780-117">Om du använder AD FS för enkel Sign-On med Microsoft 365 kan du börja använda Azure AD Anslut Health för att övervaka [AD FS-infrastrukturen.](/azure/active-directory/hybrid/how-to-connect-health-adfs)</span><span class="sxs-lookup"><span data-stu-id="e6780-117">If you're using AD FS for Single Sign-On with Microsoft 365, you'll want to begin [using Azure AD Connect Health to monitor your AD FS infrastructure](/azure/active-directory/hybrid/how-to-connect-health-adfs).</span></span>  <br/> |
|<span data-ttu-id="e6780-118">**Övervaka Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="e6780-118">**Programmatically monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="e6780-119">Se våra riktlinjer om hur du [Microsoft 365 API för hantering.](/office/office-365-management-api/office-365-management-apis-overview)</span><span class="sxs-lookup"><span data-stu-id="e6780-119">Refer to our guidance on the [Microsoft 365 Management API](/office/office-365-management-api/office-365-management-apis-overview).</span></span>  <br/> |

<span data-ttu-id="e6780-120">Här är en kort länk som du kan använda för att komma tillbaka: [https://aka.ms/monitorconnectivity365]()</span><span class="sxs-lookup"><span data-stu-id="e6780-120">Here's a short link you can use to come back: [https://aka.ms/monitorconnectivity365]()</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e6780-121">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e6780-121">Related topics</span></span>

[<span data-ttu-id="e6780-122">Konfigurera Microsoft 365 Enterprise tjänster och program</span><span class="sxs-lookup"><span data-stu-id="e6780-122">Configure Microsoft 365 Enterprise services and applications</span></span>](configure-services-and-applications.md)
  
[<span data-ttu-id="e6780-123">Gör din organisation redo för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e6780-123">Get your organization ready for Microsoft 365 Enterprise</span></span>](get-your-organization-ready-for-office-365.md)
  
[<span data-ttu-id="e6780-124">Nätverksplanering och prestandajustering för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e6780-124">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)
  
[<span data-ttu-id="e6780-125">Microsoft 365 med lokala miljöer</span><span class="sxs-lookup"><span data-stu-id="e6780-125">Microsoft 365 integration with on-premises environments</span></span>](microsoft-365-integration.md)
  
[<span data-ttu-id="e6780-126">Hantera Microsoft 365 slutpunkter</span><span class="sxs-lookup"><span data-stu-id="e6780-126">Managing Microsoft 365 endpoints</span></span>](managing-office-365-endpoints.md)
