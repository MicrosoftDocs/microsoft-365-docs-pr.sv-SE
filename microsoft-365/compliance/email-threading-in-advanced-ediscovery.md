---
title: E-posttrådning i Advanced eDiscovery
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: När du genomför en Advanced eDiscovery e-posttrådning parsas en e-postkonversation och varje meddelande avgränsas i olika kategorier.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b087bfc84175f80daaf1c0d2f1394584a70757ac
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/26/2020
ms.locfileid: "52161619"
---
# <a name="email-threading-in-advanced-ediscovery"></a><span data-ttu-id="1d905-103">E-posttrådning i Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1d905-103">Email threading in Advanced eDiscovery</span></span>

<span data-ttu-id="1d905-104">Tänk dig en e-postkonversation som har på gång ett tag.</span><span class="sxs-lookup"><span data-stu-id="1d905-104">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="1d905-105">I de flesta fall innehåller det sista e-postmeddelandet i tråden innehållet i alla tidigare e-postmeddelanden. Om du granskar det senaste e-postmeddelandet får du en fullständig kontext av den konversation som inträffat i tråden.</span><span class="sxs-lookup"><span data-stu-id="1d905-105">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="1d905-106">E-posttråd identifierar sådana e-postmeddelanden så att granskare kan granska en del av insamlade dokument utan att förlora något sammanhang.</span><span class="sxs-lookup"><span data-stu-id="1d905-106">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="1d905-107">Vad innebär e-posttrådning?</span><span class="sxs-lookup"><span data-stu-id="1d905-107">What does email threading do?</span></span>

<span data-ttu-id="1d905-108">E-posttrådning parsar varje e-postmeddelande och dekonfigurerar det till enskilda meddelanden. varje e-postmeddelande är en kedja av enskilda meddelanden.</span><span class="sxs-lookup"><span data-stu-id="1d905-108">Email threading parses each email and deconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="1d905-109">Därefter analyseras alla e-postmeddelanden i granskningsuppsättningen för att avgöra om ett e-postmeddelande har unikt innehåll eller om kedjan finns i ett annat e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="1d905-109">Then, it analyzes all emails in the review set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="1d905-110">I slutet är e-postmeddelanden indelade i fyra kategorier:</span><span class="sxs-lookup"><span data-stu-id="1d905-110">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="1d905-111">**Inkluderande**: det sista meddelandet i e-postmeddelandet har unikt innehåll, och e-postmeddelandet har alla bifogade filer som inkluderades i andra e-postmeddelanden där innehållet ingår i det här e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="1d905-111">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="1d905-112">**Inklusive minus**: det sista meddelandet i e-postmeddelandet har unikt innehåll, men e-postmeddelandet innehåller inte några av de bifogade filer som inkluderades i andra e-postmeddelanden som innehållet ingår i det här e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="1d905-112">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="1d905-113">**Inkluderande kopia**: en exakt kopia av en inkluderande/inkluderande e-post</span><span class="sxs-lookup"><span data-stu-id="1d905-113">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="1d905-114">**Inget:** Innehållet i det här e-postmeddelandet ingår i minst ett e-postmeddelande som markeras som inkluderande/inkluderande minus.</span><span class="sxs-lookup"><span data-stu-id="1d905-114">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="1d905-115">Hur skiljer sig den från konversationer i Outlook?</span><span class="sxs-lookup"><span data-stu-id="1d905-115">How is it different from conversations in Outlook?</span></span>

<span data-ttu-id="1d905-116">Det här låter ungefär som konversationsgruppingarna i Outlook.</span><span class="sxs-lookup"><span data-stu-id="1d905-116">At a glance, this sounds similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="1d905-117">Det finns dock vissa viktiga skillnader.</span><span class="sxs-lookup"><span data-stu-id="1d905-117">However, there are some important distinctions.</span></span> <span data-ttu-id="1d905-118">Tänk dig en e-postkonversation som är indelade i två konversationer. Någon har till exempel svarat på ett e-postmeddelande som inte är det senaste i konversationen, så de två senaste e-postmeddelandena i konversationen har båda unikt innehåll.</span><span class="sxs-lookup"><span data-stu-id="1d905-118">Consider an email conversation that got forked into two conversations; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="1d905-119">Outlook kunde ändå gruppera e-postmeddelandena i en enda konversation. Att bara läsa det senaste e-postmeddelandet skulle innebära att kontexten för det andra till sista e-postmeddelandet, som också innehåller unikt innehåll, saknas.</span><span class="sxs-lookup"><span data-stu-id="1d905-119">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="1d905-120">Eftersom e-posttråd parsar ut varje e-postmeddelande i enskilda komponenter och jämför dem, markerar e-posttrådning både i de två sista e-postmeddelandena som inkluderande, så att du inte missar något sammanhang så länge du läser alla e-postmeddelanden som markerats som inkluderande.</span><span class="sxs-lookup"><span data-stu-id="1d905-120">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusive, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>
