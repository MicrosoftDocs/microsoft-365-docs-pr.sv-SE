---
title: Skapa en nytto last för utbildning för attack simulering
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Administratörer kan läsa mer om hur man skapar anpassade nytto laster för utbildning för angrepps simulering i Microsoft Defender för Office 365.
ms.openlocfilehash: c42090634f6fa9500ae4c3e781b49b607ee928f5
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667550"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="a97a9-103">Skapa en anpassad nyttolast för att träna på attacksimulering</span><span class="sxs-lookup"><span data-stu-id="a97a9-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="a97a9-104">Microsoft erbjuder en robust nytto Last katalog för olika sociala teknik tekniker som kan kopplas till din utbildning för utskrivning av attacker.</span><span class="sxs-lookup"><span data-stu-id="a97a9-104">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="a97a9-105">Men du kanske vill skapa anpassade nytto laster som fungerar bättre för din organisation.</span><span class="sxs-lookup"><span data-stu-id="a97a9-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="a97a9-106">I den här artikeln beskrivs hur du skapar en nytto last för utbildning för attack simulering i Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="a97a9-106">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="a97a9-107">Du kan skapa en nytto last genom att klicka på **skapa en nytto Last** på [fliken dedikerade **nytto laster**](https://security.microsoft.com/attacksimulator?viewid=payload) eller i [guiden skapa simulering](attack-simulation-training.md#selecting-a-payload).</span><span class="sxs-lookup"><span data-stu-id="a97a9-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="a97a9-108">I det första steget i guiden kan du välja en nytto Last typ.</span><span class="sxs-lookup"><span data-stu-id="a97a9-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="a97a9-109">**För närvarande är bara e-post tillgänglig**.</span><span class="sxs-lookup"><span data-stu-id="a97a9-109">**Currently, only email is available**.</span></span>

<span data-ttu-id="a97a9-110">Välj sedan en associerad teknik.</span><span class="sxs-lookup"><span data-stu-id="a97a9-110">Next, select an associated technique.</span></span> <span data-ttu-id="a97a9-111">Se mer information om tekniker när du [väljer en social teknik teknik](attack-simulation-training.md#selecting-a-social-engineering-technique).</span><span class="sxs-lookup"><span data-stu-id="a97a9-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="a97a9-112">I nästa steg namnger du din nytto Last.</span><span class="sxs-lookup"><span data-stu-id="a97a9-112">In the next step name your payload.</span></span> <span data-ttu-id="a97a9-113">Du kan också ange en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="a97a9-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="a97a9-114">Konfigurera nytto Last</span><span class="sxs-lookup"><span data-stu-id="a97a9-114">Configure payload</span></span>

<span data-ttu-id="a97a9-115">Nu är det dags att bygga din nytto Last.</span><span class="sxs-lookup"><span data-stu-id="a97a9-115">Now it's time to build your payload.</span></span> <span data-ttu-id="a97a9-116">Ange avsändarens namn, e-postadress och meddelandets ämne i avsnittet **avsändare** .</span><span class="sxs-lookup"><span data-stu-id="a97a9-116">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="a97a9-117">Välj en nät fiske-URL i listan.</span><span class="sxs-lookup"><span data-stu-id="a97a9-117">Pick a phishing URL from the the provided list.</span></span> <span data-ttu-id="a97a9-118">Denna URL kommer senare att bäddas in i meddelande texten.</span><span class="sxs-lookup"><span data-stu-id="a97a9-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="a97a9-119">Du kan välja en intern e-postadress för avsändarens avsändare, som kommer att visas som en annan anställd i företaget.</span><span class="sxs-lookup"><span data-stu-id="a97a9-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="a97a9-120">Detta ökar det mottagligt för nytto lasten och hjälper anställda att hålla sig utsatt för risk för interna hot.</span><span class="sxs-lookup"><span data-stu-id="a97a9-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="a97a9-121">Det finns en RTF-redigerare som kan skapa din nytto Last.</span><span class="sxs-lookup"><span data-stu-id="a97a9-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="a97a9-122">Du kan också importera ett e-postmeddelande som du har skapat i förväg.</span><span class="sxs-lookup"><span data-stu-id="a97a9-122">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="a97a9-123">När du skapar bröd texten i e-postmeddelandet kan du dra nytta av de **dynamiska märkningarna** för att anpassa e-postmeddelandet till dina mål.</span><span class="sxs-lookup"><span data-stu-id="a97a9-123">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="a97a9-124">Klicka på **phishing-länken** för att lägga till den tidigare valda nät fiske adressen i meddelande texten.</span><span class="sxs-lookup"><span data-stu-id="a97a9-124">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![Phishing-länk och dynamiska Taggar markerade i nytto last för Microsoft Defender för Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="a97a9-126">Om du vill spara tid kan du växla till alternativet att **ersätta alla länkar i e-postmeddelandet med phishing-länken**.</span><span class="sxs-lookup"><span data-stu-id="a97a9-126">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="a97a9-127">När du är klar med att bygga upp nytto lasten klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a97a9-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="a97a9-128">Lägga till indikatorer</span><span class="sxs-lookup"><span data-stu-id="a97a9-128">Adding indicators</span></span>

<span data-ttu-id="a97a9-129">Med indikatorer blir det lättare för anställda att komma via attack simuleringen förstå hur de kan leta efter i framtida attacker.</span><span class="sxs-lookup"><span data-stu-id="a97a9-129">Indicators will help employees going through the attack simulation understand clue they can look for in future attacks.</span></span> <span data-ttu-id="a97a9-130">Börja genom att klicka på **Lägg till indikator**.</span><span class="sxs-lookup"><span data-stu-id="a97a9-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="a97a9-131">Välj en indikator du vill använda i list rutan.</span><span class="sxs-lookup"><span data-stu-id="a97a9-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="a97a9-132">Listan granskas för att innehålla de vanligaste LED trådar som visas i nät fiske meddelanden.</span><span class="sxs-lookup"><span data-stu-id="a97a9-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="a97a9-133">När du markerat det här alternativet kontrollerar du att indikator placeringen är inställd på **från bröd texten i e-** postmeddelandet och klickar på **Markera text**.</span><span class="sxs-lookup"><span data-stu-id="a97a9-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="a97a9-134">Markera den del av nytto lasten där denna indikator visas och klicka på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="a97a9-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![Markerad text i meddelande texten för att lägga till en symbol i utbildning för attack simulering](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="a97a9-136">Lägg till en egen beskrivning som beskriver indikatorn och klicka i indikatorn för förhands granskning för att se en förhands granskning av indikatorn.</span><span class="sxs-lookup"><span data-stu-id="a97a9-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="a97a9-137">När du är klar klickar du på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="a97a9-137">Once done, click **Add**.</span></span> <span data-ttu-id="a97a9-138">Upprepa de här stegen tills du har täckt alla indikatorer i din nytto Last.</span><span class="sxs-lookup"><span data-stu-id="a97a9-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="a97a9-139">Granska nytto Last</span><span class="sxs-lookup"><span data-stu-id="a97a9-139">Review payload</span></span>

<span data-ttu-id="a97a9-140">Du är klar med att bygga din nytto Last.</span><span class="sxs-lookup"><span data-stu-id="a97a9-140">You're done building your payload.</span></span> <span data-ttu-id="a97a9-141">Nu är det dags att granska informationen och se en förhands granskning av din nytto Last.</span><span class="sxs-lookup"><span data-stu-id="a97a9-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="a97a9-142">I förhands granskningen visas alla indikatorer som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="a97a9-142">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="a97a9-143">Du kan redigera varje del av nytto lasten från det här steget.</span><span class="sxs-lookup"><span data-stu-id="a97a9-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="a97a9-144">**Skicka** in din betalning när du är nöjd.</span><span class="sxs-lookup"><span data-stu-id="a97a9-144">Once satisfied, **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a97a9-145">De nytto laster som du har skapat har **klient organisationen** som källa.</span><span class="sxs-lookup"><span data-stu-id="a97a9-145">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="a97a9-146">När du väljer nytto laster bör du kontrol lera att du inte filtrerar bort **klient organisationen**.</span><span class="sxs-lookup"><span data-stu-id="a97a9-146">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>
