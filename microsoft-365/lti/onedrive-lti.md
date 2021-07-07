---
title: Användning Microsoft OneDrive Learning verktygskompatibilitet
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Skapa och betygs gradera uppgifter, skapa och hantera kursinnehåll och samarbeta i filer i realtid med den nya appen Microsoft OneDrive Learning Tools Interoperability App.
ms.openlocfilehash: bcb374ed1666f23fa5f3d4692f43a4369670e891
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322227"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="44708-103">Integrera Microsoft OneDrive LTI med Canvas</span><span class="sxs-lookup"><span data-stu-id="44708-103">Integrate Microsoft OneDrive LTI with Canvas</span></span>

<span data-ttu-id="44708-104">Att Microsoft OneDrive en LTI med Canvas är en process i två steg.</span><span class="sxs-lookup"><span data-stu-id="44708-104">Integrating Microsoft OneDrive LTI with Canvas is a two step process.</span></span> <span data-ttu-id="44708-105">Med det första steget Microsoft OneDrive funktionen i Canvas, och med det andra steget Microsoft OneDrive LTI tillgängligt i Canvas-kurser.</span><span class="sxs-lookup"><span data-stu-id="44708-105">The first step enables Microsoft OneDrive in Canvas, and the second step makes the Microsoft OneDrive LTI available within Canvas courses.</span></span>

## <a name="recommended-browser-settings"></a><span data-ttu-id="44708-106">Rekommenderade webbläsarinställningar</span><span class="sxs-lookup"><span data-stu-id="44708-106">Recommended browser settings</span></span>

- <span data-ttu-id="44708-107">Cookies ska aktiveras för Microsoft OneDrive.</span><span class="sxs-lookup"><span data-stu-id="44708-107">Cookies should be enabled for Microsoft OneDrive.</span></span>
- <span data-ttu-id="44708-108">Popup-fönster ska inte blockeras för Microsoft OneDrive.</span><span class="sxs-lookup"><span data-stu-id="44708-108">Popups should not be blocked for Microsoft OneDrive.</span></span>

> [!NOTE]
> - <span data-ttu-id="44708-109">Cookies är inte aktiverade som standard i Chrome-webbläsaren inkognitoläge och måste aktiveras.</span><span class="sxs-lookup"><span data-stu-id="44708-109">Cookies are not enabled by default in the Chrome browser incognito mode, and will need to be enabled.</span></span>
> - <span data-ttu-id="44708-110">Microsoft OneDrive LTI fungerar i privat läge i Microsoft Edge webbläsare.</span><span class="sxs-lookup"><span data-stu-id="44708-110">Microsoft OneDrive LTI works in the private mode in Microsoft Edge browser.</span></span> <span data-ttu-id="44708-111">Kontrollera att du inte har blockerat cookies (som är aktiverade som standard).</span><span class="sxs-lookup"><span data-stu-id="44708-111">Ensure that you have not blocked cookies (which are enabled by default).</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a><span data-ttu-id="44708-112">Aktivera Microsoft OneDrive LTI i Canvas</span><span class="sxs-lookup"><span data-stu-id="44708-112">Enable Microsoft OneDrive LTI in Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44708-113">Den person som utför den här integrationen bör vara administratör för Canvas och administratör för Microsoft 365 klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="44708-113">The person who performs this integration should be an administrator of Canvas and an administrator of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="44708-114">Logga in Microsoft OneDrive <a href="https://onedrivelti.microsoft.com/admin" target="_blank">LTI-registreringsportalen</a></span><span class="sxs-lookup"><span data-stu-id="44708-114">Sign into the <a href="https://onedrivelti.microsoft.com/admin" target="_blank">Microsoft OneDrive LTI Registration Portal</a></span></span>
1. <span data-ttu-id="44708-115">Välj knappen **Administratörsmedgivande** och godkänn behörigheterna.</span><span class="sxs-lookup"><span data-stu-id="44708-115">Select the **Admin Consent** button and accept the permissions.</span></span>

> [!CAUTION]
> <span data-ttu-id="44708-116">Om det här steget inte utförs får du ett felmeddelande i följande steg och du kan inte utföra det här steget på en timme när du har fått felmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="44708-116">If this step isn't performed, the following step will give you an error, and you won't be able to take this step for an hour once you've gotten the error.</span></span>

3. <span data-ttu-id="44708-117">Välj knappen **Skapa ny LTI-klient.**</span><span class="sxs-lookup"><span data-stu-id="44708-117">Select the **Create new LTI Tenant** button.</span></span> <span data-ttu-id="44708-118">På sidan LTI Registration väljer du **Canvas** i listrutan och anger bas-URL-adressen för Canvas-instansen.</span><span class="sxs-lookup"><span data-stu-id="44708-118">On the LTI Registration page select **Canvas** in the dropdown and enter the base URL of your Canvas instance.</span></span>

> [!NOTE]
> <span data-ttu-id="44708-119">Om din Canvas-instans till exempel https://contoso.test.instructure.com är ]( https://contoso.test.instructure.com) ska den fullständiga webbadressen anges.</span><span class="sxs-lookup"><span data-stu-id="44708-119">If your Canvas instance is, for example, https://contoso.test.instructure.com](https://contoso.test.instructure.com), then the complete URL should be entered.</span></span>

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="Administrationssidan för LTI-klientorganisationen med ett listreringsfält för att välja LTI-konsumentplattformen och ett textfält för URL.":::

4. <span data-ttu-id="44708-121">Kopiera JSON genom att välja **knappen** Kopiera (en ikon till höger som visar två sidor ovanpå varandra).</span><span class="sxs-lookup"><span data-stu-id="44708-121">Copy the JSON by selecting the **Copy** button (an icon on the right that shows two pages on top of one another).</span></span> <span data-ttu-id="44708-122">Detta används för att generera nyckeln i Canvas.</span><span class="sxs-lookup"><span data-stu-id="44708-122">This will be used to generate the key in Canvas.</span></span>

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="En bild som visar knappen Kopiera som kopierar den JSON-text som visas och gör den tillgänglig för nyckelgenerering i Canvas.":::

5. <span data-ttu-id="44708-124">Logga in på Canvas-instansen som administratör och välj **Utvecklarnycklar** på menyn till vänster på sidan.</span><span class="sxs-lookup"><span data-stu-id="44708-124">Sign into your Canvas instance as the administrator and select **Developer Keys** from the menu on the left side of the page.</span></span> <span data-ttu-id="44708-125">Skapa en utvecklarnyckel i listrutan genom att välja **LTI-nyckel** i listrutan uppe till höger på sidan.</span><span class="sxs-lookup"><span data-stu-id="44708-125">From the dropdown, create a developer key by choosing **LTI Key** from the dropdown on the upper right of the page.</span></span>

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="En skärmbild som visar det vänstra navigeringsfältet med Utvecklarnycklar markerat och LTI-tangentposten markerad i en listmeny till höger på sidan.":::

6. <span data-ttu-id="44708-127">På sidan Configure i listrutan **Method** väljer du Klistra in **JSON** som metod och klistrar in den JSON-text du kopierade i steg 5 i textfältet som visas.</span><span class="sxs-lookup"><span data-stu-id="44708-127">On the Configure page, in the **Method** dropdown, select **Paste JSON** as the method and paste the JSON text you copied in Step 5 in the text field that appears.</span></span>
7. <span data-ttu-id="44708-128">Spara nyckeln så blir den tillgänglig i Canvas i läget **Av.**</span><span class="sxs-lookup"><span data-stu-id="44708-128">Save the key, and it becomes available in Canvas in an **Off** state.</span></span> <span data-ttu-id="44708-129">Aktivera nyckeln **och** kopiera den nyckel som anges i kolumnen **Information** som ska användas i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="44708-129">Turn the key **On** and copy the key given in the **Details** column to be used in the next step.</span></span>

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="Arbetsytesidan med nyckeln i läget Off. Den måste vara aktiverad och nyckeln måste kopieras från informationskolumnen på den här sidan.":::

8. <span data-ttu-id="44708-131">Gå tillbaka till Microsoft OneDrive för LTI-registrering och klistra in nyckeln i **fältet Canvas klient-ID.**</span><span class="sxs-lookup"><span data-stu-id="44708-131">Return to the Microsoft OneDrive LTI Registration portal and paste the key in the **Canvas Client ID** field.</span></span> <span data-ttu-id="44708-132">Välj **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="44708-132">Select **Next** when you're ready.</span></span>

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="Registreringssidan för LTI-klientorganisation, som visar JSON-texten och textrutan som nyckeln ska kopieras till.":::

9. <span data-ttu-id="44708-134">Granska och spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="44708-134">Review and save your changes.</span></span> <span data-ttu-id="44708-135">Ett meddelande visas om att registreringen har lyckats.</span><span class="sxs-lookup"><span data-stu-id="44708-135">A message will be displayed on successful registration.</span></span>
10. <span data-ttu-id="44708-136">Du kan också granska din registreringsinformation genom att välja knappen Visa **LTI-innehavare** på startsidan.</span><span class="sxs-lookup"><span data-stu-id="44708-136">Your registration details can also be reviewed by selecting the **View LTI Tenants** button on the home page.</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="44708-137">Aktivera Microsoft OneDrive LTI i Canvas-kurser</span><span class="sxs-lookup"><span data-stu-id="44708-137">Enable Microsoft OneDrive LTI in Canvas Courses</span></span>

<span data-ttu-id="44708-138">En Canvas-administratör kan aktivera funktionen Microsoft OneDrive LTI för alla kurser.</span><span class="sxs-lookup"><span data-stu-id="44708-138">A Canvas administrator can enable Microsoft OneDrive LTI for all courses.</span></span> <span data-ttu-id="44708-139">Om Microsoft OneDrive LTI krävs i en särskild kurs (och inte i alla kurser), måste kursläraren följa samma steg i kursinställningarna.</span><span class="sxs-lookup"><span data-stu-id="44708-139">If Microsoft OneDrive LTI is needed in a specific course (and not all courses), the course educator needs to follow the same steps within the course settings.</span></span>

1. <span data-ttu-id="44708-140">Logga in som administratör och gå till **avsnittet Inställningar** administratör.</span><span class="sxs-lookup"><span data-stu-id="44708-140">Sign in as an administrator and go to the **Settings** section.</span></span>
2. <span data-ttu-id="44708-141">Gå till **avsnittet Appar** och välj knappen Visa **appkonfigurationer.**</span><span class="sxs-lookup"><span data-stu-id="44708-141">Go to the **Apps** section and select the **View App Configurations** button.</span></span>
3. <span data-ttu-id="44708-142">Välj knappen **Lägg till** app.</span><span class="sxs-lookup"><span data-stu-id="44708-142">Select the **Add App** button.</span></span>
4. <span data-ttu-id="44708-143">I **listrutan Konfigurationstyp** väljer du **alternativet Efter klient-ID.**</span><span class="sxs-lookup"><span data-stu-id="44708-143">In the **Configuration Type** dropdown, choose the **By Client ID** option.</span></span>
5. <span data-ttu-id="44708-144">Klistra in värdet för utvecklarnyckeln som genererades tidigare i fältet **Klient-ID** och välj **knappen** Skicka.</span><span class="sxs-lookup"><span data-stu-id="44708-144">Paste the value of the developer key generated previously in the **Client ID** field, and select the **Submit** button.</span></span>

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="Sidan Lägg till app, med alternativet Efter klient-ID under listrutan Konfigurationstyp.":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="44708-146">Samarbetsfunktioner Inställningar för Microsoft OneDrive LTI i Canvas-kurser</span><span class="sxs-lookup"><span data-stu-id="44708-146">Collaboration Settings for Microsoft OneDrive LTI in Canvas Courses</span></span>

> [!NOTE]
> <span data-ttu-id="44708-147">För att samarbete ska fungera för lärare och elever bör du inte aktivera inställningen för samarbete.</span><span class="sxs-lookup"><span data-stu-id="44708-147">For collaboration to work for educators and students, you shouldn't enable the collaboration setting.</span></span> <span data-ttu-id="44708-148">Kontrollera att inställningen inte är aktiverad genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="44708-148">To make sure the setting isn't enabled, follow the steps below.</span></span>

1. <span data-ttu-id="44708-149">Logga in som administratör och gå till avsnittet **Inställningar** administratör.</span><span class="sxs-lookup"><span data-stu-id="44708-149">Sign in as an admin and go to the **Settings** section.</span></span>
1. <span data-ttu-id="44708-150">Gå **till avsnittet Funktionsalternativ** och gå sedan till **avsnittet** Kurs.</span><span class="sxs-lookup"><span data-stu-id="44708-150">Go to **Feature Options** section, and then go to the **Course** section.</span></span>
1. <span data-ttu-id="44708-151">Ange att **funktionen Verktyg för externt** samarbete inte ska aktiveras.</span><span class="sxs-lookup"><span data-stu-id="44708-151">Set the **External Collaborations Tool** feature to be not enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="44708-152">Samarbete kan tilldelas enskilda elever och grupper av elever.</span><span class="sxs-lookup"><span data-stu-id="44708-152">Collaboration can be assigned to individual students and to groups of students.</span></span> <span data-ttu-id="44708-153">Tilldelning till enskilda elever fungerar som standard.</span><span class="sxs-lookup"><span data-stu-id="44708-153">Assigning to individual students works by default.</span></span> <span data-ttu-id="44708-154">Följ de här stegen för att kunna tilldela samarbete till en grupp elever:</span><span class="sxs-lookup"><span data-stu-id="44708-154">To be able to assign collaboration to group of students, follow these steps:</span></span>

1. <span data-ttu-id="44708-155">Logga in som administratör och gå till **avsnittet Utvecklarnycklar.**</span><span class="sxs-lookup"><span data-stu-id="44708-155">Login as admin and go to the **Developer Keys** section.</span></span>
1. <span data-ttu-id="44708-156">Leta reda på nyckeln med värdet 17000000000710 och ställ in den på **På**.</span><span class="sxs-lookup"><span data-stu-id="44708-156">Find the key with value 170000000000710 and set it to **On**.</span></span>
