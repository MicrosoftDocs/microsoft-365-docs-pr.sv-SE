---
title: Insikt och rapport för SMTP-autentiseringsklienter på instrumentpanelen för e-postflöde
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig att använda SMTP-autentiseringsinsikter och -rapporten i instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för & för att övervaka e-postavsändare i organisationen som använder autentiserad SMTP (SMTP AUTH) för att skicka e-postmeddelanden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a979f0e80fc303868bf2572974563323035fc4bc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207069"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="95330-103">Insikt och rapport för SMTP-autentiseringsklienter i Säkerhets- & efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="95330-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="95330-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="95330-104">**Applies to**</span></span>
- [<span data-ttu-id="95330-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="95330-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="95330-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="95330-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="95330-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95330-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="95330-108">Insikten **för SMTP-autentiseringsklienter** i instrumentpanelen för e-postflöde och rapporten tillhörande [SMTP-autentiseringsklienter](#smtp-auth-clients-report) i kompatibilitetscentret för [säkerhet i &](https://protection.office.com) markerar användningen av sändningsprotokoll för SMTP-AUTH-klienten för användare eller systemkonton i organisationen. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="95330-108">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) in the [Security & Compliance Center](https://protection.office.com) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="95330-109">Det här äldre protokollet (som använder slutpunkts-smtp.office365.com) erbjuder endast grundläggande autentisering och är känslig för användning av komprometterade konton för att skicka e-post.</span><span class="sxs-lookup"><span data-stu-id="95330-109">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="95330-110">Med insikten och rapporten kan du kontrollera ovanlig aktivitet för sändning via SMTP AUTH-e-post.</span><span class="sxs-lookup"><span data-stu-id="95330-110">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="95330-111">Den visar även TLS-användningsdata för klienter eller enheter som använder SMTP AUTH.</span><span class="sxs-lookup"><span data-stu-id="95330-111">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="95330-112">Widgeten anger antalet användare eller tjänstkonton som har använt SMTP-autentiseringsprotokoll under de senaste 7 dagarna.</span><span class="sxs-lookup"><span data-stu-id="95330-112">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![Widget för SMTP-autentiseringsklienter på instrumentpanelen för e-postflöde & Säkerhets- och efterlevnadscenter](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="95330-114">Om du klickar på antalet meddelanden på widgeten visas den utfällade **menyn SMTP Auth-klienter.**</span><span class="sxs-lookup"><span data-stu-id="95330-114">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="95330-115">Den utfällda utfällningen ger en aggregerad vy över TLS-användning och -volymer för den senaste veckan.</span><span class="sxs-lookup"><span data-stu-id="95330-115">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![Information som visas när du klickar på widgeten SMTP Auth-klienter på instrumentpanelen för e-postflöde](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="95330-117">Du kan klicka på **rapportlänken SMTP Auth-klienter** för att gå till rapporten SMTP Auth-klienter enligt beskrivningen i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="95330-117">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="95330-118">Rapporten SMTP Auth-klienter</span><span class="sxs-lookup"><span data-stu-id="95330-118">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="95330-119">Rapportvyn för rapporten SMTP Auth-klienter</span><span class="sxs-lookup"><span data-stu-id="95330-119">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="95330-120">Som standard visar rapporten data för de senaste 7 dagarna, men data är tillgängliga för de senaste 90 dagarna.</span><span class="sxs-lookup"><span data-stu-id="95330-120">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="95330-121">Översiktsavsnittet innehåller följande diagram:</span><span class="sxs-lookup"><span data-stu-id="95330-121">The overview section contains the following charts:</span></span>

- <span data-ttu-id="95330-122">**Visa data efter: Skicka** volym: Som standard visar diagrammet antalet SMTP-klientmeddelanden som skickades från alla domäner **(Visa data för:** Alla avsändardomäner är markerat som standard).</span><span class="sxs-lookup"><span data-stu-id="95330-122">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="95330-123">Du kan filtrera resultatet till en viss avsändardomän genom att klicka på Visa **data** för och välja avsändardomänen i listrutan.</span><span class="sxs-lookup"><span data-stu-id="95330-123">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="95330-124">Om du hovrar över en specifik datapunkt (dag) visas antalet meddelanden.</span><span class="sxs-lookup"><span data-stu-id="95330-124">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![Skicka volymvyn i rapporten SMTP Auth-klienter i säkerhets- & Säkerhets- och efterlevnadscenter](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="95330-126">**Visa data efter: TLS-användning:** I diagrammet visas procentandelen TLS-användning för alla meddelanden från SMTP-autentiseringsklienten under den valda tidsperioden.</span><span class="sxs-lookup"><span data-stu-id="95330-126">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="95330-127">Med det här diagrammet kan du identifiera och vidta åtgärder på användare och systemkonton som fortfarande använder äldre versioner av TLS.</span><span class="sxs-lookup"><span data-stu-id="95330-127">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![Vyn TLS-användning i rapporten SMTP-autentiseringsklienter i & Säkerhets- och efterlevnadscenter](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="95330-129">Om du klickar **på** Filter i en rapportvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="95330-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="95330-130">Klicka **på Begär rapport** om du vill få en mer detaljerad version av rapporten i ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="95330-130">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="95330-131">Du kan ange datumintervallet och mottagarna för att ta emot rapporten.</span><span class="sxs-lookup"><span data-stu-id="95330-131">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="95330-132">Tabellvyn Information för rapporten SMTP Auth-klienter</span><span class="sxs-lookup"><span data-stu-id="95330-132">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="95330-133">Om du **klickar på Visa** informationstabell beror den information som visas på det diagram som du tittar på:</span><span class="sxs-lookup"><span data-stu-id="95330-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="95330-134">**Visa data genom: Skicka volym:** Följande information visas i en tabell:</span><span class="sxs-lookup"><span data-stu-id="95330-134">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="95330-135">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="95330-135">**Sender address**</span></span>
  - <span data-ttu-id="95330-136">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="95330-136">**Message count**</span></span>

  <span data-ttu-id="95330-137">Om du markerar en rad visas samma information i en utfällbladstext.</span><span class="sxs-lookup"><span data-stu-id="95330-137">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="95330-138">**Visa data efter: TLS-användning:** Följande information visas i en tabell:</span><span class="sxs-lookup"><span data-stu-id="95330-138">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="95330-139">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="95330-139">**Sender address**</span></span>
  - <span data-ttu-id="95330-140">**TLS1,0 %**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="95330-140">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="95330-141">**TLS1,1 %**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="95330-141">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="95330-142">**TLS1,2 %**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="95330-142">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="95330-143">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="95330-143">**Message count**</span></span>

  <span data-ttu-id="95330-144"><sup>\*</sup> I den här kolumnen visas både procentandelen och antalet meddelanden från avsändaren.</span><span class="sxs-lookup"><span data-stu-id="95330-144"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="95330-145">Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="95330-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="95330-146">Om du markerar en rad visas liknande information i en utfällbladstext:</span><span class="sxs-lookup"><span data-stu-id="95330-146">If you select a row, similar details are shown in a flyout:</span></span>

![Informationsfällblad från detaljtabellen i TLS-användningsvyn i rapporten SMTP Auth-klienter](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="95330-148">Klicka **på Begär rapport** om du vill få en mer detaljerad version av rapporten i ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="95330-148">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="95330-149">Du kan ange datumintervallet och mottagarna för att ta emot rapporten.</span><span class="sxs-lookup"><span data-stu-id="95330-149">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="95330-150">Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="95330-150">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="95330-151">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="95330-151">Related topics</span></span>

<span data-ttu-id="95330-152">Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinformation i Säkerhets- & efterlevnadscenter.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="95330-152">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
