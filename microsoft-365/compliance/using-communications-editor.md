---
title: Använda kommunikationsredigeraren
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
ms.assetid: ''
description: Använd kommunikationsredigeraren för att ändra text- och kopplingsfältvariabler när du formaterar innehållet.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6dcfb58dff3a3acf99340895872bb2da9795d9c8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2021
ms.locfileid: "52161774"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="19182-103">Använda kommunikationsredigeraren</span><span class="sxs-lookup"><span data-stu-id="19182-103">Use the communications editor</span></span>

<span data-ttu-id="19182-104">När du definierar innehållet på portalens innehåll, aviseringar om juridiska meddelanden och relaterade påminnelser/eskalering kan du använda kommunikationsredigeraren för att formatera och dynamiskt anpassa innehållet.</span><span class="sxs-lookup"><span data-stu-id="19182-104">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can use the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="19182-105">RTF-redigerare</span><span class="sxs-lookup"><span data-stu-id="19182-105">Rich text editor</span></span>

<span data-ttu-id="19182-106">Med Kommunikationsredigeraren kan du anpassa texten med redigeringsalternativen.</span><span class="sxs-lookup"><span data-stu-id="19182-106">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="19182-107">Användare kan till exempel ändra teckensnitt, skapa punktlistor, markera innehåll och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="19182-107">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span>

## <a name="merge-field-variables"></a><span data-ttu-id="19182-108">Sammanfoga fältvariabler</span><span class="sxs-lookup"><span data-stu-id="19182-108">Merge field variables</span></span>

<span data-ttu-id="19182-109">Du kan använda variabler för sammanfogning av e-post från Kommunikationsredigeraren för att bädda in anpassade attribut i brödtexten i en kommunikation.</span><span class="sxs-lookup"><span data-stu-id="19182-109">You can use email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="19182-110">När de skickas till den dokumenterade uppslagsinstruktionen fylls den i med motsvarande fält.</span><span class="sxs-lookup"><span data-stu-id="19182-110">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="19182-111">När den skickades till dokumenterianen Johan Svensson skulle till exempel kopplingsinstruktionen [Förnamn] översättas med motsvarande namn.</span><span class="sxs-lookup"><span data-stu-id="19182-111">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span>

<span data-ttu-id="19182-112">Du kan använda kopplingsinstruktioner för e-post **genom** att välja ikonerna för kopplingsinstruktionen högst upp i RTF-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="19182-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="19182-113">Platshållaren läggs till utifrån platsen för användarens markör.</span><span class="sxs-lookup"><span data-stu-id="19182-113">The placeholder will be added based off the location of the users' cursor.</span></span>

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="19182-114">Lista över kopplingsinstruktionsvariabler</span><span class="sxs-lookup"><span data-stu-id="19182-114">List of merge field variables</span></span>

| <span data-ttu-id="19182-115">Fältnamn</span><span class="sxs-lookup"><span data-stu-id="19182-115">Field name</span></span>                  | <span data-ttu-id="19182-116">Fältinformation</span><span class="sxs-lookup"><span data-stu-id="19182-116">Field details</span></span> |
| :------------------- | :------------------- |
| <span data-ttu-id="19182-117">Visningsnamn</span><span class="sxs-lookup"><span data-stu-id="19182-117">Display Name</span></span>  | <span data-ttu-id="19182-118">Den som ger sig av för- och efternamn.</span><span class="sxs-lookup"><span data-stu-id="19182-118">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="19182-119">Bekräftelselänk</span><span class="sxs-lookup"><span data-stu-id="19182-119">Acknowledgment Link</span></span> | <span data-ttu-id="19182-120">En anpassad länk för att registrera varje enskild persons bekräftelse.</span><span class="sxs-lookup"><span data-stu-id="19182-120">A customized link to record each custodian's acknowledgment.</span></span>|                 |
| <span data-ttu-id="19182-121">Portallänk</span><span class="sxs-lookup"><span data-stu-id="19182-121">Portal Link</span></span>     | <span data-ttu-id="19182-122">En anpassad länk för den uppsnadares efterlevnadsportal.</span><span class="sxs-lookup"><span data-stu-id="19182-122">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="19182-123">Utfärdar officer</span><span class="sxs-lookup"><span data-stu-id="19182-123">Issuing Officer</span></span>                   | <span data-ttu-id="19182-124">E-postadressen till den angivna utfärdaren.</span><span class="sxs-lookup"><span data-stu-id="19182-124">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="19182-125">Utgivningsdatum</span><span class="sxs-lookup"><span data-stu-id="19182-125">Issuing Date</span></span>                   | <span data-ttu-id="19182-126">Datumet då meddelandet utfärdades (UTC).</span><span class="sxs-lookup"><span data-stu-id="19182-126">The date that the notice was issued (UTC).</span></span>              |
|||
