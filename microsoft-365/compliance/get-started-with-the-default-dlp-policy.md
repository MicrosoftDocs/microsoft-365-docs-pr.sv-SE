---
title: Kom igång med DLP-standardprincipen
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/10/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du använder rapporten för att förfina organisationens standardprincip för skydd mot dataförlust (DLP).
ms.openlocfilehash: 4530e570f0ce593a7d2cb62acc28dfa4e1658df0
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162989"
---
# <a name="get-started-with-the-default-dlp-policy"></a><span data-ttu-id="5d0a7-103">Kom igång med DLP-standardprincipen</span><span class="sxs-lookup"><span data-stu-id="5d0a7-103">Get started with the default DLP policy</span></span>

<span data-ttu-id="5d0a7-104">Innan du ens har skapat din första DLP-princip (Data Loss Prevention) hjälper DLP till att skydda känslig information med en standardprincip.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-104">Before you even create your first data loss prevention (DLP) policy, DLP is helping to protect your sensitive information with a default policy.</span></span> <span data-ttu-id="5d0a7-105">Den här standardprincipen och dess rekommendation (visas nedan) hjälper dig att skydda känsligt innehåll genom att meddela dig när e-post eller dokument som innehåller ett kreditkortsnummer har delats med någon utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-105">This default policy and its recommendation (shown below) help keep your sensitive content secure by notifying you when email or documents containing a credit card number were shared with someone outside your organization.</span></span> <span data-ttu-id="5d0a7-106">Du ser den här rekommendationen på **startsidan** för &amp; Säkerhetsefterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-106">You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="5d0a7-107">Du kan använda den här widgeten för att snabbt visa när och hur mycket känslig information som har delats, och sedan förfina standard-DLP-principen med bara ett eller två klick.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-107">You can use this widget to quickly view when and how much sensitive information was shared, and then refine the default DLP policy in just a click or two.</span></span> <span data-ttu-id="5d0a7-108">Du kan också redigera standard-DLP-principen när som helst eftersom den är helt anpassningsbar.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-108">You can also edit the default DLP policy at any time because it's fully customizable.</span></span> <span data-ttu-id="5d0a7-109">Observera att om du inte ser rekommendationen från början kan du prova att klicka på **+Mer** längst ned i **avsnittet Rekommenderas för** dig.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-109">Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![Widget med namnet Ytterligare skydda delat innehåll](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a><span data-ttu-id="5d0a7-111">Visa rapporten och förfina DLP-standardprincipen</span><span class="sxs-lookup"><span data-stu-id="5d0a7-111">View the report and refine the default DLP policy</span></span>

<span data-ttu-id="5d0a7-112">När widgeten visar att användarna har delat känslig information med personer utanför organisationen väljer du **Förfina DLP-principen** längst ned.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-112">When the widget shows you that users have shared sensitive information with people outside your organization, choose **Refine DLP policy** at the bottom.</span></span> 
  
<span data-ttu-id="5d0a7-113">I den detaljerade rapporten visas när och hur mycket innehåll som innehåller kreditkortsnummer som delats de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-113">The detailed report shows you when and how much content containing credit card numbers was shared in the past 30 days.</span></span> <span data-ttu-id="5d0a7-114">Observera att regelmatchning kan ta upp till 48 timmar innan de visas i widgeten.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-114">Note that rule matches can take up to 48 hours to show up in the widget.</span></span>
  
<span data-ttu-id="5d0a7-115">Standardprincipen för DLP gör följande för att skydda den känsliga informationen:</span><span class="sxs-lookup"><span data-stu-id="5d0a7-115">To help protect the sensitive information, the default DLP policy:</span></span>
  
- <span data-ttu-id="5d0a7-116">Upptäcker när innehåll i Exchange, SharePoint och OneDrive som innehåller minst ett kreditkortsnummer delas med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-116">Detects when content in Exchange, SharePoint, and OneDrive that contains at least one credit card number is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="5d0a7-117">Visar ett principtips och skickar ett e-postmeddelande till användare när de försöker dela den här känsliga informationen med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-117">Shows a policy tip and sends an email notification to users when they attempt to share this sensitive information with people outside your organization.</span></span> <span data-ttu-id="5d0a7-118">Mer information om de här alternativen finns i Skicka [e-postmeddelanden och visa principtips för DLP-principer.](use-notifications-and-policy-tips.md)</span><span class="sxs-lookup"><span data-stu-id="5d0a7-118">For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
- <span data-ttu-id="5d0a7-119">Genererar detaljerade aktivitetsrapporter så att du kan spåra sådant som vem som har delat innehållet med personer utanför organisationen och när de gjorde det.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-119">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it.</span></span> <span data-ttu-id="5d0a7-120">Du kan använda [DLP-rapporter och](view-the-dlp-reports.md) [granskningsloggdata](search-the-audit-log-in-security-and-compliance.md) (där **aktivitet**  =  **DLP**) för att visa den här informationen.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-120">You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="5d0a7-121">Om du snabbt vill förfina standard-DLP-principen kan du välja att följande ska användas:</span><span class="sxs-lookup"><span data-stu-id="5d0a7-121">To quickly refine the default DLP policy, you can choose to have it:</span></span>
  
- <span data-ttu-id="5d0a7-122">Skicka ett e-postmeddelande med en incidentrapport när användare delar den här känsliga informationen med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-122">Send you an incident report email when users share this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="5d0a7-123">Lägg till andra användare i e-posthändelserapporten.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-123">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="5d0a7-124">Blockera åtkomst till innehåll som innehåller känslig information, men tillåt användaren att åsidosätta och dela eller skicka vid behov.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-124">Block access to the content containing the sensitive information, but allow the user to override and share or send if they need to.</span></span>
    
<span data-ttu-id="5d0a7-125">Mer information om incidentrapporter eller om att begränsa åtkomst finns i Referens [för dataförlustskydd.](data-loss-prevention-policies.md)</span><span class="sxs-lookup"><span data-stu-id="5d0a7-125">For more information on incident reports or restricting access, see [Data loss prevention reference](data-loss-prevention-policies.md).</span></span>
  
<span data-ttu-id="5d0a7-126">Om du vill ändra de här alternativen senare kan du redigera standard-DLP-principen när som helst – se nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-126">If you want to change these options later, you can edit the default DLP policy at any time - see the next section.</span></span>
  
![Inställningar för widget med namnet Ytterligare skydda delat innehåll](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a><span data-ttu-id="5d0a7-128">Redigera standard-DLP-principen</span><span class="sxs-lookup"><span data-stu-id="5d0a7-128">Edit the default DLP policy</span></span>

<span data-ttu-id="5d0a7-129">Den här principen heter **Standard-DLP-princip** och visas under **Skydd mot dataförlust** **på** sidan Princip i &amp; Säkerhetsefterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-129">This policy is named **Default DLP policy** and appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="5d0a7-130">Den här principen är helt anpassningsbar, samma som alla DLP-princip du skapar själv från grunden.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-130">This policy is fully customizable, the same as any DLP policy that you create yourself from scratch.</span></span> <span data-ttu-id="5d0a7-131">Du kan också inaktivera eller ta bort principen så att användarna inte längre får principtips eller e-postaviseringar.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-131">You can also turn off or delete the policy, so that your users no longer receive policy tips or email notifications.</span></span>
  
![DLP-princip med namnet Standard-DLP-princip](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="5d0a7-133">När widgeten visas och inte visas</span><span class="sxs-lookup"><span data-stu-id="5d0a7-133">When the widget does and does not appear</span></span>

<span data-ttu-id="5d0a7-134">Widgeten **Med namnet Ytterligare skydd av** delat innehåll visas i **avsnittet** Rekommenderas för dig **på sidan** Start i &amp; Säkerhetsefterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-134">The widget named **Further protect shared content** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="5d0a7-135">Den här widgeten visas bara om:</span><span class="sxs-lookup"><span data-stu-id="5d0a7-135">This widget appears only when:</span></span>
  
- <span data-ttu-id="5d0a7-136">Det finns inga principer för dataförlustskydd i &amp; Säkerhetsefterlevnad eller Exchange administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-136">There are no data loss prevention policies in the Security &amp; Compliance Center or Exchange admin center.</span></span> <span data-ttu-id="5d0a7-137">Den här widgeten är avsedd att hjälpa dig att komma igång med DLP, så den visas inte om du redan har DLP-principer.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-137">This widget is intended to help you get started with DLP, so it doesn't appear if you already have DLP policies.</span></span>
    
- <span data-ttu-id="5d0a7-138">Innehåll som innehåller minst ett kreditkort har delats med någon utanför organisationen under de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-138">Content containing least one credit card has been shared with someone outside your organization in the past 30 days.</span></span>
    
<span data-ttu-id="5d0a7-139">Observera att regelmatchning kan ta upp till 48 timmar innan widgeten är tillgänglig, så när känslig information som delas externt har upptäckts kan det ta upp till två dagar innan rekommendationen visas.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-139">Note that rule matches can take up to 48 hours to be available to the widget, so after sensitive information shared externally is detected, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="5d0a7-140">Slutligen försvinner widgeten från startsidan när du använder widgeten för  att förfina standard-DLP-principen.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-140">Finally, after you use the widget to refine the default DLP policy, the widget disappears from the **Home** page.</span></span> 
  

