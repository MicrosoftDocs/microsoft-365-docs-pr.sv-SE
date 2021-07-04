---
title: Viktig information om Microsoft 365 Efterlevnadscenter för teckenuppsättning med dubbel byte
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
ms.openlocfilehash: b7883495c5b187b98e6b0539eaa075e4f8d3af6e
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256393"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a><span data-ttu-id="61bc8-103">Viktig information om stöd för teckenuppsättning med dubbel byte (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="61bc8-103">Support for double byte character set release notes (preview)</span></span>

 <span data-ttu-id="61bc8-104">Microsoft 365 Information Protection har nu stöd för teckenuppsättningsspråk med dubbla byte för:</span><span class="sxs-lookup"><span data-stu-id="61bc8-104">Microsoft 365 Information Protection now supports double byte character set languages for:</span></span>

- <span data-ttu-id="61bc8-105">Kinesiska (förenklad)</span><span class="sxs-lookup"><span data-stu-id="61bc8-105">Chinese (simplified)</span></span>
- <span data-ttu-id="61bc8-106">Kinesiska (traditionell)</span><span class="sxs-lookup"><span data-stu-id="61bc8-106">Chinese (traditional)</span></span>
- <span data-ttu-id="61bc8-107">Koreanska</span><span class="sxs-lookup"><span data-stu-id="61bc8-107">Korean</span></span>
- <span data-ttu-id="61bc8-108">Japanska</span><span class="sxs-lookup"><span data-stu-id="61bc8-108">Japanese</span></span>

<span data-ttu-id="61bc8-109">Det här stödet är tillgängligt för känsliga informationstyper och nyckelordsordlistor och kommer att återspeglas i dataförlustskydd (för Exchange Online, SharePoint Online, OneDrive för företag och Teams), kommunikationsefterlevnad, automatisk etikettering i Office-appar och Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="61bc8-109">This support is available for sensitive information types and keyword dictionaries and will be reflected in data loss prevention (for Exchange Online, SharePoint Online, OneDrive for Business, and Teams), Communications Compliance, Auto Labelling in office apps and Microsoft Cloud App Security.</span></span>

## <a name="known-issues"></a><span data-ttu-id="61bc8-110">Kända problem</span><span class="sxs-lookup"><span data-stu-id="61bc8-110">Known issues</span></span>

- <span data-ttu-id="61bc8-111">När en textfil som bifogats i ett e-postmeddelande är i UTF-8-format utan byteordningsmärke (BOM), identifieras inte e-postmeddelandet av principen för kommunikationsefterlevnad.</span><span class="sxs-lookup"><span data-stu-id="61bc8-111">When a text file attached to an email is in UTF-8 format without byte order mark (BOM), the email is not detected by the Communication Compliance policy.</span></span>

- <span data-ttu-id="61bc8-112">Principer för kommunikationsefterlevnad kan inte identifiera värden om en mening angetts för principvillkoret: "Meddelandet innehåller något av dessa ord".</span><span class="sxs-lookup"><span data-stu-id="61bc8-112">Communication Compliance policies cannot detect values if a sentence is entered for the policy condition: “Message contains any of these words”.</span></span> <span data-ttu-id="61bc8-113">Om den text som anges i principen är skriven som ett ord kan den identifieras; men om den är skriven mitt i en mening identifieras den inte.</span><span class="sxs-lookup"><span data-stu-id="61bc8-113">If the text specified in the policy is written as a word, it can be detected; however, if it is written in the middle of a sentence, it will not be detected.</span></span>

- <span data-ttu-id="61bc8-114">Principer för kommunikationsefterlevnad som anger ordlistor som typinformation identifierar inte Teams privata chattar och kanalchattar.</span><span class="sxs-lookup"><span data-stu-id="61bc8-114">Communication Compliance policies that specify dictionaries as type information do not detect Teams private chats and channel chats.</span></span>

- <span data-ttu-id="61bc8-115">Följande villkor stöds inte för kommunikationsefterlevnad i det här skedet (vi planerar att åtgärda problemen i framtiden):</span><span class="sxs-lookup"><span data-stu-id="61bc8-115">The following conditions are not supported for Communication Compliance at this stage (we plan to fix these issues in the future):</span></span> 
  - <span data-ttu-id="61bc8-116">"Meddelandet innehåller något av dessa ord"</span><span class="sxs-lookup"><span data-stu-id="61bc8-116">“Message contains any of these words”</span></span>
  - <span data-ttu-id="61bc8-117">"Meddelandet innehåller inget av dessa ord"</span><span class="sxs-lookup"><span data-stu-id="61bc8-117">“Message contains none of these words”</span></span>
  - <span data-ttu-id="61bc8-118">"Bifogad fil innehåller något av dessa ord"</span><span class="sxs-lookup"><span data-stu-id="61bc8-118">“Attachment contains any of these words”</span></span>
  - <span data-ttu-id="61bc8-119">"Bifogad fil innehåller något av dessa ord"</span><span class="sxs-lookup"><span data-stu-id="61bc8-119">“Attachment contains any of these words”</span></span>

<span data-ttu-id="61bc8-120">I stället rekommenderar vi att du skapar en anpassad typ av känslig information (SIT: Sensitive Information Type) med nyckelordsordlista som identifierar mönster i meddelanden och bilagor, och använder detta anpassade SIT som ett villkor för principen om kommunikation efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="61bc8-120">Instead we recommend creating a custom Sensitive Information Type (SIT) with keyword dictionary which will detect patterns across messages and attachments, and using this custom SIT as a Communication Compliance policy condition.</span></span>


