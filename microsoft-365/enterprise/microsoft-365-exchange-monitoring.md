---
title: Exchange Online-övervakning för Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: Använd Exchange Online-övervakning för information om e-postincidenter eller rekommendationer i Microsoft 365.
ms.openlocfilehash: 53dc7f990f57fd8d4da68bd424947676cbf0e85d
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572907"
---
# <a name="exchange-online-monitoring-for-microsoft-365"></a><span data-ttu-id="7469e-103">Exchange Online-övervakning för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7469e-103">Exchange Online monitoring for Microsoft 365</span></span>

<span data-ttu-id="7469e-104">Du kan använda Exchange Online-övervakning i Administrationscentret för Microsoft 365 till att övervaka hälsan för Exchange-tjänsten för din organisations Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="7469e-104">You can use Exchange Online monitoring in the Microsoft 365 admin center to monitor the health of the Exchange service for your organization’s Microsoft 365 subscription.</span></span> <span data-ttu-id="7469e-105">I Exchange Online-övervakningen finns information om incidenter och rekommendationer som samlas in i följande kategorier:</span><span class="sxs-lookup"><span data-stu-id="7469e-105">Exchange Online monitoring provides you with information about incidents and advisories that are collected in these categories:</span></span>

- <span data-ttu-id="7469e-106">**Infrastruktur**: Ett problem identifieras i Microsoft 365-infrastrukturen som Microsoft äger för att ge regelbundna uppdateringar och lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="7469e-106">**Infrastructure**: Issue is detected in the Microsoft 365 infrastructure that Microsoft owns for providing regular updates and resolving the issue.</span></span> <span data-ttu-id="7469e-107">Till exempel kan användarna inte få åtkomst till Exchange Online på grund av problem med Exchange eller annan molninfrastruktur för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7469e-107">For example, users cannot access Exchange Online because of issues with Exchange or other Microsoft 365 cloud infrastructure.</span></span>
- <span data-ttu-id="7469e-108">**Tredje parts infrastruktur**: Ett problem identifieras i tredje parts infrastruktur som din organisation är beroende av och det krävs åtgärder från din organisation för att lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="7469e-108">**Third-party infrastructure**: Issue is detected in third-party infrastructure on which your organization has taken a dependency and requires action from your organization for resolution.</span></span> <span data-ttu-id="7469e-109">Till exempel kan användarautentiserings transaktioner begränsas av en tredjepartsleverantör av säkerhetstokentjänster (STS), vilket hindrar användare från att ansluta till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7469e-109">For example, user authentication transactions are getting throttled by a third-party security token service (STS) provider that prevents users from connecting to Exchange Online.</span></span>
- <span data-ttu-id="7469e-110">**Kundinfrastruktur**: Ett problem identifieras i din organisations infrastruktur och det krävs åtgärder från din organisation för att lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="7469e-110">**Customer infrastructure**: Issue is detected in your organization's infrastructure and requires action from your organization for resolution.</span></span> <span data-ttu-id="7469e-111">Till exempel kan användare inte få åtkomst till Exchange Online eftersom de inte kan få en autentiseringstoken från STS-leverantören som finns i din organisation, på grund av ett utgånget certifikat.</span><span class="sxs-lookup"><span data-stu-id="7469e-111">For example, users cannot access Exchange Online because they are unable to obtain an authentication token from STS provider hosted by your organization because of an expired certificate.</span></span>

<span data-ttu-id="7469e-112">Här är ett exempel på sidan **Tjänststatus** i Administrationscentret för Microsoft 365, tillgänglig från **Hälsa > Tjänststatus**.</span><span class="sxs-lookup"><span data-stu-id="7469e-112">Here is an example of the **Service health** page in the Microsoft 365 admin center, available from **Health > Service health**.</span></span>

![Sidan Tjänststatus i administrationscentret för Microsoft 365](../media/microsoft-365-exchange-monitoring/service-health-dashboard-example.png)

<span data-ttu-id="7469e-114">Värdet i kolumnen **Status** anger om tjänsten är felfri eller om det finns rekommendationer eller incidenter baserat på de molntjänster som Microsoft underhåller.</span><span class="sxs-lookup"><span data-stu-id="7469e-114">The value of the **Status** column indicates whether the service is healthy or has advisories or incidents based on the cloud services that Microsoft maintains.</span></span> 

<span data-ttu-id="7469e-115">Värdet i kolumnen **Organisations- och tredjepartsproblem** anger att organisationens infrastruktur eller programvara från tredje part påverkar tjänststatusens användning i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7469e-115">The value of the **Your org and 3rd party issues** column indicates that your organization's infrastructure or third-party software affects your users service health experience with Exchange Online.</span></span> <span data-ttu-id="7469e-116">Vid rekommendationer och incidenter krävs åtgärder *från dig* för att lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="7469e-116">Advisories or incidents require *your* actions to resolve.</span></span>

<span data-ttu-id="7469e-117">Här är ett exempel på sidan för **Exchange Online**-övervakning i Administrationscentret för Microsoft 365, tillgängligt från **Hälsa > Tjänststatus > Exchange Online**.</span><span class="sxs-lookup"><span data-stu-id="7469e-117">Here is an example of the **Exchange Online** monitoring page in the Microsoft 365 admin center, available from **Health > Service health > Exchange Online**.</span></span>

![Sidan för Exchange Online-övervakning i Administrationscentret för Microsoft 365](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example.png)

<span data-ttu-id="7469e-119">Med sidan för **Exchange Online**-övervakning kan du se om Exchange Online-tjänsten är felfri eller inte, och om det finns några associerade incidenter eller rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="7469e-119">With the **Exchange Online** monitoring page, you can see whether the Exchange Online service is healthy or not and whether there are any associated incidents or advisories.</span></span> <span data-ttu-id="7469e-120">Med Exchange Online-övervakning kan du titta på tjänststatusen för specifika e-postscenarier och se signaler nästan i realtid för att avgöra effekten efter scenario.</span><span class="sxs-lookup"><span data-stu-id="7469e-120">With Exchange Online monitoring, you can look at the service health for specific email scenarios and view near real-time signals to determine the impact by scenario.</span></span> 

## <a name="requirements"></a><span data-ttu-id="7469e-121">Krav</span><span class="sxs-lookup"><span data-stu-id="7469e-121">Requirements</span></span>

<span data-ttu-id="7469e-122">Den här förhandsversionen är aktiverad för kunder som uppfyller följande krav:</span><span class="sxs-lookup"><span data-stu-id="7469e-122">This preview is enabled for customers who meet these requirements:</span></span> 

- <span data-ttu-id="7469e-123">Din organisation måste ha ett licensantal på minst 10 000, med en eller en kombination av dessa produkter: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="7469e-123">Your organization needs to have a license count of at least 10,000, from one or a combination of these products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> 

  <span data-ttu-id="7469e-124">Din organisation kan t. ex. ha 3 000 Office 365 E3-licenser och 8 500 Microsoft 365 E5, för totalt 11 500 licenser för de kvalificerande produkterna.</span><span class="sxs-lookup"><span data-stu-id="7469e-124">For example, your organization can have 3,000 Office 365 E3 licenses and 8,500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>

- <span data-ttu-id="7469e-125">Din organisation måste ha minst 50 månatliga aktiva Exchange Online-användare.</span><span class="sxs-lookup"><span data-stu-id="7469e-125">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

<span data-ttu-id="7469e-126">Med Exchange Online-övervakning kan du visa hälsan för följande e-postklienter baserat på läsaktiviteten för e-post:</span><span class="sxs-lookup"><span data-stu-id="7469e-126">With Exchange Online monitoring you can view the health for the following email clients based on email read activity:</span></span>

- <span data-ttu-id="7469e-127">Outlook (skrivbordsversion)</span><span class="sxs-lookup"><span data-stu-id="7469e-127">Outlook Desktop</span></span>
- <span data-ttu-id="7469e-128">Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="7469e-128">Outlook on the Web</span></span>
- <span data-ttu-id="7469e-129">Inbyggda e-postklienter för iOS och Android</span><span class="sxs-lookup"><span data-stu-id="7469e-129">Native mail clients of iOS and Android</span></span> 
- <span data-ttu-id="7469e-130">Outlook Mobile-app på iOS och Android</span><span class="sxs-lookup"><span data-stu-id="7469e-130">Outlook Mobile app in iOS and Android</span></span> 
- <span data-ttu-id="7469e-131">Outlook Mac-klient</span><span class="sxs-lookup"><span data-stu-id="7469e-131">Outlook Mac client</span></span>

<span data-ttu-id="7469e-132">För dessa klienter kan du se antalet aktiva användare under de senaste 30 minuterna baserat på användare som läser ett e-postmeddelande, samt antalet incidenter och rekommendationer på instrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="7469e-132">For these clients, you can see the number of active users in the last 30 minutes based on users reading an email, along with number of incidents and advisories in the dashboard.</span></span> <span data-ttu-id="7469e-133">Dessa data jämförs med samma intervall för föregående vecka för att se om det finns ett problem.</span><span class="sxs-lookup"><span data-stu-id="7469e-133">This data is compared to the same interval for the previous week to see if there’s an issue.</span></span> 

>[!Note]
> <span data-ttu-id="7469e-134">Antalet aktiva användare mäts med en enskild aktivitet, till exempel när en användare läser ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="7469e-134">Active user count is measured by a single activity, for example, when a user reads an email.</span></span> <span data-ttu-id="7469e-135">Den redovisar bara de senaste 30 minuternas aktivitet.</span><span class="sxs-lookup"><span data-stu-id="7469e-135">It only accounts for the last 30 minutes of activity.</span></span>
>

<span data-ttu-id="7469e-136">Du kan också övervaka Exchange Online-hälsan för följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="7469e-136">You can also monitor Exchange Online health for the following scenarios:</span></span>

- <span data-ttu-id="7469e-137">**E-postflöde**: Antalet meddelanden som skickas till en postlåda utan fördröjning när meddelandet kommit till Microsoft 365-nätverket.</span><span class="sxs-lookup"><span data-stu-id="7469e-137">**Mail flow**: The number of messages successfully delivered to a mailbox without any delay after the message reached the Microsoft 365 network.</span></span> 
- <span data-ttu-id="7469e-138">**Grundläggande autentisering och modern autentisering**: Antalet användare som har verifierats i Exchange Online-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="7469e-138">**Basic Authentication and Modern Authentication**: The number of users successfully validated in the Exchange Online service.</span></span>

![Ett exempel på övervakning av Exchange-hälsan för e-postleverans](../media/microsoft-365-exchange-monitoring/exhange-monitoring-scenario-example.png)

<span data-ttu-id="7469e-140">För alla de här scenarierna gäller nyckeltalen för de senaste 30 minuterna på huvudinstrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="7469e-140">For all these scenarios, the key numbers are for the last 30 minutes in the main dashboard.</span></span> <span data-ttu-id="7469e-141">Detaljerade vyer för vart och ett av dessa scenarier visar trenden nästan i realtid för sju dagar med 30 minuters aggregerade jämfört med föregående vecka.</span><span class="sxs-lookup"><span data-stu-id="7469e-141">Detailed views for each of these scenarios shows the near real-time trend for seven days with the 30-minute aggregate compared with the previous week.</span></span> 

## <a name="send-us-feedback"></a><span data-ttu-id="7469e-142">Skicka feedback</span><span class="sxs-lookup"><span data-stu-id="7469e-142">Send us feedback</span></span>

<span data-ttu-id="7469e-143">Du kan lämna feedback på två sätt:</span><span class="sxs-lookup"><span data-stu-id="7469e-143">There are two ways you can provide feedback:</span></span>

- <span data-ttu-id="7469e-144">Använd alternativet **Ge feedback** som finns på varje sida i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7469e-144">Use the **Give feedback** option available on every page of the Microsoft 365 admin center.</span></span>
- <span data-ttu-id="7469e-145">Skicka feedback med länken **Är det här inlägget användbart?** för en särskild incident eller rekommendation.</span><span class="sxs-lookup"><span data-stu-id="7469e-145">Submit feedback using the **Is this post helpful?** link for a specific incident or advisory.</span></span>

![Länken ”Är det här inlägget användbart?”](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example-incident-feedback.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="7469e-148">Vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="7469e-148">Frequently asked questions</span></span>

#### <a name="1-why-dont-i-see-exchange-online-monitoring-under-health-in-the-microsoft-365-admin-center"></a><span data-ttu-id="7469e-149">1. Varför ser jag inte ”Exchange Online-övervakning” under Hälsa i Administrationscentret för Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="7469e-149">1. Why don’t I see “Exchange Online monitoring” under Health in the Microsoft 365 admin center?</span></span> 

<span data-ttu-id="7469e-150">Kontrollera först att du har aktiverat det nya Administrationscentret på **Startsidan** i Administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7469e-150">First, make sure you’ve enabled the new admin center on the **Home** page of the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="7469e-151">Kontrollera sedan att du uppfyller båda följande krav:</span><span class="sxs-lookup"><span data-stu-id="7469e-151">Then make sure you meet both of the following requirements:</span></span> 

- <span data-ttu-id="7469e-152">Din organisation måste ha ett licensantal på minst 10 000, med en eller en kombination av dessa produkter: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="7469e-152">Your organization needs to have a license count of at least 10,000, from one or a combination of these products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> 
- <span data-ttu-id="7469e-153">Din organisation måste ha minst 50 månatliga aktiva Exchange Online-användare.</span><span class="sxs-lookup"><span data-stu-id="7469e-153">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

<span data-ttu-id="7469e-154">Om licensantalet för din organisation understiger 10 000 användare och antalet månatliga aktiva användare hamnar under 50 användare aktiveras inte Exchange Online-övervakning förrän dessa kraven uppfyllts.</span><span class="sxs-lookup"><span data-stu-id="7469e-154">If the license count for your organization goes below 10,000 users and the monthly active users goes below 50 users, Exchange Online monitoring won’t be enabled until these requirements are met.</span></span>

#### <a name="2-the-active-user-count-in-the-dashboard-for-each-client-appears-to-be-low-we-have-a-lot-of-active-licenses-assigned-to-users-what-does-this-mean"></a><span data-ttu-id="7469e-155">2. Antalet aktiva användare på instrumentpanelen för varje klient verkar vara lågt.</span><span class="sxs-lookup"><span data-stu-id="7469e-155">2. The active user count in the dashboard for each client appears to be low.</span></span> <span data-ttu-id="7469e-156">Vi har många aktiva licenser tilldelade till användare.</span><span class="sxs-lookup"><span data-stu-id="7469e-156">We have a lot of active licenses assigned to users.</span></span> <span data-ttu-id="7469e-157">Vad betyder det här?</span><span class="sxs-lookup"><span data-stu-id="7469e-157">What does this mean?</span></span> 

<span data-ttu-id="7469e-158">Antalet aktiva användare som visas i övervakningen baseras på en 30-minutersperiod där användare har utfört aktiviteten som anges i funktionen.</span><span class="sxs-lookup"><span data-stu-id="7469e-158">The active user count shown in monitoring is based on a 30-minute window where users have performed the activity called out in the feature.</span></span> <span data-ttu-id="7469e-159">Det här ska inte förväxlas med användningstal.</span><span class="sxs-lookup"><span data-stu-id="7469e-159">This shouldn’t be confused with usage numbers.</span></span> <span data-ttu-id="7469e-160">Använd aktivitetsrapporter i Administrationscentret för Microsoft 365 (**Rapporter > Användning**) för att visa användningstal.</span><span class="sxs-lookup"><span data-stu-id="7469e-160">To view usage numbers, use activity reports in the Microsoft 365 admin center (**Reports > Usage**).</span></span>

#### <a name="3-will-there-be-other-monitoring-scenarios-for-other-services-such-as-teams-and-sharepoint"></a><span data-ttu-id="7469e-161">3. Kommer det att finnas andra övervakningsscenarier för andra tjänster, till exempel Teams och SharePoint?</span><span class="sxs-lookup"><span data-stu-id="7469e-161">3. Will there be other monitoring scenarios for other services such as Teams and SharePoint?</span></span> 

<span data-ttu-id="7469e-162">Microsoft har integrerat den här funktionen direkt i instrumentpanelen för tjänststatus i Administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7469e-162">Microsoft is integrating this experience directly inside the Service Health dashboard in the Microsoft 365 admin center.</span></span> <span data-ttu-id="7469e-163">Detta ger Microsoft möjlighet att utöka övervakningsscenarier för andra tjänster, som kommer att meddelas när det finns nyheter att dela.</span><span class="sxs-lookup"><span data-stu-id="7469e-163">This will provide opportunities for Microsoft to extend monitoring scenarios for other services, which will be announced when there is news to share.</span></span> 

#### <a name="4-what-is-the-plan-for-general-availability-of-this-experience"></a><span data-ttu-id="7469e-164">4. Vad är planen för att få allmän tillgänglighet för den här funktionen?</span><span class="sxs-lookup"><span data-stu-id="7469e-164">4. What is the plan for general availability of this experience?</span></span> 

<span data-ttu-id="7469e-165">Microsoft har integrerat Exchange Online-övervakning direkt på **Tjänststatus**-instrumentpanelen i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7469e-165">Microsoft has integrated Exchange Online monitoring directly on the **Service Health** dashboard in the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="7469e-166">Med den här nya integrerade funktionen är Microsofts plan att samla in din feedback och sedan definiera vår plan för allmän tillgänglighet.</span><span class="sxs-lookup"><span data-stu-id="7469e-166">With this new integrated experience, Microsoft's plan is to collect your feedback and then define our plan for general availability.</span></span>

#### <a name="5-is-this-a-free-included-or-paid-extra-feature"></a><span data-ttu-id="7469e-167">5. Är det här en kostnadsfri (inkluderad) eller betald (extra) funktion?</span><span class="sxs-lookup"><span data-stu-id="7469e-167">5. Is this a free (included) or paid (extra) feature?</span></span> 

<span data-ttu-id="7469e-168">Den här funktionen är en allmänt tillgänglig förhandsversion och är bara tillgänglig för kunder som uppfyller kraven i fråga 1.</span><span class="sxs-lookup"><span data-stu-id="7469e-168">This feature is in Public preview and only available for customers that meet the requirements in question 1.</span></span>

<!--
>[!Note]
>INTERNAL: That decision is pending
>
--> 

#### <a name="6-how-do-i-provide-feedback"></a><span data-ttu-id="7469e-169">6. Hur ger jag feedback?</span><span class="sxs-lookup"><span data-stu-id="7469e-169">6. How do I provide feedback?</span></span> 

<span data-ttu-id="7469e-170">Om du vill lämna allmän feedback kan du använda ikonen **Ge feedback** längst ned till höger på sidan för **Exchange Online**-övervakning.</span><span class="sxs-lookup"><span data-stu-id="7469e-170">For general feedback, use the **Give feedback** icon on the bottom-right corner of the **Exchange Online** monitoring page.</span></span> 

<span data-ttu-id="7469e-171">För att lämna feedback om incidenter eller rekommendationer använder du länken **Är det här inlägget användbart?**.</span><span class="sxs-lookup"><span data-stu-id="7469e-171">For feedback on incidents or advisories, use the **Is this post helpful?** link.</span></span>

#### <a name="7-where-is-the-data-instrumented-for-the-scenarios-that-show-activity-trends"></a><span data-ttu-id="7469e-172">7. Var är data instrumenterad för de scenarier som visar aktivitetstrender?</span><span class="sxs-lookup"><span data-stu-id="7469e-172">7. Where is the data instrumented for the scenarios that show activity trends?</span></span>

<span data-ttu-id="7469e-173">Data är instrumenterade i Exchange Online-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="7469e-173">The data is instrumented in the Exchange Online service.</span></span> <span data-ttu-id="7469e-174">Om det finns ett fel som uppstår innan begäran når Exchange Online eller om det finns ett fel i Exchange Online ser du en nedgång i aktivitetssignalen.</span><span class="sxs-lookup"><span data-stu-id="7469e-174">If there is a failure that happens before the request reaches Exchange Online or there is a failure in Exchange Online, you will see a drop in the activity signal.</span></span>

