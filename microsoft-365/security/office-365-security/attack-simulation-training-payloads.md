---
title: Skapa en nyttolast för utbildning av attackattacker
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
description: Administratörer kan lära sig att skapa anpassade nyttolaster för utbildning av attackattacker i Microsoft Defender för Office 365.
ms.technology: mdo
ms.openlocfilehash: ac7963b71c466e8dfdc513a2563776cd4e10af95
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878766"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="ae4f1-103">Skapa en anpassad nyttolast för att träna på attacksimulering</span><span class="sxs-lookup"><span data-stu-id="ae4f1-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="ae4f1-104">**Gäller för** [Microsoft Defender för Office 365 abonnemang 2](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="ae4f1-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="ae4f1-105">Microsoft erbjuder en robust katalog över nyttolaster för olika tekniker för social teknik som kan paras ihop med din attack simuleringsutbildning.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-105">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="ae4f1-106">Men det kan vara bra att skapa anpassade nyttolaster som fungerar bättre för din organisation.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-106">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="ae4f1-107">I den här artikeln beskrivs hur du skapar en nyttolast i utbildningen Attack simulering i Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-107">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="ae4f1-108">Du kan skapa en nyttolast genom att klicka på Skapa en nyttolast på antingen den dedikerade fliken Nyttolaster eller i [guiden för att skapa simulering.](attack-simulation-training.md#selecting-a-payload) [  ](https://security.microsoft.com/attacksimulator?viewid=payload) </span><span class="sxs-lookup"><span data-stu-id="ae4f1-108">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="ae4f1-109">Det första steget i guiden är att välja en nyttolasttyp.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-109">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="ae4f1-110">**För närvarande är endast e-post tillgänglig.**</span><span class="sxs-lookup"><span data-stu-id="ae4f1-110">**Currently, only email is available**.</span></span>

<span data-ttu-id="ae4f1-111">Välj sedan en associerad teknik.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-111">Next, select an associated technique.</span></span> <span data-ttu-id="ae4f1-112">Mer information om tekniker finns under [Välja en social engineering-teknik.](attack-simulation-training.md#selecting-a-social-engineering-technique)</span><span class="sxs-lookup"><span data-stu-id="ae4f1-112">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="ae4f1-113">I nästa steg ska du namnge din nyttolast.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-113">In the next step name your payload.</span></span> <span data-ttu-id="ae4f1-114">Du kan också ge den en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-114">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="ae4f1-115">Konfigurera nyttolast</span><span class="sxs-lookup"><span data-stu-id="ae4f1-115">Configure payload</span></span>

<span data-ttu-id="ae4f1-116">Nu är det dags att skapa din nyttolast.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-116">Now it's time to build your payload.</span></span> <span data-ttu-id="ae4f1-117">Ange avsändarens namn, e-postadress och ämne i avsnittet **Avsändarinformation.**</span><span class="sxs-lookup"><span data-stu-id="ae4f1-117">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="ae4f1-118">Välj en nätfiske-URL i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-118">Pick a phishing URL from the provided list.</span></span> <span data-ttu-id="ae4f1-119">Den här URL-adressen bäddas senare in i meddelandets brödtext.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-119">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="ae4f1-120">Du kan välja ett internt e-postmeddelande för nyttolastens avsändare, vilket gör att nyttolasten visas som kommer från en annan anställd på företaget.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-120">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="ae4f1-121">Detta ökar känsligheten för nyttolasten och utbildar anställda om risken för interna hot.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-121">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="ae4f1-122">Det finns en RTF-redigerare som kan skapa din nyttolast.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-122">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="ae4f1-123">Du kan också importera ett e-postmeddelande som du har skapat i förväg.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-123">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="ae4f1-124">När du skapar brödtexten i e-postmeddelandet kan du använda de dynamiska **taggarna för** att anpassa e-postmeddelandet efter dina mål.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-124">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="ae4f1-125">Klicka **på Nätfiskelänk** för att lägga till den tidigare markerade nätfiske-URL:en i meddelandets brödtext.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-125">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![Nätfiskelänk och dynamiska taggar markerade när nyttolast skapas för Microsoft Defender för Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="ae4f1-127">Spara tid genom att aktivera alternativet att ersätta **alla länkar i e-postmeddelandet med nätfiskelänken**.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-127">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="ae4f1-128">När du är klar med att skapa nyttolasten som du vill klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-128">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="ae4f1-129">Lägga till indikatorer</span><span class="sxs-lookup"><span data-stu-id="ae4f1-129">Adding indicators</span></span>

<span data-ttu-id="ae4f1-130">Indikatorer hjälper anställda att gå genom attack simuleringen förstå ledtråden de kan leta efter i framtida attacker.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-130">Indicators will help employees going through the attack simulation understand the clue they can look for in future attacks.</span></span> <span data-ttu-id="ae4f1-131">Börja med att klicka på **Lägg till indikator**.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-131">To start, click **Add indicator**.</span></span>

<span data-ttu-id="ae4f1-132">Välj en indikator som du vill använda i listrutan.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-132">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="ae4f1-133">Listan används för att visa de vanligaste ledtrådarna i nätfiskemeddelanden.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-133">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="ae4f1-134">När du är markerad kontrollerar du att indikatorns placering är inställd på Från **brödtexten i e-postmeddelandet** och klickar på **Markera text**.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-134">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="ae4f1-135">Markera den del av nyttolasten där indikatorn visas och klicka på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-135">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![Markerad text i meddelandets brödtext som ska läggas till i en indikator i simuleringsutbildning för attack](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="ae4f1-137">Lägg till en anpassad beskrivning för att beskriva indikatorn och klicka i förhandsgranskningsrutan för indikatorn så visas en förhandsgranskning av indikatorn.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-137">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="ae4f1-138">Klicka på Lägg till när du **är klar.**</span><span class="sxs-lookup"><span data-stu-id="ae4f1-138">Once done, click **Add**.</span></span> <span data-ttu-id="ae4f1-139">Upprepa dessa steg tills du har tagit upp alla indikatorer i din nyttolast.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-139">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="ae4f1-140">Granska nyttolast</span><span class="sxs-lookup"><span data-stu-id="ae4f1-140">Review payload</span></span>

<span data-ttu-id="ae4f1-141">Du är klar med att skapa din nyttolast.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-141">You're done building your payload.</span></span> <span data-ttu-id="ae4f1-142">Nu är det dags att granska informationen och se en förhandsgranskning av din nyttolast.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-142">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="ae4f1-143">Förhandsgranskningen innehåller alla indikatorer som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-143">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="ae4f1-144">Du kan redigera varje del av nyttolasten från det här steget.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-144">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="ae4f1-145">När den är nöjd kan **du skicka** in din nyttolast.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-145">Once satisfied, you can **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae4f1-146">Payloads that you've created will have **Tenant** as their source.</span><span class="sxs-lookup"><span data-stu-id="ae4f1-146">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="ae4f1-147">Se till att du inte filtrerar ut klientorganisationen när du väljer **nyttolaster.**</span><span class="sxs-lookup"><span data-stu-id="ae4f1-147">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>

## <a name="related-links"></a><span data-ttu-id="ae4f1-148">Relaterade länkar</span><span class="sxs-lookup"><span data-stu-id="ae4f1-148">Related links</span></span>

[<span data-ttu-id="ae4f1-149">Kom igång med Attack simuleringsträning</span><span class="sxs-lookup"><span data-stu-id="ae4f1-149">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="ae4f1-150">Skapa en simulering av nätfiskeattacker</span><span class="sxs-lookup"><span data-stu-id="ae4f1-150">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="ae4f1-151">Få insikter genom att träna på attacksimulering</span><span class="sxs-lookup"><span data-stu-id="ae4f1-151">Gain insights through Attack simulation training</span></span>](attack-simulation-training-insights.md)
