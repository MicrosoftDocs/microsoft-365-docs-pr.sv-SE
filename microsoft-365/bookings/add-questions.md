---
title: Lägg till anpassade och nödvändiga frågor till bokningssidan
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: fd6b7587-5055-4bcd-83a4-13bd4929bfff
description: Om du behöver ställa frågor till kunderna när de bokar ett möte med dig online kan du lägga till anpassade frågor och obligatoriska frågor på bokningssidan.
ms.openlocfilehash: ebbb07857fd8bb196f769dfb7e71ad25a85dfd54
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/09/2020
ms.locfileid: "47420272"
---
# <a name="add-custom-and-required-questions-to-the-booking-page"></a><span data-ttu-id="c1525-103">Lägg till anpassade och nödvändiga frågor till bokningssidan</span><span class="sxs-lookup"><span data-stu-id="c1525-103">Add custom and required questions to the booking page</span></span>

<span data-ttu-id="c1525-104">Med Bookings kan du skapa frågor för att ställa dina kunder när de gör bokningsbokningar.</span><span class="sxs-lookup"><span data-stu-id="c1525-104">Bookings lets you create questions to ask your customers when they are booking appointments.</span></span> <span data-ttu-id="c1525-105">Du kan också välja vilka frågor som krävs.</span><span class="sxs-lookup"><span data-stu-id="c1525-105">It also lets you choose which questions are required.</span></span>

<span data-ttu-id="c1525-106">Du kopplar frågorna till en tjänst, så att varje tjänst kan ha olika uppsättning frågor.</span><span class="sxs-lookup"><span data-stu-id="c1525-106">You associate the questions with a service, so each service can have a different set of questions.</span></span> <span data-ttu-id="c1525-107">En hårstylt kan exempelvis fråga kunder som bokar en avtalad tid med hårfärg om de har kända allergier på nyanser eller utserer.</span><span class="sxs-lookup"><span data-stu-id="c1525-107">For example, a hair stylist may ask customers who are booking a hair coloring appointment if they have any known allergies to bleaches or tints.</span></span> <span data-ttu-id="c1525-108">På så sätt kan du och dina kunder spara tid när de kommer till den avtalade tiden.</span><span class="sxs-lookup"><span data-stu-id="c1525-108">This allows you and your customers to save time when they arrive for their appointment.</span></span>

<span data-ttu-id="c1525-109">Kunderna kommer att se de anpassade frågorna när de skapar sin avtalade tid på bokningssidan.</span><span class="sxs-lookup"><span data-stu-id="c1525-109">The customers will see the custom questions when they are creating their appointment on the booking page.</span></span> <span data-ttu-id="c1525-110">Personalen kommer att se de anpassade frågorna när de skapar en ny bokning från Bookings-kalendern eller när de visar en befintlig avtalad tid.</span><span class="sxs-lookup"><span data-stu-id="c1525-110">Staff will see the custom questions when they create a new booking from the Bookings calendar or when viewing an existing appointment.</span></span> <span data-ttu-id="c1525-111">Bookings sparar alla dina frågor i en huvudlista så att du inte behöver skapa samma frågor för varje tjänst på nytt.</span><span class="sxs-lookup"><span data-stu-id="c1525-111">Bookings saves all of your questions to a master list so that you don't have to re-create the same questions for every service.</span></span> <span data-ttu-id="c1525-112">Du kan också välja om frågor krävs eller är valfria.</span><span class="sxs-lookup"><span data-stu-id="c1525-112">You can also choose whether questions are required or optional.</span></span>

> [!NOTE]
> <span data-ttu-id="c1525-113">Du ser kundens svar på frågorna när du tittar på deras avtalade tid i bokningskalendern.</span><span class="sxs-lookup"><span data-stu-id="c1525-113">The customer's answers to the questions can be seen when you look at their appointment in the booking calendar.</span></span>

<span data-ttu-id="c1525-114">Mer information om hur du anpassar och anpassar din bokningssida finns på [Anpassa din bokningssida.](customize-booking-page.md)</span><span class="sxs-lookup"><span data-stu-id="c1525-114">For more information about how to personalize and customize your booking page, see [Customize your booking page](customize-booking-page.md).</span></span>

## <a name="add-custom-questions-to-your-services"></a><span data-ttu-id="c1525-115">Lägga till anpassade frågor till dina tjänster</span><span class="sxs-lookup"><span data-stu-id="c1525-115">Add custom questions to your services</span></span>

1. <span data-ttu-id="c1525-116">Logga in på Microsoft 365 och gå till **Bookings.**</span><span class="sxs-lookup"><span data-stu-id="c1525-116">Sign in to Microsoft 365 and go to **Bookings**.</span></span>

1. <span data-ttu-id="c1525-117">Gå till **Tjänster och** redigera en befintlig tjänst eller Lägg till **en tjänst.**</span><span class="sxs-lookup"><span data-stu-id="c1525-117">Go to **Services** and either edit an existing service or **Add a service**.</span></span>

1. <span data-ttu-id="c1525-118">Rulla ned till **avsnittet Anpassade** fält och välj sedan **Ändra**.</span><span class="sxs-lookup"><span data-stu-id="c1525-118">Scroll down to the **Custom fields** section, and then select **Modify**.</span></span>

   <span data-ttu-id="c1525-119">Vi har redan lagt till några grundläggande frågor om kundinformation: e-post, telefonnummer, kundadress och kundanteckningar.</span><span class="sxs-lookup"><span data-stu-id="c1525-119">We already added some basic customer information questions: Customer email, phone number, customer address, and customer notes.</span></span> <span data-ttu-id="c1525-120">Första gången du gör detta markeras frågorna om kundinformation i grått.</span><span class="sxs-lookup"><span data-stu-id="c1525-120">The first time you do this, the customer information questions are highlighted in gray.</span></span> <span data-ttu-id="c1525-121">Det innebär att användaren kommer att se den här frågan.</span><span class="sxs-lookup"><span data-stu-id="c1525-121">That means that the user will see this question.</span></span> <span data-ttu-id="c1525-122">Om du väljer frågan försvinner markeringsrutan runt den och kunden kommer inte att tillfrågas om den frågan.</span><span class="sxs-lookup"><span data-stu-id="c1525-122">If you select the question, the highlight box around it will disappear and your customer won't be asked that question.</span></span>

   <span data-ttu-id="c1525-123">I det här exemplet har telefonnummer och kundanteckningar inaktiverats och vi har skapat två nya anpassade frågor att ställa.</span><span class="sxs-lookup"><span data-stu-id="c1525-123">In this example, phone number and customer notes have been turned off and we created two new custom questions to ask.</span></span>

   ![Bild på skärmen anpassade frågor](../media/bookings-questions-custom-fields.png)

1. <span data-ttu-id="c1525-125">För att göra frågan obligatorisk markerar du **kryssrutan** Obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="c1525-125">To make the question required, select the **Required** checkbox.</span></span> <span data-ttu-id="c1525-126">Kunden kan inte slutföra boknings efter att han eller hon har besvarat de frågor som krävs.</span><span class="sxs-lookup"><span data-stu-id="c1525-126">Your customer won't be able to complete the booking until they've answered the required questions.</span></span>

1. <span data-ttu-id="c1525-127">Om du vill skapa en anpassad fråga **väljer du Lägg till** en fråga högst upp i panelen.</span><span class="sxs-lookup"><span data-stu-id="c1525-127">To create a custom question, select **Add a question** from the top of the panel.</span></span> <span data-ttu-id="c1525-128">Skriv din fråga och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c1525-128">Write your question, and then select **Save**.</span></span>

1. <span data-ttu-id="c1525-129">Aktivera frågan genom att klicka på den.</span><span class="sxs-lookup"><span data-stu-id="c1525-129">Click on the question to enable it.</span></span> <span data-ttu-id="c1525-130">En markerad ruta visas runt den och frågan aktiveras.</span><span class="sxs-lookup"><span data-stu-id="c1525-130">A highlighted box appears around it and the question is enabled.</span></span>

1. <span data-ttu-id="c1525-131">Klicka **på** OK högst upp på sidan och sedan **på Spara tjänsten.**</span><span class="sxs-lookup"><span data-stu-id="c1525-131">Click **Ok** at the top of the page, and then **Save the service**.</span></span>

<span data-ttu-id="c1525-132">Bookings sparar alla dina anpassade frågor i en huvudlista så att du enkelt kan lägga till frågor till varje tjänst utan att behöva ange samma frågor flera gånger.</span><span class="sxs-lookup"><span data-stu-id="c1525-132">Bookings will save all of your custom questions in a master list so that you can easily add questions to each service without needing to repeatedly type the same questions.</span></span> <span data-ttu-id="c1525-133">Om du till exempel öppnar en annan tjänst, visas frågan du skapade för den första tjänsten i avsnittet Anpassade fält, men det vill sig vara inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="c1525-133">For example, if you open a different service, the question you created for the first service will show in the Custom fields section, but it wil be disabled.</span></span> <span data-ttu-id="c1525-134">Klicka på frågan så att en markerad rektangel visas och frågan aktiveras.</span><span class="sxs-lookup"><span data-stu-id="c1525-134">Click the question so that a highlighted rectangle displays and the question is enabled.</span></span>

<span data-ttu-id="c1525-135">I det här exemplet kan du se att frågorna som har lagts till för den första tjänsten är tillgängliga för den här tjänsten.</span><span class="sxs-lookup"><span data-stu-id="c1525-135">In this example, you can see that the questions that were added for the first service are available for this service.</span></span> <span data-ttu-id="c1525-136">Alla frågor som du skapar för den här tjänsten blir tillgängliga för alla tjänster.</span><span class="sxs-lookup"><span data-stu-id="c1525-136">Any questions you create for this service will be available for all services.</span></span>

   ![Bild av frågor som visas för flera tjänster](../media/bookings-questions-services.png)

<span data-ttu-id="c1525-138">Om din bokningssida redan är publicerad behöver du inte göra något mer.</span><span class="sxs-lookup"><span data-stu-id="c1525-138">If your booking page is already published, you don't need to do anything else.</span></span> <span data-ttu-id="c1525-139">Kunderna kommer att se frågorna nästa gång de bokar in dig.</span><span class="sxs-lookup"><span data-stu-id="c1525-139">Customers will see the questions the next time they book with you.</span></span> <span data-ttu-id="c1525-140">Om din bokningssida inte har publicerats än går du till bokningssidan från sidan Outlook på webben och väljer **Spara och publicera.** </span><span class="sxs-lookup"><span data-stu-id="c1525-140">If your booking page isn't published yet, go to the **booking page** from Outlook on the web, and then select **Save and publish**.</span></span>

> [!WARNING]
> <span data-ttu-id="c1525-141">Du kan också ta bort frågor från huvudlistan.</span><span class="sxs-lookup"><span data-stu-id="c1525-141">You can also delete questions from the master list.</span></span> <span data-ttu-id="c1525-142">Men om du tar bort en fråga tas den bort från alla tjänster.</span><span class="sxs-lookup"><span data-stu-id="c1525-142">However, if you delete a question it will be deleted from every service.</span></span> <span data-ttu-id="c1525-143">Vi rekommenderar att du inaktiverar frågan genom att välja den för att säkerställa att du inte påverkar några andra tjänster.</span><span class="sxs-lookup"><span data-stu-id="c1525-143">We recommend that you disable the question by selecting it to ensure you do not impact any other services.</span></span> <span data-ttu-id="c1525-144">Du kan se att en fråga är inaktiverad om den inte omges av en markerad rektangel.</span><span class="sxs-lookup"><span data-stu-id="c1525-144">You can see that a question is disabled if it is not surrounded by a highlighted rectangle.</span></span>

## <a name="customer-experience"></a><span data-ttu-id="c1525-145">Kundupplevelse</span><span class="sxs-lookup"><span data-stu-id="c1525-145">Customer experience</span></span>

<span data-ttu-id="c1525-146">När dina kunder bokar en tid med dig visas frågor om grundläggande kundinformation i **avsnittet Lägg till information.**</span><span class="sxs-lookup"><span data-stu-id="c1525-146">When your customers book an appointment with you, the basic customer information questions will show in the **Add your details** section.</span></span> <span data-ttu-id="c1525-147">Alla anpassade frågor som du lägger till finns **i avsnittet Ange ytterligare information.**</span><span class="sxs-lookup"><span data-stu-id="c1525-147">Any customized questions you add will be in the **Provide additional information** section.</span></span>

![Bild av vad kunder ser när frågor aktiveras](../media/bookings-questions-customer.png)

## <a name="staff-experience"></a><span data-ttu-id="c1525-149">Personalupplevelse</span><span class="sxs-lookup"><span data-stu-id="c1525-149">Staff experience</span></span>

<span data-ttu-id="c1525-150">När dina kunder bokar ett möte med dig ser din personal frågorna och kundens svar i bokningskalendern.</span><span class="sxs-lookup"><span data-stu-id="c1525-150">When your customers book an appointment with you, your staff will see the questions and the customer's answers on the booking calendar.</span></span> <span data-ttu-id="c1525-151">Du visar den  genom att gå till \> **Bookings-kalendern och** sedan öppna en avtalad tid.</span><span class="sxs-lookup"><span data-stu-id="c1525-151">To see it, go to **Bookings** \> **Calendar** and then open an appointment.</span></span>

![Bild av vad personalen ser när frågor aktiveras](../media/bookings-questions-staff.png)
