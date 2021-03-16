---
title: Rensa en mobil enhet i Basic Mobility and Security
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Använd inbyggd basic mobility and security för att ta bort information från registrerade enheter.
ms.openlocfilehash: ddf13ef6627d70128064e2d8bd185203244b12e4
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819814"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="20171-103">Rensa en mobil enhet i Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="20171-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="20171-104">Du kan använda den inbyggda grundläggande rörlighet och säkerhet för Microsoft 365 för att ta bort enbart organisationsinformation, eller för att utföra en fabriksåterställning för att ta bort all information från en mobil enhet och återställa den till fabriksinställningarna.</span><span class="sxs-lookup"><span data-stu-id="20171-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="20171-105">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="20171-105">Before you begin</span></span>

<span data-ttu-id="20171-106">Mobila enheter kan lagra känslig information om organisationen och ge åtkomst till organisationens Microsoft 365-resurser.</span><span class="sxs-lookup"><span data-stu-id="20171-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="20171-107">För att skydda organisationens information kan du göra fabriksåterställning eller ta bort företagsdata:</span><span class="sxs-lookup"><span data-stu-id="20171-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>

- <span data-ttu-id="20171-108">**Fabriksåterställning:** Tar bort alla data på en användares mobila enhet, inklusive installerade program, foton och personlig information.</span><span class="sxs-lookup"><span data-stu-id="20171-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="20171-109">När rensningen är klar återställs enheten till fabriksinställningarna.</span><span class="sxs-lookup"><span data-stu-id="20171-109">When the wipe is complete, the device is restored to its factory settings.</span></span>

- <span data-ttu-id="20171-110">**Ta bort företagsdata:** Tar bara bort organisationsdata och lämnar installerade program, foton och personlig information på en användares mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="20171-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>

- <span data-ttu-id="20171-111">**När en enhet rensas (fabriksåterställning eller ta bort företagsdata)** tas enheten bort från listan med hanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="20171-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="20171-112">**Återställa en enhet automatiskt:** Du kan konfigurera en grundläggande mobilitets- och säkerhetsprincip som automatiskt fabriksåterställer en enhet när en användare inte lyckats ange enhetslösenordet ett visst antal gånger.</span><span class="sxs-lookup"><span data-stu-id="20171-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="20171-113">Det gör du genom att följa stegen i [Skapa säkerhetsprinciper för enheter i grundläggande rörlighet och säkerhet.](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="20171-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies.md).</span></span>
    
- <span data-ttu-id="20171-114">**Om du vill veta hur användarupplevelsen ser ut** när du rensar deras enhet kan du gå till   [Vad påverkar användaren och enheten?](#whats-the-user-and-device-impact).</span><span class="sxs-lookup"><span data-stu-id="20171-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="20171-115">Rensa en mobil enhet</span><span class="sxs-lookup"><span data-stu-id="20171-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="20171-116">Gå till [administrationscentret för Microsoft 365.](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)</span><span class="sxs-lookup"><span data-stu-id="20171-116">Go to the [Microsoft 365 admin center](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span></span>

2. <span data-ttu-id="20171-117">Skriv Hantering av mobila enheter i sökfältet och välj **Hantering av mobila** enheter i listan med resultat.</span><span class="sxs-lookup"><span data-stu-id="20171-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Alternativ för hantering av mobila enheter med Enkel rörlighet och Secruity":::

3. <span data-ttu-id="20171-119">Välj **Hantera enheter**.</span><span class="sxs-lookup"><span data-stu-id="20171-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="20171-120">Välj den enhet du vill rensa.</span><span class="sxs-lookup"><span data-stu-id="20171-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="20171-121">Välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="20171-121">Select **Manage**.</span></span>

6. <span data-ttu-id="20171-122">Välj den typ av fjärrensning du vill göra.</span><span class="sxs-lookup"><span data-stu-id="20171-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="20171-123">Om du vill göra en fullständig rensning och återställa enheten till fabriksinställningarna väljer du **Fabriksåterställning**.</span><span class="sxs-lookup"><span data-stu-id="20171-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="20171-124">Om du vill göra en selektiv rensning och bara ta bort Microsoft 365-organisationsinformation väljer du **Ta bort företagsdata.**</span><span class="sxs-lookup"><span data-stu-id="20171-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="20171-125">Om du vill ta bort enheten från din organisation väljer du **Ta bort enhet**.</span><span class="sxs-lookup"><span data-stu-id="20171-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="20171-126">Bekräfta genom att välja **Ja**.</span><span class="sxs-lookup"><span data-stu-id="20171-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="20171-127">Hur vet jag att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="20171-127">How do I know it worked?</span></span>

<span data-ttu-id="20171-128">Du ser inte längre den mobila enheten i listan över hanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="20171-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="20171-129">Varför skulle du vilja rensa en enhet?</span><span class="sxs-lookup"><span data-stu-id="20171-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="20171-130">Rensa en enhet av följande anledningar:</span><span class="sxs-lookup"><span data-stu-id="20171-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="20171-131">Mobila enheter som smartphones och surfplattor blir allt mer fullödig hela tiden.</span><span class="sxs-lookup"><span data-stu-id="20171-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="20171-132">Det innebär att det är enklare för användarna att lagra känslig företagsinformation som personuppgifter eller konfidentiella meddelanden och att använda den var de än är.</span><span class="sxs-lookup"><span data-stu-id="20171-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="20171-133">Om en av de mobila enheterna försvinner eller blir stulen kan en utparning av enheten förhindra att organisationens information hamnar i fel händer.</span><span class="sxs-lookup"><span data-stu-id="20171-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="20171-134">Om en användare lämnar organisationen med en personlig enhet som är registrerad i Basic Mobility and Security kan du förhindra att organisationsinformationen går med den användaren genom att göra en fabriksåterställning.</span><span class="sxs-lookup"><span data-stu-id="20171-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="20171-135">Om din organisation tillhandahåller mobila enheter åt användare kan du då och då behöva tilldela om enheterna.</span><span class="sxs-lookup"><span data-stu-id="20171-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="20171-136">Genom att göra en fabriksåterställning på en enhet innan du tilldelar den till en ny användare kan du se till att känslig information från den tidigare ägaren tas bort.</span><span class="sxs-lookup"><span data-stu-id="20171-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="20171-137">Hur påverkar det användaren och enheten?</span><span class="sxs-lookup"><span data-stu-id="20171-137">What's the user and device impact?</span></span>

<span data-ttu-id="20171-138">Rensningen skickas direkt till den mobila enheten och enheten markeras som inte kompatibel i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="20171-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="20171-139">Även om alla data tas bort när en enhet återställs till fabriksinställningarna beskriver följande tabell vilket innehåll som tas bort för varje enhetstyp när en enhet tas bort när företagsdata tas bort.</span><span class="sxs-lookup"><span data-stu-id="20171-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="20171-140">**Påverkan på innehållet**</span><span class="sxs-lookup"><span data-stu-id="20171-140">**Content impact**</span></span>|<span data-ttu-id="20171-141">**iOS 10 och senare**</span><span class="sxs-lookup"><span data-stu-id="20171-141">**iOS 10 and later**</span></span>|<span data-ttu-id="20171-142">**Android 5 och senare**</span><span class="sxs-lookup"><span data-stu-id="20171-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="20171-143">Appdata för Microsoft 365 rensas om enheten skyddas av App Protection-principer för Intune.</span><span class="sxs-lookup"><span data-stu-id="20171-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="20171-144">Apparna tas inte bort.</span><span class="sxs-lookup"><span data-stu-id="20171-144">The apps aren't removed.</span></span> <span data-ttu-id="20171-145">För enheter som inte skyddas av MAM-principer (Mobile Application Management) tar Outlook och OneDrive inte bort cachelagrade data.</span><span class="sxs-lookup"><span data-stu-id="20171-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="20171-146">**Obs!** För att använda Intune-appskyddsprinciper måste du ha en Intune-licens.</span><span class="sxs-lookup"><span data-stu-id="20171-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="20171-147">Ja</span><span class="sxs-lookup"><span data-stu-id="20171-147">Yes</span></span>|<span data-ttu-id="20171-148">Ja</span><span class="sxs-lookup"><span data-stu-id="20171-148">Yes</span></span>|
|<span data-ttu-id="20171-149">Principinställningarna som används av Basic Mobility och Security på enheter tillämpas inte längre. användare kan ändra inställningarna.</span><span class="sxs-lookup"><span data-stu-id="20171-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="20171-150">Ja</span><span class="sxs-lookup"><span data-stu-id="20171-150">Yes</span></span>|<span data-ttu-id="20171-151">Ja</span><span class="sxs-lookup"><span data-stu-id="20171-151">Yes</span></span>|
|<span data-ttu-id="20171-152">E-postprofiler som skapats med Basic Mobility and Security tas bort och cachelagrad e-post på enheten tas bort.</span><span class="sxs-lookup"><span data-stu-id="20171-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="20171-153">Ja</span><span class="sxs-lookup"><span data-stu-id="20171-153">Yes</span></span>|<span data-ttu-id="20171-154">Uppgift saknas</span><span class="sxs-lookup"><span data-stu-id="20171-154">N/A</span></span>|
>[!NOTE]
><span data-ttu-id="20171-155">Företagsportalappen finns i App Store för iOS och Play Store för Android-enheter.</span><span class="sxs-lookup"><span data-stu-id="20171-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="20171-156">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="20171-156">Related topics</span></span>

[<span data-ttu-id="20171-157">Konfigurera grundläggande Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="20171-157">Set up Basic Mobility and Security</span></span>](set-up.md)
