---
title: Använd regler för e-postflöde för att se vad användarna rapporterar till Microsoft
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Du kan skapa en Exchange-flödesregel för att förhindra att användarna skickar e-postmeddelanden till Microsoft för analys och använder dem i dina egna säkerhetsprocesser
ms.openlocfilehash: ae8655416840dc326344e2c2aea7c67486389492
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806033"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="f8894-103">Använd regler för e-postflöde för att se vad användarna rapporterar till Microsoft</span><span class="sxs-lookup"><span data-stu-id="f8894-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="f8894-104">Det finns flera sätt att skicka falska positiva och falska negativa meddelanden till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="f8894-104">There are multiple ways you can send false positive and false negative messages to Microsoft for analysis.</span></span> <span data-ttu-id="f8894-105">Som administratör kan du använda regler för e-postflöde för att se vad användarna rapporterar till Microsoft som skräppost, icke-skräppost och nätfiskebedrägerier.</span><span class="sxs-lookup"><span data-stu-id="f8894-105">As an administrator, you can use mail flow rules to see what your users are reporting to Microsoft as spam, non-spam, and phishing scams.</span></span> <span data-ttu-id="f8894-106">Mer information finns i [Skicka meddelanden om skräppost, icke-skräppost och nätfisketill Microsoft för analys](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="f8894-106">For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span> <span data-ttu-id="f8894-107">Omvänt kan du skapa en Exchange-flödesregel (kallas även en transportregel) för att förhindra att användarna skickar e-postmeddelanden till Microsoft för analys och använder dem i dina egna säkerhetsprocesser.</span><span class="sxs-lookup"><span data-stu-id="f8894-107">Conversely, you can create an Exchange mail flow rule (also known as a transport rule) to prevent your users from sending email messages to Microsoft for analysis and use them in your own security processes.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f8894-108">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="f8894-108">What do you need to know before you begin?</span></span>

<span data-ttu-id="f8894-109">Beräknad tid att slutföra: 5 minuter</span><span class="sxs-lookup"><span data-stu-id="f8894-109">Estimated time to complete: 5 minutes</span></span>

<span data-ttu-id="f8894-110">Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="f8894-110">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="f8894-111">Mer information om vilka behörigheter du behöver finns i postposterna "E-postflöde" och "Outlook på webbpostlådeprinciperna" i [Exchange Online-behörigheter](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions).</span><span class="sxs-lookup"><span data-stu-id="f8894-111">To see what permissions you need, see the "Mail flow"  and "Outlook on the web mailbox policies" entries in [Exchange Online permissions](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions).</span></span>

<span data-ttu-id="f8894-112">Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns i [Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="f8894-112">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a><span data-ttu-id="f8894-113">Använd EAC för att skapa en e-postflödesregel för att visa användarnas manuella skräppost, nätfiske och inte skräppostrapporter</span><span class="sxs-lookup"><span data-stu-id="f8894-113">Use the EAC to create a mail flow rule to view users' manual junk, phishing, and not junk reports</span></span>

1. <span data-ttu-id="f8894-114">Navigera till regler för **e-postflöde** \> **i**EAC.</span><span class="sxs-lookup"><span data-stu-id="f8894-114">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="f8894-115">Klicka ![på](../../media/ITPro-EAC-AddIcon.gif) Lägg till ikon och välj sedan **Skapa en ny regel**.</span><span class="sxs-lookup"><span data-stu-id="f8894-115">Click ![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="f8894-116">Ge regeln ett namn och klicka sedan på **Fler alternativ**.</span><span class="sxs-lookup"><span data-stu-id="f8894-116">Give the rule a name and then click **More options**.</span></span>

4. <span data-ttu-id="f8894-117">Under **Använd den här regeln om**väljer du **Mottagaren** och väljer sedan adress innehåller något av **dessa ord**.</span><span class="sxs-lookup"><span data-stu-id="f8894-117">Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.</span></span>

5. <span data-ttu-id="f8894-118">Gör följande steg i rutan **Ange ord eller fraser:**</span><span class="sxs-lookup"><span data-stu-id="f8894-118">In the **specify words or phrases** box, do the following steps:</span></span>

   - <span data-ttu-id="f8894-119">Skriv `abuse@messaging.microsoft.com`, klicka](../../media/ITPro-EAC-AddIcon.gif)på `junk@office365.microsoft.com` **Lägg till** ![lägg](../../media/ITPro-EAC-AddIcon.gif)till ikon, skriv och klicka sedan på Lägg **till** ![ikon .</span><span class="sxs-lookup"><span data-stu-id="f8894-119">Type `abuse@messaging.microsoft.com`, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif), type `junk@office365.microsoft.com` and then click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="f8894-120">Dessa e-postadresser används för att skicka falska negativa meddelanden till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f8894-120">These email addresses are used to submit false negative messages to Microsoft.</span></span>

   - <span data-ttu-id="f8894-121">Skriv `phish@office365.microsoft.com` och klicka sedan](../../media/ITPro-EAC-AddIcon.gif)på Lägg **till** ![lägg till ikon .</span><span class="sxs-lookup"><span data-stu-id="f8894-121">Type `phish@office365.microsoft.com` and then click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="f8894-122">Den här e-postadressen används för att skicka missade nätfiskemeddelanden till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f8894-122">This email address is used to submit missed phishing messages to Microsoft.</span></span>

   - <span data-ttu-id="f8894-123">Skriv `false_positive@messaging.microsoft.com`, klicka](../../media/ITPro-EAC-AddIcon.gif)på `not_junk@office365.microsoft.com` **Lägg till** ![ikonen,](../../media/ITPro-EAC-AddIcon.gif)skriv och klicka sedan på Lägg **till** ![ikonen .</span><span class="sxs-lookup"><span data-stu-id="f8894-123">Type `false_positive@messaging.microsoft.com`, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif), type `not_junk@office365.microsoft.com`, and then click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="f8894-124">Dessa e-postadresser används för att skicka falska positiva meddelanden till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f8894-124">These email addresses are used to submit false positive messages to Microsoft.</span></span>

   - <span data-ttu-id="f8894-125">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8894-125">Click **OK**.</span></span>

6. <span data-ttu-id="f8894-126">Under **Gör följande**väljer du Hemlig kopia av meddelandet **till...** och väljer sedan de postlådor där du vill ta emot meddelandena.</span><span class="sxs-lookup"><span data-stu-id="f8894-126">Under **Do the following**, select **Bcc the message to...** and then and then select the mailboxes where you'd like to receive the messages.</span></span>

7. <span data-ttu-id="f8894-127">Om du vill kan du göra val för att granska regeln, testa regeln, aktivera regeln under en viss tidsperiod och andra val.</span><span class="sxs-lookup"><span data-stu-id="f8894-127">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="f8894-128">Vi rekommenderar att du testar regeln under en period innan du tillämpar den.</span><span class="sxs-lookup"><span data-stu-id="f8894-128">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="f8894-129">Se [Regler för e-postflöde](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span><span class="sxs-lookup"><span data-stu-id="f8894-129">See [Procedures for mail flow rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span></span>

8. <span data-ttu-id="f8894-130">Klicka på **spara-knappen** för att spara regeln.</span><span class="sxs-lookup"><span data-stu-id="f8894-130">Click the **save** button to save the rule.</span></span> <span data-ttu-id="f8894-131">Den visas i listan över regler.</span><span class="sxs-lookup"><span data-stu-id="f8894-131">It appears in your list of rules.</span></span>

<span data-ttu-id="f8894-132">När du har skapat och tillämpat regeln kopieras alla meddelanden som skickas från din organisation till angivna e-postadresser till den angivna postlådan.</span><span class="sxs-lookup"><span data-stu-id="f8894-132">After you create and enforce the rule, any messages that are sent from your organization to specified email addresses will be copied to the specified mailbox.</span></span>
