---
title: Kontrollera fel i sökfrågan
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
ms.custom: seo-marvel-apr2020
description: Lär dig hur du hittar fel och skrivfel i nyckelordsfrågan för eDiscovery-sökningar innan du kör sökningen.
ms.openlocfilehash: 9c041ca690df3306347cbca77df3ba9639801245
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311694"
---
# <a name="check-your-search-query-for-errors"></a><span data-ttu-id="a7384-103">Kontrollera fel i sökfrågan</span><span class="sxs-lookup"><span data-stu-id="a7384-103">Check your search query for errors</span></span>
  
<span data-ttu-id="a7384-104">Här är en lista över de tecken som inte stöds och som vi söker efter i sökfrågor för innehållssökning och bas-eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a7384-104">Here's a list of the unsupported characters that we check for in search queries for Content search and Core eDiscovery.</span></span> <span data-ttu-id="a7384-105">Tecken som inte stöds är ofta dolda och leder vanligtvis till ett sökfel eller oväntade resultat.</span><span class="sxs-lookup"><span data-stu-id="a7384-105">Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="a7384-106">**Smarta citattecken** – Smarta enkla och dubbla citattecken (kallas även typografiska citattecken) stöds inte.</span><span class="sxs-lookup"><span data-stu-id="a7384-106">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported.</span></span> <span data-ttu-id="a7384-107">Endast raka citattecken kan användas i en sökfråga.</span><span class="sxs-lookup"><span data-stu-id="a7384-107">Only straight quotation marks can be used in a search query.</span></span> 

- <span data-ttu-id="a7384-108">**Icke utskrivbara tecken** och kontrolltecken – Icke utskrivbara tecken och kontrolltecken representerar inte en skriven symbol, till exempel ett alfanumeriskt tecken.</span><span class="sxs-lookup"><span data-stu-id="a7384-108">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as an alpha-numeric character.</span></span> <span data-ttu-id="a7384-109">Exempel på icke utskrivbara tecken och kontrolltecken är tecken som formaterar text eller separata rader med text.</span><span class="sxs-lookup"><span data-stu-id="a7384-109">Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 

- <span data-ttu-id="a7384-110">**Vänster-till-höger-** och höger-till-vänster-markeringar – Dessa markeringar är kontrolltecken som används för att ange textriktningen för språk som är från vänster till höger (till exempel svenska och spanska) och språk som är från höger till vänster (t.ex. arabiska och hebreiska).</span><span class="sxs-lookup"><span data-stu-id="a7384-110">**Left-to-right and right-to-left marks** - These marks are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>

- <span data-ttu-id="a7384-111">**Booleska operatorer** med gemener – Om du använder en boolesk operator, till exempel **OCH,** **ELLER** och **ICKE** i en sökfråga, måste den vara versal.</span><span class="sxs-lookup"><span data-stu-id="a7384-111">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase.</span></span> <span data-ttu-id="a7384-112">När vi kontrollerar om det finns stavfel i en fråga anger frågesyntaxen ofta att en boolesk operator används, även om gemener (operatorer) kan användas. till exempel  `(WordA or WordB) and (WordC or WordD)` .</span><span class="sxs-lookup"><span data-stu-id="a7384-112">When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>

## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="a7384-113">Vad händer om en fråga har ett tecken som inte stöds?</span><span class="sxs-lookup"><span data-stu-id="a7384-113">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="a7384-114">Om tecken som inte stöds hittas i frågan visas ett varningsmeddelande där det står att tecken som inte stöds hittas och föreslår ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="a7384-114">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters were found and suggests an alternative.</span></span> <span data-ttu-id="a7384-115">Du kan sedan välja att behålla den ursprungliga frågan eller ersätta den med den föreslagna reviderade frågan.</span><span class="sxs-lookup"><span data-stu-id="a7384-115">You then have the option keep the original query or replace it with the suggested revised query.</span></span>

<span data-ttu-id="a7384-116">Här är ett exempel på varningsmeddelandet som visas när du klickar på Sök efter **stavfel** i sökfrågan i föregående skärmbild.</span><span class="sxs-lookup"><span data-stu-id="a7384-116">Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot.</span></span> <span data-ttu-id="a7384-117">Observera att den ursprungliga frågan använder smarta citattecken och booleska operatorer med gemener.</span><span class="sxs-lookup"><span data-stu-id="a7384-117">Note the original query used smart quotes and lowercase Boolean operators.</span></span>
  
![Ett varningsmeddelande visas med en föreslagen ändring för frågan](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="a7384-119">Förhindra tecken som inte stöds i dina sökfrågor</span><span class="sxs-lookup"><span data-stu-id="a7384-119">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="a7384-120">Tecken som inte stöds läggs vanligtvis till i en fråga när du kopierar frågan eller delar av frågan från andra program (till exempel Microsoft Word eller Microsoft Excel) och klistrar in dem i nyckelordsrutan på frågesidan i en innehållssökning.</span><span class="sxs-lookup"><span data-stu-id="a7384-120">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and paste them in the keyword box on the query page of a Content Search.</span></span> <span data-ttu-id="a7384-121">Det bästa sättet att förhindra tecken som inte stöds är att skriva frågan i rutan nyckelord.</span><span class="sxs-lookup"><span data-stu-id="a7384-121">The best way to prevent unsupported characters is to just type the query in the keyword box.</span></span> <span data-ttu-id="a7384-122">Du kan också kopiera en fråga från Word eller Excel och sedan klistra in den i en textredigerare, till exempel Microsoft Anteckningar.</span><span class="sxs-lookup"><span data-stu-id="a7384-122">Or you can copy a query from Word or Excel, and then paste it in a plain text editor, such as Microsoft Notepad.</span></span> <span data-ttu-id="a7384-123">Spara textfilen och välj **ANSI** i **listrutan** Kodning.</span><span class="sxs-lookup"><span data-stu-id="a7384-123">Save the text file and select **ANSI** in the **Encoding** drop-down list.</span></span> <span data-ttu-id="a7384-124">Det här tar bort all formatering och tecken som inte stöds.</span><span class="sxs-lookup"><span data-stu-id="a7384-124">This will remove any formatting and unsupported characters.</span></span> <span data-ttu-id="a7384-125">Sedan kan du kopiera och klistra in frågan från textfilen till nyckelordsfrågerutan.</span><span class="sxs-lookup"><span data-stu-id="a7384-125">Then you can copy and paste the query from the text file to the keyword query box.</span></span>
