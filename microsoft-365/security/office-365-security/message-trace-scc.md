---
title: Meddelandespårning i Säkerhets- och efterlevnadscenter
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan använda meddelandespårning i Säkerhets- & för att ta reda på vad som har hänt med meddelanden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1ce26f7a6cdad15019e2b40eb6f8746e5723d4f0
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290663"
---
# <a name="message-trace-in-the-security--compliance-center"></a><span data-ttu-id="e1417-103">Meddelandespårning i Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="e1417-103">Message trace in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e1417-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="e1417-104">**Applies to**</span></span>
- [<span data-ttu-id="e1417-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e1417-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e1417-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="e1417-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="e1417-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e1417-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

## <a name="message-trace-features"></a><span data-ttu-id="e1417-108">Funktioner för meddelandespårning</span><span class="sxs-lookup"><span data-stu-id="e1417-108">Message trace features</span></span>

<span data-ttu-id="e1417-109">Meddelandespårning i Säkerhets- & efterlevnadscenter följer e-postmeddelanden när de färdas genom din Exchange Online-organisation.</span><span class="sxs-lookup"><span data-stu-id="e1417-109">Message trace in the Security & Compliance Center follows email messages as they travel through your Exchange Online organization.</span></span> <span data-ttu-id="e1417-110">Du kan avgöra om ett meddelande har tagits emot, avvisats, skjutits upp eller levererats av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="e1417-110">You can determine if a message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="e1417-111">Det visar också vilka åtgärder som har vidtagits för meddelandet innan det nått sin slutgiltiga status.</span><span class="sxs-lookup"><span data-stu-id="e1417-111">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="e1417-112">Meddelandespårning i Säkerhets- & Kompatibilitetscenter förbättrar den ursprungliga meddelandespårningen som var tillgänglig i administrationscentret för Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="e1417-112">Message trace in the Security & Compliance Center improves upon the original message trace that was available in the Exchange admin center (EAC).</span></span> <span data-ttu-id="e1417-113">Du kan använda informationen från meddelandespårning för att effektivt besvara användarfrågor om vad som har hänt med meddelanden, felsöka problem med e-postflödet och verifiera principändringar.</span><span class="sxs-lookup"><span data-stu-id="e1417-113">You can use the information from message trace to efficiently answer user questions about what happened to messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="e1417-114">Om du vill göra en meddelandespårning måste du vara medlem i rollgrupperna Organisationshantering, Efterlevnadshantering eller Support.</span><span class="sxs-lookup"><span data-stu-id="e1417-114">To do a message trace, you need to be a member of the Organization Management, Compliance Management or Help Desk role groups.</span></span> <span data-ttu-id="e1417-115">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e1417-115">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
>
> - <span data-ttu-id="e1417-116">Det maximala antalet meddelanden som visas i resultatet beror på vilken [](#choose-report-type) rapporttyp du har valt (mer information finns i avsnittet Välj rapporttyp).</span><span class="sxs-lookup"><span data-stu-id="e1417-116">The maximum number of messages that are displayed in the results depends on the report type you selected (see the [Choose report type](#choose-report-type) section for details).</span></span> <span data-ttu-id="e1417-117">Cmdleten [Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/get-historicalsearch) i Exchange Online PowerShell eller fristående EOP PowerShell returnerar alla meddelanden i resultatet.</span><span class="sxs-lookup"><span data-stu-id="e1417-117">The [Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/get-historicalsearch) cmdlet in Exchange Online PowerShell or standalone EOP PowerShell returns all messages in the results.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="e1417-118">Öppna meddelandespårning</span><span class="sxs-lookup"><span data-stu-id="e1417-118">Open message trace</span></span>

1. <span data-ttu-id="e1417-119">Öppna Säkerhets- & Efterlevnadscenter <https://protection.office.com> på.</span><span class="sxs-lookup"><span data-stu-id="e1417-119">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="e1417-120">Expandera **e-postflödet** och välj sedan **Meddelandespårning.**</span><span class="sxs-lookup"><span data-stu-id="e1417-120">Expand **Mail flow**, and then select **Message trace**.</span></span>

## <a name="message-trace-page"></a><span data-ttu-id="e1417-121">Meddelandespårningssida</span><span class="sxs-lookup"><span data-stu-id="e1417-121">Message trace page</span></span>

<span data-ttu-id="e1417-122">Härifrån kan du starta en ny standardspårning genom att klicka på **knappen Starta en** spårning.</span><span class="sxs-lookup"><span data-stu-id="e1417-122">From here you can start a new default trace by clicking on the **Start a trace** button.</span></span> <span data-ttu-id="e1417-123">Då söker du efter alla meddelanden för alla avsändare och mottagare under de senaste två dagarna.</span><span class="sxs-lookup"><span data-stu-id="e1417-123">This will search for all messages for all senders and recipients for the last two days.</span></span> <span data-ttu-id="e1417-124">Du kan också använda en av de lagrade frågorna från tillgängliga frågekategorier och antingen köra dem som de är eller använda dem som utgångspunkt för dina egna frågor:</span><span class="sxs-lookup"><span data-stu-id="e1417-124">Or you can use one of the stored queries from the available query categories and either run them as-is or use them as starting points for your own queries:</span></span>

- <span data-ttu-id="e1417-125">**Standardfrågor:** Inbyggda frågor från Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e1417-125">**Default queries**: Built-in queries provided by Microsoft 365.</span></span>

- <span data-ttu-id="e1417-126">**Anpassade frågor:** Frågor sparas av administratörer i organisationen för framtida bruk.</span><span class="sxs-lookup"><span data-stu-id="e1417-126">**Custom queries**: Queries saved by admins in your organization for future use.</span></span>

- <span data-ttu-id="e1417-127">**Automatisktavsparade frågor:** De senaste tio senaste körningsfrågorna.</span><span class="sxs-lookup"><span data-stu-id="e1417-127">**Autosaved queries**: The last ten most recently run queries.</span></span> <span data-ttu-id="e1417-128">Den här listan gör det enkelt att fortsätta där du slutade.</span><span class="sxs-lookup"><span data-stu-id="e1417-128">This list makes it simple to pick up where you left off.</span></span>

<span data-ttu-id="e1417-129">På den här sidan finns **också ett avsnitt** för nedladdningsbara rapporter för begäranden du har skickat in, samt själva rapporterna när det finns tillgängliga för nedladdning.</span><span class="sxs-lookup"><span data-stu-id="e1417-129">Also on this page is a **Downloadable reports** section for the requests you've submitted, as well as the reports themselves when they're are available for download.</span></span>

## <a name="options-for-a-new-message-trace"></a><span data-ttu-id="e1417-130">Alternativ för en ny meddelandespårning</span><span class="sxs-lookup"><span data-stu-id="e1417-130">Options for a new message trace</span></span>

### <a name="filter-by-senders-and-recipients"></a><span data-ttu-id="e1417-131">Filtrera efter avsändare och mottagare</span><span class="sxs-lookup"><span data-stu-id="e1417-131">Filter by senders and recipients</span></span>

<span data-ttu-id="e1417-132">Standardvärdena är **Alla avsändare** och **Alla** mottagare, men du kan använda följande fält för att filtrera resultatet:</span><span class="sxs-lookup"><span data-stu-id="e1417-132">The default values are **All senders** and **All recipients**, but you can use the following fields to filter the results:</span></span>

- <span data-ttu-id="e1417-133">**Av dessa personer:** Klicka i det här fältet om du vill välja en eller flera avsändare från organisationen.</span><span class="sxs-lookup"><span data-stu-id="e1417-133">**By these people**: Click in this field to select one or more senders from your organization.</span></span> <span data-ttu-id="e1417-134">Du kan också börja skriva ett namn så filtreras objekten i listan efter vad du har skrivit, ungefär som en söksida fungerar.</span><span class="sxs-lookup"><span data-stu-id="e1417-134">You can also start to type a name and the items in the list will be filtered by what you've typed, much like how a search page behaves.</span></span>

- <span data-ttu-id="e1417-135">**För de här personerna:** Klicka i det här fältet för att välja en eller flera mottagare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="e1417-135">**To these people**: Click in this field to select one or more recipients in your organization.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="e1417-136">Du kan också skriva e-postadresserna till externa avsändare och mottagare.</span><span class="sxs-lookup"><span data-stu-id="e1417-136">You can also type the email addresses of external senders and recipients.</span></span> <span data-ttu-id="e1417-137">Jokertecken stöds (till exempel), men du kan inte använda flera jokerteckenposter i `*@contoso.com` samma fält samtidigt.</span><span class="sxs-lookup"><span data-stu-id="e1417-137">Wildcards are supported (for example, `*@contoso.com`), but you can't use multiple wildcard entries in the same field at the same time.</span></span>
>
> - <span data-ttu-id="e1417-138">Du kan klistra in flera avsändare eller mottagare, avgränsade med semikolon ( `;` ).</span><span class="sxs-lookup"><span data-stu-id="e1417-138">You can paste multiple senders or recipients lists separated by semicolons (`;`).</span></span> <span data-ttu-id="e1417-139">blanksteg ( `\s` ), vagnreturer ( `\r` ) eller nästa rad ( `\n` ).</span><span class="sxs-lookup"><span data-stu-id="e1417-139">spaces (`\s`), carriage returns (`\r`), or next lines (`\n`).</span></span>

### <a name="time-range"></a><span data-ttu-id="e1417-140">Tidsperiod</span><span class="sxs-lookup"><span data-stu-id="e1417-140">Time range</span></span>

<span data-ttu-id="e1417-141">Standardvärdet är **2 dagar,** men du kan ange datum-/tidsintervall på upp till 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="e1417-141">The default value is **2 days**, but you can specify date/time ranges of up to 90 days.</span></span> <span data-ttu-id="e1417-142">När du använder datum-/tidsintervall bör du tänka på följande:</span><span class="sxs-lookup"><span data-stu-id="e1417-142">When you use date/time ranges, consider these issues:</span></span>

- <span data-ttu-id="e1417-143">Som standard väljer du tidintervallet i **skjutreglagevyn** med en tidsrad.</span><span class="sxs-lookup"><span data-stu-id="e1417-143">By default, you select the time range in **Slider** view using a time line.</span></span> <span data-ttu-id="e1417-144">Du kan bara välja vilka dag- och tidsinställningar som visas.</span><span class="sxs-lookup"><span data-stu-id="e1417-144">You can only select the day or time settings that are displayed.</span></span> <span data-ttu-id="e1417-145">Om du försöker välja ett värde mellan fästs start-/slutbubblan på den närmaste inställningen som visas.</span><span class="sxs-lookup"><span data-stu-id="e1417-145">Trying to select an in-between value will snap the start/end bubble to the nearest displayed setting.</span></span>

  ![Ett skjutreglage i en ny meddelandespårning i Säkerhets- & Efterlevnadscenter](../../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

  <span data-ttu-id="e1417-147">Men du kan också  växla till vyn Anpassad där  du kan ange värden för **Startdatum**  och Slutdatum (inklusive tider), och du kan också välja tidszon för datum/tidsintervall.</span><span class="sxs-lookup"><span data-stu-id="e1417-147">But, you can also switch to **Custom** view where you can specify the **Start date** and **End date** values (including times), and you can also select the **Time zone** for the date/time range.</span></span> <span data-ttu-id="e1417-148">Observera att **tidszonsinställningen** gäller för både frågeindata och frågeresultat.</span><span class="sxs-lookup"><span data-stu-id="e1417-148">Note that the **Time zone** setting applies to both your query inputs and your query results.</span></span>

  ![Ett anpassat tidintervall i en ny meddelandespårning i Säkerhets- & Efterlevnadscenter](../../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

  <span data-ttu-id="e1417-150">I 10 dagar eller mindre visas resultaten  direkt som en sammanfattningsrapport.</span><span class="sxs-lookup"><span data-stu-id="e1417-150">For 10 days or less, the results are available instantly as a **Summary** report.</span></span> <span data-ttu-id="e1417-151">Om du anger ett tidsperiod som är något längre än 10 dagar försenas **resultatet** eftersom de bara är tillgängliga som en nedladdningsbar CSV-fil **(utökade** sammanfattnings- eller utökade rapporter).</span><span class="sxs-lookup"><span data-stu-id="e1417-151">If you specify a time range that's even slightly greater than 10 days, the results will be delayed as they are only available as a downloadable CSV file ( **Enhanced summary** or **Extended** reports).</span></span>

  <span data-ttu-id="e1417-152">Mer information om de olika rapporttyperna finns i avsnittet [Välj rapporttyp](#choose-report-type) i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="e1417-152">For more information about the different report types, see the [Choose report type](#choose-report-type) section in this article.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e1417-153">Förbättrade sammanfattnings- och utökade rapporter förbereds med arkiverade meddelandespårningsdata och det kan ta upp till flera timmar innan rapporten är tillgänglig för nedladdning.</span><span class="sxs-lookup"><span data-stu-id="e1417-153">Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available for download.</span></span> <span data-ttu-id="e1417-154">Beroende på hur många andra administratörer som också har skickat rapportförfrågningar samtidigt kan du också märka en fördröjning innan bearbetningen startar för din i köade begäran.</span><span class="sxs-lookup"><span data-stu-id="e1417-154">Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before processing starts for your queued request.</span></span>

- <span data-ttu-id="e1417-155">När du sparar en **fråga i** skjutreglagevyn sparas det relativa tidsperioden (till exempel tre dagar från i dag).</span><span class="sxs-lookup"><span data-stu-id="e1417-155">Saving a query in **Slider** view saves the relative time range (for example, 3 days from today).</span></span> <span data-ttu-id="e1417-156">När du  sparar en fråga i vyn Anpassad sparas det absoluta datum-/tidsintervallet (till exempel 2018-05-06 13:00 till 2018-05-08 18:00).</span><span class="sxs-lookup"><span data-stu-id="e1417-156">Saving a query in **Custom** view saves the absolute date/time range (for example, 2018-05-06 13:00 to 2018-05-08 18:00).</span></span>

### <a name="more-search-options"></a><span data-ttu-id="e1417-157">Fler sökalternativ</span><span class="sxs-lookup"><span data-stu-id="e1417-157">More search options</span></span>

#### <a name="delivery-status"></a><span data-ttu-id="e1417-158">Leveransstatus</span><span class="sxs-lookup"><span data-stu-id="e1417-158">Delivery status</span></span>

<span data-ttu-id="e1417-159">Du kan låta standardvärdet **Alla vara** markerat eller så kan du välja något av följande värden för att filtrera resultatet:</span><span class="sxs-lookup"><span data-stu-id="e1417-159">You can leave the default value **All** selected, or you can select one of the following values to filter the results:</span></span>

- <span data-ttu-id="e1417-160">**Levererad:** Meddelandet levererades till målet.</span><span class="sxs-lookup"><span data-stu-id="e1417-160">**Delivered**: The message was successfully delivered to the intended destination.</span></span>

- <span data-ttu-id="e1417-161">**Väntande:** Leverans av meddelandet försöker eller försöker på nytt.</span><span class="sxs-lookup"><span data-stu-id="e1417-161">**Pending**: Delivery of the message is being attempted or re-attempted.</span></span>

- <span data-ttu-id="e1417-162">**Expanderat:** En mottagare i distributionsgruppen expanderades innan den levereras till de enskilda medlemmarna i gruppen.</span><span class="sxs-lookup"><span data-stu-id="e1417-162">**Expanded**: A distribution group recipient was expanded before delivery to the individual members of the group.</span></span>

- <span data-ttu-id="e1417-163">**Misslyckades:** Meddelandet levererades inte.</span><span class="sxs-lookup"><span data-stu-id="e1417-163">**Failed**: The message was not delivered.</span></span>

- <span data-ttu-id="e1417-164">**I karantän:** Meddelandet har satts i karantän (som skräppost, massutskick eller nätfiske).</span><span class="sxs-lookup"><span data-stu-id="e1417-164">**Quarantined**: The message was quarantined (as spam, bulk mail, or phishing).</span></span> <span data-ttu-id="e1417-165">Mer information finns i [e-postmeddelanden i karantän i EOP.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="e1417-165">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

- <span data-ttu-id="e1417-166">**Filtrerad som skräppost:** Meddelandet identifierades som skräppost och avvisades eller blockerades (inte i karantän).</span><span class="sxs-lookup"><span data-stu-id="e1417-166">**Filtered as spam**: The message was identified spam, and was rejected or blocked (not quarantined).</span></span>

- <span data-ttu-id="e1417-167">**Hämtar status:** Meddelandet togs nyligen emot av Microsoft 365, men inga andra statusdata är tillgängliga ännu.</span><span class="sxs-lookup"><span data-stu-id="e1417-167">**Getting status:** The message was recently received by Microsoft 365, but no other status data is yet available.</span></span> <span data-ttu-id="e1417-168">Kom tillbaka om några minuter.</span><span class="sxs-lookup"><span data-stu-id="e1417-168">Check back in a few minutes.</span></span>

> [!NOTE]
> <span data-ttu-id="e1417-169">Värdena **Väntande, i** **karantän och** Filter som **skräppost** är bara tillgängliga för sökningar under 10 dagar.</span><span class="sxs-lookup"><span data-stu-id="e1417-169">The values **Pending,** **Quarantined**, and **Filter as spam** are only available for searches less than 10 days.</span></span> <span data-ttu-id="e1417-170">Det kan också finnas en fördröjning på 5 till 10 minuter mellan den faktiska och rapporterade leveransstatusen.</span><span class="sxs-lookup"><span data-stu-id="e1417-170">Also, there might be a 5 to 10 minute delay between the actual and reported delivery status.</span></span>

#### <a name="message-id"></a><span data-ttu-id="e1417-171">Meddelande-ID</span><span class="sxs-lookup"><span data-stu-id="e1417-171">Message ID</span></span>

<span data-ttu-id="e1417-172">Det här är det Internetmeddelande-ID (kallas även klient-ID) som finns i **meddelande-ID:** huvudfältet i meddelandehuvudet.</span><span class="sxs-lookup"><span data-stu-id="e1417-172">This is the internet message ID (also known as the Client ID) that's found in the **Message-ID:** header field in the message header.</span></span> <span data-ttu-id="e1417-173">Användarna kan ge dig det här värdet om de vill undersöka specifika meddelanden.</span><span class="sxs-lookup"><span data-stu-id="e1417-173">Users can give you this value to investigate specific messages.</span></span>

<span data-ttu-id="e1417-174">Det här värdet är konstant under meddelandets livslängd.</span><span class="sxs-lookup"><span data-stu-id="e1417-174">This value is constant for the lifetime of the message.</span></span> <span data-ttu-id="e1417-175">För meddelanden som skapas i Microsoft 365 eller Exchange är värdet i formatet, inklusive `<GUID@ServerFQDN>` vinkelparenteser ( \< \> ).</span><span class="sxs-lookup"><span data-stu-id="e1417-175">For messages created in Microsoft 365 or Exchange, the value is in the format `<GUID@ServerFQDN>`, including the angle brackets (\< \>).</span></span> <span data-ttu-id="e1417-176">Till exempel `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span><span class="sxs-lookup"><span data-stu-id="e1417-176">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span> <span data-ttu-id="e1417-177">Andra meddelandesystem kan använda andra syntax eller värden.</span><span class="sxs-lookup"><span data-stu-id="e1417-177">Other messaging systems might use different syntax or values.</span></span> <span data-ttu-id="e1417-178">Det här värdet ska vara unikt, men inte alla e-postsystem som följer det här kravet.</span><span class="sxs-lookup"><span data-stu-id="e1417-178">This value is supposed to be unique, but not all email systems strictly follow this requirement.</span></span> <span data-ttu-id="e1417-179">Om **meddelande-ID: rubrikfältet** inte finns eller är tomt för inkommande meddelanden från externa källor tilldelas ett godtyckligt värde.</span><span class="sxs-lookup"><span data-stu-id="e1417-179">If the **Message-ID:** header field doesn't exist or is blank for incoming messages from external sources, an arbitrary value is assigned.</span></span>

<span data-ttu-id="e1417-180">När du **filtrerar resultatet med meddelande-ID** måste du inkludera hela strängen, inklusive vinkelparenteser.</span><span class="sxs-lookup"><span data-stu-id="e1417-180">When you use **Message ID** to filter the results, be sure to include the full string, including any angle brackets.</span></span>

#### <a name="direction"></a><span data-ttu-id="e1417-181">Riktning</span><span class="sxs-lookup"><span data-stu-id="e1417-181">Direction</span></span>

<span data-ttu-id="e1417-182">Du kan låta  standardvärdet Alla vara markerat eller välja **Inkommande** (meddelanden som skickas till mottagare i organisationen) eller Utgående **(meddelanden** som skickas från användare i organisationen) för att filtrera resultaten.</span><span class="sxs-lookup"><span data-stu-id="e1417-182">You can leave the default value **All** selected, or you can select **Inbound** (messages sent to recipients in your organization) or **Outbound** (messages sent from users in your organization) to filter the results.</span></span>

#### <a name="original-client-ip-address"></a><span data-ttu-id="e1417-183">Ursprunglig klient-IP-adress</span><span class="sxs-lookup"><span data-stu-id="e1417-183">Original client IP address</span></span>

<span data-ttu-id="e1417-184">Du kan filer resultaten efter klientens IP-adress och undersöka hackade datorer som skickar stora mängder skräppost eller skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="e1417-184">You can filer the results by client IP address to investigate hacked computers that are sending large amounts of spam or malware.</span></span> <span data-ttu-id="e1417-185">Även om meddelandena verkar komma från flera avsändare är det troligt att samma dator genererar alla meddelanden.</span><span class="sxs-lookup"><span data-stu-id="e1417-185">Although the messages might appear to come from multiple senders, it's likely that the same computer is generating all of the messages.</span></span>

> [!NOTE]
> <span data-ttu-id="e1417-186">Informationen om klient-IP-adressen är endast tillgänglig i 10 dagar  och finns bara tillgänglig i den utökade sammanfattningen eller utökade rapporter (nedladdningsbara CSV-filer). </span><span class="sxs-lookup"><span data-stu-id="e1417-186">The client IP address information is only available for 10 days, and is only available in the **Enhanced summary** or **Extended** reports (downloadable CSV files).</span></span>

### <a name="choose-report-type"></a><span data-ttu-id="e1417-187">Välj rapporttyp</span><span class="sxs-lookup"><span data-stu-id="e1417-187">Choose report type</span></span>

<span data-ttu-id="e1417-188">De tillgängliga rapporttyperna är:</span><span class="sxs-lookup"><span data-stu-id="e1417-188">The available report types are:</span></span>

- <span data-ttu-id="e1417-189">**Sammanfattning:** Tillgängligt om tidsperioden är mindre än 10 dagar och inte kräver ytterligare filtreringsalternativ.</span><span class="sxs-lookup"><span data-stu-id="e1417-189">**Summary**: Available if the time range is less than 10 days, and requires no additional filtering options.</span></span> <span data-ttu-id="e1417-190">Resultatet blir nästan direkt tillgängligt när du klickar på **Sök.**</span><span class="sxs-lookup"><span data-stu-id="e1417-190">The results are available almost immediately after you click **Search**.</span></span> <span data-ttu-id="e1417-191">Rapporten returnerar upp till 20 000 resultat.</span><span class="sxs-lookup"><span data-stu-id="e1417-191">The report returns up to 20000 results.</span></span>

- <span data-ttu-id="e1417-192">**Förbättrad sammanfattning** eller **utökad:** De här rapporterna är endast tillgängliga som nedladdningsbara CSV-filer och kräver ett eller flera av följande filtreringsalternativ oavsett **tidsperiod:** Av dessa **personer,** Till dessa personer eller **Meddelande-ID.**</span><span class="sxs-lookup"><span data-stu-id="e1417-192">**Enhanced summary** or **Extended**: These reports are only available as downloadable CSV files, and require one or more of the following filtering options regardless of the time range: **By these people**, **To these people**, or **Message ID**.</span></span> <span data-ttu-id="e1417-193">Du kan använda jokertecken för avsändare eller mottagare (till exempel \* @contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e1417-193">You can use wildcards for the senders or the recipients (for example, \*@contoso.com).</span></span> <span data-ttu-id="e1417-194">Den utökade sammanfattningsrapporten returnerar upp till 5 000 resultat.</span><span class="sxs-lookup"><span data-stu-id="e1417-194">The Enhanced summary report returns up to 50000 results.</span></span> <span data-ttu-id="e1417-195">Den utökade rapporten returnerar upp till 1 000 resultat.</span><span class="sxs-lookup"><span data-stu-id="e1417-195">The Extended report returns up to 1000 results.</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="e1417-196">Förbättrade sammanfattnings- och utökade rapporter förbereds med arkiverade meddelandespårningsdata och det kan ta flera timmar innan rapporten kan laddas ned.</span><span class="sxs-lookup"><span data-stu-id="e1417-196">Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available to download.</span></span> <span data-ttu-id="e1417-197">Beroende på hur många andra administratörer som också har skickat rapportförfrågningar samtidigt kan du också märka en fördröjning innan din i köade begäran börjar bearbetas.</span><span class="sxs-lookup"><span data-stu-id="e1417-197">Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before your queued request starts to be processed.</span></span>
> 
> - <span data-ttu-id="e1417-198">Du kan välja en utökad sammanfattning eller utökad rapport för ett datum-/tidsintervall, men vanligtvis är de sista fyra timmarna med arkiverade data ännu inte tillgängliga för dessa två typer av rapporter.</span><span class="sxs-lookup"><span data-stu-id="e1417-198">While you can select an Enhanced summary or Extended report for any date/time range, commonly the last four hours of archived data will not yet be available for these two types of reports.</span></span>

<span data-ttu-id="e1417-199">När du klickar på Nästa visas en sammanfattningssida med de filtreringsalternativ som du har valt, en unik (redigerbar) rubrik för rapporten och den e-postadress som får meddelandet när meddelandespårningen har slutförts (också redigerbar och måste finnas i någon av organisationens godkända domäner).</span><span class="sxs-lookup"><span data-stu-id="e1417-199">When you click **Next**, you're presented with a summary page that lists the filtering options that you selected, a unique (editable) title for the report, and the email address that receives the notification when the message trace completes (also editable, and must be in one of your organization's accepted domains).</span></span> <span data-ttu-id="e1417-200">Klicka **på Förbered rapport** för att skicka meddelandespårningen.</span><span class="sxs-lookup"><span data-stu-id="e1417-200">Click **Prepare report** to submit the message trace.</span></span> <span data-ttu-id="e1417-201">På **huvudsidan för meddelandespårning** kan du se status för rapporten i avsnittet **nedladdningsbara** rapporter.</span><span class="sxs-lookup"><span data-stu-id="e1417-201">On the main **Message trace** page, you can see the status of the report in the **Downloadable reports** section.</span></span>

<span data-ttu-id="e1417-202">Mer information om den information som returneras i de olika rapporttyperna finns i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="e1417-202">For more information about the information that's returned in the different report types, see the next section.</span></span>

## <a name="message-trace-results"></a><span data-ttu-id="e1417-203">Meddelandespårningsresultat</span><span class="sxs-lookup"><span data-stu-id="e1417-203">Message trace results</span></span>

<span data-ttu-id="e1417-204">De olika rapporttyperna returnerar olika informationsnivåer.</span><span class="sxs-lookup"><span data-stu-id="e1417-204">The different report types return different levels of information.</span></span> <span data-ttu-id="e1417-205">Den information som är tillgänglig i de olika rapporterna beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="e1417-205">The information that's available in the different reports is described in the following sections.</span></span>

### <a name="summary-report-output"></a><span data-ttu-id="e1417-206">Sammanfattningsrapportresultat</span><span class="sxs-lookup"><span data-stu-id="e1417-206">Summary report output</span></span>

<span data-ttu-id="e1417-207">När meddelandespårningen har körts visas resultatet, sorterat efter fallande datum/tid (senaste först).</span><span class="sxs-lookup"><span data-stu-id="e1417-207">After running the message trace, the results will be listed, sorted by descending date/time (most recent first).</span></span>

![Sammanfattningsrapportresultat för meddelandespårning i Säkerhets- & Efterlevnadscenter](../../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

<span data-ttu-id="e1417-209">Sammanfattningsrapporten innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="e1417-209">The summary report contains the following information:</span></span>

- <span data-ttu-id="e1417-210">**Datum:** Datum och tid då meddelandet togs emot av tjänsten med hjälp av den konfigurerade UTC-tidszonen.</span><span class="sxs-lookup"><span data-stu-id="e1417-210">**Date**: The date and time at which the message was received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="e1417-211">**Avsändare:** E-postadressen för avsändaren @ *(aliasdomänen).*</span><span class="sxs-lookup"><span data-stu-id="e1417-211">**Sender**: The email address of the sender (*alias*@*domain*).</span></span>

- <span data-ttu-id="e1417-212">**Mottagare:** Mottagarens eller mottagarnas e-postadress.</span><span class="sxs-lookup"><span data-stu-id="e1417-212">**Recipient**: The email address of the recipient or recipients.</span></span> <span data-ttu-id="e1417-213">För meddelanden som skickas till flera mottagare finns det en rad per mottagare.</span><span class="sxs-lookup"><span data-stu-id="e1417-213">For a message sent to multiple recipients, there's one line per recipient.</span></span> <span data-ttu-id="e1417-214">Om mottagaren är en distributionsgrupp, dynamisk distributionsgrupp eller e-postaktiverad säkerhetsgrupp blir gruppen den första mottagaren och därefter finns varje medlem i gruppen på en separat rad.</span><span class="sxs-lookup"><span data-stu-id="e1417-214">If the recipient is a distribution group, dynamic distribution group, or mail-enabled security group, the group will be the first recipient, and then each member of the group is on a separate line.</span></span>

- <span data-ttu-id="e1417-215">**Ämne:** De första 256 tecknen i meddelandets **ämnesfält.**</span><span class="sxs-lookup"><span data-stu-id="e1417-215">**Subject**: The first 256 characters of the message's **Subject:** field.</span></span>

- <span data-ttu-id="e1417-216">**Status:** Dessa värden beskrivs i [avsnittet Leveransstatus.](#delivery-status)</span><span class="sxs-lookup"><span data-stu-id="e1417-216">**Status**: These values are described in the [Delivery status](#delivery-status) section.</span></span>

<span data-ttu-id="e1417-217">Som standard läses de första 250 resultaten in och är lättillgängliga.</span><span class="sxs-lookup"><span data-stu-id="e1417-217">By default, the first 250 results are loaded and readily available.</span></span> <span data-ttu-id="e1417-218">När du rullar nedåt finns det en liten paus när nästa uppsättning resultat läses in.</span><span class="sxs-lookup"><span data-stu-id="e1417-218">When you scroll down, there's a slight pause as the next batch of results are loaded.</span></span> <span data-ttu-id="e1417-219">I stället för att  rulla kan du klicka på Läs in alla för att läsa in alla resultat upp till maximalt 10 000.</span><span class="sxs-lookup"><span data-stu-id="e1417-219">Instead of scrolling, you can click **Load all** to load all of the results up to a maximum of 10,000.</span></span>

<span data-ttu-id="e1417-220">Du kan klicka på kolumnrubrikerna för att sortera resultatet efter värdena i kolumnen i stigande eller fallande ordning.</span><span class="sxs-lookup"><span data-stu-id="e1417-220">You can click on the column headers to sort the results by the values in that column in ascending or descending order.</span></span>

<span data-ttu-id="e1417-221">Du kan klicka **på Filtrera** resultat om du vill filtrera resultatet efter en eller flera kolumner.</span><span class="sxs-lookup"><span data-stu-id="e1417-221">You can click **Filter results** to filter the results by one or more columns.</span></span>

<span data-ttu-id="e1417-222">Du kan exportera resultatet när du har markerat en eller flera rader genom att klicka på **Exportera** resultat och sedan välja Exportera alla **resultat,** Exportera inlästa **resultat** eller Exportera **markerat.**</span><span class="sxs-lookup"><span data-stu-id="e1417-222">You can export the results after you've selected one or more rows by clicking **Export results** and then selecting **Export all results**, **Export loaded results**, or **Export selected**.</span></span>

#### <a name="find-related-records-for-this-message"></a><span data-ttu-id="e1417-223">Hitta relaterade poster för det här meddelandet</span><span class="sxs-lookup"><span data-stu-id="e1417-223">Find related records for this message</span></span>

<span data-ttu-id="e1417-224">Relaterade meddelandeposter är poster som delade samma meddelande-ID.</span><span class="sxs-lookup"><span data-stu-id="e1417-224">Related message records are records that shared the same Message ID.</span></span> <span data-ttu-id="e1417-225">Kom ihåg att även ett enskilt meddelande som skickas mellan två personer kan generera flera poster.</span><span class="sxs-lookup"><span data-stu-id="e1417-225">Remember, even a single message sent between two people can generate multiple records.</span></span> <span data-ttu-id="e1417-226">Antalet poster ökar när meddelandet påverkas av distributionsgruppsexpansion, vidarebefordran, e-postflödesregler (kallas även transportregler) osv.</span><span class="sxs-lookup"><span data-stu-id="e1417-226">The number of records increases when the message is affected by distribution group expansion, forwarding, mail flow rules (also known as transport rules), etc.</span></span>

<span data-ttu-id="e1417-227">När du har markera kryssrutan för en rad kan du hitta  relaterade poster för meddelandet  genom att klicka på knappen Sök relaterat som visas eller genom att välja Fler alternativ För att hitta relaterade poster för ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> meddelandet).</span><span class="sxs-lookup"><span data-stu-id="e1417-227">After you select a row's check box, you can find related records for the message by clicking the **Find related** button that appears, or by selecting **More options** ![More](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Find related records for this message**).</span></span>

<span data-ttu-id="e1417-228">Mer information om meddelande-ID finns i avsnittet Meddelande-ID tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="e1417-228">For more information about the Message ID, see the Message ID section earlier in this article.</span></span>

#### <a name="message-trace-details"></a><span data-ttu-id="e1417-229">Information om meddelandespårning</span><span class="sxs-lookup"><span data-stu-id="e1417-229">Message trace details</span></span>

<span data-ttu-id="e1417-230">I sammanfattningsrapportens utdata kan du visa information om ett meddelande med någon av följande metoder:</span><span class="sxs-lookup"><span data-stu-id="e1417-230">In the summary report output, you can view details about a message by using either of the following methods:</span></span>

- <span data-ttu-id="e1417-231">Markera raden (klicka någonstans på raden utom kryssrutan).</span><span class="sxs-lookup"><span data-stu-id="e1417-231">Select the row (click anywhere in the row except the check box).</span></span>

- <span data-ttu-id="e1417-232">Markera radens kryssruta och klicka **på Fler alternativ** Visa ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **meddelandeinformation.**</span><span class="sxs-lookup"><span data-stu-id="e1417-232">Select the row's check box and click **More options** ![More](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **View message details**.</span></span>

   ![Information när du dubbelklickat på en rad i meddelandespårningen för sammanfattningsrapport resulterar i & Säkerhets- och efterlevnadscenter](../../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

<span data-ttu-id="e1417-234">Informationen i meddelandespårningen innehåller följande ytterligare information som inte finns i sammanfattningsrapporten:</span><span class="sxs-lookup"><span data-stu-id="e1417-234">The message trace details contain the following additional information that's not present in the summary report:</span></span>

- <span data-ttu-id="e1417-235">**Meddelandehändelser:** Det här avsnittet innehåller klassificeringar som hjälper till att kategorisera åtgärder som tjänsten vidtar för meddelanden.</span><span class="sxs-lookup"><span data-stu-id="e1417-235">**Message events**: This section contains classifications that help categorize the actions that the service takes on messages.</span></span> <span data-ttu-id="e1417-236">**Några av de mest intressanta händelser som** du kan stöta på är:</span><span class="sxs-lookup"><span data-stu-id="e1417-236">**Some of the more interesting events** that you might encounter are:</span></span>

  - <span data-ttu-id="e1417-237">**Ta** emot: Meddelandet togs emot av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="e1417-237">**Receive**: The message was received by the service.</span></span>

  - <span data-ttu-id="e1417-238">**Skicka:** Meddelandet skickades av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="e1417-238">**Send**: The message was sent by the service.</span></span>

  - <span data-ttu-id="e1417-239">**Fel:** Meddelandet kunde inte levereras.</span><span class="sxs-lookup"><span data-stu-id="e1417-239">**Fail**: The message failed to be delivered.</span></span>

  - <span data-ttu-id="e1417-240">**Leverera:** Meddelandet levererades till en postlåda.</span><span class="sxs-lookup"><span data-stu-id="e1417-240">**Deliver**: The message was delivered to a mailbox.</span></span>

  - <span data-ttu-id="e1417-241">**Expandera:** Meddelandet skickades till en distributionsgrupp som expanderats.</span><span class="sxs-lookup"><span data-stu-id="e1417-241">**Expand**: The message was sent to a distribution group that was expanded.</span></span>

  - <span data-ttu-id="e1417-242">**Överföring:** Mottagare har flyttats till ett nytt meddelande på grund av innehållskonvertering, begränsningar för mottagare eller agenter.</span><span class="sxs-lookup"><span data-stu-id="e1417-242">**Transfer**: Recipients were moved to a bifurcated message because of content conversion, message recipient limits, or agents.</span></span>

  - <span data-ttu-id="e1417-243">**Skjut upp:** Meddelandets leverans har skjutits upp och kan försökas igen senare.</span><span class="sxs-lookup"><span data-stu-id="e1417-243">**Defer**: The message delivery was postponed and might be re-attempted later.</span></span>

  - <span data-ttu-id="e1417-244">**Löst:** Meddelandet omdirigerades till en ny mottagaradress baserat på ett active Directory-upp tittande.</span><span class="sxs-lookup"><span data-stu-id="e1417-244">**Resolved**: The message was redirected to a new recipient address based on an Active Directory look up.</span></span> <span data-ttu-id="e1417-245">När detta händer visas den ursprungliga mottagaradressen på en separat rad i meddelandespårningen tillsammans med meddelandets slutgiltiga leveransstatus.</span><span class="sxs-lookup"><span data-stu-id="e1417-245">When this happens, the original recipient address is listed in a separate row in the message trace along with the final delivery status for the message.</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="e1417-246">Ett ojämnt meddelande som levereras genererar flera **händelseposter** i meddelandespårningen.</span><span class="sxs-lookup"><span data-stu-id="e1417-246">An uneventful message that's successfully delivered will generate multiple **Event** entries in the message trace.</span></span>
  > 
  > - <span data-ttu-id="e1417-247">Listan är inte uttömmande.</span><span class="sxs-lookup"><span data-stu-id="e1417-247">This list is not meant to be exhaustive.</span></span> <span data-ttu-id="e1417-248">Beskrivningar av fler händelser finns i Händelsetyper [i meddelandespårningsloggen.](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log)</span><span class="sxs-lookup"><span data-stu-id="e1417-248">For descriptions of more events, see [Event types in the message tracking log](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log).</span></span> <span data-ttu-id="e1417-249">Observera att den här länken Exchange Server ämne (lokal Exchange).</span><span class="sxs-lookup"><span data-stu-id="e1417-249">Note that this link is an Exchange Server (on-premises Exchange) topic.</span></span>

- <span data-ttu-id="e1417-250">**Mer information:** Det här avsnittet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="e1417-250">**More information**: This section contains the following details:</span></span>

  - <span data-ttu-id="e1417-251">**Meddelande-ID:** Det här värdet beskrivs i [avsnittet Meddelande-ID](#message-id) tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="e1417-251">**Message ID**: This value is described in the [Message ID](#message-id) section earlier in this article.</span></span> <span data-ttu-id="e1417-252">Till exempel `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span><span class="sxs-lookup"><span data-stu-id="e1417-252">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

  - <span data-ttu-id="e1417-253">**Meddelandestorlek**</span><span class="sxs-lookup"><span data-stu-id="e1417-253">**Message size**</span></span>

  - <span data-ttu-id="e1417-254">**Från IP:** IP-adressen för datorn som skickade meddelandet.</span><span class="sxs-lookup"><span data-stu-id="e1417-254">**From IP**: The IP address of the computer that sent the message.</span></span> <span data-ttu-id="e1417-255">För utgående meddelanden som skickas från Exchange Online är det här värdet tomt.</span><span class="sxs-lookup"><span data-stu-id="e1417-255">For outbound messages sent from Exchange Online, this value is blank.</span></span>

  - <span data-ttu-id="e1417-256">**Till IP:** IP-adressen eller adresserna där tjänsten försökte leverera meddelandet.</span><span class="sxs-lookup"><span data-stu-id="e1417-256">**To IP**: The IP address or addresses where the service attempted to deliver the message.</span></span> <span data-ttu-id="e1417-257">Om meddelandet har flera mottagare visas de.</span><span class="sxs-lookup"><span data-stu-id="e1417-257">If the message has multiple recipients, these are displayed.</span></span> <span data-ttu-id="e1417-258">Det här värdet är tomt för inkommande meddelanden som skickas till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e1417-258">For inbound messages sent to Exchange Online, this value is blank.</span></span>

### <a name="enhanced-summary-reports"></a><span data-ttu-id="e1417-259">Förbättrade sammanfattningsrapporter</span><span class="sxs-lookup"><span data-stu-id="e1417-259">Enhanced summary reports</span></span>

<span data-ttu-id="e1417-260">Tillgängliga (slutförda) förbättrade sammanfattningsrapporter finns tillgängliga **i avsnittet hämtningsbara rapporter** i meddelandespårningen i början.</span><span class="sxs-lookup"><span data-stu-id="e1417-260">Available (completed) Enhanced summary reports are available in the **Downloadable reports** section at the beginning message trace.</span></span> <span data-ttu-id="e1417-261">Följande information finns i rapporten:</span><span class="sxs-lookup"><span data-stu-id="e1417-261">The following information is available in the report:</span></span>

- <span data-ttu-id="e1417-262">**origin_timestamp:** Datum och tid då meddelandet ursprungligen togs emot av tjänsten med hjälp av den <sup>\*</sup> konfigurerade UTC-tidszonen.</span><span class="sxs-lookup"><span data-stu-id="e1417-262">**origin_timestamp**<sup>\*</sup>: The date and time when the message was initially received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="e1417-263">**sender_address:** Avsändarens e-postadress @ *(aliasdomän).*</span><span class="sxs-lookup"><span data-stu-id="e1417-263">**sender_address**: The sender's email address (*alias*@*domain*).</span></span>

- <span data-ttu-id="e1417-264">**Recipient_status:** Status för leverans av meddelandet till mottagaren.</span><span class="sxs-lookup"><span data-stu-id="e1417-264">**Recipient_status**: The status of the delivery of the message to the recipient.</span></span> <span data-ttu-id="e1417-265">Om meddelandet skickades till flera mottagare visas alla mottagare och motsvarande status för dem, i \<*email address*\> formatet: ## \<*status*\></span><span class="sxs-lookup"><span data-stu-id="e1417-265">If the message was sent to multiple recipients, it will show all the recipients and the corresponding status for each, in the format: \<*email address*\>##\<*status*\>.</span></span> <span data-ttu-id="e1417-266">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="e1417-266">For example:</span></span>

  - <span data-ttu-id="e1417-267">**##Receive, Send** means the message was received by the service and was sent to the intended destination.</span><span class="sxs-lookup"><span data-stu-id="e1417-267">**##Receive, Send** means the message was received by the service and was sent to the intended destination.</span></span>

  - <span data-ttu-id="e1417-268">**##Receive, fail** means the message was received by the service but delivery to the intended destination failed.</span><span class="sxs-lookup"><span data-stu-id="e1417-268">**##Receive, Fail** means the message was received by the service but delivery to the intended destination failed.</span></span>

  - <span data-ttu-id="e1417-269">**##Receive, Deliver** means the message was received by the service and was delivered to the recipient's mailbox.</span><span class="sxs-lookup"><span data-stu-id="e1417-269">**##Receive, Deliver** means the message was received by the service and was delivered to the recipient's mailbox.</span></span>

- <span data-ttu-id="e1417-270">**message_subject:** De första 256 tecknen i meddelandets **ämnesfält.**</span><span class="sxs-lookup"><span data-stu-id="e1417-270">**message_subject**: The first 256 characters of the message's **Subject** field.</span></span>

- <span data-ttu-id="e1417-271">**total_bytes:** Storleken på meddelandet i byte, inklusive bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="e1417-271">**total_bytes**: The size of the message in bytes, including attachments.</span></span>

- <span data-ttu-id="e1417-272">**message_id:** Det här värdet beskrivs i avsnittet [Meddelande-ID](#message-id) tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="e1417-272">**message_id**: This value is described in the [Message ID](#message-id) section earlier in this article.</span></span> <span data-ttu-id="e1417-273">Till exempel `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span><span class="sxs-lookup"><span data-stu-id="e1417-273">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

- <span data-ttu-id="e1417-274">**network_message_id:** Ett unikt meddelande-ID-värde som finns kvar i alla kopior av meddelandet som kan skapas på grund av expandering eller distributionsgruppsexpansion.</span><span class="sxs-lookup"><span data-stu-id="e1417-274">**network_message_id**: A unique message ID value that persists across all copies of the message that might be created due to bifurcation or distribution group expansion.</span></span> <span data-ttu-id="e1417-275">Ett exempelvärde är `1341ac7b13fb42ab4d4408cf7f55890f` .</span><span class="sxs-lookup"><span data-stu-id="e1417-275">An example value is `1341ac7b13fb42ab4d4408cf7f55890f`.</span></span>

- <span data-ttu-id="e1417-276">**original_client_ip:** IP-adressen för avsändarens klient.</span><span class="sxs-lookup"><span data-stu-id="e1417-276">**original_client_ip**: The IP address of the sender's client.</span></span>

- <span data-ttu-id="e1417-277">**riktning:** Anger om meddelandet skickades inkommande (1) till din organisation eller om det skickades utgående (2) från din organisation.</span><span class="sxs-lookup"><span data-stu-id="e1417-277">**directionality**: Indicates whether the message was sent inbound (1) to your organization, or whether it was sent outbound (2) from your organization.</span></span>

- <span data-ttu-id="e1417-278">**connector_id:** Namnet på käll- eller målkopplingen.</span><span class="sxs-lookup"><span data-stu-id="e1417-278">**connector_id**: The name of the source or destination connector.</span></span> <span data-ttu-id="e1417-279">Mer information om kopplingar i Exchange Online finns i Konfigurera [e-postflöde med kopplingar i Office 365.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)</span><span class="sxs-lookup"><span data-stu-id="e1417-279">For more information about connectors in Exchange Online, see [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

- <span data-ttu-id="e1417-280">**delivery_priority:** <sup>\*</sup> Om meddelandet skickades med **hög,** **låg** eller **normal** prioritet.</span><span class="sxs-lookup"><span data-stu-id="e1417-280">**delivery_priority**<sup>\*</sup>: Whether the message was sent with **High**, **Low**, or **Normal** priority.</span></span>

<span data-ttu-id="e1417-281"><sup>\*</sup> De här egenskaperna är bara tillgängliga i utökade sammanfattningsrapporter.</span><span class="sxs-lookup"><span data-stu-id="e1417-281"><sup>\*</sup> These properties are only available in Enhanced summary reports.</span></span>

### <a name="extended-reports"></a><span data-ttu-id="e1417-282">Utökade rapporter</span><span class="sxs-lookup"><span data-stu-id="e1417-282">Extended reports</span></span>

<span data-ttu-id="e1417-283">Tillgängliga (slutförda) utökade rapporter är tillgängliga **i avsnittet nedladdningsbara** rapporter i början av meddelandespårning.</span><span class="sxs-lookup"><span data-stu-id="e1417-283">Available (completed) Extended reports are available in the **Downloadable reports** section at the beginning of message trace.</span></span> <span data-ttu-id="e1417-284">Praktiskt taget all information från en utökad sammanfattningsrapport finns tillgänglig i en utökad rapport (med undantag för **origin_timestamp** och **delivery_priority).**</span><span class="sxs-lookup"><span data-stu-id="e1417-284">Virtually all of the information from an Enhanced summary report is available in an Extended report (with the exception of **origin_timestamp** and **delivery_priority**).</span></span> <span data-ttu-id="e1417-285">Följande ytterligare information är endast tillgänglig i en utökad rapport:</span><span class="sxs-lookup"><span data-stu-id="e1417-285">The following additional information is only available in an Extended report:</span></span>

- <span data-ttu-id="e1417-286">**client_ip:** IP-adressen för den e-postserver eller meddelandeklient som skickade meddelandet.</span><span class="sxs-lookup"><span data-stu-id="e1417-286">**client_ip**: The IP address of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="e1417-287">**client_hostname:** Värdnamnet eller FQDN för e-postservern eller meddelandeklienten som skickade meddelandet.</span><span class="sxs-lookup"><span data-stu-id="e1417-287">**client_hostname**: The host name or FQDN of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="e1417-288">**server_ip:** IP-adressen för källan eller målservern.</span><span class="sxs-lookup"><span data-stu-id="e1417-288">**server_ip**: The IP address of the source or destination server.</span></span>

- <span data-ttu-id="e1417-289">**server_hostname:** Målserverns värdnamn eller FQDN.</span><span class="sxs-lookup"><span data-stu-id="e1417-289">**server_hostname**: The host name or FQDN of the destination server.</span></span>

- <span data-ttu-id="e1417-290">**source_context:** Extra information kopplad till **källfältet.**</span><span class="sxs-lookup"><span data-stu-id="e1417-290">**source_context**: Extra information associated with the **source** field.</span></span> <span data-ttu-id="e1417-291">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="e1417-291">For example:</span></span>

  - `Protocol Filter Agent`

  - `3489061114359050000`

- <span data-ttu-id="e1417-292">**källa:** Exchange Online-komponenten som ansvarar för händelsen.</span><span class="sxs-lookup"><span data-stu-id="e1417-292">**source**: The Exchange Online component that's responsible for the event.</span></span> <span data-ttu-id="e1417-293">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="e1417-293">For example:</span></span>

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- <span data-ttu-id="e1417-294">**event_id:** De motsvarar värdena för **meddelandehändelsen** som förklaras i Avsnittet [Hitta relaterade poster för det här](#find-related-records-for-this-message) meddelandet.</span><span class="sxs-lookup"><span data-stu-id="e1417-294">**event_id**: These correspond to the **Message event** values that are explained in the [Find related records for this message](#find-related-records-for-this-message) section.</span></span>

- <span data-ttu-id="e1417-295">**internal_message_id:** En meddelandeidentifierare som har tilldelats av Exchange Online-servern som för närvarande bearbetar meddelandet.</span><span class="sxs-lookup"><span data-stu-id="e1417-295">**internal_message_id**: A message identifier that's assigned by the Exchange Online server that's currently processing the message.</span></span>

- <span data-ttu-id="e1417-296">**recipient_address:** E-postadresserna till meddelandets mottagare.</span><span class="sxs-lookup"><span data-stu-id="e1417-296">**recipient_address**: The email addresses of the message's recipients.</span></span> <span data-ttu-id="e1417-297">Flera e-postadresser avgränsas med semikolontecken (;).</span><span class="sxs-lookup"><span data-stu-id="e1417-297">Multiple email addresses are separated by the semicolon character (;).</span></span>

- <span data-ttu-id="e1417-298">**recipient_count:** Det totala antalet mottagare i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="e1417-298">**recipient_count**: The total number of recipients in the message.</span></span>

- <span data-ttu-id="e1417-299">**related_recipient_address:** Används med `EXPAND` `REDIRECT` och `RESOLVE` händelser för att visa andra mottagares e-postadresser som är kopplade till meddelandet.</span><span class="sxs-lookup"><span data-stu-id="e1417-299">**related_recipient_address**: Used with `EXPAND`, `REDIRECT`, and `RESOLVE` events to display other recipient email addresses that are associated with the message.</span></span>

- <span data-ttu-id="e1417-300">**referens:** Det här fältet innehåller ytterligare information för specifika typer av händelser.</span><span class="sxs-lookup"><span data-stu-id="e1417-300">**reference**: This field contains additional information for specific types of events.</span></span> <span data-ttu-id="e1417-301">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="e1417-301">For example:</span></span>

  - <span data-ttu-id="e1417-302">**DSN:** Innehåller rapportlänken, som är **message_id-värdet** för det associerade leveransstatusmeddelandet (kallas även DSN, rapport om utebliven leverans, NDR eller icke-leveranskavisering) om ett DSN genereras senare till den här händelsen.</span><span class="sxs-lookup"><span data-stu-id="e1417-302">**DSN**: Contains the report link, which is the **message_id** value of the associated delivery status notification (also known as a DSN, non-delivery report, NDR, or bounce message) if a DSN is generated subsequent to this event.</span></span> <span data-ttu-id="e1417-303">Om det här är ett DSN-meddelande innehåller det **message_id** det ursprungliga meddelandet som DSN skapades för.</span><span class="sxs-lookup"><span data-stu-id="e1417-303">If this is a DSN message, this field contains the **message_id** value of the original message that the DSN was generated for.</span></span>

  - <span data-ttu-id="e1417-304">**EXPANDERA:** Innehåller **related_recipient_address** värdet för relaterade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="e1417-304">**EXPAND**: Contains the **related_recipient_address** value of the related messages.</span></span>

  - <span data-ttu-id="e1417-305">**RECEIVE**: Kan innehålla **det message_id** relaterade meddelandet om meddelandet har skapats av andra processer (till exempel inkorgsregler).</span><span class="sxs-lookup"><span data-stu-id="e1417-305">**RECEIVE**: Might contain the **message_id** value of the related message if the message was generated by other processes (for example, Inbox rules).</span></span>

  - <span data-ttu-id="e1417-306">**SEND**: Contains the **internal_message_id** value of any DSN messages.</span><span class="sxs-lookup"><span data-stu-id="e1417-306">**SEND**: Contains the **internal_message_id** value of any DSN messages.</span></span>

  - <span data-ttu-id="e1417-307">**ÖVERFÖRING:** Innehåller **internal_message_id** värdet för det meddelande som ska delas upp (t.ex. efter innehållskonvertering, begränsningar för mottagare eller representanter för meddelanden).</span><span class="sxs-lookup"><span data-stu-id="e1417-307">**TRANSFER**: Contains the **internal_message_id** value of the message that's being forked (for example, by content conversion, message recipient limits, or agents).</span></span>

  - <span data-ttu-id="e1417-308">**MAILBOXRULE:** Innehåller **det internal_message_id** för det inkommande meddelandet som orsakade att inkorgsregeln genererade det utgående meddelandet.</span><span class="sxs-lookup"><span data-stu-id="e1417-308">**MAILBOXRULE**: Contains the **internal_message_id** value of the inbound message that caused the Inbox rule to generate the outbound message.</span></span>

    <span data-ttu-id="e1417-309">För andra typer av händelser är det här fältet vanligtvis tomt.</span><span class="sxs-lookup"><span data-stu-id="e1417-309">For other types of events, this field is usually blank.</span></span>

- <span data-ttu-id="e1417-310">**return_path:** Den avsändar-e-postadress som anges av kommandot **E-POST** FRÅN som skickade meddelandet.</span><span class="sxs-lookup"><span data-stu-id="e1417-310">**return_path**: The return email address specified by the **MAIL FROM** command that sent the message.</span></span> <span data-ttu-id="e1417-311">Även om fältet aldrig är tomt kan värdet för null-avsändaradressen representeras `<>` som.</span><span class="sxs-lookup"><span data-stu-id="e1417-311">Although this field is never empty, it can have the null sender address value represented as `<>`.</span></span>

- <span data-ttu-id="e1417-312">**message_info:** Ytterligare information om meddelandet.</span><span class="sxs-lookup"><span data-stu-id="e1417-312">**message_info**: Additional information about the message.</span></span> <span data-ttu-id="e1417-313">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="e1417-313">For example:</span></span>

  - <span data-ttu-id="e1417-314">Datum-tid för meddelandets ursprung i UTC för `DELIVER` och `SEND` händelser.</span><span class="sxs-lookup"><span data-stu-id="e1417-314">The message origination date-time in UTC for `DELIVER` and `SEND` events.</span></span> <span data-ttu-id="e1417-315">Datum-tid för ursprung är tiden då meddelandet först angav Exchange Online-organisationen.</span><span class="sxs-lookup"><span data-stu-id="e1417-315">The origination date-time is the time when the message first entered the Exchange Online organization.</span></span> <span data-ttu-id="e1417-316">UTC-datumtiden representeras i ISO 8601-datum/tid-format: , där = år, = månad, = dag, anger början av `yyyy-mm-ddThh:mm:ss.fffZ` `yyyy` `mm` `dd` `T` `hh` tidskomponenten, = timme, `mm` = minut, = sekund, `ss` `fff` = `Z` `Zulu` bråktal i en sekund och betecknar, vilket är ett annat sätt att betecknar UTC.</span><span class="sxs-lookup"><span data-stu-id="e1417-316">The UTC date-time is represented in the ISO 8601 date-time format: `yyyy-mm-ddThh:mm:ss.fffZ`, where `yyyy` = year, `mm` = month, `dd` = day, `T` indicates the beginning of the time component, `hh` = hour, `mm` = minute, `ss` = second, `fff` = fractions of a second, and `Z` signifies `Zulu`, which is another way to denote UTC.</span></span>

  - <span data-ttu-id="e1417-317">Autentiseringsfel.</span><span class="sxs-lookup"><span data-stu-id="e1417-317">Authentication errors.</span></span> <span data-ttu-id="e1417-318">Du kan till exempel se värdet och typen av autentisering `11a` som användes när autentiseringsfelet inträffade.</span><span class="sxs-lookup"><span data-stu-id="e1417-318">For example, you might see the value `11a` and the type of authentication that was used when the authentication error occurred.</span></span>

- <span data-ttu-id="e1417-319">**tenant_id:** Ett GUID-värde som representerar Exchange Online-organisationen (till exempel `39238e87-b5ab-4ef6-a559-af54c6b07b42` ).</span><span class="sxs-lookup"><span data-stu-id="e1417-319">**tenant_id**: A GUID value that represents the Exchange Online organization (for example, `39238e87-b5ab-4ef6-a559-af54c6b07b42`).</span></span>

- <span data-ttu-id="e1417-320">**original_server_ip:** IP-adressen till den ursprungliga servern.</span><span class="sxs-lookup"><span data-stu-id="e1417-320">**original_server_ip**: The IP address of the original server.</span></span>

- <span data-ttu-id="e1417-321">**custom_data:** Innehåller data som är relaterade till specifika händelsetyper.</span><span class="sxs-lookup"><span data-stu-id="e1417-321">**custom_data**: Contains data related to specific event types.</span></span> <span data-ttu-id="e1417-322">Mer information finns i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="e1417-322">For more information, see the following sections.</span></span>

#### <a name="custom_data-values"></a><span data-ttu-id="e1417-323">custom_data värden</span><span class="sxs-lookup"><span data-stu-id="e1417-323">custom_data values</span></span>

<span data-ttu-id="e1417-324">Fältet **custom_data** för en `AGENTINFO` händelse används av olika Exchange Online-agenter för att logga information om bearbetningen av meddelanden.</span><span class="sxs-lookup"><span data-stu-id="e1417-324">The **custom_data** field for an `AGENTINFO` event is used by a variety of Exchange Online agents to log message processing details.</span></span> <span data-ttu-id="e1417-325">Några av de mer intressanta representanterna beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="e1417-325">Some of the more interesting agents are described in the following sections.</span></span>

#### <a name="spam-filter-agent"></a><span data-ttu-id="e1417-326">Agent för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="e1417-326">Spam filter agent</span></span>

<span data-ttu-id="e1417-327">Ett **custom_data** som börjar med `S:SFA` är från skräppostfilteragenten.</span><span class="sxs-lookup"><span data-stu-id="e1417-327">A **custom_data** value that starts with `S:SFA` is from the spam filter agent.</span></span> <span data-ttu-id="e1417-328">Huvuduppgifterna beskrivs i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="e1417-328">The key details are described in the following table:</span></span>

****

|<span data-ttu-id="e1417-329">Value</span><span class="sxs-lookup"><span data-stu-id="e1417-329">Value</span></span>|<span data-ttu-id="e1417-330">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e1417-330">Description</span></span>|
|---|---|
|`SFV=NSPM`|<span data-ttu-id="e1417-331">Meddelandet har markerats som icke skräppost och skickats till avsedda mottagare.</span><span class="sxs-lookup"><span data-stu-id="e1417-331">The message was marked as non-spam and was sent to the intended recipients.</span></span>|
|`SFV=SPM`|<span data-ttu-id="e1417-332">Meddelandet markerades som skräppost genom skräppostfiltrering (kallas även innehållsfiltrering).</span><span class="sxs-lookup"><span data-stu-id="e1417-332">The message was marked as spam by anti-spam filtering (also known as content filtering).</span></span>|
|`SFV=BLK`|<span data-ttu-id="e1417-333">Filtreringen hoppades över och meddelandet blockerades eftersom det kommer från en blockerad avsändare.</span><span class="sxs-lookup"><span data-stu-id="e1417-333">Filtering was skipped and the message was blocked because it originated from a blocked sender.</span></span>|
|`SFV=SKS`|<span data-ttu-id="e1417-334">Meddelandet markerades som skräppost innan det bearbetas av skräppostfiltrering.</span><span class="sxs-lookup"><span data-stu-id="e1417-334">The message was marked as spam prior to being processed by anti-spam filtering.</span></span> <span data-ttu-id="e1417-335">Detta inkluderar meddelanden där meddelandet har matchat en e-postflödesregel (även känt som transportregel) som automatiskt markerat det som skräppost och förbigått all ytterligare filtrering.</span><span class="sxs-lookup"><span data-stu-id="e1417-335">This includes messages where the message matched a mail flow rule (also known as a transport rule) to automatically mark it as spam and bypass all additional filtering.</span></span>|
|`SCL=<number>`|<span data-ttu-id="e1417-336">Mer information om de olika SCL-värdena och vad de betyder finns i [Konfidensnivåer för skräppost.](spam-confidence-levels.md)</span><span class="sxs-lookup"><span data-stu-id="e1417-336">For more information about the different SCL values and what they mean, see [Spam confidence levels](spam-confidence-levels.md).</span></span>|
|`PCL=<number>`|<span data-ttu-id="e1417-337">PCL-värdet (Phishing Confidence Level) för meddelandet.</span><span class="sxs-lookup"><span data-stu-id="e1417-337">The Phishing Confidence Level (PCL) value of the message.</span></span> <span data-ttu-id="e1417-338">De kan tolkas på samma sätt som SCL-värdena har dokumenterats i [konfidensnivåer för skräppost.](spam-confidence-levels.md)</span><span class="sxs-lookup"><span data-stu-id="e1417-338">These can be interpreted the same way as the SCL values documented in [Spam confidence levels](spam-confidence-levels.md).</span></span>|
|`DI=SB`|<span data-ttu-id="e1417-339">Meddelandets avsändare blockerades.</span><span class="sxs-lookup"><span data-stu-id="e1417-339">The sender of the message was blocked.</span></span>|
|`DI=SQ`|<span data-ttu-id="e1417-340">Meddelandet har satts i karantän.</span><span class="sxs-lookup"><span data-stu-id="e1417-340">The message was quarantined.</span></span>|
|`DI=SD`|<span data-ttu-id="e1417-341">Meddelandet togs bort.</span><span class="sxs-lookup"><span data-stu-id="e1417-341">The message was deleted.</span></span>|
|`DI=SJ`|<span data-ttu-id="e1417-342">Meddelandet skickades till mottagarens skräppostmapp.</span><span class="sxs-lookup"><span data-stu-id="e1417-342">The message was sent to the recipient's Junk Email folder.</span></span>|
|`DI=SN`|<span data-ttu-id="e1417-343">Meddelandet skickades via den vanliga utgående leveranspoolen.</span><span class="sxs-lookup"><span data-stu-id="e1417-343">The message was routed through the normal outbound delivery pool.</span></span>|
|`DI=SO`|<span data-ttu-id="e1417-344">Meddelandet skickades via leveranspoolen med högre risk.</span><span class="sxs-lookup"><span data-stu-id="e1417-344">The message was routed through the higher risk delivery pool.</span></span> <span data-ttu-id="e1417-345">Mer information finns i [högriskleveranspool för utgående meddelanden.](high-risk-delivery-pool-for-outbound-messages.md)</span><span class="sxs-lookup"><span data-stu-id="e1417-345">For more information, see [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span>|
|`SFS=[a]|SFS=[b]`|<span data-ttu-id="e1417-346">Detta betyder att reglerna för skräppost har matchats.</span><span class="sxs-lookup"><span data-stu-id="e1417-346">This denotes that spam rules were matched.</span></span>|
|`IPV=CAL`|<span data-ttu-id="e1417-347">Meddelandet släpptes igenom skräppostfiltret då IP-adressen specificerades i en lista över tillåtna IP-adresser i anslutningsfiltret.</span><span class="sxs-lookup"><span data-stu-id="e1417-347">The message was allowed through the spam filters because the IP address was specified in an IP Allow list in the connection filter.</span></span>|
|`H=<EHLOstring>`|<span data-ttu-id="e1417-348">En anslutande e-mailservers HELO- eller OEHLO-sträng.</span><span class="sxs-lookup"><span data-stu-id="e1417-348">The HELO or EHLO string of the connecting email server.</span></span>|
|`PTR=<ReverseDNS>`|<span data-ttu-id="e1417-349">PTR-posten för den avsändande IP-adressen, som även kallas den omvända DNS-adressen.</span><span class="sxs-lookup"><span data-stu-id="e1417-349">The PTR record of the sending IP address, also known as the reverse DNS address.</span></span>|
|

<span data-ttu-id="e1417-350">Ett **exempel custom_data** värde för ett meddelande som filtreras efter skräppost så här:</span><span class="sxs-lookup"><span data-stu-id="e1417-350">An example **custom_data** value for a message that's filtered for spam like this:</span></span>

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a><span data-ttu-id="e1417-351">Filteragent för skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="e1417-351">Malware filter agent</span></span>

<span data-ttu-id="e1417-352">Ett **custom_data** som börjar med kommer `S:AMA` från filteragenten för skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="e1417-352">A **custom_data** value that starts with `S:AMA` is from the malware filter agent.</span></span> <span data-ttu-id="e1417-353">Huvuduppgifterna beskrivs i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="e1417-353">The key details are described in the following table:</span></span>

****

|<span data-ttu-id="e1417-354">Value</span><span class="sxs-lookup"><span data-stu-id="e1417-354">Value</span></span>|<span data-ttu-id="e1417-355">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e1417-355">Description</span></span>|
|---|---|
|<span data-ttu-id="e1417-356">`AMA=SUM|v=1|` eller `AMA=EV|v=1`</span><span class="sxs-lookup"><span data-stu-id="e1417-356">`AMA=SUM|v=1|` or `AMA=EV|v=1`</span></span>|<span data-ttu-id="e1417-357">Meddelandet har fastställt att det innehåller skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="e1417-357">The message was determined to contain malware.</span></span> <span data-ttu-id="e1417-358">`SUM` anger att skadlig programvara kan ha upptäckts av ett antal motorer.</span><span class="sxs-lookup"><span data-stu-id="e1417-358">`SUM` indicates the malware could've been detected by any number of engines.</span></span> <span data-ttu-id="e1417-359">`EV` anger att skadlig programvara har upptäckts av en specifik motor.</span><span class="sxs-lookup"><span data-stu-id="e1417-359">`EV` indicates the malware was detected by a specific engine.</span></span> <span data-ttu-id="e1417-360">När skadlig programvara identifieras av en motor utlöser detta de efterföljande åtgärderna.</span><span class="sxs-lookup"><span data-stu-id="e1417-360">When malware is detected by an engine this triggers the subsequent actions.</span></span>|
|`Action=r`|<span data-ttu-id="e1417-361">Meddelandet har ersatts.</span><span class="sxs-lookup"><span data-stu-id="e1417-361">The message was replaced.</span></span>|
|`Action=p`|<span data-ttu-id="e1417-362">Meddelandet har kringgåts.</span><span class="sxs-lookup"><span data-stu-id="e1417-362">The message was bypassed.</span></span>|
|`Action=d`|<span data-ttu-id="e1417-363">Meddelandet har skjutits upp.</span><span class="sxs-lookup"><span data-stu-id="e1417-363">The message was deferred.</span></span>|
|`Action=s`|<span data-ttu-id="e1417-364">Meddelandet togs bort.</span><span class="sxs-lookup"><span data-stu-id="e1417-364">The message was deleted.</span></span>|
|`Action=st`|<span data-ttu-id="e1417-365">Meddelandet har kringgåts.</span><span class="sxs-lookup"><span data-stu-id="e1417-365">The message was bypassed.</span></span>|
|`Action=sy`|<span data-ttu-id="e1417-366">Meddelandet har kringgåts.</span><span class="sxs-lookup"><span data-stu-id="e1417-366">The message was bypassed.</span></span>|
|`Action=ni`|<span data-ttu-id="e1417-367">Meddelandet avvisades.</span><span class="sxs-lookup"><span data-stu-id="e1417-367">The message was rejected.</span></span>|
|`Action=ne`|<span data-ttu-id="e1417-368">Meddelandet avvisades.</span><span class="sxs-lookup"><span data-stu-id="e1417-368">The message was rejected.</span></span>|
|`Action=b`|<span data-ttu-id="e1417-369">Meddelandet blockerades.</span><span class="sxs-lookup"><span data-stu-id="e1417-369">The message was blocked.</span></span>|
|`Name=<malware>`|<span data-ttu-id="e1417-370">Namnet på den skadlig programvara som identifierades.</span><span class="sxs-lookup"><span data-stu-id="e1417-370">The name of the malware that was detected.</span></span>|
|`File=<filename>`|<span data-ttu-id="e1417-371">Namnet på filen som innehöll den skadliga programvaran.</span><span class="sxs-lookup"><span data-stu-id="e1417-371">The name of the file that contained the malware.</span></span>|
|

<span data-ttu-id="e1417-372">Ett exempel **custom_data** ett meddelande som innehåller skadlig programvara ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="e1417-372">An example **custom_data** value for a message that contains malware looks like this:</span></span>

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a><span data-ttu-id="e1417-373">Transportregelagent</span><span class="sxs-lookup"><span data-stu-id="e1417-373">Transport Rule agent</span></span>

<span data-ttu-id="e1417-374">Ett **custom_data** som börjar med `S:TRA` kommer från transportregelagenten för e-postflödesregler (kallas även transportregler).</span><span class="sxs-lookup"><span data-stu-id="e1417-374">A **custom_data** value that starts with`S:TRA` is from the Transport Rule agent for mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="e1417-375">Huvuduppgifterna beskrivs i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="e1417-375">The key details are described in the following table:</span></span>

****

|<span data-ttu-id="e1417-376">Value</span><span class="sxs-lookup"><span data-stu-id="e1417-376">Value</span></span>|<span data-ttu-id="e1417-377">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e1417-377">Description</span></span>|
|---|---|
|`ETR|ruleId=<guid>`|<span data-ttu-id="e1417-378">Det regel-ID som matchades.</span><span class="sxs-lookup"><span data-stu-id="e1417-378">The rule ID that was matched.</span></span>|
|`St=<datetime>`|<span data-ttu-id="e1417-379">Datum och tid i UTC när regelmatchning inträffade.</span><span class="sxs-lookup"><span data-stu-id="e1417-379">The date and time in UTC when the rule match occurred.</span></span>|
|`Action=<ActionDefinition>`|<span data-ttu-id="e1417-380">Åtgärden som tillämpats.</span><span class="sxs-lookup"><span data-stu-id="e1417-380">The action that was applied.</span></span> <span data-ttu-id="e1417-381">En lista över tillgängliga åtgärder finns i [E-postflödesregelåtgärder i Exchange Online.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="e1417-381">For a list of available actions, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>|
|`Mode=<Mode>`|<span data-ttu-id="e1417-382">Läget för regeln.</span><span class="sxs-lookup"><span data-stu-id="e1417-382">The mode of the rule.</span></span> <span data-ttu-id="e1417-383">Giltiga värden är:</span><span class="sxs-lookup"><span data-stu-id="e1417-383">Valid values are:</span></span><ul><li><span data-ttu-id="e1417-384">Framtvinga: Alla åtgärder för regeln tillämpas.</span><span class="sxs-lookup"><span data-stu-id="e1417-384">**Enforce**: All actions on the rule will be enforced.</span></span></li><li><span data-ttu-id="e1417-385">**Test med principtips:** Alla policytipsåtgärder skickas, men andra åtgärder vid tvingande åtgärder kommer inte att vidtas.</span><span class="sxs-lookup"><span data-stu-id="e1417-385">**Test with Policy Tips:**: Any Policy Tip actions will be sent, but other enforcement actions will not be acted on.</span></span></li><li><span data-ttu-id="e1417-386">**Testa utan principtips:** Åtgärder visas i en loggfil, men avsändarna meddelas inte på något sätt och åtgärder vid tillämpning kommer inte att vidtas.</span><span class="sxs-lookup"><span data-stu-id="e1417-386">**Test without Policy Tips**: Actions will be listed in a log file, but senders will not be notified in any way, and enforcement actions will not be acted on.</span></span></li></ul>|
|

<span data-ttu-id="e1417-387">Ett exempel **custom_data** värde för ett meddelande som matchar villkoren i en e-postflödesregel ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="e1417-387">An example **custom_data** value for a messages that matches the conditions of a mail flow rule looks like this:</span></span>

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
