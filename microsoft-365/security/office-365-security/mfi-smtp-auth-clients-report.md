---
title: Rapporten SMTP Auth-klienter
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig mer om smtp-autentiseringsklientrapporten i instrumentpanelen för e-postflödet i Security & Compliance Center.
ms.openlocfilehash: 90d008bf775c692431fb5b832652ceb97f9fd760
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818825"
---
# <a name="smtp-auth-clients-report"></a><span data-ttu-id="9a3d1-103">Rapporten SMTP Auth-klienter</span><span class="sxs-lookup"><span data-stu-id="9a3d1-103">SMTP Auth clients report</span></span>

<span data-ttu-id="9a3d1-104">I rapporten **SMTP Auth-klienter** belysers användningen av SMTP Auth-klientöverföringsprotokollet av användare eller systemkonton i organisationen.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-104">The **SMTP Auth clients** report highlights the use of the SMTP Auth client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="9a3d1-105">Det här äldre protokollet (som använder slutpunkten smtp.office365.com) erbjuder endast grundläggande autentisering och kan användas av komprometterade konton för att skicka e-post.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-105">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span>  <span data-ttu-id="9a3d1-106">Med den här rapporten kan du söka efter ovanlig aktivitet.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-106">This report allows you to check for unusual activity.</span></span> <span data-ttu-id="9a3d1-107">Den visar också TLS-användningsdata för klienter eller enheter som använder SMTP Auth.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-107">It also shows the TLS usage data for clients or devices using SMTP Auth.</span></span>

<span data-ttu-id="9a3d1-108">Widgeten som visas på instrumentpanelen e-postflöde anger antalet användare eller tjänstkonton som har använt SMTP Auth-protokollet under de senaste 7 dagarna.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-108">The widget that's shown in the Mail Flow dashboard indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![SMTP-autentiseringsklienter rapporterar i instrumentpanelen för e-postflödet i Security & Compliance Center](../../media/smtp-auth-clients-report-selected.png)

<span data-ttu-id="9a3d1-110">Om du klickar på widgeten öppnas ett utfällbart utfällbart alternativ som ger en aggregerad vy över TLS-användningen och volymerna för den senaste veckan.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-110">Clicking on the widget opens a flyout that provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![Utfällbara i rapporten SMTP Auth-klienter](../../media/smtp-auth-clients-flyout.png)

<span data-ttu-id="9a3d1-112">När du klickar på länken **SMTP Auth Clients Report** visas två huvuddata pivoter och två datavyer.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-112">When you click on the **SMTP Auth Clients Report** link, you'll see two main data pivots and two data views.</span></span> <span data-ttu-id="9a3d1-113">Data pivoter är **skicka volym** och **TLS användning**.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-113">The data pivots are the **Sending Volume** and **TLS Usage**.</span></span> <span data-ttu-id="9a3d1-114">Datavyerna är diagrammet och detaljtabellen.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-114">The data views are the chart and the details table.</span></span>

<span data-ttu-id="9a3d1-115">Vyn **Skicka volym** visar antalet meddelanden som skickades med SMTP-autentisering för det angivna tidsintervallet.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-115">The **Sending Volume** view shows the number of messages that were sent using SMTP Auth for the specified time range.</span></span> <span data-ttu-id="9a3d1-116">Du kan justera intervallet genom att klicka på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-116">You can adjust the range by clicking **Filters**.</span></span> <span data-ttu-id="9a3d1-117">Diagrammet ordnas efter avsändatordomän.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-117">The chart is organized by sender domain.</span></span> <span data-ttu-id="9a3d1-118">Du kan se separata data för varje domän genom att välja domänen i **listrutan Visa data.**</span><span class="sxs-lookup"><span data-stu-id="9a3d1-118">You can see separate data for each domain by selecting the domain in the **Show data for** drop down.</span></span>

![Skicka volym i rapporten SMTP Auth Clients](../../media/smtp-auth-clients-report-sending-volume.png)

<span data-ttu-id="9a3d1-120">Du kan visa detaljerad information om avsändarna och deras meddelandeantal genom att klicka på **Visa informationstabell**.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-120">You can view detailed information about the senders and their message counts by clicking **View details table**.</span></span> <span data-ttu-id="9a3d1-121">Om du vill återgå till diagrammet klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-121">To return to the chart, click **View report**.</span></span>

![Informationstabell för att skicka volym i rapporten SMTP-autentiseringsklienter](../../media/smtp-auth-clients-report-details-sending-volume.png)

<span data-ttu-id="9a3d1-123">**TLS-användnings** pivot är viktigt på grund av den kommande utfasningen av TLS1.0 och TLS1.1 i Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-123">The **TLS Usage** pivot is important due to the upcoming deprecation of TLS1.0 and TLS1.1 in Office 365.</span></span> <span data-ttu-id="9a3d1-124">Många äldre enheter och program kan inte skicka e-post om de bara kan använda TLS1.0 med SMTP Auth. Med den här pivoten kan du identifiera och vidta åtgärder för användare och systemkonton som fortfarande använder äldre versioner av TLS.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-124">Many legacy devices and applications will be unable to send email if they are only capable of using TLS1.0 with SMTP Auth. This pivot allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

![TLS-användning i rapporten SMTP-autentiseringsklienter](../../media/smtp-auth-clients-report-tls-usage.png)

<span data-ttu-id="9a3d1-126">Du kan visa detaljerad information om avsändare, versioner av TLS som de använder med SMTP Auth och deras meddelande räknas genom att klicka på **Visa informationstabell**.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-126">You can view detailed information about the senders, the versions of TLS they are using with SMTP Auth, and their message counts by clicking **View details table**.</span></span> <span data-ttu-id="9a3d1-127">Om du vill återgå till diagrammet klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-127">To return to the chart, click **View report**.</span></span>

<span data-ttu-id="9a3d1-128">Du kan också hämta en mer detaljerad version av rapporten genom att klicka på Begär rapport.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-128">You can also download a more detailed version of the report by clicking Request report.</span></span>

![Informationstabell för TLS-användning i rapporten SMTP-autentiseringsklienter](../../media/smtp-auth-clients-report-details-tls-usage.png)

## <a name="related-topics"></a><span data-ttu-id="9a3d1-130">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="9a3d1-130">Related topics</span></span>

<span data-ttu-id="9a3d1-131">Mer information om andra insikter om e-postflöde i instrumentpanelen för e-postflödet finns [i Insikterna för e-postflöde i Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="9a3d1-131">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
