---
title: Viktig information om efterlevnadsstöd för Microsoft 365 för teckenuppsättning med dubbel byte ( förhandsversion)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Viktig information om stöd för teckenuppsättningar med dubbla byte.
ms.openlocfilehash: 1c2244c49a92aa2c00fad06caa8194cf7e32220e
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/22/2020
ms.locfileid: "52161629"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a><span data-ttu-id="f801a-103">Viktig information om stöd för teckenuppsättning med dubbel byte (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="f801a-103">Support for double byte character set release notes (preview)</span></span>

 <span data-ttu-id="f801a-104">Microsoft 365 Information Protection har nu stöd för teckenuppsättningsspråk med dubbla byte i förhandsgranskning för:</span><span class="sxs-lookup"><span data-stu-id="f801a-104">Microsoft 365 Information Protection now supports in preview double byte character set languages for:</span></span>

- <span data-ttu-id="f801a-105">Kinesiska (förenklad)</span><span class="sxs-lookup"><span data-stu-id="f801a-105">Chinese (simplified)</span></span>
- <span data-ttu-id="f801a-106">Kinesiska (traditionell)</span><span class="sxs-lookup"><span data-stu-id="f801a-106">Chinese (traditional)</span></span>
- <span data-ttu-id="f801a-107">Korean</span><span class="sxs-lookup"><span data-stu-id="f801a-107">Korean</span></span>
- <span data-ttu-id="f801a-108">Japanese</span><span class="sxs-lookup"><span data-stu-id="f801a-108">Japanese</span></span>

<span data-ttu-id="f801a-109">Det här stödet är tillgängligt för känsliga informationstyper och nyckelordsordlistor och kommer att återspeglas i dataförlustskydd, kommunikationsefterlevnad, Exchange Online, SharePoint Online, OneDrive för företag och Teams-lösningar.</span><span class="sxs-lookup"><span data-stu-id="f801a-109">This support is available for sensitive information types and keyword dictionaries and will be reflected in data loss prevention, communications compliance, Exchange Online, SharePoint Online, OneDrive for Business, and Teams solutions.</span></span>

## <a name="known-issues"></a><span data-ttu-id="f801a-110">Kända problem</span><span class="sxs-lookup"><span data-stu-id="f801a-110">Known issues</span></span>

- <span data-ttu-id="f801a-111">När en textfil som bifogats i ett e-postmeddelande är i UTF-8-format utan byteordningsmärke (BOM), identifieras inte e-postmeddelandet av principen för kommunikationsefterlevnad.</span><span class="sxs-lookup"><span data-stu-id="f801a-111">When a text file attached to an email is in UTF-8 format without byte order mark (BOM), the email is not detected by the Communication Compliance policy.</span></span>

- <span data-ttu-id="f801a-112">Principer för kommunikationsefterlevnad kan inte identifiera värden om en mening angetts för principvillkoret: "Meddelandet innehåller något av dessa ord".</span><span class="sxs-lookup"><span data-stu-id="f801a-112">Communication Compliance policies cannot detect values if a sentence is entered for the policy condition: “Message contains any of these words”.</span></span> <span data-ttu-id="f801a-113">Om den text som anges i principen är skriven som ett ord kan den identifieras; men om den är skriven mitt i en mening identifieras den inte.</span><span class="sxs-lookup"><span data-stu-id="f801a-113">If the text specified in the policy is written as a word, it can be detected; however, if it is written in the middle of a sentence, it will not be detected.</span></span>

- <span data-ttu-id="f801a-114">Principer för kommunikationsefterlevnad som anger ordlistor som typinformation identifierar inte Teams privata chattar och kanalchattar.</span><span class="sxs-lookup"><span data-stu-id="f801a-114">Communication Compliance policies that specify dictionaries as type information do not detect Teams private chats and channel chats.</span></span>

- <span data-ttu-id="f801a-115">Följande villkor stöds inte för kommunikationsefterlevnad i det här skedet (vi planerar att åtgärda problemen i framtiden):</span><span class="sxs-lookup"><span data-stu-id="f801a-115">The following conditions are not supported for Communication Compliance at this stage (we plan to fix these issues in the future):</span></span> 
  - <span data-ttu-id="f801a-116">"Meddelandet innehåller något av dessa ord"</span><span class="sxs-lookup"><span data-stu-id="f801a-116">“Message contains any of these words”</span></span>
  - <span data-ttu-id="f801a-117">"Meddelandet innehåller inget av dessa ord"</span><span class="sxs-lookup"><span data-stu-id="f801a-117">“Message contains none of these words”</span></span>
  - <span data-ttu-id="f801a-118">"Bifogad fil innehåller något av dessa ord"</span><span class="sxs-lookup"><span data-stu-id="f801a-118">“Attachment contains any of these words”</span></span>
  - <span data-ttu-id="f801a-119">"Bifogad fil innehåller något av dessa ord"</span><span class="sxs-lookup"><span data-stu-id="f801a-119">“Attachment contains any of these words”</span></span>

<span data-ttu-id="f801a-120">I stället rekommenderar vi att du skapar en anpassad typ av känslig information (SIT: Sensitive Information Type) med nyckelordsordlista som identifierar mönster i meddelanden och bilagor, och använder detta anpassade SIT som ett villkor för principen om kommunikation efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="f801a-120">Instead we recommend creating a custom Sensitive Information Type (SIT) with keyword dictionary which will detect patterns across messages and attachments, and using this custom SIT as a Communication Compliance policy condition.</span></span>
