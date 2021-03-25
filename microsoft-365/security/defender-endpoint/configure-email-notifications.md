---
title: Konfigurera aviseringsmeddelanden i Microsoft Defender för Slutpunkt
description: Du kan använda Microsoft Defender för Endpoint för att konfigurera inställningar för e-postaviseringar för säkerhetsvarningar, baserat på allvarlighetsgrad och andra villkor.
keywords: e-postaviseringar, konfigurera aviseringsmeddelanden, microsoft defender atp-meddelanden, microsoft defender atp-aviseringar, windows 10 enterprise, windows 10 education
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
ms.openlocfilehash: d8b68e6b6dc42de5730aa634386406d4762b1fa2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163689"
---
# <a name="configure-alert-notifications-in-microsoft-defender-atp"></a><span data-ttu-id="5fb55-104">Konfigurera aviseringsmeddelanden i Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="5fb55-104">Configure alert notifications in Microsoft Defender ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5fb55-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="5fb55-105">**Applies to:**</span></span>
- [<span data-ttu-id="5fb55-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="5fb55-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5fb55-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5fb55-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="5fb55-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="5fb55-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5fb55-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="5fb55-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-emailconfig-abovefoldlink)

<span data-ttu-id="5fb55-110">Du kan konfigurera Defender för Endpoint så att e-postaviseringar skickas till vissa mottagare för nya aviseringar.</span><span class="sxs-lookup"><span data-stu-id="5fb55-110">You can configure Defender for Endpoint to send email notifications to specified recipients for new alerts.</span></span> <span data-ttu-id="5fb55-111">Med den här funktionen kan du identifiera en grupp personer som omedelbart informeras och kan agera på aviseringar utifrån deras allvarlighetsgrad.</span><span class="sxs-lookup"><span data-stu-id="5fb55-111">This feature enables you to identify a group of individuals who will immediately be informed and can act on alerts based on their severity.</span></span>

> [!NOTE]
> <span data-ttu-id="5fb55-112">Endast användare med behörigheten Hantera säkerhetsinställningar kan konfigurera e-postaviseringar.</span><span class="sxs-lookup"><span data-stu-id="5fb55-112">Only users with 'Manage security settings' permissions can configure email notifications.</span></span> <span data-ttu-id="5fb55-113">Om du har valt att använda grundläggande behörighetshantering kan användare med roller som säkerhetsadministratör eller global administratör konfigurera e-postaviseringar.</span><span class="sxs-lookup"><span data-stu-id="5fb55-113">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications.</span></span>

<span data-ttu-id="5fb55-114">Du kan ange allvarlighetsnivåer för aviseringar som utlöser aviseringar.</span><span class="sxs-lookup"><span data-stu-id="5fb55-114">You can set the alert severity levels that trigger notifications.</span></span> <span data-ttu-id="5fb55-115">Du kan också lägga till eller ta bort mottagare av e-postaviseringen.</span><span class="sxs-lookup"><span data-stu-id="5fb55-115">You can also add or remove recipients of the email notification.</span></span> <span data-ttu-id="5fb55-116">Nya mottagare får ett meddelande om påträffade aviseringar när de har lagts till.</span><span class="sxs-lookup"><span data-stu-id="5fb55-116">New recipients get notified about alerts encountered after they are added.</span></span> <span data-ttu-id="5fb55-117">Mer information om aviseringar finns i [Visa och ordna kön Aviseringar.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="5fb55-117">For more information about alerts, see [View and organize the Alerts queue](alerts-queue.md).</span></span>

<span data-ttu-id="5fb55-118">Om du använder rollbaserad åtkomstkontroll (RBAC) får mottagarna endast meddelanden baserat på enhetsgrupper som har konfigurerats i aviseringsregeln.</span><span class="sxs-lookup"><span data-stu-id="5fb55-118">If you're using role-based access control (RBAC), recipients will only receive notifications based on the device groups that were configured in the notification rule.</span></span>
<span data-ttu-id="5fb55-119">Användare med rätt behörighet kan bara skapa, redigera eller ta bort meddelanden som är begränsade till enhetens grupphanteringsomfång.</span><span class="sxs-lookup"><span data-stu-id="5fb55-119">Users with the proper permission can only create, edit, or delete notifications that are limited to their device group management scope.</span></span>
<span data-ttu-id="5fb55-120">Endast användare som tilldelats rollen Global administratör kan hantera meddelanderegler som är konfigurerade för alla enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="5fb55-120">Only users assigned to the Global administrator role can manage notification rules that are configured for all device groups.</span></span>

<span data-ttu-id="5fb55-121">E-postmeddelandet innehåller grundläggande information om aviseringen och en länk till portalen där du kan undersöka frågan ytterligare.</span><span class="sxs-lookup"><span data-stu-id="5fb55-121">The email notification includes basic information about the alert and a link to the portal where you can do further investigation.</span></span>


## <a name="create-rules-for-alert-notifications"></a><span data-ttu-id="5fb55-122">Skapa regler för aviseringar</span><span class="sxs-lookup"><span data-stu-id="5fb55-122">Create rules for alert notifications</span></span>
<span data-ttu-id="5fb55-123">Du kan skapa regler som bestämmer enheter och allvarlighetsgrad för aviseringar för att skicka e-postaviseringar till och aviseringsmottagarna.</span><span class="sxs-lookup"><span data-stu-id="5fb55-123">You can create rules that determine the devices and alert severities to send email notifications for and the notification recipients.</span></span>


1. <span data-ttu-id="5fb55-124">Välj Inställningar Aviseringsmeddelanden **i**  >  **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="5fb55-124">In the navigation pane, select **Settings** > **Alert notifications**.</span></span>

2. <span data-ttu-id="5fb55-125">Klicka på **Lägg till aviseringsregel.**</span><span class="sxs-lookup"><span data-stu-id="5fb55-125">Click **Add notification rule**.</span></span>

3. <span data-ttu-id="5fb55-126">Ange allmän information:</span><span class="sxs-lookup"><span data-stu-id="5fb55-126">Specify the General information:</span></span>
    - <span data-ttu-id="5fb55-127">**Regelnamn** – ange ett namn på meddelanderegeln.</span><span class="sxs-lookup"><span data-stu-id="5fb55-127">**Rule name** - Specify a name for the notification rule.</span></span>
    - <span data-ttu-id="5fb55-128">**Ta med organisationsnamn** – Ange kundens namn som visas i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="5fb55-128">**Include organization name** - Specify the customer name that appears on the email notification.</span></span>
    - <span data-ttu-id="5fb55-129">**Inkludera klientspecifik portallänk – Lägger** till en länk med klientorganisations-ID:t för att tillåta åtkomst till en viss klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="5fb55-129">**Include tenant-specific portal link** - Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    - <span data-ttu-id="5fb55-130">**Ta med enhetsinformation** – Innehåller enhetens namn i e-postaviseringstexten.</span><span class="sxs-lookup"><span data-stu-id="5fb55-130">**Include device information** - Includes the device name in the email alert body.</span></span>
    
        >[!NOTE]
        > <span data-ttu-id="5fb55-131">Den här informationen kan bearbetas av mottagarens e-postservrar som inte finns på den geografiska plats som du har valt för Defender för slutpunktsdata.</span><span class="sxs-lookup"><span data-stu-id="5fb55-131">This information might be processed by recipient mail servers that ar not in the geographic location you have selected for your Defender for Endpoint data.</span></span>

    - <span data-ttu-id="5fb55-132">**Enheter** – Välj om du vill meddela mottagare för aviseringar på alla enheter (endast rollen Global administratör) eller för valda enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="5fb55-132">**Devices** - Choose whether to notify recipients for alerts on all devices (Global administrator role only) or on selected device groups.</span></span> <span data-ttu-id="5fb55-133">Mer information finns i Skapa [och hantera enhetsgrupper](machine-groups.md).</span><span class="sxs-lookup"><span data-stu-id="5fb55-133">For more information, see [Create and manage device groups](machine-groups.md).</span></span>
    - <span data-ttu-id="5fb55-134">**Aviserings allvarlighetsgrad** – välj en allvarlighetsnivå för aviseringen.</span><span class="sxs-lookup"><span data-stu-id="5fb55-134">**Alert severity** - Choose the alert severity level.</span></span>

4. <span data-ttu-id="5fb55-135">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="5fb55-135">Click **Next**.</span></span>
    
5. <span data-ttu-id="5fb55-136">Ange mottagarens e-postadress och klicka sedan på **Lägg till mottagare.**</span><span class="sxs-lookup"><span data-stu-id="5fb55-136">Enter the recipient's email address then click **Add recipient**.</span></span> <span data-ttu-id="5fb55-137">Du kan lägga till flera e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="5fb55-137">You can add multiple email addresses.</span></span>

6. <span data-ttu-id="5fb55-138">Kontrollera att e-postmottagarna kan ta emot e-postaviseringar genom att välja **Skicka testmeddelande**.</span><span class="sxs-lookup"><span data-stu-id="5fb55-138">Check that email recipients are able to receive the email notifications by selecting **Send test email**.</span></span>

7. <span data-ttu-id="5fb55-139">Klicka **på Spara meddelanderegel.**</span><span class="sxs-lookup"><span data-stu-id="5fb55-139">Click **Save notification rule**.</span></span>

## <a name="edit-a-notification-rule"></a><span data-ttu-id="5fb55-140">Redigera en aviseringsregel</span><span class="sxs-lookup"><span data-stu-id="5fb55-140">Edit a notification rule</span></span>
1. <span data-ttu-id="5fb55-141">Välj den aviseringsregel som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="5fb55-141">Select the notification rule you'd like to edit.</span></span>

2. <span data-ttu-id="5fb55-142">Uppdatera informationen på fliken Allmänt och Mottagare.</span><span class="sxs-lookup"><span data-stu-id="5fb55-142">Update the General and Recipient tab information.</span></span>

3. <span data-ttu-id="5fb55-143">Klicka **på Spara meddelanderegel.**</span><span class="sxs-lookup"><span data-stu-id="5fb55-143">Click **Save notification rule**.</span></span>


## <a name="delete-notification-rule"></a><span data-ttu-id="5fb55-144">Ta bort meddelanderegel</span><span class="sxs-lookup"><span data-stu-id="5fb55-144">Delete notification rule</span></span>

1. <span data-ttu-id="5fb55-145">Välj den meddelanderegel som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="5fb55-145">Select the notification rule you'd like to delete.</span></span>

2. <span data-ttu-id="5fb55-146">Klicka på **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="5fb55-146">Click **Delete**.</span></span>


## <a name="troubleshoot-email-notifications-for-alerts"></a><span data-ttu-id="5fb55-147">Felsöka e-postaviseringar för aviseringar</span><span class="sxs-lookup"><span data-stu-id="5fb55-147">Troubleshoot email notifications for alerts</span></span>
<span data-ttu-id="5fb55-148">Det här avsnittet innehåller en lista över olika problem som kan uppstå när du använder e-postaviseringar för aviseringar.</span><span class="sxs-lookup"><span data-stu-id="5fb55-148">This section lists various issues that you may encounter when using email notifications for alerts.</span></span>

<span data-ttu-id="5fb55-149">**Problem:** Avsedd mottagare rapporterar att de inte får aviseringarna.</span><span class="sxs-lookup"><span data-stu-id="5fb55-149">**Problem:** Intended recipients report they are not getting the notifications.</span></span>

<span data-ttu-id="5fb55-150">**Lösning:** Kontrollera att meddelandena inte blockeras av e-postfilter:</span><span class="sxs-lookup"><span data-stu-id="5fb55-150">**Solution:** Make sure that the notifications are not blocked by email filters:</span></span>

1. <span data-ttu-id="5fb55-151">Kontrollera att Defender för slutpunktens e-postaviseringar inte skickas till mappen Skräppost.</span><span class="sxs-lookup"><span data-stu-id="5fb55-151">Check that the Defender for Endpoint email notifications are not sent to the Junk Email folder.</span></span> <span data-ttu-id="5fb55-152">Markera dem som Inte skräppost.</span><span class="sxs-lookup"><span data-stu-id="5fb55-152">Mark them as Not junk.</span></span>
2. <span data-ttu-id="5fb55-153">Kontrollera att e-postsäkerhetsprodukten inte blockerar e-postaviseringarna från Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="5fb55-153">Check that your email security product is not blocking the email notifications from Defender for Endpoint.</span></span>
3. <span data-ttu-id="5fb55-154">Kontrollera dina e-postprogramsregler som kanske fångar och flyttar din Defender för slutpunkts-e-postaviseringar.</span><span class="sxs-lookup"><span data-stu-id="5fb55-154">Check your email application rules that might be catching and moving your Defender for Endpoint email notifications.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5fb55-155">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="5fb55-155">Related topics</span></span>
- [<span data-ttu-id="5fb55-156">Uppdatera inställningar för datalagring</span><span class="sxs-lookup"><span data-stu-id="5fb55-156">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="5fb55-157">Konfigurera avancerade funktioner</span><span class="sxs-lookup"><span data-stu-id="5fb55-157">Configure advanced features</span></span>](advanced-features.md)
