---
title: Cortana-integration med Office 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7257cb50-0d5c-4f7a-ac2e-9fe5d13bb5cb
description: 'Läs om hur du använder Cortana när den är integrerad med Office 365. Du kan inaktivera Cortana i administrationscentret för att begränsa dess åtkomst till organisationens data. '
ms.openlocfilehash: 8f20c9b96ee57dcdf5da99dc08ffeb72465bc515
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42808221"
---
# <a name="cortana-in-office-365"></a><span data-ttu-id="fbe21-104">Cortana i Office 365</span><span class="sxs-lookup"><span data-stu-id="fbe21-104">Cortana in Office 365</span></span>

<span data-ttu-id="fbe21-105">Cortana är en molnbaserad digital assistent och Microsoft 365- och Office 365-tjänst som fungerar på dina enheter och Microsoft-tjänster.</span><span class="sxs-lookup"><span data-stu-id="fbe21-105">Cortana is a cloud-based digital assistant and Microsoft 365 and Office 365 service that works across your devices and Microsoft services.</span></span> <span data-ttu-id="fbe21-106">Cortana kan använda information som lagras i Microsoft 365 och Office 365 för att hjälpa personer i organisationen att hålla sig uppdaterade och få insikter, föreslagna uppgifter och hjälp med sina möten, dokument och kontakter.</span><span class="sxs-lookup"><span data-stu-id="fbe21-106">Cortana can use information stored in Microsoft 365 and Office 365 to help people in your organization stay up to date and get insights, suggested tasks, and help with their meetings, documents, and contacts.</span></span>
  
## <a name="info-for-admins"></a><span data-ttu-id="fbe21-107">Information för administratörer</span><span class="sxs-lookup"><span data-stu-id="fbe21-107">Info for admins</span></span>

<span data-ttu-id="fbe21-108">Efterlevnad är ett åtagande som Microsoft gör gentemot företagskunder.</span><span class="sxs-lookup"><span data-stu-id="fbe21-108">Compliance is a commitment that Microsoft makes to enterprise customers.</span></span> [<span data-ttu-id="fbe21-109">Läs mer om Microsofts ramverk för efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="fbe21-109">Learn more about the Microsoft compliance framework.</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=2109173)

<span data-ttu-id="fbe21-110">I enlighet med andra Microsoft 365- och Office 365-tjänster skyddas och skyddas kompatibla Cortana-funktioner med förbehåll för villkoren för onlinetjänster som innehåller en uppsättning löften som innebär skydd av användardata mot oavsiktlig förlust, ändring, obehörigt röjande eller åtkomst, eller olaglig förstörelse.</span><span class="sxs-lookup"><span data-stu-id="fbe21-110">Consistent with other Microsoft 365 and Office 365 services, compliant Cortana features are protected and secured subject to the Online Service Terms that includes a set of promises involving protection of user data against accidental loss, alteration, unauthorized disclosure or access, or unlawful destruction.</span></span> <span data-ttu-id="fbe21-111">Alla andra Cortana-funktioner (dvs. Cortana-anslutna tjänster) omfattas av [Microsoft Services-avtalet](https://go.microsoft.com/fwlink/p/?LinkId=2109174) och [Microsofts sekretesspolicy.](https://go.microsoft.com/fwlink/p/?LinkId=2109175)</span><span class="sxs-lookup"><span data-stu-id="fbe21-111">All other Cortana features (i.e., Cortana optional connected services) are subject to the [Microsoft Services Agreement](https://go.microsoft.com/fwlink/p/?LinkId=2109174) and  [Microsoft Privacy Statement.](https://go.microsoft.com/fwlink/p/?LinkId=2109175)</span></span>

<span data-ttu-id="fbe21-112">Cortana-tjänster är uppdelade i två datakategorier, **kompatibla** och **valfria anslutna tjänster**, som du kan styra.</span><span class="sxs-lookup"><span data-stu-id="fbe21-112">Cortana services are broken into two data categories, **compliant** and **optional connected services**, which you can control.</span></span>

## <a name="turn-off-cortana-optional-connected-services"></a><span data-ttu-id="fbe21-113">Inaktivera Cortana-anslutna tjänster som tillval</span><span class="sxs-lookup"><span data-stu-id="fbe21-113">Turn off Cortana optional connected services</span></span>

<span data-ttu-id="fbe21-114">Cortana-valfria anslutna tjänster kan stängas av för anställda i organisationen.</span><span class="sxs-lookup"><span data-stu-id="fbe21-114">Cortana optional connected services can be turned off for employees at your organization.</span></span> <span data-ttu-id="fbe21-115">Detta inaktiverar Cortanas valfria anslutna tjänster i Cortana i Windows och Cortana-mobilappen.</span><span class="sxs-lookup"><span data-stu-id="fbe21-115">This will disable Cortana optional connected services in Cortana on Windows and the Cortana mobile app.</span></span> <span data-ttu-id="fbe21-116">Detta inkluderar Cortana-påminnelser, listor, uppgifter och andra funktioner.</span><span class="sxs-lookup"><span data-stu-id="fbe21-116">This includes Cortana reminders, lists, tasks, and other features.</span></span> <span data-ttu-id="fbe21-117">Tjänster i den kompatibla kategorin (d.v.s. Cortana OST-upplevelser), till exempel Cortanas Briefing-e-post och Spela upp mina e-postmeddelanden i Outlook mobile, förblir aktiva.</span><span class="sxs-lookup"><span data-stu-id="fbe21-117">Services in the compliant category (i.e., Cortana OST experiences), such as Cortana’s Briefing email, and Play My Emails in Outlook mobile, will remain active.</span></span>

1. <span data-ttu-id="fbe21-118">Välj **Inställningar inställningar** > **i** administrationscentret för Microsoft 365 och välj **Cortana**.</span><span class="sxs-lookup"><span data-stu-id="fbe21-118">In the Microsoft 365 admin center, select **Settings** > **Settings** and select **Cortana**.</span></span>

4. <span data-ttu-id="fbe21-119">Markera kryssrutan för **Tillåt Cortana-valfria anslutna upplevelser att använda dina organisationers Microsoft-värddata** för att aktivera eller inaktivera Cortana-anslutna upplevelser.</span><span class="sxs-lookup"><span data-stu-id="fbe21-119">Select the checkbox for **Allow Cortana optional connected experiences to use your organizations's Microsoft hosted data** to enable or disable Cortana connected experiences.</span></span>

5. <span data-ttu-id="fbe21-120">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="fbe21-120">Select **Save changes**.</span></span>

## <a name="turn-off-cortana-ost-experiences"></a><span data-ttu-id="fbe21-121">Inaktivera Cortana OST-upplevelser</span><span class="sxs-lookup"><span data-stu-id="fbe21-121">Turn off Cortana OST experiences</span></span>

<span data-ttu-id="fbe21-122">Organisationens anställda kan välja bort Cortana OST-upplevelser individuellt genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="fbe21-122">Your organization's employees can opt out of Cortana OST experiences individually by following the steps below.</span></span>

1. <span data-ttu-id="fbe21-123">Öppna Outlook Mobile.</span><span class="sxs-lookup"><span data-stu-id="fbe21-123">Open Outlook mobile.</span></span>

2. <span data-ttu-id="fbe21-124">Gå till **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="fbe21-124">Go to **Settings**.</span></span>
  
3. <span data-ttu-id="fbe21-125">Välj **Spela upp min e-post**.</span><span class="sxs-lookup"><span data-stu-id="fbe21-125">Select **Play My Emails**.</span></span>

4. <span data-ttu-id="fbe21-126">Flytta växlingen till av på de konton som du vill inaktivera.</span><span class="sxs-lookup"><span data-stu-id="fbe21-126">Move the toggle to off on the accounts you want to disable.</span></span>

### <a name="briefing-email"></a><span data-ttu-id="fbe21-127">Briefing e-post</span><span class="sxs-lookup"><span data-stu-id="fbe21-127">Briefing email</span></span>

<span data-ttu-id="fbe21-128">Om du inaktiverar Cortana i Aktivitetsfältet inaktiveras inte Cortanas briefing-e-post.</span><span class="sxs-lookup"><span data-stu-id="fbe21-128">Disabling Cortana on the taskbar won't disable Cortana’s Briefing email.</span></span> <span data-ttu-id="fbe21-129">Anställda måste avsluta prenumerationen individuellt.</span><span class="sxs-lookup"><span data-stu-id="fbe21-129">Employees must unsubscribe individually.</span></span> <span data-ttu-id="fbe21-130">Personer från din organisation kan välja bort Cortanas Briefing-e-post genom att välja **Avsluta prenumerationen** i meddelandets sidfot.</span><span class="sxs-lookup"><span data-stu-id="fbe21-130">Individuals from your organization can opt out of Cortana’s Briefing email by selecting **Unsubscribe** in the footer of the message.</span></span>
