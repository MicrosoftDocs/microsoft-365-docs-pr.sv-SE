---
title: Office 365 Skype för Business Data borttagning
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: I den här artikeln hittar du en förklaring till data borttagning i Skype för företag, inklusive vilka typer av innehåll som inte behålls.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bf317f2ecd3d547ae8601553a34fb43fb4b5bd9d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694749"
---
# <a name="skype-for-business-data-deletion-in-office-365"></a><span data-ttu-id="58699-103">Data borttagning för Skype för företag i Office 365</span><span class="sxs-lookup"><span data-stu-id="58699-103">Skype for Business Data Deletion in Office 365</span></span>

<span data-ttu-id="58699-104">Med Skype för företag kan du arkivera peer-to-peer-snabb meddelanden, direkt meddelanden och innehålls överförings aktiviteter i möten.</span><span class="sxs-lookup"><span data-stu-id="58699-104">Skype for Business provides archiving of peer-to-peer instant messages, multiparty instant messages, and content upload activities in meetings.</span></span> <span data-ttu-id="58699-105">Arkiverings funktionen kräver Exchange och styrs av användarens Exchange-post låda-attribut, som arkiverar både e-post och Skype för företag.</span><span class="sxs-lookup"><span data-stu-id="58699-105">The archiving capability requires Exchange and is controlled by the user's Exchange mailbox In-Place Hold attribute, which archives both email and Skype for Business contents.</span></span>

<span data-ttu-id="58699-106">All arkivering i Skype för företag betraktas som "arkivering på användar nivå" eftersom du aktiverar eller inaktiverar den för en eller flera specifika användare eller grupper av användare genom att skapa, konfigurera och tillämpa en princip för arkivering av användar nivå för dessa användare.</span><span class="sxs-lookup"><span data-stu-id="58699-106">All archiving in Skype for Business is considered "user-level archiving" because you enable or disable it for one or more specific users or groups of users by creating, configuring, and applying a user-level archiving policy for those users.</span></span> <span data-ttu-id="58699-107">Det finns ingen direkt kontroll över inställningar för arkivering i administrations centret för Skype för företag.</span><span class="sxs-lookup"><span data-stu-id="58699-107">There is no direct control of archiving settings from within the Skype for Business admin center.</span></span>

<span data-ttu-id="58699-108">Följande typer av innehåll arkiveras inte i Skype för företag:</span><span class="sxs-lookup"><span data-stu-id="58699-108">The following types of content are not archived in Skype for Business:</span></span>

- <span data-ttu-id="58699-109">Fil överföringar mellan peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="58699-109">Peer-to-peer file transfers</span></span>
- <span data-ttu-id="58699-110">Ljud/video för peer-to-peer snabb meddelanden och konferenser</span><span class="sxs-lookup"><span data-stu-id="58699-110">Audio/video for peer-to-peer instant messages and conferences</span></span>
- <span data-ttu-id="58699-111">Program delning för peer-to-peer snabb meddelanden och konferenser</span><span class="sxs-lookup"><span data-stu-id="58699-111">Application sharing for peer-to-peer instant messages and conferences</span></span>
- <span data-ttu-id="58699-112">Konferens anteckningar</span><span class="sxs-lookup"><span data-stu-id="58699-112">Conferencing annotations</span></span> 

## <a name="meeting-content-retention"></a><span data-ttu-id="58699-113">Bevarande av mötes innehåll</span><span class="sxs-lookup"><span data-stu-id="58699-113">Meeting Content Retention</span></span>

<span data-ttu-id="58699-114">Kunder som använder Skype för företag kan ladda upp innehåll till ett Skype för företag-möte som bilagor, till exempel PowerPoint-presentationer, OneNote-filer och andra filer.</span><span class="sxs-lookup"><span data-stu-id="58699-114">Customers using Skype for Business can upload content to a Skype for Business meeting as attachments, such as PowerPoint presentations, OneNote files, and other files.</span></span> <span data-ttu-id="58699-115">Bevarande perioden för innehåll som har laddats upp till ett möte ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="58699-115">The retention period for content that has been uploaded to a meeting is as follows:</span></span>

- <span data-ttu-id="58699-116">**Ett möte med en gång** – innehållet bevaras i 15 dagar från och med den sista personen som lämnar mötet.</span><span class="sxs-lookup"><span data-stu-id="58699-116">**One-time meeting** - Content is retained for 15 days starting from when the last person leaves the meeting.</span></span>
- <span data-ttu-id="58699-117">**Återkommande möte** – innehållet behålls i 15 dagar efter att den sista personen har lämnat den sista sessionen av mötet.</span><span class="sxs-lookup"><span data-stu-id="58699-117">**Recurring meeting** - Content is retained for 15 days after the last person leaves the last session of the meeting.</span></span> <span data-ttu-id="58699-118">Timern för kvarhållande återställer om någon ansluter till samma mötesinbjudan inom 15 dagar.</span><span class="sxs-lookup"><span data-stu-id="58699-118">The retention timer resets if someone joins the same meeting session within 15 days.</span></span> <span data-ttu-id="58699-119">Anta till exempel att ett Skype för företag-möte ska inträffa varje vecka i ett år och en fil laddas upp till mötet under den första instansen.</span><span class="sxs-lookup"><span data-stu-id="58699-119">For example, assume a Skype for Business meeting is scheduled to occur on a weekly basis for one year, and a file is uploaded to the meeting during the first instance.</span></span> <span data-ttu-id="58699-120">Om minst en person ansluter till mötesinbjudan varje vecka bevaras filen i Skype för företag – Online-servrar för hela året plus 15 dagar efter att den sista personen har lämnat det sista mötet i serien.</span><span class="sxs-lookup"><span data-stu-id="58699-120">If at least one person joins the meeting session every week, the file is retained in Skype for Business Online servers for the entire year plus 15 days after the last person leaves the last meeting of the series.</span></span>
- <span data-ttu-id="58699-121">**Möte nu** – innehållet behålls i 8 timmar efter mötets slut tid.</span><span class="sxs-lookup"><span data-stu-id="58699-121">**Meet Now meeting** - Content is retained for 8 hours after the meeting end time.</span></span>

> [!NOTE]
> <span data-ttu-id="58699-122">Om en användare inte är licensierad eller inaktive rad (till exempel om **msRTCSIP-UserEnabled** är inställt på *false*) och sedan återkallas eller återaktiveras, kommer Mötes innehåll inte att bevaras.</span><span class="sxs-lookup"><span data-stu-id="58699-122">If a user is unlicensed or disabled (e.g., if **msRTCSIP-userenabled** is set to *False*), and is then re-licensed or reenabled, meeting content is not retained.</span></span>

## <a name="meeting-expiration"></a><span data-ttu-id="58699-123">Mötet upphör</span><span class="sxs-lookup"><span data-stu-id="58699-123">Meeting Expiration</span></span>

<span data-ttu-id="58699-124">Användare kan komma åt ett visst möte efter att mötet har avslut ATS, beroende på följande tids perioder:</span><span class="sxs-lookup"><span data-stu-id="58699-124">Users can access a specific meeting after the meeting has ended, subject to the following expiration time periods:</span></span>

- <span data-ttu-id="58699-125">**Ett möte med en gång** -mötet upphör att gälla 14 dagar efter den schemalagda mötets slut tid.</span><span class="sxs-lookup"><span data-stu-id="58699-125">**One-time meeting** - Meeting expires 14 days after the scheduled meeting end time.</span></span>
- <span data-ttu-id="58699-126">**Återkommande möte med slutdatum** -mötet upphör att gälla 14 dagar efter den schemalagda slut tiden för det senaste Mötes tillfället.</span><span class="sxs-lookup"><span data-stu-id="58699-126">**Recurring meeting with end date** - Meeting expires 14 days after the scheduled end time of the last meeting occurrence.</span></span>
- <span data-ttu-id="58699-127">Möte **nu slutar svara** efter 8 timmar.</span><span class="sxs-lookup"><span data-stu-id="58699-127">**Meet Now meeting** - Meeting expires after 8 hours.</span></span>

## <a name="whiteboard-collaboration"></a><span data-ttu-id="58699-128">Whiteboard-samarbete</span><span class="sxs-lookup"><span data-stu-id="58699-128">Whiteboard Collaboration</span></span>

<span data-ttu-id="58699-129">Anteckningar som gjorts på whiteboardtavlor visas av alla deltagare.</span><span class="sxs-lookup"><span data-stu-id="58699-129">Annotations made on whiteboards will be seen by all participants.</span></span> <span data-ttu-id="58699-130">När du sparar en whiteboard sparas whiteboard och alla anteckningar på en Skype för företag-Server, och den bevaras på servern enligt de principer för giltighets datum som anges av administratören.</span><span class="sxs-lookup"><span data-stu-id="58699-130">When saving a whiteboard, the whiteboard and all annotations will be stored on a Skype for Business server, and it will be retained on the server according to meeting content expiration policies set by the administrator.</span></span>

## <a name="audio-test-service"></a><span data-ttu-id="58699-131">Ljud test tjänst</span><span class="sxs-lookup"><span data-stu-id="58699-131">Audio Test Service</span></span>

<span data-ttu-id="58699-132">Ett kort (cirka 5 sekunder) exempel på din röst spelas in under samtalet.</span><span class="sxs-lookup"><span data-stu-id="58699-132">A short (approximately 5 seconds) sample of your voice is recorded during the Audio Test Service call.</span></span> <span data-ttu-id="58699-133">Röst provet används för att kontrol lera och/eller verifiera ljud kvaliteten på ditt Skype för företag-samtal baserat på inspelningens kvalitet.</span><span class="sxs-lookup"><span data-stu-id="58699-133">The voice sample is used by you to check and/or verify the sound quality of your Skype for Business call based on the quality of the recording.</span></span> <span data-ttu-id="58699-134">När ljud test tjänstens samtal är slut raderas röst provet.</span><span class="sxs-lookup"><span data-stu-id="58699-134">When the Audio Test Service call ends, the voice sample is deleted.</span></span>

## <a name="persistent-group-chat"></a><span data-ttu-id="58699-135">Beständig gruppchatt</span><span class="sxs-lookup"><span data-stu-id="58699-135">Persistent Group Chat</span></span>

<span data-ttu-id="58699-136">I beständiga gruppchatt sparas innehållet i gruppchatt-konversationer.</span><span class="sxs-lookup"><span data-stu-id="58699-136">Persistent Group Chat stores the content of group chat conversations.</span></span> <span data-ttu-id="58699-137">Om den är aktive rad kan administratören kontrol lera kvarhållningsperioden, den server där informationen lagras, om gruppchattens historik är arkiverad efter efterlevnad eller andra ändamål och hantera/ändra alla egenskaper i ett rum.</span><span class="sxs-lookup"><span data-stu-id="58699-137">If enabled, the administrator can control the retention period, the server on which this information is stored, if Group Chat history is archived for compliance or other purposes, and manage/modify any properties on a room.</span></span> <span data-ttu-id="58699-138">Användare med olika roller har åtkomst till beständiga data på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="58699-138">Users with different roles have different access to the persisted data, as follows:</span></span>

- <span data-ttu-id="58699-139">Administratörer kan ta bort gammalt innehåll (till exempel innehåll som har publicerats före ett visst datum) från ett chattrum för att hålla databasens storlek avsevärt.</span><span class="sxs-lookup"><span data-stu-id="58699-139">Administrators can delete older content (for example, content posted before a certain date) from any chat room to keep the size of the database from growing greatly.</span></span> <span data-ttu-id="58699-140">Eller så kan de ta bort eller ersätta meddelanden som är olämpliga för ett visst chattrum (eller som ansågs olämpliga).</span><span class="sxs-lookup"><span data-stu-id="58699-140">Or, they can remove or replace messages considered inappropriate for a given chat room (or considered unsuitable).</span></span>
- <span data-ttu-id="58699-141">Slutanvändare, inklusive meddelande författare, kan inte ta bort innehåll från ett chattrum.</span><span class="sxs-lookup"><span data-stu-id="58699-141">End-users, including message authors, cannot delete content from any chat room.</span></span>
- <span data-ttu-id="58699-142">Chattrum kan inaktivera rum men inte ta bort rum.</span><span class="sxs-lookup"><span data-stu-id="58699-142">Chat room managers can disable rooms but cannot delete rooms.</span></span> <span data-ttu-id="58699-143">Endast administratörer kan ta bort ett chattrum när det har skapats.</span><span class="sxs-lookup"><span data-stu-id="58699-143">Only administrators can delete a chat room after it is created.</span></span>