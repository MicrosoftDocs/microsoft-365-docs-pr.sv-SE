---
title: Bekräfta en undantagsavisering
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du Advanced eDiscovery hur du skickar och följer upp aviseringar om juridiska meddelanden via e-post och hur du övervakar status för skyldigheter.
ms.openlocfilehash: 393d8884a4d4d39056267666fdce6a2754cb582b
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "52161563"
---
# <a name="acknowledge-a-hold-notification"></a><span data-ttu-id="5597c-103">Bekräfta en undantagsavisering</span><span class="sxs-lookup"><span data-stu-id="5597c-103">Acknowledge a hold notification</span></span>

<span data-ttu-id="5597c-104">När du svarar på en begäran eller undersökning av ett regelverk kan du behöva informera den som är skyldig att skydda elektroniskt lagrad information (ESI) och allt material som kan vara relevant för en aktiv eller kommande juridisk fråga.</span><span class="sxs-lookup"><span data-stu-id="5597c-104">When responding to a regulatory request or investigation, you may be required to inform custodians of their obligation to preserve electronically stored information (ESI) and any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="5597c-105">När de har skickats måste juridiska grupper veta att varje vårdnadshavare har tagit emot, läst, förstått och gått med på att följa de givna instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="5597c-105">Once sent, legal teams must know that each custodian has received, read, understood, and agreed to follow the given instructions.</span></span>

<span data-ttu-id="5597c-106">För att minska tiden, kostnaden och arbetet med att följa upp med dina biblioteksklienter kan du med Advanced eDiscovery skicka och följa upp aviseringar om juridiska frågor via e-post.</span><span class="sxs-lookup"><span data-stu-id="5597c-106">To help reduce the time, cost, and effort of following up with your custodians,  Advanced eDiscovery allows you to send and follow up on legal hold notifications through email.</span></span> <span data-ttu-id="5597c-107">Förutom e-postmeddelanden har varje vårdnadshavare tillgång till en portal för individuell efterlevnad, så att vårdnadshavare kan hållas informerade om ändringar av deras status för skyldigheter.</span><span class="sxs-lookup"><span data-stu-id="5597c-107">In addition to email notices, each custodian will have access to an individualized Compliance Portal, allowing custodians to be kept informed of changes to their obligation status.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="5597c-108">E-postaviseringar</span><span class="sxs-lookup"><span data-stu-id="5597c-108">Email notifications</span></span>

<span data-ttu-id="5597c-109">När en avisering om juridiskt förvaring har utfärdats får varje enskild dokumenterare ett unikt och personligt personligt e-postmeddelande med den definierade meddelandet om juridiskt förvaring och ytterligare instruktioner.</span><span class="sxs-lookup"><span data-stu-id="5597c-109">After a Legal Hold Notification has been issued, each custodian will receive a unique and personalized email containing your defined legal hold notice and added instructions.</span></span> 

> [!TIP]
> <span data-ttu-id="5597c-110">Se hur du kan använda den  [inbyggda](using-communications-editor.md) kommunikationsredigeraren så att din vårdnadshavare kan bekräfta sitt meddelande eller komma åt efterlevnadsportalen direkt från sin e-post.</span><span class="sxs-lookup"><span data-stu-id="5597c-110">See how you can use the built-in  [Communication Editor](using-communications-editor.md) to allow your custodians to acknowledge their notice or access their Compliance Portal directly from their email.</span></span>

<span data-ttu-id="5597c-111">Beroende på konfigurationen av din juridiska information kan dina bibliotek få följande meddelanden:</span><span class="sxs-lookup"><span data-stu-id="5597c-111">Based on the configuration of your legal hold notification, your custodians may receive the following notices:</span></span> 

- <span data-ttu-id="5597c-112">**Meddelande om utfärdning:** Det första meddelandet som skickas till din vårdnadshavare.</span><span class="sxs-lookup"><span data-stu-id="5597c-112">**Issuance notice:** The first notice sent to your custodian.</span></span> <span data-ttu-id="5597c-113">Det här meddelandet innehåller utfärdningsanvisningar och meddelandet om väntande tid läggs till i slutet av meddelandet.</span><span class="sxs-lookup"><span data-stu-id="5597c-113">This notice will contain your issuance instructions and the hold notice appended to the end of your message.</span></span>

- <span data-ttu-id="5597c-114">**Påminnelsemeddelande:** Om den är aktiverad skickas ett påminnelsemeddelande till dina brevare baserat på den angivna frekvensen och det angivna intervallet.</span><span class="sxs-lookup"><span data-stu-id="5597c-114">**Reminder notice:** If enabled, a reminder notice will be sent to your custodians based on the specified frequency and interval.</span></span> <span data-ttu-id="5597c-115">Påminnelserna kommer att fortsätta att skickas antingen tills den som förser den som skickar den har bekräftat sitt meddelande eller tills antalet påminnelser har förbrukats.</span><span class="sxs-lookup"><span data-stu-id="5597c-115">The reminders will continue to be sent either until the custodian has acknowledged their notice or until the number of reminders have been exhausted.</span></span>

- <span data-ttu-id="5597c-116">**Eskaleringsmeddelande:** Om den är aktiverad skickas ett eskaleringsmeddelande till din vårdnadshavare och deras chef när påminnelserna har förbrukats.</span><span class="sxs-lookup"><span data-stu-id="5597c-116">**Escalation notice:** If enabled, an escalation notice will be sent to your custodian and their manager after the reminder notices have been exhausted.</span></span> <span data-ttu-id="5597c-117">Systemet skickar automatiskt eskaleringsaviseringar tills det angivna antalet eskaleringar har slutförts eller tills den insnavigare bekräftar sin avisering om att han eller hon håller på att vänta.</span><span class="sxs-lookup"><span data-stu-id="5597c-117">The system will automatically send escalation notices until the specified number of escalations have been completed or until the custodian acknowledges their hold notification.</span></span>

- <span data-ttu-id="5597c-118">**Meddelande om nyissue:** Om innehållet i meddelandet om förvaring uppdateras skickas det uppdaterade meddelandet automatiskt till den uppse håller på att undersökas.</span><span class="sxs-lookup"><span data-stu-id="5597c-118">**Reissue notice:** During the course of an investigation, if the contents of the hold notice are updated, then the updated notice will automatically be sent to the custodian.</span></span>

- <span data-ttu-id="5597c-119">**Meddelande:** När en vårdnadshavare frisläpps från ärendet skickas releasemeddelandet.</span><span class="sxs-lookup"><span data-stu-id="5597c-119">**Release notice:** When a custodian is released from the case, they'll be sent the release notice.</span></span> 

## <a name="compliance-portal"></a><span data-ttu-id="5597c-120">Efterlevnadsportalen</span><span class="sxs-lookup"><span data-stu-id="5597c-120">Compliance Portal</span></span>

<span data-ttu-id="5597c-121">Förutom e-postaviseringarna har varje enskild vårdnadshavare tillgång till en unik efterlevnadsportal.</span><span class="sxs-lookup"><span data-stu-id="5597c-121">In addition to the email notifications, each custodian will have access to a unique Compliance Portal.</span></span> <span data-ttu-id="5597c-122">Via portalen kan varje enskild användare visa, komma åt och bekräfta att de aktiva meddelandena är inhållna.</span><span class="sxs-lookup"><span data-stu-id="5597c-122">Through the portal, each custodian can view, access, and acknowledge their active hold notifications.</span></span>

![Efterlevnadsportalen för en vårdnadshavare](../media/CustodianPortal.jpg)
