---
title: Skapa ett nyttolast för att simulera attacker
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratörer kan lära sig hur man skapar anpassade nyttolaster för att simulera attacker i Microsoft Defender för Office 365.
ms.technology: mdo
ms.openlocfilehash: 6cc5dd4a48ab89193133cfaf823d0a1b1868fa79
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929196"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="c31f9-103">Skapa en anpassad nyttolast för att träna på attacksimulering</span><span class="sxs-lookup"><span data-stu-id="c31f9-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="c31f9-104">Microsoft tillhandahåller en robust katalog för nyttolaster för olika tekniker för social teknik som kan paras ihop med din utbildnings attacksimulering.</span><span class="sxs-lookup"><span data-stu-id="c31f9-104">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="c31f9-105">Men det kan vara bra att skapa anpassade nyttolaster som fungerar bättre för din organisation.</span><span class="sxs-lookup"><span data-stu-id="c31f9-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="c31f9-106">I den här artikeln beskrivs hur du skapar en nyttolast i utbildningen Attack-simulering i Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="c31f9-106">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="c31f9-107">Du kan skapa en nyttolast genom att klicka på Skapa en nyttolast på antingen den dedikerade fliken Nyttolaster eller i [guiden för att skapa simulering.](attack-simulation-training.md#selecting-a-payload) [  ](https://security.microsoft.com/attacksimulator?viewid=payload) </span><span class="sxs-lookup"><span data-stu-id="c31f9-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="c31f9-108">I det första steget i guiden väljer du en nyttolasttyp.</span><span class="sxs-lookup"><span data-stu-id="c31f9-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="c31f9-109">**För närvarande är endast e-post tillgänglig.**</span><span class="sxs-lookup"><span data-stu-id="c31f9-109">**Currently, only email is available**.</span></span>

<span data-ttu-id="c31f9-110">Välj sedan en associerad teknik.</span><span class="sxs-lookup"><span data-stu-id="c31f9-110">Next, select an associated technique.</span></span> <span data-ttu-id="c31f9-111">Mer information om olika tekniker finns [i Välja en social engineering-teknik.](attack-simulation-training.md#selecting-a-social-engineering-technique)</span><span class="sxs-lookup"><span data-stu-id="c31f9-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="c31f9-112">Namnge din nyttolast i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="c31f9-112">In the next step name your payload.</span></span> <span data-ttu-id="c31f9-113">Du kan också ge den en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="c31f9-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="c31f9-114">Konfigurera nyttolast</span><span class="sxs-lookup"><span data-stu-id="c31f9-114">Configure payload</span></span>

<span data-ttu-id="c31f9-115">Nu är det dags att skapa din nyttolast.</span><span class="sxs-lookup"><span data-stu-id="c31f9-115">Now it's time to build your payload.</span></span> <span data-ttu-id="c31f9-116">Ange avsändarens namn, e-postadress och ämne i avsnittet Med **avsändarinformation.**</span><span class="sxs-lookup"><span data-stu-id="c31f9-116">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="c31f9-117">Välj en nätfiske-URL i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="c31f9-117">Pick a phishing URL from the provided list.</span></span> <span data-ttu-id="c31f9-118">Den här URL-adressen bäddas senare in i meddelandets brödtext.</span><span class="sxs-lookup"><span data-stu-id="c31f9-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="c31f9-119">Du kan välja ett internt e-postmeddelande för payloadens avsändare, så att nyttolasten visas som kommer från en annan anställd på företaget.</span><span class="sxs-lookup"><span data-stu-id="c31f9-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="c31f9-120">Detta ökar känsligheten för nyttolasten och utbildar anställda om risken för interna hot.</span><span class="sxs-lookup"><span data-stu-id="c31f9-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="c31f9-121">En RTF-redigerare finns tillgänglig för att skapa din nyttolast.</span><span class="sxs-lookup"><span data-stu-id="c31f9-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="c31f9-122">Du kan också importera ett e-postmeddelande som du har skapat i förväg.</span><span class="sxs-lookup"><span data-stu-id="c31f9-122">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="c31f9-123">När du skapar brödtexten i e-postmeddelandet kan du dra nytta av de **dynamiska taggarna** för att anpassa e-postmeddelandet efter dina mål.</span><span class="sxs-lookup"><span data-stu-id="c31f9-123">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="c31f9-124">Klicka **på nätfiskelänk** för att lägga till den tidigare markerade nätfiske-URL:en i meddelandets brödtext.</span><span class="sxs-lookup"><span data-stu-id="c31f9-124">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![Nätfiskelänk och dynamiska taggar markerade när nyttolast skapades för Microsoft Defender för Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="c31f9-126">Spara tid genom att växla alternativet att ersätta **alla länkar i e-postmeddelandet med nätfiskelänken.**</span><span class="sxs-lookup"><span data-stu-id="c31f9-126">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="c31f9-127">När du är klar med att skapa nyttolasten som du vill klickar du på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="c31f9-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="c31f9-128">Lägga till indikatorer</span><span class="sxs-lookup"><span data-stu-id="c31f9-128">Adding indicators</span></span>

<span data-ttu-id="c31f9-129">Indikatorer hjälper anställda att gå igenom attackberäkningen och förstå ledtråden de kan leta efter i framtida attacker.</span><span class="sxs-lookup"><span data-stu-id="c31f9-129">Indicators will help employees going through the attack simulation understand the clue they can look for in future attacks.</span></span> <span data-ttu-id="c31f9-130">Börja med att klicka på **Lägg till-indikator.**</span><span class="sxs-lookup"><span data-stu-id="c31f9-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="c31f9-131">Välj en indikator som du vill använda i listrutan.</span><span class="sxs-lookup"><span data-stu-id="c31f9-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="c31f9-132">Den här listan är listad för att innehålla de vanligaste ledtrådarna som visas i nätfiskemeddelanden.</span><span class="sxs-lookup"><span data-stu-id="c31f9-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="c31f9-133">När det är markerat kontrollerar du att indikatorns placering är inställd på Från brödtexten i **e-postmeddelandet** och klickar **på Markera text.**</span><span class="sxs-lookup"><span data-stu-id="c31f9-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="c31f9-134">Markera den del av nyttolasten där indikatorn visas och klicka på **Markera.**</span><span class="sxs-lookup"><span data-stu-id="c31f9-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![Markerad text i meddelandets brödtext som ska läggas till i en indikator i attacksimuleringsutbildning](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="c31f9-136">Lägg till en anpassad beskrivning för att beskriva indikatorn och klicka i förhandsgranskningsrutan för att se en förhandsgranskning av indikatorn.</span><span class="sxs-lookup"><span data-stu-id="c31f9-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="c31f9-137">Klicka på Lägg till när du **är klar.**</span><span class="sxs-lookup"><span data-stu-id="c31f9-137">Once done, click **Add**.</span></span> <span data-ttu-id="c31f9-138">Upprepa dessa steg tills du har tagit upp alla indikatorer i din nyttolast.</span><span class="sxs-lookup"><span data-stu-id="c31f9-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="c31f9-139">Granska nyttolast</span><span class="sxs-lookup"><span data-stu-id="c31f9-139">Review payload</span></span>

<span data-ttu-id="c31f9-140">Du är klar med att skapa din nyttolast.</span><span class="sxs-lookup"><span data-stu-id="c31f9-140">You're done building your payload.</span></span> <span data-ttu-id="c31f9-141">Nu är det dags att granska informationen och se en förhandsgranskning av din nyttolast.</span><span class="sxs-lookup"><span data-stu-id="c31f9-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="c31f9-142">Förhandsgranskningen innehåller alla indikatorer som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="c31f9-142">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="c31f9-143">I det här steget kan du redigera varje del av nyttolasten.</span><span class="sxs-lookup"><span data-stu-id="c31f9-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="c31f9-144">När du är nöjd kan **du skicka** in din nyttolast.</span><span class="sxs-lookup"><span data-stu-id="c31f9-144">Once satisfied, you can **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c31f9-145">Payloads that you've created will have **Tenant** as their source.</span><span class="sxs-lookup"><span data-stu-id="c31f9-145">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="c31f9-146">När du väljer nyttolaster ska du se till att du inte filtrerar bort **klientorganisationen.**</span><span class="sxs-lookup"><span data-stu-id="c31f9-146">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>

## <a name="related-links"></a><span data-ttu-id="c31f9-147">Relaterade länkar</span><span class="sxs-lookup"><span data-stu-id="c31f9-147">Related links</span></span>

[<span data-ttu-id="c31f9-148">Kom igång med Attack simuleringsträning</span><span class="sxs-lookup"><span data-stu-id="c31f9-148">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="c31f9-149">Skapa en simulering av nätfiskeattack</span><span class="sxs-lookup"><span data-stu-id="c31f9-149">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="c31f9-150">Få insikter genom att träna på attacksimulering</span><span class="sxs-lookup"><span data-stu-id="c31f9-150">Gain insights through Attack simulation training</span></span>](attack-simulation-training-insights.md)
