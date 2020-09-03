---
title: Rensa en mobil enhet i grundläggande mobilitet och säkerhet
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
description: Använd inbyggd grundläggande mobilitet och säkerhet för att ta bort information från registrerade enheter.
ms.openlocfilehash: 4d854c7d4d81cd0b49ec7f81a49de5478b08f049
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337119"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="63eba-103">Rensa en mobil enhet i grundläggande mobilitet och säkerhet</span><span class="sxs-lookup"><span data-stu-id="63eba-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="63eba-104">Du kan använda inbyggd grundläggande mobilitet och säkerhet för Microsoft 365 för att ta bort bara organisationsinformation, eller för att göra en fabriks återställning för att ta bort all information från en mobil enhet och återställa den till fabriks inställningarna.</span><span class="sxs-lookup"><span data-stu-id="63eba-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="63eba-105">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="63eba-105">Before you begin</span></span>

<span data-ttu-id="63eba-106">Mobila enheter kan lagra känslig organisationsinformation och ge till gång till organisationens Microsoft 365-resurser.</span><span class="sxs-lookup"><span data-stu-id="63eba-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="63eba-107">För att skydda organisationens information kan du göra fabriks återställning eller ta bort företags data:</span><span class="sxs-lookup"><span data-stu-id="63eba-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>
    
- <span data-ttu-id="63eba-108">**Fabriks återställning**: tar bort alla data på en användares mobila enhet, inklusive installerade program, foton och personlig information.</span><span class="sxs-lookup"><span data-stu-id="63eba-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="63eba-109">När rensningen är klar återställs enheten till fabriks inställningarna.</span><span class="sxs-lookup"><span data-stu-id="63eba-109">When the wipe is complete, the device is restored to its factory settings.</span></span>
    
- <span data-ttu-id="63eba-110">**Ta bort företags data**: tar bara bort organisations data och lämnar installerade program, foton och personlig information på en användares mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="63eba-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>   

- <span data-ttu-id="63eba-111">**När en enhet rensas (fabriks återställning eller tar bort företags data)** tas enheten bort från listan med hanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="63eba-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="63eba-112">**Återställa en enhet automatiskt**: du kan konfigurera en grundläggande mobilitet och säkerhets principer som automatiskt fabrik återställer en enhet efter det att användaren försöker ange enhets lösen ordet ett visst antal gånger.</span><span class="sxs-lookup"><span data-stu-id="63eba-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="63eba-113">Följ stegen i [skapa säkerhets principer för enheter i grundläggande mobilitet och säkerhet](create-device-security-policies-in-basic-mmobility-and-security.md).</span><span class="sxs-lookup"><span data-stu-id="63eba-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies-in-basic-mmobility-and-security.md).</span></span>
    
- <span data-ttu-id="63eba-114">**Om du vill ha information om hur du kan ta reda på användar upplevelsen** när du rensar sin enhet, se  [Vad är användare och enhets påverkan?](#whats-the-user-and-device-impact).</span><span class="sxs-lookup"><span data-stu-id="63eba-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>   

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="63eba-115">Rensa en mobil enhet</span><span class="sxs-lookup"><span data-stu-id="63eba-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="63eba-116">Gå till [administrations centret för Microsoft 365](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span><span class="sxs-lookup"><span data-stu-id="63eba-116">Go to the [Microsoft 365 admin center](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span></span>
    
2. <span data-ttu-id="63eba-117">Skriv hantering av mobila enheter i Sök fältet och välj **hantering av mobila enheter** i resultat listan.</span><span class="sxs-lookup"><span data-stu-id="63eba-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span> 

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Grundläggande alternativ för mobilitet och secruity mobila enheter":::

3. <span data-ttu-id="63eba-119">Välj **Hantera enheter**.</span><span class="sxs-lookup"><span data-stu-id="63eba-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="63eba-120">Välj den enhet som du vill rensa.</span><span class="sxs-lookup"><span data-stu-id="63eba-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="63eba-121">Välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="63eba-121">Select **Manage**.</span></span>

6. <span data-ttu-id="63eba-122">Välj den typ av fjärrsvep du vill göra.</span><span class="sxs-lookup"><span data-stu-id="63eba-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="63eba-123">Om du vill göra en fullständig rensning och återställa enheten till fabriks inställningarna väljer du **fabriks återställning**.</span><span class="sxs-lookup"><span data-stu-id="63eba-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="63eba-124">Om du vill göra en selektiv rensning och bara ta bort Microsoft 365-organisationsinformation väljer du **ta bort företags data**.</span><span class="sxs-lookup"><span data-stu-id="63eba-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="63eba-125">Om du vill ta bort enheten från din organisation väljer du **ta bort enhet**.</span><span class="sxs-lookup"><span data-stu-id="63eba-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="63eba-126">Välj **Ja** för att bekräfta.</span><span class="sxs-lookup"><span data-stu-id="63eba-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="63eba-127">Hur vet jag att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="63eba-127">How do I know it worked?</span></span>

<span data-ttu-id="63eba-128">Den mobila enheten visas inte längre i listan med hanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="63eba-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="63eba-129">Varför vill du rensa en enhet?</span><span class="sxs-lookup"><span data-stu-id="63eba-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="63eba-130">Rensa en enhet av följande anledningar:</span><span class="sxs-lookup"><span data-stu-id="63eba-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="63eba-131">Mobila enheter som smartphones och surfplattor blir mer fulla hela tiden.</span><span class="sxs-lookup"><span data-stu-id="63eba-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="63eba-132">Det innebär att det är lättare för användarna att lagra känslig företags information, till exempel person uppgifter eller konfidentiella meddelanden, samt komma åt den när du är på språng.</span><span class="sxs-lookup"><span data-stu-id="63eba-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="63eba-133">Om någon av dessa mobila enheter tappas bort eller stjäls kan du förhindra att organisationens information slutar på ett felaktigt sätt genom att rensa enheten.</span><span class="sxs-lookup"><span data-stu-id="63eba-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="63eba-134">När en användare lämnar organisationen med en personlig enhet som är registrerad i grundläggande mobilitet och säkerhet kan du förhindra att organisations informationen går vidare med den användaren genom att göra en fabriks återställning.</span><span class="sxs-lookup"><span data-stu-id="63eba-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="63eba-135">Om din organisation tillhandahåller mobila enheter för användarna kan du behöva flytta över dem då och då.</span><span class="sxs-lookup"><span data-stu-id="63eba-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="63eba-136">Om du gör en fabriks återställning på en enhet innan du tilldelar den till en ny användare ser du till att känslig information från den tidigare ägaren tas bort.</span><span class="sxs-lookup"><span data-stu-id="63eba-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="63eba-137">Vad händer med användare och enheter?</span><span class="sxs-lookup"><span data-stu-id="63eba-137">What's the user and device impact?</span></span>

<span data-ttu-id="63eba-138">Rensningen skickas direkt till den mobila enheten och enheten markeras som icke-kompatibel i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="63eba-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="63eba-139">När alla data tas bort när en enhet återställs till fabriks inställningarna beskrivs i följande tabell vilket innehåll som tas bort för varje enhet när en enhet tas bort från företags data.</span><span class="sxs-lookup"><span data-stu-id="63eba-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="63eba-140">**Innehålls upphastighet**</span><span class="sxs-lookup"><span data-stu-id="63eba-140">**Content impace**</span></span>|<span data-ttu-id="63eba-141">**iOS 10 och senare**</span><span class="sxs-lookup"><span data-stu-id="63eba-141">**iOS 10 and later**</span></span>|<span data-ttu-id="63eba-142">**Android 5 och senare**</span><span class="sxs-lookup"><span data-stu-id="63eba-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="63eba-143">Microsoft 365-AppData rensas om enheten skyddas av Intune App Protection-principer.</span><span class="sxs-lookup"><span data-stu-id="63eba-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="63eba-144">Apparna har inte tagits bort.</span><span class="sxs-lookup"><span data-stu-id="63eba-144">The apps aren't removed.</span></span> <span data-ttu-id="63eba-145">För enheter som inte skyddas av MAM (Mobile Application Management) kan inte Outlook och OneDrive ta bort cachelagrade data.</span><span class="sxs-lookup"><span data-stu-id="63eba-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="63eba-146">**Obs!** För att tillämpa principer för Intune-appen måste du ha en Intune-licens.</span><span class="sxs-lookup"><span data-stu-id="63eba-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="63eba-147">Ja</span><span class="sxs-lookup"><span data-stu-id="63eba-147">Yes</span></span>|<span data-ttu-id="63eba-148">Ja</span><span class="sxs-lookup"><span data-stu-id="63eba-148">Yes</span></span>|
|<span data-ttu-id="63eba-149">Princip inställningar som tillämpas av grundläggande mobilitet och säkerhet på enheter genomdrivs inte längre; användare kan ändra inställningarna.</span><span class="sxs-lookup"><span data-stu-id="63eba-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="63eba-150">Ja</span><span class="sxs-lookup"><span data-stu-id="63eba-150">Yes</span></span>|<span data-ttu-id="63eba-151">Ja</span><span class="sxs-lookup"><span data-stu-id="63eba-151">Yes</span></span>|
|<span data-ttu-id="63eba-152">E-postprofiler som skapas av grundläggande mobilitet och säkerhet tas bort och cachelagrad e-post på enheten tas bort.</span><span class="sxs-lookup"><span data-stu-id="63eba-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="63eba-153">Ja</span><span class="sxs-lookup"><span data-stu-id="63eba-153">Yes</span></span>|<span data-ttu-id="63eba-154">Saknas</span><span class="sxs-lookup"><span data-stu-id="63eba-154">N/A</span></span>|
>[!NOTE] 
><span data-ttu-id="63eba-155">Företagsportalsappen är tillgänglig i App Store för iOS och Play Store för Android-enheter.</span><span class="sxs-lookup"><span data-stu-id="63eba-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="63eba-156">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="63eba-156">Related topics</span></span>

[<span data-ttu-id="63eba-157">Konfigurera grundläggande mobilitet och säkerhet</span><span class="sxs-lookup"><span data-stu-id="63eba-157">Set up Basic Mobility and Security</span></span>](set-up-basic-mobility-and-security.md)