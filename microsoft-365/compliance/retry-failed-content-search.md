---
title: Försök att försöka med en innehållssökning igen för att lösa ett innehållsplatsfel
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Under en undersökning kan du använda knappen Försök igen för att lösa innehållssökningar som har fel på innehållsplatsen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fb85a882ef111aa38a73dbe155a9ad0ef57dd3de
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311826"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a><span data-ttu-id="8d86a-103">Försök att försöka med en innehållssökning igen för att lösa ett innehållsplatsfel</span><span class="sxs-lookup"><span data-stu-id="8d86a-103">Retry a Content Search to resolve a content location error</span></span>

<span data-ttu-id="8d86a-104">När du använder Innehållssökning i säkerhets- och efterlevnadscentret för att söka i ett stort antal postlådor kan du få sökfel som liknar felet:</span><span class="sxs-lookup"><span data-stu-id="8d86a-104">When you use Content Search in the security and compliance center to search a large number of mailboxes, you may get search errors that are similar to the  error:</span></span>

```text
Error


The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

<span data-ttu-id="8d86a-105">De här felen (med felkoder för CS001-002, CS003-002, CS008-009, CS012-002 och andra fel i formuläret CS0XX-0XX) anger att innehållssökning inte kunde söka efter specifika innehållsplatser. I det här exemplet genomsökdes inte två postlådor.</span><span class="sxs-lookup"><span data-stu-id="8d86a-105">These errors (with error codes of CS001-002, CS003-002, CS008-009, CS012-002, and other errors of the form CS0XX-0XX) indicate that Content Search failed to search specific content locations; in this example, two mailboxes weren't searched.</span></span> <span data-ttu-id="8d86a-106">De här felen visas på den utfällande sidan med statusinformation i Innehållssökning.</span><span class="sxs-lookup"><span data-stu-id="8d86a-106">These errors are displayed on the status details flyout page of the Content Search.</span></span>

## <a name="cause-of-content-location-errors"></a><span data-ttu-id="8d86a-107">Orsak till platsfel</span><span class="sxs-lookup"><span data-stu-id="8d86a-107">Cause of content location errors</span></span>

<span data-ttu-id="8d86a-108">Vid sökning efter ett stort antal postlådor fördelas sökningen över tusentals servrar i ett Microsoft-datacenter.</span><span class="sxs-lookup"><span data-stu-id="8d86a-108">When searching a large number of mailboxes, the search is distributed across thousands of servers in a Microsoft datacenter.</span></span> <span data-ttu-id="8d86a-109">Vid en tidpunkt kan vissa servrar vara i omstartstillstånd eller under processen för redundens till redundanta kopior.</span><span class="sxs-lookup"><span data-stu-id="8d86a-109">At any one time, specific servers could be in reboot state or in the process of failing over to redundant copies.</span></span> <span data-ttu-id="8d86a-110">I båda fallen tar innehållssökningens begäran att hämta data time out. I exemplet ovan visades felen för postlådorna som misslyckades på grund av tidsinställningen för sökningen.</span><span class="sxs-lookup"><span data-stu-id="8d86a-110">In either of these cases, the Content Search's request to retrieve data will time out. In the previous example, the errors for the mailboxes that failed were the result of the search timing out.</span></span>

## <a name="resolving-content-location-errors"></a><span data-ttu-id="8d86a-111">Lösa fel i innehållsplatser</span><span class="sxs-lookup"><span data-stu-id="8d86a-111">Resolving content location errors</span></span>

<span data-ttu-id="8d86a-112">Om du startar om sökningen resulterar det ofta i liknande fel på olika servrar.</span><span class="sxs-lookup"><span data-stu-id="8d86a-112">Restarting the search will often result in similar errors on different servers.</span></span> <span data-ttu-id="8d86a-113">I stället för att starta om sökningen klickar **du på** knappen Försök igen som visas högst upp på sidan med sökresultat.</span><span class="sxs-lookup"><span data-stu-id="8d86a-113">Instead of restarting the search, click the **Retry** button that is displayed at the top of the search results page.</span></span>

![Klicka på knappen Försök igen för att lösa fel på innehållsplatsen](../media/retrycontentsearch3.png)

<span data-ttu-id="8d86a-115">Resultatet blir att sökningen endast för postlådorna som misslyckades kommer att misslyckas.</span><span class="sxs-lookup"><span data-stu-id="8d86a-115">This will result in the retrying the search only for the mailboxes that failed.</span></span> <span data-ttu-id="8d86a-116">När du försöker söka igen behålls de andra resultat som returnerats.</span><span class="sxs-lookup"><span data-stu-id="8d86a-116">When you retry the search, the other results that were successfully returned are retained.</span></span>

## <a name="tips-to-avoid-content-location-errors"></a><span data-ttu-id="8d86a-117">Tips för att undvika fel vid innehållsplats</span><span class="sxs-lookup"><span data-stu-id="8d86a-117">Tips to avoid content location errors</span></span>

<span data-ttu-id="8d86a-118">Här är ytterligare orsaker till fel på innehållsplatsen och några tips som hjälper dig att undvika dem när du söker i stora antal postlådor.</span><span class="sxs-lookup"><span data-stu-id="8d86a-118">Here are some additional causes of content location errors and some tips to help you avoid them when searching large numbers of mailboxes.</span></span>

- <span data-ttu-id="8d86a-119">Postlådan som genomsöks kan vara upptagen på grund av användaraktivitet.</span><span class="sxs-lookup"><span data-stu-id="8d86a-119">The mailbox being searched might be busy due to user activity.</span></span> <span data-ttu-id="8d86a-120">I det här fallet kan söktjänsten begränsa sig själv för att förhindra att postlådan blir otillgänglig.</span><span class="sxs-lookup"><span data-stu-id="8d86a-120">In this case, the search service might throttle itself to prevent the mailbox from becoming unavailable.</span></span> <span data-ttu-id="8d86a-121">Försök att undvika detta genom att köra sökningar under icke-arbetstid.</span><span class="sxs-lookup"><span data-stu-id="8d86a-121">To avoid this, try running searches during non-business hours.</span></span>

- <span data-ttu-id="8d86a-122">Sökfrågan kan hämta för mycket innehåll från postlådan.</span><span class="sxs-lookup"><span data-stu-id="8d86a-122">The search query might be retrieving too much content from the mailbox.</span></span> <span data-ttu-id="8d86a-123">Om möjligt kan du försöka begränsa sökningens omfattning med hjälp av nyckelord, datumintervall och sökvillkor.</span><span class="sxs-lookup"><span data-stu-id="8d86a-123">If possible, try to narrow the scope of the search by using keywords, date ranges, and search conditions.</span></span>

- <span data-ttu-id="8d86a-124">För många nyckelord eller nyckelordsfraser när du skapar en sökfråga med hjälp av [nyckelordslistan](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches).</span><span class="sxs-lookup"><span data-stu-id="8d86a-124">Too many keywords or keyword phrases when you create a search query using the [keywords list](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches).</span></span> <span data-ttu-id="8d86a-125">När du kör en sökfråga som använder listan nyckelord kör tjänsten i princip en separat sökning för varje rad i nyckelordslistan så att statistik kan skapas.</span><span class="sxs-lookup"><span data-stu-id="8d86a-125">When you run a search query that uses the keywords list, the service essentially runs a separate search for each row in the keyword list so that statistics can be generated.</span></span> <span data-ttu-id="8d86a-126">Om du använder nyckelordslistan i sökfrågor minimerar du antalet rader i nyckelordslistan eller delar upp antalet nyckelord i mindre listor och skapar olika sökningar för varje nyckelordslista.</span><span class="sxs-lookup"><span data-stu-id="8d86a-126">If you're using the keywords list in search queries, minimize the number of rows in the keyword list or divide the number keywords into smaller lists and create a different search for each keyword list.</span></span>

  > [!NOTE]
  > <span data-ttu-id="8d86a-127">För att minska problemen som orsakas av stora nyckelordslistor är du nu begränsad till högst 20 rader i nyckelordslistan för en sökfråga.</span><span class="sxs-lookup"><span data-stu-id="8d86a-127">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

- <span data-ttu-id="8d86a-128">För många sökningar utförs på samma postlåda samtidigt.</span><span class="sxs-lookup"><span data-stu-id="8d86a-128">Too many searches are being performed on the same mailbox at the same time.</span></span> <span data-ttu-id="8d86a-129">Försök om möjligt att köra en sökning i taget på en postlåda.</span><span class="sxs-lookup"><span data-stu-id="8d86a-129">If possible, try to run one search at a time on any one mailbox.</span></span>

- <span data-ttu-id="8d86a-130">Söka i för många postlådor i en enda sökning.</span><span class="sxs-lookup"><span data-stu-id="8d86a-130">Searching too many mailboxes in a single search.</span></span> <span data-ttu-id="8d86a-131">Sannolikheten för fel vid innehållsplats ökar vid sökning av ett stort antal postlådor.</span><span class="sxs-lookup"><span data-stu-id="8d86a-131">The probability of content location errors increases when searching a large number of mailboxes.</span></span> <span data-ttu-id="8d86a-132">Försök om möjligt att köra flera sökningar så att varje sökning inkluderar en delmängd postlådor i organisationen.</span><span class="sxs-lookup"><span data-stu-id="8d86a-132">If possible, try to run multiple searches so that each search includes a subset of  mailboxes in your organization.</span></span>

- <span data-ttu-id="8d86a-133">Obligatoriskt underhåll utförs för postlådan.</span><span class="sxs-lookup"><span data-stu-id="8d86a-133">Required maintenance is being performed on the mailbox.</span></span> <span data-ttu-id="8d86a-134">Även om det här orsakar antagligen oregelvänt, vänta en stund efter att innehållsplatsen har mottagits och försök sedan igen.</span><span class="sxs-lookup"><span data-stu-id="8d86a-134">Though this cause probably occurs infrequently, wait a little while after receiving the content location error and then retry the search.</span></span>
