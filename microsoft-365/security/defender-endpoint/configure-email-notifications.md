---
title: Konfigurera aviseringsmeddelanden i Microsoft Defender för Slutpunkt
description: Du kan använda Microsoft Defender för Endpoint för att konfigurera inställningar för e-postaviseringar för säkerhetsvarningar, baserat på allvarlighetsgrad och andra villkor.
keywords: e-postaviseringar, konfigurera aviseringsmeddelanden, Microsoft Defender för slutpunkt, Microsoft Defender för slutpunktsaviseringar, windows 10 Enterprise, windows 10 education
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c60bed1fb2cc17c9f5dfbd1289ae5f5b5e13faec
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933955"
---
# <a name="configure-alert-notifications-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="fccd5-104">Konfigurera aviseringsmeddelanden i Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="fccd5-104">Configure alert notifications in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fccd5-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="fccd5-105">**Applies to:**</span></span>
- [<span data-ttu-id="fccd5-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="fccd5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fccd5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fccd5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="fccd5-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="fccd5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fccd5-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="fccd5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-emailconfig-abovefoldlink)

<span data-ttu-id="fccd5-110">Du kan konfigurera Defender för Endpoint så att e-postaviseringar skickas till vissa mottagare för nya aviseringar.</span><span class="sxs-lookup"><span data-stu-id="fccd5-110">You can configure Defender for Endpoint to send email notifications to specified recipients for new alerts.</span></span> <span data-ttu-id="fccd5-111">Med den här funktionen kan du identifiera en grupp personer som omedelbart informeras och kan agera på aviseringar utifrån deras allvarlighetsgrad.</span><span class="sxs-lookup"><span data-stu-id="fccd5-111">This feature enables you to identify a group of individuals who will immediately be informed and can act on alerts based on their severity.</span></span>

> [!NOTE]
> <span data-ttu-id="fccd5-112">Endast användare med behörigheten Hantera säkerhetsinställningar kan konfigurera e-postaviseringar.</span><span class="sxs-lookup"><span data-stu-id="fccd5-112">Only users with 'Manage security settings' permissions can configure email notifications.</span></span> <span data-ttu-id="fccd5-113">Om du har valt att använda grundläggande behörighetshantering kan användare med roller som säkerhetsadministratör eller global administratör konfigurera e-postaviseringar.</span><span class="sxs-lookup"><span data-stu-id="fccd5-113">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications.</span></span>

<span data-ttu-id="fccd5-114">Du kan ange allvarlighetsnivåer för aviseringar som utlöser aviseringar.</span><span class="sxs-lookup"><span data-stu-id="fccd5-114">You can set the alert severity levels that trigger notifications.</span></span> <span data-ttu-id="fccd5-115">Du kan också lägga till eller ta bort mottagare av e-postaviseringen.</span><span class="sxs-lookup"><span data-stu-id="fccd5-115">You can also add or remove recipients of the email notification.</span></span> <span data-ttu-id="fccd5-116">Nya mottagare får ett meddelande om aviseringar som utlöses när de läggs till.</span><span class="sxs-lookup"><span data-stu-id="fccd5-116">New recipients get notified about alerts triggered after they're added.</span></span> <span data-ttu-id="fccd5-117">Mer information om aviseringar finns i [Visa och ordna kön Aviseringar.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="fccd5-117">For more information about alerts, see [View and organize the Alerts queue](alerts-queue.md).</span></span>

<span data-ttu-id="fccd5-118">Om du använder rollbaserad åtkomstkontroll (RBAC) får mottagarna endast meddelanden baserat på enhetsgrupper som har konfigurerats i aviseringsregeln.</span><span class="sxs-lookup"><span data-stu-id="fccd5-118">If you're using role-based access control (RBAC), recipients will only receive notifications based on the device groups that were configured in the notification rule.</span></span>
<span data-ttu-id="fccd5-119">Användare med rätt behörighet kan bara skapa, redigera eller ta bort meddelanden som är begränsade till enhetens grupphanteringsomfång.</span><span class="sxs-lookup"><span data-stu-id="fccd5-119">Users with the proper permission can only create, edit, or delete notifications that are limited to their device group management scope.</span></span>
<span data-ttu-id="fccd5-120">Endast användare som tilldelats rollen Global administratör kan hantera meddelanderegler som är konfigurerade för alla enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="fccd5-120">Only users assigned to the Global administrator role can manage notification rules that are configured for all device groups.</span></span>

<span data-ttu-id="fccd5-121">E-postmeddelandet innehåller grundläggande information om aviseringen och en länk till portalen där du kan undersöka frågan ytterligare.</span><span class="sxs-lookup"><span data-stu-id="fccd5-121">The email notification includes basic information about the alert and a link to the portal where you can do further investigation.</span></span>


## <a name="create-rules-for-alert-notifications"></a><span data-ttu-id="fccd5-122">Skapa regler för aviseringar</span><span class="sxs-lookup"><span data-stu-id="fccd5-122">Create rules for alert notifications</span></span>
<span data-ttu-id="fccd5-123">Du kan skapa regler som bestämmer enheter och allvarlighetsgrad för aviseringar för att skicka e-postaviseringar till och aviseringsmottagarna.</span><span class="sxs-lookup"><span data-stu-id="fccd5-123">You can create rules that determine the devices and alert severities to send email notifications for and the notification recipients.</span></span>


1. <span data-ttu-id="fccd5-124">I navigeringsfönstret väljer du Inställningar  >  **E-postaviseringar**.</span><span class="sxs-lookup"><span data-stu-id="fccd5-124">In the navigation pane, select **Settings** > **Email notifications**.</span></span>

2. <span data-ttu-id="fccd5-125">Klicka **på Lägg till objekt.**</span><span class="sxs-lookup"><span data-stu-id="fccd5-125">Click **Add item**.</span></span>

3. <span data-ttu-id="fccd5-126">Ange allmän information:</span><span class="sxs-lookup"><span data-stu-id="fccd5-126">Specify the General information:</span></span>
    - <span data-ttu-id="fccd5-127">**Regelnamn** – ange ett namn på meddelanderegeln.</span><span class="sxs-lookup"><span data-stu-id="fccd5-127">**Rule name** - Specify a name for the notification rule.</span></span>
    - <span data-ttu-id="fccd5-128">**Ta med organisationsnamn** – Ange kundens namn som visas i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="fccd5-128">**Include organization name** - Specify the customer name that appears on the email notification.</span></span>
    - <span data-ttu-id="fccd5-129">**Inkludera klientspecifik portallänk – Lägger** till en länk med klientorganisations-ID:t för att tillåta åtkomst till en viss klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="fccd5-129">**Include tenant-specific portal link** - Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    - <span data-ttu-id="fccd5-130">**Ta med enhetsinformation** – Innehåller enhetens namn i e-postaviseringstexten.</span><span class="sxs-lookup"><span data-stu-id="fccd5-130">**Include device information** - Includes the device name in the email alert body.</span></span>
    
        >[!NOTE]
        > <span data-ttu-id="fccd5-131">Den här informationen kan bearbetas av mottagarens e-postservrar som inte finns på den geografiska plats som du har valt för Defender för slutpunktsdata.</span><span class="sxs-lookup"><span data-stu-id="fccd5-131">This information might be processed by recipient mail servers that ar not in the geographic location you have selected for your Defender for Endpoint data.</span></span>

    - <span data-ttu-id="fccd5-132">**Enheter** – Välj om du vill meddela mottagare för aviseringar på alla enheter (endast rollen Global administratör) eller för valda enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="fccd5-132">**Devices** - Choose whether to notify recipients for alerts on all devices (Global administrator role only) or on selected device groups.</span></span> <span data-ttu-id="fccd5-133">Mer information finns i Skapa [och hantera enhetsgrupper](machine-groups.md).</span><span class="sxs-lookup"><span data-stu-id="fccd5-133">For more information, see [Create and manage device groups](machine-groups.md).</span></span>
    - <span data-ttu-id="fccd5-134">**Aviserings allvarlighetsgrad** – välj en allvarlighetsnivå för aviseringen.</span><span class="sxs-lookup"><span data-stu-id="fccd5-134">**Alert severity** - Choose the alert severity level.</span></span>

4. <span data-ttu-id="fccd5-135">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="fccd5-135">Click **Next**.</span></span>
    
5. <span data-ttu-id="fccd5-136">Ange mottagarens e-postadress och klicka sedan på **Lägg till mottagare.**</span><span class="sxs-lookup"><span data-stu-id="fccd5-136">Enter the recipient's email address then click **Add recipient**.</span></span> <span data-ttu-id="fccd5-137">Du kan lägga till flera e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="fccd5-137">You can add multiple email addresses.</span></span>

6. <span data-ttu-id="fccd5-138">Kontrollera att e-postmottagarna kan få e-postaviseringar genom att **välja Skicka testmeddelande**.</span><span class="sxs-lookup"><span data-stu-id="fccd5-138">Check that email recipients can receive the email notifications by selecting **Send test email**.</span></span>

7. <span data-ttu-id="fccd5-139">Klicka **på Spara meddelanderegel.**</span><span class="sxs-lookup"><span data-stu-id="fccd5-139">Click **Save notification rule**.</span></span>

## <a name="edit-a-notification-rule"></a><span data-ttu-id="fccd5-140">Redigera en aviseringsregel</span><span class="sxs-lookup"><span data-stu-id="fccd5-140">Edit a notification rule</span></span>
1. <span data-ttu-id="fccd5-141">Välj den aviseringsregel som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="fccd5-141">Select the notification rule you'd like to edit.</span></span>

2. <span data-ttu-id="fccd5-142">Uppdatera informationen på fliken Allmänt och Mottagare.</span><span class="sxs-lookup"><span data-stu-id="fccd5-142">Update the General and Recipient tab information.</span></span>

3. <span data-ttu-id="fccd5-143">Klicka **på Spara meddelanderegel.**</span><span class="sxs-lookup"><span data-stu-id="fccd5-143">Click **Save notification rule**.</span></span>


## <a name="delete-notification-rule"></a><span data-ttu-id="fccd5-144">Ta bort meddelanderegel</span><span class="sxs-lookup"><span data-stu-id="fccd5-144">Delete notification rule</span></span>

1. <span data-ttu-id="fccd5-145">Välj den meddelanderegel som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="fccd5-145">Select the notification rule you'd like to delete.</span></span>

2. <span data-ttu-id="fccd5-146">Klicka på **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="fccd5-146">Click **Delete**.</span></span>


## <a name="troubleshoot-email-notifications-for-alerts"></a><span data-ttu-id="fccd5-147">Felsöka e-postaviseringar för aviseringar</span><span class="sxs-lookup"><span data-stu-id="fccd5-147">Troubleshoot email notifications for alerts</span></span>
<span data-ttu-id="fccd5-148">Det här avsnittet innehåller en lista över olika problem som kan uppstå när du använder e-postaviseringar för aviseringar.</span><span class="sxs-lookup"><span data-stu-id="fccd5-148">This section lists various issues that you may encounter when using email notifications for alerts.</span></span>

<span data-ttu-id="fccd5-149">**Problem:** Avsedd mottagare rapporterar att de inte får aviseringarna.</span><span class="sxs-lookup"><span data-stu-id="fccd5-149">**Problem:** Intended recipients report they're not getting the notifications.</span></span>

<span data-ttu-id="fccd5-150">**Lösning:** Kontrollera att meddelandena inte blockeras av e-postfilter:</span><span class="sxs-lookup"><span data-stu-id="fccd5-150">**Solution:** Make sure that the notifications aren't blocked by email filters:</span></span>

1. <span data-ttu-id="fccd5-151">Kontrollera att Defender för slutpunktens e-postaviseringar inte skickas till mappen Skräppost.</span><span class="sxs-lookup"><span data-stu-id="fccd5-151">Check that the Defender for Endpoint email notifications aren't sent to the Junk Email folder.</span></span> <span data-ttu-id="fccd5-152">Markera dem som Inte skräppost.</span><span class="sxs-lookup"><span data-stu-id="fccd5-152">Mark them as Not junk.</span></span>
2. <span data-ttu-id="fccd5-153">Kontrollera att din e-postsäkerhetsprodukt inte blockerar e-postaviseringarna från Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="fccd5-153">Check that your email security product isn't blocking the email notifications from Defender for Endpoint.</span></span>
3. <span data-ttu-id="fccd5-154">Kontrollera dina e-postprogramsregler som kanske fångar och flyttar din Defender för slutpunkts-e-postaviseringar.</span><span class="sxs-lookup"><span data-stu-id="fccd5-154">Check your email application rules that might be catching and moving your Defender for Endpoint email notifications.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fccd5-155">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="fccd5-155">Related topics</span></span>
- [<span data-ttu-id="fccd5-156">Uppdatera inställningar för datalagring</span><span class="sxs-lookup"><span data-stu-id="fccd5-156">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="fccd5-157">Konfigurera avancerade funktioner</span><span class="sxs-lookup"><span data-stu-id="fccd5-157">Configure advanced features</span></span>](advanced-features.md)
