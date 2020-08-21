---
title: SMTP-AUTH-klienter inblick och rapport i instrument panelen för e-postflöde
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära dig hur du använder SMTP AUTH inblick och rapport i instrument panelen för e-postflöde i säkerhets & Compliance Center för att övervaka e-avsändare i organisationen som använder autentiserad SMTP (SMTP AUTH) för att skicka e-postmeddelanden.
ms.openlocfilehash: 65e5569bcd79caef071ee2103d18a4e985c19dbb
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826875"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="2202c-103">SMTP-AUTH-klienter inblick och rapportera i säkerhets & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="2202c-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

<span data-ttu-id="2202c-104">**SMTP-AUTH-klienterna** fokuserar på [instrument panelen för e-postflöden](mail-flow-insights-v2.md) och den associerade [SMTP-authn-rapporten](#smtp-auth-clients-report) markerar användning av SMTP auth client sändning Protocol via användare eller system konton i din organisation.</span><span class="sxs-lookup"><span data-stu-id="2202c-104">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="2202c-105">Det här bakåtkompatibla protokollet (som använder slut punkts smtp.office365.com) endast erbjuder grundläggande inloggningsautentisering och är känsligt för att användas av obehöriga konton för att skicka e-post.</span><span class="sxs-lookup"><span data-stu-id="2202c-105">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="2202c-106">Med inblick och rapport kan du söka efter ovanlig aktivitet för SMTP-profilens e-postinlägg.</span><span class="sxs-lookup"><span data-stu-id="2202c-106">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="2202c-107">Det visar också TLS-dataanvändningen för klienter eller enheter med SMTP-autentisering.</span><span class="sxs-lookup"><span data-stu-id="2202c-107">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="2202c-108">Widgeten visar antalet användare eller tjänst konton som har använt SMTP Authentication Protocol under de senaste 7 dagarna.</span><span class="sxs-lookup"><span data-stu-id="2202c-108">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![Widget för SMTP-AUTH-klienter i instrument panelen för e-postflöde i säkerhets & Compliance Center](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="2202c-110">Om du klickar på antalet meddelanden i widgeten visas en **SMTP-AUTH-klienter** .</span><span class="sxs-lookup"><span data-stu-id="2202c-110">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="2202c-111">Den utfällbara vyn visar en sammanslagen vy av TLS-användning och volymerna under den senaste veckan.</span><span class="sxs-lookup"><span data-stu-id="2202c-111">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![Information utfälld när du klickar på widgeten SMTP-AUTH-klienter i instrument panelen för e-postflöde](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="2202c-113">Du kan klicka på länken **SMTP-AUTH-klienter** för att gå till rapporten SMTP-AUTH-klienter enligt beskrivningen i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="2202c-113">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="2202c-114">Rapporten SMTP Auth-klienter</span><span class="sxs-lookup"><span data-stu-id="2202c-114">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="2202c-115">Rapportvy för rapporten SMTP-AUTH-klienter</span><span class="sxs-lookup"><span data-stu-id="2202c-115">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="2202c-116">Som standard visar rapporten data för de senaste 7 dagarna, men data är tillgängliga under de senaste 90 dagarna.</span><span class="sxs-lookup"><span data-stu-id="2202c-116">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="2202c-117">Avsnittet Översikt innehåller följande diagram:</span><span class="sxs-lookup"><span data-stu-id="2202c-117">The overview section contains the following charts:</span></span>

- <span data-ttu-id="2202c-118">**Visa data genom: skicka volym**: diagrammet visar som standard antalet SMTP auth client-meddelanden som skickades från alla domäner (**Visa data för: alla avsändare** är markerade som standard).</span><span class="sxs-lookup"><span data-stu-id="2202c-118">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="2202c-119">Du kan filtrera resultaten till en viss avsändares domän genom att klicka på **Visa data för** och välja avsändar domänen i list rutan.</span><span class="sxs-lookup"><span data-stu-id="2202c-119">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="2202c-120">Om du hovrar över en viss data punkt (dag) visas antalet meddelanden.</span><span class="sxs-lookup"><span data-stu-id="2202c-120">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![Skicka vyn volym i rapporten SMTP-AUTH-klienter i säkerhets & efterlevnad](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="2202c-122">**Visa data genom: TLS-användning**: diagrammet visar procent andelen av TLS-användning för alla SMTP auth client-meddelanden under den valda tids perioden.</span><span class="sxs-lookup"><span data-stu-id="2202c-122">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="2202c-123">I det här diagrammet kan du identifiera och vidta åtgärder för användare och system konton som fortfarande använder äldre versioner av TLS.</span><span class="sxs-lookup"><span data-stu-id="2202c-123">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![Vyn användning av TLS i rapporten SMTP-AUTH-klienter i säkerhets & efterlevnad](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="2202c-125">Om du klickar på **filter** i en rapportvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="2202c-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="2202c-126">Klicka på **rapporten Request** för att få en mer detaljerad version av rapporten i ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="2202c-126">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="2202c-127">Du kan ange datum intervallet och mottagarna för att få rapporten.</span><span class="sxs-lookup"><span data-stu-id="2202c-127">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="2202c-128">Vyn detaljerad tabell för rapporten SMTP-AUTH-klienter</span><span class="sxs-lookup"><span data-stu-id="2202c-128">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="2202c-129">Om du klickar på **Visa informations tabell**beror informationen som visas på diagrammet du tittade på:</span><span class="sxs-lookup"><span data-stu-id="2202c-129">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="2202c-130">**Visa data genom: skicka volym**: följande information visas i en tabell:</span><span class="sxs-lookup"><span data-stu-id="2202c-130">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="2202c-131">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="2202c-131">**Sender address**</span></span>
  - <span data-ttu-id="2202c-132">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="2202c-132">**Message count**</span></span>

  <span data-ttu-id="2202c-133">Om du markerar en rad visas samma detaljer i en utfällbar lista.</span><span class="sxs-lookup"><span data-stu-id="2202c-133">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="2202c-134">**Visa data genom: TLS-användning**: följande information visas i en tabell:</span><span class="sxs-lookup"><span data-stu-id="2202c-134">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="2202c-135">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="2202c-135">**Sender address**</span></span>
  - <span data-ttu-id="2202c-136">**TLS 1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2202c-136">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="2202c-137">**TLS 1.1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2202c-137">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="2202c-138">**TLS 1.2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2202c-138">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="2202c-139">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="2202c-139">**Message count**</span></span>

  <span data-ttu-id="2202c-140"><sup>\*</sup> I den här kolumnen visas både procent andelen och antalet meddelanden från avsändaren.</span><span class="sxs-lookup"><span data-stu-id="2202c-140"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="2202c-141">Om du klickar på **filter** i en detaljerad tabellvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="2202c-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="2202c-142">Om du markerar en rad visas liknande information i en utfällbar lista:</span><span class="sxs-lookup"><span data-stu-id="2202c-142">If you select a row, similar details are shown in a flyout:</span></span>

![Information som utfälls från tabellen information i vyn TLS-användning i SMTP-authn-klienter](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="2202c-144">Klicka på **rapporten Request** för att få en mer detaljerad version av rapporten i ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="2202c-144">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="2202c-145">Du kan ange datum intervallet och mottagarna för att få rapporten.</span><span class="sxs-lookup"><span data-stu-id="2202c-145">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="2202c-146">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="2202c-146">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2202c-147">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="2202c-147">Related topics</span></span>

<span data-ttu-id="2202c-148">Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="2202c-148">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
