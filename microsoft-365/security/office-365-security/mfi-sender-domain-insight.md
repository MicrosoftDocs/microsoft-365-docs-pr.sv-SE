---
title: Åtgärda statistik över avsändaredomän
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
description: Administratörer kan lära sig mer om åtkomstbesiktningen av korrigeringsavsändaren i instrumentpanelen för e-postflödet i Security & Compliance Center.
ms.openlocfilehash: 2db1b971ef39f8b207b349ca53237ff87cc9193e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42809695"
---
# <a name="fix-sender-domain-insight"></a><span data-ttu-id="fe883-103">Åtgärda statistik över avsändaredomän</span><span class="sxs-lookup"><span data-stu-id="fe883-103">Fix sender domain insight</span></span>

<span data-ttu-id="fe883-104">Office 365 kräver meddelanden som skickas från interna lokala e-postmiljöer till Office 365 för att uppfylla vissa säkerhetskriterier:</span><span class="sxs-lookup"><span data-stu-id="fe883-104">Office 365 requires messages sending from internal on-premises email environments to Office 365 to meet certain security criteria:</span></span>

- <span data-ttu-id="fe883-105">Du har skapat en inkommande anslutningsapp i Office 365 för att autentisera SMTP-anslutningar från den lokala e-postservern med hjälp av käll-IP-adressen eller ett certifikat.</span><span class="sxs-lookup"><span data-stu-id="fe883-105">You've created an inbound connector in Office 365 to authenticate SMTP connections from your on-premises email server by using the source IP address or a certificate.</span></span>

- <span data-ttu-id="fe883-106">Du har konfigurerat din lokala e-postserver för att vidarebefordra e-post via Office 365 till den externa världen.</span><span class="sxs-lookup"><span data-stu-id="fe883-106">You've configured your on-premises email server to relay email via Office 365 to external world.</span></span>

- <span data-ttu-id="fe883-107">I konfigurationen är ett av följande satser sant:</span><span class="sxs-lookup"><span data-stu-id="fe883-107">In your configuration, one of the following statements is true:</span></span>

  - <span data-ttu-id="fe883-108">Avsändarens e-postdomän är registrerad i din Office 365-organisation.</span><span class="sxs-lookup"><span data-stu-id="fe883-108">The sender's email domain is registered in your Office 365 organization.</span></span> <span data-ttu-id="fe883-109">Mer information finns i Lägga till domäner i Office 365.</span><span class="sxs-lookup"><span data-stu-id="fe883-109">For more information, see Add Domains in Office 365.</span></span>

  - <span data-ttu-id="fe883-110">Din lokala e-postserver är konfigurerad för att använda ett certifikat för att skicka e-post till Office 365, certifikatet innehåller eller matchar exakt ett domännamn som du har registrerat i Office 365 och du har skapat en certifikatbaserad anslutningsapp i Office 365 med den Domän.</span><span class="sxs-lookup"><span data-stu-id="fe883-110">Your on-premises email server is configured to use a certificate to send email to Office 365, the certificate contains or exactly matches a domain name that you've registered in Office 365, and you've created a certificate based connector in Office 365 with that domain.</span></span> 

<span data-ttu-id="fe883-111">Meddelanden som inte uppfyller kriterierna kommer inte att tillskrivas organisationen och kan avvisas.</span><span class="sxs-lookup"><span data-stu-id="fe883-111">Messages that don't meet the criteria will not be attributed to the organization and could be rejected.</span></span>

<span data-ttu-id="fe883-112">**Fix-domäninsikten** visar e-post från din lokala miljö som inte uppfyller kriterierna, hjälper dig att identifiera potentiellt komprometterade datorer och användarkonton i din lokala e-postmiljö och hjälper dig att vidta åtgärder för att åtgärda.</span><span class="sxs-lookup"><span data-stu-id="fe883-112">The **Fix sender domain** insight shows you email from your on-premises environment that doesn't meet the criteria, helps you to identify potentially compromised machines and user accounts in your on-premises email environment, and helps you to take remediation actions.</span></span>

![Fix-domäninformationen i instrumentpanelen för e-postflödet i Security & Compliance Center](../../media/sender-domain-insight-selected.png)

<span data-ttu-id="fe883-114">När du klickar på **Visa information**tas du till en annan widget med mer information som visas i följande diagram:</span><span class="sxs-lookup"><span data-stu-id="fe883-114">When you click **View details**, you are taken to another widget with more details as shown in the following diagram:</span></span>

![Widgeten Information i fix-domänens insikt](../../media/sender-domain-view-details.png)

<span data-ttu-id="fe883-116">Den inkommande anslutningsappen som användes för att leverera meddelandena till Office 365 visas.</span><span class="sxs-lookup"><span data-stu-id="fe883-116">You'll see the inbound connector that was used to deliver the messages to Office 365.</span></span> <span data-ttu-id="fe883-117">Du kan också klicka på **Visa exempelmeddelande-ID:er** för att se information om de meddelanden som skickades från din lokala e-postmiljö.</span><span class="sxs-lookup"><span data-stu-id="fe883-117">You can also click **view sample message IDs** to see details for the messages that were sent from your on-premises email environment.</span></span> <span data-ttu-id="fe883-118">Eftersom dessa meddelanden avvisades av Office 365 kan du inte använda meddelandespårning, men du kan använda exempelmeddelande-ID:n för att spåra meddelandena i din lokala e-postmiljö.</span><span class="sxs-lookup"><span data-stu-id="fe883-118">Because these messages were rejected by Office 365, you can't use message trace, but you can use the sample message ids to track the messages in your on-premises email environment.</span></span>

![Visa exempelmeddelande-ID:er i fix-domänens insikt](../../media/sender-domain-view-sample-message-ids.png)

## <a name="see-also"></a><span data-ttu-id="fe883-120">Se även</span><span class="sxs-lookup"><span data-stu-id="fe883-120">See also</span></span>

<span data-ttu-id="fe883-121">Mer information om andra insikter om e-postflöde i instrumentpanelen för e-postflödet finns [i Insikterna för e-postflöde i Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="fe883-121">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
