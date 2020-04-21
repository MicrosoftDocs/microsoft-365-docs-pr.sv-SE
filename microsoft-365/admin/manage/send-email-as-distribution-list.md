---
title: Skicka e-post som en distributionslista
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a7c98273-067e-4162-b3a1-4ba081796012
description: Läs om hur du skickar e-post som en distributionslista i Microsoft 365.
ms.openlocfilehash: e9f8e52350dfd27e58ee160ed10f5c45e33391d7
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628070"
---
# <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="b8191-103">Skicka e-post som en distributionslista</span><span class="sxs-lookup"><span data-stu-id="b8191-103">Send email as a distribution list</span></span>

<span data-ttu-id="b8191-104">I Microsoft 365 kan du skicka e-post som en distributionslista.</span><span class="sxs-lookup"><span data-stu-id="b8191-104">In Microsoft 365, you can send email as a distribution list.</span></span> <span data-ttu-id="b8191-105">När en person som är medlem i distributionslistan svarar på ett meddelande som skickas till distributionslistan, verkar e-postmeddelandet komma från distributionslistan, inte från den enskilda användaren.</span><span class="sxs-lookup"><span data-stu-id="b8191-105">When a person who is a member of the distribution list replies to a message sent to the distribution list, the email appears to be from the distribution list, not from the individual user.</span></span> <span data-ttu-id="b8191-106">Det här avsnittet visar hur du gör detta.</span><span class="sxs-lookup"><span data-stu-id="b8191-106">This topic shows you how to do this.</span></span>
  
## <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="b8191-107">Skicka e-post som en distributionslista</span><span class="sxs-lookup"><span data-stu-id="b8191-107">Send email as a distribution list</span></span>

<span data-ttu-id="b8191-108">Innan du utför de här stegen kontrollerar du att du har lagts till i en Microsoft 365-distributionslista och att du har beviljats Send som behörighet för den.</span><span class="sxs-lookup"><span data-stu-id="b8191-108">Before you perform these steps, make sure you've been added to a Microsoft 365 distribution list and you've have been granted Send as permission on it.</span></span>
  
 <span data-ttu-id="b8191-109">**Administratörer**: Kontrollera att du har följt stegen i [Lägg till en Microsoft 365-användare eller kontakt i en lista](../email/add-user-or-contact-to-distribution-list.md) och tillåt medlemmar att skicka [e-post som ett Microsoft 365-gruppavsnitt](../create-groups/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) och lagt till rätt personer i distributionslistan.</span><span class="sxs-lookup"><span data-stu-id="b8191-109">**Admins**: Make sure you've followed the steps in the [Add a Microsoft 365 user or contact to a list](../email/add-user-or-contact-to-distribution-list.md) and [Allow members to send email as a Microsoft 365 Group](../create-groups/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) topics, and added the correct people to the distribution list.</span></span>
  
1. <span data-ttu-id="b8191-110">Öppna Outlook på webben och gå till inkorgen.</span><span class="sxs-lookup"><span data-stu-id="b8191-110">Open Outlook on the web and go to your inbox.</span></span> 
    
2. <span data-ttu-id="b8191-111">Öppna ett meddelande som skickades till distributionslistan.</span><span class="sxs-lookup"><span data-stu-id="b8191-111">Open a message that was sent to the distribution list.</span></span> 
    
3. <span data-ttu-id="b8191-112">Välj **Svara**.</span><span class="sxs-lookup"><span data-stu-id="b8191-112">Select **Reply**.</span></span> 
    
4. <span data-ttu-id="b8191-113">Längst ned i meddelandet väljer du **Mer** \> **Visa från**.</span><span class="sxs-lookup"><span data-stu-id="b8191-113">At the bottom of the message, select **More** \> **Show from**.</span></span><br/> <span data-ttu-id="b8191-114">![Välj Mer och välj sedan Visa från](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span><span class="sxs-lookup"><span data-stu-id="b8191-114">![Select More and then choose Show From](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span></span>
  
5. <span data-ttu-id="b8191-115">Högerklicka på Adressen Från - `Ina@weewalter.me` till exempel - och välj **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="b8191-115">Right-click on the From address - such as `Ina@weewalter.me` - and choose **Remove**.</span></span><br/> <span data-ttu-id="b8191-116">![Ta bort FROM-aliaset](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span><span class="sxs-lookup"><span data-stu-id="b8191-116">![Remove the FROM alias](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span></span>
  
6. <span data-ttu-id="b8191-117">Skriv sedan distributionslisteadressen, till exempel support@contoso.com och skicka meddelandet.</span><span class="sxs-lookup"><span data-stu-id="b8191-117">Then type the distribution list address such as support@contoso.com, and send the message.</span></span> <span data-ttu-id="b8191-118">Nästa gång du svarar från distributionslistan visas dess adress som ett alternativ i listan **Från.**</span><span class="sxs-lookup"><span data-stu-id="b8191-118">The next time you reply from the distribution list, its address will appear as an option in the **From** list.</span></span><br/><span data-ttu-id="b8191-119">![Alias för den delade postlådan visas](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span><span class="sxs-lookup"><span data-stu-id="b8191-119">![Alias of the shared mailbox appears](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span></span>
  

