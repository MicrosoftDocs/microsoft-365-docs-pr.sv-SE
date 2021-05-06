---
title: Använda innehållssökning för att söka efter importerade data från tredje part
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: Använd verktyget eDiscovery för innehållssökning för att söka efter objekt som importerats till postlådor i Microsoft 365 från en datakälla från tredje part genom att skapa frågor.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 24ca63cf78b85f7b8b5181d5babd16058b641128
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "52161593"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a><span data-ttu-id="f0880-103">Använda innehållssökning för att söka efter data från tredje part som importerats med en anpassad partnerkoppling</span><span class="sxs-lookup"><span data-stu-id="f0880-103">Use Content Search to search third-party data imported by a custom partner connector</span></span>

<span data-ttu-id="f0880-104">Du kan använda [verktyget eDiscovery](content-search.md) för innehållssökning i Säkerhets- och efterlevnadscenter för & för att söka efter objekt som importerats till postlådor i Microsoft 365 från en datakälla från tredje part.</span><span class="sxs-lookup"><span data-stu-id="f0880-104">You can use the [Content Search eDiscovery tool](content-search.md) in the Security & Compliance Center to search for items imported to mailboxes in Microsoft 365 from a third-party data source.</span></span> <span data-ttu-id="f0880-105">Du kan skapa en fråga för att söka i alla importerade dataobjekt från tredje part eller så kan du skapa en fråga för att söka efter specifika dataobjekt från tredje part.</span><span class="sxs-lookup"><span data-stu-id="f0880-105">You can create a query to search all imported third-party data items or you can create a query to search specific third-party data items.</span></span> <span data-ttu-id="f0880-106">Du kan också skapa en frågebaserad bevarandeprincip eller ett frågebaserat eDiscovery-bevarande för att bevara data från tredje part.</span><span class="sxs-lookup"><span data-stu-id="f0880-106">Also, you can also create a query-based retention policy or a query-based eDiscovery hold to preserve third-party data.</span></span>
  
<span data-ttu-id="f0880-107">Mer information om hur du arbetar med en partner för att importera data från tredje part och en lista över de datatyper från tredje part som du kan importera till Microsoft 365 finns i Arbeta med en partner för att arkivera data från tredje part [i Office 365.](work-with-partner-to-archive-third-party-data.md)</span><span class="sxs-lookup"><span data-stu-id="f0880-107">For more information about working with a partner to import third-party data and a list of the third-party data types that you can import to Microsoft 365, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0880-108">Vägledningen i den här artikeln gäller endast data från tredje part som importerats av en anpassad partnerkoppling.</span><span class="sxs-lookup"><span data-stu-id="f0880-108">The guidance in this article only applies to third-party data that was imported by a custom partner connector.</span></span> <span data-ttu-id="f0880-109">Den här artikeln gäller inte för data från tredje part som importeras med hjälp av datakopplingar från tredje part i [Microsofts efterlevnadscenter.](archiving-third-party-data.md#third-party-data-connectors)</span><span class="sxs-lookup"><span data-stu-id="f0880-109">This article doesn't apply to third-party data that is imported by using the [third-party data connectors](archiving-third-party-data.md#third-party-data-connectors) in the Microsoft compliance center.</span></span>
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="f0880-110">Skapa en fråga för att söka i alla data från tredje part</span><span class="sxs-lookup"><span data-stu-id="f0880-110">Creating a query to search all third-party data</span></span>

<span data-ttu-id="f0880-111">Om du vill söka efter (eller välja att behålla) alla typer av data från tredje part som du har importerat till Office 365 kan du använda värdeparet för meddelanden i nyckelordsrutan för en innehållssökning eller när du skapar ett frågebaserat `kind:externaldata` håll.</span><span class="sxs-lookup"><span data-stu-id="f0880-111">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold.</span></span> <span data-ttu-id="f0880-112">Om du till exempel vill söka efter objekt som importerats från en datakälla från tredje part och innehåller ordet "contoso" i egenskapen Ämne för det importerade objektet använder du följande fråga:</span><span class="sxs-lookup"><span data-stu-id="f0880-112">For example, to search for items imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```powershell
kind:externaldata AND subject:contoso
```

<span data-ttu-id="f0880-113">Exemplet med föregående nyckelordsfråga innehåller ämnesegenskapen.</span><span class="sxs-lookup"><span data-stu-id="f0880-113">The previous keyword query example includes the subject property.</span></span> <span data-ttu-id="f0880-114">En lista med andra egenskaper för dataobjekt från tredje part som kan ingå i en nyckelordsfråga finns i avsnittet "Mer information" i Arbeta med en partner för att arkivera data från tredje part [i Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span><span class="sxs-lookup"><span data-stu-id="f0880-114">For a list of other properties for third-party data items that can include in a keyword query, see the "More information" section in [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="f0880-115">När du skapar frågor för att söka och lagra data från tredje part kan du också använda villkor för att begränsa sökresultatet.</span><span class="sxs-lookup"><span data-stu-id="f0880-115">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results.</span></span> <span data-ttu-id="f0880-116">Mer information om hur du skapar innehållssökningsfrågor finns [i Nyckelordsfrågor och sökvillkor för innehållssökning.](keyword-queries-and-search-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="f0880-116">For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="f0880-117">Skapa en fråga för att söka efter specifika typer av data från tredje part</span><span class="sxs-lookup"><span data-stu-id="f0880-117">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="f0880-118">I stället för att söka efter alla typer av data från tredje part kan du skapa frågor som bara söker efter en viss typ av data från tredje part med hjälp av följande meddelandeegenskap: *värdepar* i nyckelordsrutan för en innehållssökning:</span><span class="sxs-lookup"><span data-stu-id="f0880-118">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message *property: value* pair in the keyword box for a Content Search:</span></span>
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="f0880-119">Om du till exempel vill söka efter Facebook-data som innehåller ordet "contoso" i egenskapen Ämne använder du följande fråga:</span><span class="sxs-lookup"><span data-stu-id="f0880-119">For example, to search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="f0880-120">I följande tabell visas de datatyper från tredje part som du kan söka i, och värdet som ska användas för meddelandeegenskapen för att specifikt söka efter den typen av  `itemclass:` data från tredje part.</span><span class="sxs-lookup"><span data-stu-id="f0880-120">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data.</span></span> <span data-ttu-id="f0880-121">Frågesyntaxen är inte fallkänslig.</span><span class="sxs-lookup"><span data-stu-id="f0880-121">The query syntax isn't case-sensitive.</span></span> 
  
|<span data-ttu-id="f0880-122">**Datatyp från tredje part**</span><span class="sxs-lookup"><span data-stu-id="f0880-122">**Third-party data type**</span></span>|<span data-ttu-id="f0880-123">**Värde för  `itemclass:` egenskap**</span><span class="sxs-lookup"><span data-stu-id="f0880-123">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f0880-124">AIM</span><span class="sxs-lookup"><span data-stu-id="f0880-124">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="f0880-125">American Sådd</span><span class="sxs-lookup"><span data-stu-id="f0880-125">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="f0880-126">AOL med pivotklient</span><span class="sxs-lookup"><span data-stu-id="f0880-126">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="f0880-127">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="f0880-127">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="f0880-128">Ares</span><span class="sxs-lookup"><span data-stu-id="f0880-128">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="f0880-129">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="f0880-129">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="f0880-130">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="f0880-130">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="f0880-131">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="f0880-131">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="f0880-132">Platshållare för Axs</span><span class="sxs-lookup"><span data-stu-id="f0880-132">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="f0880-133">Axs signerade</span><span class="sxs-lookup"><span data-stu-id="f0880-133">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="f0880-134">Voice</span><span class="sxs-lookup"><span data-stu-id="f0880-134">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="f0880-135">Bearshare</span><span class="sxs-lookup"><span data-stu-id="f0880-135">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="f0880-136">Bit Ent</span><span class="sxs-lookup"><span data-stu-id="f0880-136">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="f0880-137">Blackberry</span><span class="sxs-lookup"><span data-stu-id="f0880-137">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="f0880-138">BlackBerry-samtalsloggar</span><span class="sxs-lookup"><span data-stu-id="f0880-138">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="f0880-139">BlackBerry Messenger</span><span class="sxs-lookup"><span data-stu-id="f0880-139">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="f0880-140">BlackBerry PIN</span><span class="sxs-lookup"><span data-stu-id="f0880-140">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="f0880-141">BlackBerry-SMS</span><span class="sxs-lookup"><span data-stu-id="f0880-141">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="f0880-142">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="f0880-142">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="f0880-143">Bloomberg-meddelande</span><span class="sxs-lookup"><span data-stu-id="f0880-143">Bloomberg Message</span></span>  <br/> | `ipm.externaldata.conversation.Bloomberg Message*` <br/> |
|<span data-ttu-id="f0880-144">Bloomberg Messaging</span><span class="sxs-lookup"><span data-stu-id="f0880-144">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="f0880-145">Ruta</span><span class="sxs-lookup"><span data-stu-id="f0880-145">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="f0880-146">Cisco IM &amp; Presence Server</span><span class="sxs-lookup"><span data-stu-id="f0880-146">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="f0880-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="f0880-147">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="f0880-148">CipherCloud för Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="f0880-148">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="f0880-149">Direkt Anslut</span><span class="sxs-lookup"><span data-stu-id="f0880-149">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="f0880-150">Facebook</span><span class="sxs-lookup"><span data-stu-id="f0880-150">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="f0880-151">FastTrack</span><span class="sxs-lookup"><span data-stu-id="f0880-151">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="f0880-152">FXConnect</span><span class="sxs-lookup"><span data-stu-id="f0880-152">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="f0880-153">Flickr</span><span class="sxs-lookup"><span data-stu-id="f0880-153">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="f0880-154">Så här ser det ut</span><span class="sxs-lookup"><span data-stu-id="f0880-154">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="f0880-155">Google+</span><span class="sxs-lookup"><span data-stu-id="f0880-155">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="f0880-156">Google Talk</span><span class="sxs-lookup"><span data-stu-id="f0880-156">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="f0880-157">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="f0880-157">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="f0880-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="f0880-158">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="f0880-159">Hoppster</span><span class="sxs-lookup"><span data-stu-id="f0880-159">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="f0880-160">HubConnex</span><span class="sxs-lookup"><span data-stu-id="f0880-160">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="f0880-161">IBM Connections</span><span class="sxs-lookup"><span data-stu-id="f0880-161">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="f0880-162">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="f0880-162">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="f0880-163">ICE-chatt</span><span class="sxs-lookup"><span data-stu-id="f0880-163">ICE Chat</span></span>  <br/> | `ipm.externaldata.conversation.Ice Chat*` <br/> |
|<span data-ttu-id="f0880-164">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="f0880-164">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="f0880-165">Så här ser det ut</span><span class="sxs-lookup"><span data-stu-id="f0880-165">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="f0880-166">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="f0880-166">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="f0880-167">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="f0880-167">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="f0880-168">IRC</span><span class="sxs-lookup"><span data-stu-id="f0880-168">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="f0880-169">Jive</span><span class="sxs-lookup"><span data-stu-id="f0880-169">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="f0880-170">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="f0880-170">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="f0880-171">JXTA</span><span class="sxs-lookup"><span data-stu-id="f0880-171">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="f0880-172">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="f0880-172">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="f0880-173">MFTP</span><span class="sxs-lookup"><span data-stu-id="f0880-173">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="f0880-174">Microsoft UC</span><span class="sxs-lookup"><span data-stu-id="f0880-174">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="f0880-175">Mind Align</span><span class="sxs-lookup"><span data-stu-id="f0880-175">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="f0880-176">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="f0880-176">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="f0880-177">MSN</span><span class="sxs-lookup"><span data-stu-id="f0880-177">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="f0880-178">MySpace</span><span class="sxs-lookup"><span data-stu-id="f0880-178">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="f0880-179">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="f0880-179">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="f0880-180">OpenNap</span><span class="sxs-lookup"><span data-stu-id="f0880-180">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="f0880-181">Pinterest</span><span class="sxs-lookup"><span data-stu-id="f0880-181">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="f0880-182">Pivot</span><span class="sxs-lookup"><span data-stu-id="f0880-182">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="f0880-183">QQ</span><span class="sxs-lookup"><span data-stu-id="f0880-183">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="f0880-184">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="f0880-184">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="f0880-185">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="f0880-185">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="f0880-186">Skype för företag</span><span class="sxs-lookup"><span data-stu-id="f0880-186">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="f0880-187">Slack för företagsrutnät</span><span class="sxs-lookup"><span data-stu-id="f0880-187">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="f0880-188">SoftEther</span><span class="sxs-lookup"><span data-stu-id="f0880-188">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="f0880-189">Squawker</span><span class="sxs-lookup"><span data-stu-id="f0880-189">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="f0880-190">Symphony</span><span class="sxs-lookup"><span data-stu-id="f0880-190">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="f0880-191">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="f0880-191">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="f0880-192">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="f0880-192">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="f0880-193">Tor</span><span class="sxs-lookup"><span data-stu-id="f0880-193">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="f0880-194">TTT</span><span class="sxs-lookup"><span data-stu-id="f0880-194">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="f0880-195">Twitter</span><span class="sxs-lookup"><span data-stu-id="f0880-195">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="f0880-196">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="f0880-196">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="f0880-197">Vimeo</span><span class="sxs-lookup"><span data-stu-id="f0880-197">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="f0880-198">WinMX</span><span class="sxs-lookup"><span data-stu-id="f0880-198">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="f0880-199">Winny</span><span class="sxs-lookup"><span data-stu-id="f0880-199">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="f0880-200">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="f0880-200">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="f0880-201">Yammer</span><span class="sxs-lookup"><span data-stu-id="f0880-201">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="f0880-202">Yellow Entitet</span><span class="sxs-lookup"><span data-stu-id="f0880-202">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="f0880-203">YouTube</span><span class="sxs-lookup"><span data-stu-id="f0880-203">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
