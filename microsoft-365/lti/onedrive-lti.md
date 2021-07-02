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
ms.openlocfilehash: 985a316bac689b9bc6c53ab65782d548fcad0db8
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53257074"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="949e3-103">Integrera Microsoft OneDrive LTI med Canvas</span><span class="sxs-lookup"><span data-stu-id="949e3-103">Integrate Microsoft OneDrive LTI with Canvas</span></span>

<span data-ttu-id="949e3-104">Att Microsoft OneDrive en LTI med Canvas är en process i två steg.</span><span class="sxs-lookup"><span data-stu-id="949e3-104">Integrating Microsoft OneDrive LTI with Canvas is a two step process.</span></span> <span data-ttu-id="949e3-105">Med det första steget Microsoft OneDrive funktionen i Canvas, och med det andra steget Microsoft OneDrive LTI tillgängligt i Canvas-kurser.</span><span class="sxs-lookup"><span data-stu-id="949e3-105">The first step enables Microsoft OneDrive in Canvas, and the second step makes the Microsoft OneDrive LTI available within Canvas courses.</span></span>

## <a name="recommended-browser-settings"></a><span data-ttu-id="949e3-106">Rekommenderade webbläsarinställningar</span><span class="sxs-lookup"><span data-stu-id="949e3-106">Recommended browser settings</span></span>

- <span data-ttu-id="949e3-107">Cookies ska aktiveras för Microsoft OneDrive.</span><span class="sxs-lookup"><span data-stu-id="949e3-107">Cookies should be enabled for Microsoft OneDrive.</span></span>
- <span data-ttu-id="949e3-108">Popup-fönster ska inte blockeras för Microsoft OneDrive.</span><span class="sxs-lookup"><span data-stu-id="949e3-108">Popups should not be blocked for Microsoft OneDrive.</span></span>

> [!NOTE]
> - <span data-ttu-id="949e3-109">Cookies är inte aktiverade som standard i Chrome-webbläsaren inkognitoläge och måste aktiveras.</span><span class="sxs-lookup"><span data-stu-id="949e3-109">Cookies are not enabled by default in the Chrome browser incognito mode, and will need to be enabled.</span></span>
> - <span data-ttu-id="949e3-110">Microsoft OneDrive LTI fungerar i privat läge i Microsoft Edge webbläsare.</span><span class="sxs-lookup"><span data-stu-id="949e3-110">Microsoft OneDrive LTI works in the private mode in Microsoft Edge browser.</span></span> <span data-ttu-id="949e3-111">Kontrollera att du inte har blockerat cookies (som är aktiverade som standard).</span><span class="sxs-lookup"><span data-stu-id="949e3-111">Ensure that you have not blocked cookies (which are enabled by default).</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a><span data-ttu-id="949e3-112">Aktivera Microsoft OneDrive LTI i Canvas</span><span class="sxs-lookup"><span data-stu-id="949e3-112">Enable Microsoft OneDrive LTI in Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="949e3-113">Den person som utför den här integrationen bör vara administratör för Canvas och administratör för Microsoft 365 klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="949e3-113">The person who performs this integration should be an administrator of Canvas and an administrator of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="949e3-114">Logga in Microsoft OneDrive <a href="https://onedrivelti.microsoft.com/admin" target="_blank">LTI-registreringsportalen</a></span><span class="sxs-lookup"><span data-stu-id="949e3-114">Sign into the <a href="https://onedrivelti.microsoft.com/admin" target="_blank">Microsoft OneDrive LTI Registration Portal</a></span></span>
1. <span data-ttu-id="949e3-115">Välj knappen **Administratörsmedgivande** och godkänn behörigheterna.</span><span class="sxs-lookup"><span data-stu-id="949e3-115">Select the **Admin Consent** button and accept the permissions.</span></span>
1. <span data-ttu-id="949e3-116">Välj knappen **Skapa ny LTI-klient.**</span><span class="sxs-lookup"><span data-stu-id="949e3-116">Select the **Create new LTI Tenant** button.</span></span> <span data-ttu-id="949e3-117">På sidan LTI Registration väljer du **Canvas** i listrutan och anger bas-URL-adressen för Canvas-instansen.</span><span class="sxs-lookup"><span data-stu-id="949e3-117">On the LTI Registration page select **Canvas** in the dropdown and enter the base URL of your Canvas instance.</span></span>

> [!NOTE]
> <span data-ttu-id="949e3-118">Om din Canvas-instans till exempel https://contoso.test.instructure.com är ]( https://contoso.test.instructure.com) ska den fullständiga webbadressen anges.</span><span class="sxs-lookup"><span data-stu-id="949e3-118">If your Canvas instance is, for example, https://contoso.test.instructure.com](https://contoso.test.instructure.com), then the complete URL should be entered.</span></span>

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="Administrationssidan för LTI-klientorganisationen med ett listreringsfält för att välja LTI-konsumentplattformen och ett textfält för URL.":::

4. <span data-ttu-id="949e3-120">Kopiera JSON genom att välja **knappen** Kopiera (en ikon till höger som visar två sidor ovanpå varandra).</span><span class="sxs-lookup"><span data-stu-id="949e3-120">Copy the JSON by selecting the **Copy** button (an icon on the right that shows two pages on top of one another).</span></span> <span data-ttu-id="949e3-121">Detta används för att generera nyckeln i Canvas.</span><span class="sxs-lookup"><span data-stu-id="949e3-121">This will be used to generate the key in Canvas.</span></span>

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="En bild som visar knappen Kopiera som kopierar den JSON-text som visas och gör den tillgänglig för nyckelgenerering i Canvas.":::

5. <span data-ttu-id="949e3-123">Logga in på Canvas-instansen som administratör och välj **Utvecklarnycklar** på menyn till vänster på sidan.</span><span class="sxs-lookup"><span data-stu-id="949e3-123">Sign into your Canvas instance as the administrator and select **Developer Keys** from the menu on the left side of the page.</span></span> <span data-ttu-id="949e3-124">Skapa en utvecklarnyckel i listrutan genom att välja **LTI-nyckel** i listrutan uppe till höger på sidan.</span><span class="sxs-lookup"><span data-stu-id="949e3-124">From the dropdown, create a developer key by choosing **LTI Key** from the dropdown on the upper right of the page.</span></span>

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="En skärmbild som visar det vänstra navigeringsfältet med Utvecklarnycklar markerat och LTI-tangentposten markerad i en listmeny till höger på sidan.":::

6. <span data-ttu-id="949e3-126">På sidan Configure i listrutan **Method** väljer du Klistra in **JSON** som metod och klistrar in den JSON-text du kopierade i steg 5 i textfältet som visas.</span><span class="sxs-lookup"><span data-stu-id="949e3-126">On the Configure page, in the **Method** dropdown, select **Paste JSON** as the method and paste the JSON text you copied in Step 5 in the text field that appears.</span></span>
7. <span data-ttu-id="949e3-127">Spara nyckeln så blir den tillgänglig i Canvas i läget **Av.**</span><span class="sxs-lookup"><span data-stu-id="949e3-127">Save the key, and it becomes available in Canvas in an **Off** state.</span></span> <span data-ttu-id="949e3-128">Aktivera nyckeln **och** kopiera den nyckel som anges i kolumnen **Information** som ska användas i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="949e3-128">Turn the key **On** and copy the key given in the **Details** column to be used in the next step.</span></span>

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="Arbetsytesidan med nyckeln i läget Off. Den måste vara aktiverad och nyckeln måste kopieras från informationskolumnen på den här sidan.":::

8. <span data-ttu-id="949e3-130">Gå tillbaka till Microsoft OneDrive för LTI-registrering och klistra in nyckeln i **fältet Canvas klient-ID.**</span><span class="sxs-lookup"><span data-stu-id="949e3-130">Return to the Microsoft OneDrive LTI Registration portal and paste the key in the **Canvas Client ID** field.</span></span> <span data-ttu-id="949e3-131">Välj **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="949e3-131">Select **Next** when you're ready.</span></span>

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="Registreringssidan för LTI-klientorganisation, som visar JSON-texten och textrutan som nyckeln ska kopieras till.":::

9. <span data-ttu-id="949e3-133">Granska och spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="949e3-133">Review and save your changes.</span></span> <span data-ttu-id="949e3-134">Ett meddelande visas om att registreringen har lyckats.</span><span class="sxs-lookup"><span data-stu-id="949e3-134">A message will be displayed on successful registration.</span></span>
10. <span data-ttu-id="949e3-135">Du kan också granska din registreringsinformation genom att välja knappen Visa **LTI-innehavare** på startsidan.</span><span class="sxs-lookup"><span data-stu-id="949e3-135">Your registration details can also be reviewed by selecting the **View LTI Tenants** button on the home page.</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="949e3-136">Aktivera Microsoft OneDrive LTI i Canvas-kurser</span><span class="sxs-lookup"><span data-stu-id="949e3-136">Enable Microsoft OneDrive LTI in Canvas Courses</span></span>

<span data-ttu-id="949e3-137">En Canvas-administratör kan aktivera funktionen Microsoft OneDrive LTI för alla kurser.</span><span class="sxs-lookup"><span data-stu-id="949e3-137">A Canvas administrator can enable Microsoft OneDrive LTI for all courses.</span></span> <span data-ttu-id="949e3-138">Om Microsoft OneDrive LTI krävs i en särskild kurs (och inte i alla kurser), måste kursläraren följa samma steg i kursinställningarna.</span><span class="sxs-lookup"><span data-stu-id="949e3-138">If Microsoft OneDrive LTI is needed in a specific course (and not all courses), the course educator needs to follow the same steps within the course settings.</span></span>

1. <span data-ttu-id="949e3-139">Logga in som administratör och gå till **avsnittet Inställningar** administratör.</span><span class="sxs-lookup"><span data-stu-id="949e3-139">Sign in as an administrator and go to the **Settings** section.</span></span>
2. <span data-ttu-id="949e3-140">Gå till **avsnittet Appar** och välj knappen Visa **appkonfigurationer.**</span><span class="sxs-lookup"><span data-stu-id="949e3-140">Go to the **Apps** section and select the **View App Configurations** button.</span></span>
3. <span data-ttu-id="949e3-141">Välj knappen **Lägg till** app.</span><span class="sxs-lookup"><span data-stu-id="949e3-141">Select the **Add App** button.</span></span>
4. <span data-ttu-id="949e3-142">I **listrutan Konfigurationstyp** väljer du **alternativet Efter klient-ID.**</span><span class="sxs-lookup"><span data-stu-id="949e3-142">In the **Configuration Type** dropdown, choose the **By Client ID** option.</span></span>
5. <span data-ttu-id="949e3-143">Klistra in värdet för utvecklarnyckeln som genererades tidigare i fältet **Klient-ID** och välj **knappen** Skicka.</span><span class="sxs-lookup"><span data-stu-id="949e3-143">Paste the value of the developer key generated previously in the **Client ID** field, and select the **Submit** button.</span></span>

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="Sidan Lägg till app, med alternativet Efter klient-ID under listrutan Konfigurationstyp.":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="949e3-145">Samarbetsfunktioner Inställningar för Microsoft OneDrive LTI i Canvas-kurser</span><span class="sxs-lookup"><span data-stu-id="949e3-145">Collaboration Settings for Microsoft OneDrive LTI in Canvas Courses</span></span>

> [!NOTE]
> <span data-ttu-id="949e3-146">För att samarbete ska fungera för lärare och elever bör du inte aktivera inställningen för samarbete.</span><span class="sxs-lookup"><span data-stu-id="949e3-146">For collaboration to work for educators and students, you shouldn't enable the collaboration setting.</span></span> <span data-ttu-id="949e3-147">Kontrollera att inställningen inte är aktiverad genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="949e3-147">To make sure the setting isn't enabled, follow the steps below.</span></span>

1. <span data-ttu-id="949e3-148">Logga in som administratör och gå till avsnittet **Inställningar** administratör.</span><span class="sxs-lookup"><span data-stu-id="949e3-148">Sign in as an admin and go to the **Settings** section.</span></span>
1. <span data-ttu-id="949e3-149">Gå **till avsnittet Funktionsalternativ** och gå sedan till **avsnittet** Kurs.</span><span class="sxs-lookup"><span data-stu-id="949e3-149">Go to **Feature Options** section, and then go to the **Course** section.</span></span>
1. <span data-ttu-id="949e3-150">Ange att **funktionen Verktyg för externt** samarbete inte ska aktiveras.</span><span class="sxs-lookup"><span data-stu-id="949e3-150">Set the **External Collaborations Tool** feature to be not enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="949e3-151">Samarbete kan tilldelas enskilda elever och grupper av elever.</span><span class="sxs-lookup"><span data-stu-id="949e3-151">Collaboration can be assigned to individual students and to groups of students.</span></span> <span data-ttu-id="949e3-152">Tilldelning till enskilda elever fungerar som standard.</span><span class="sxs-lookup"><span data-stu-id="949e3-152">Assigning to individual students works by default.</span></span> <span data-ttu-id="949e3-153">Följ de här stegen för att kunna tilldela samarbete till en grupp elever:</span><span class="sxs-lookup"><span data-stu-id="949e3-153">To be able to assign collaboration to group of students, follow these steps:</span></span>

1. <span data-ttu-id="949e3-154">Logga in som administratör och gå till **avsnittet Utvecklarnycklar.**</span><span class="sxs-lookup"><span data-stu-id="949e3-154">Login as admin and go to the **Developer Keys** section.</span></span>
1. <span data-ttu-id="949e3-155">Leta reda på nyckeln med värdet 17000000000710 och ställ in den på **På**.</span><span class="sxs-lookup"><span data-stu-id="949e3-155">Find the key with value 170000000000710 and set it to **On**.</span></span>
