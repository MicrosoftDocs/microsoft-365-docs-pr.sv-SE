---
title: Skicka innehålls typer till en hubb
description: Lär dig hur du skickar innehålls typer till en hubb
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a852207bfd1a2a7643ce8895a533371d194954cf
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296238"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="6e325-103">Skicka innehålls typer till en hubb</span><span class="sxs-lookup"><span data-stu-id="6e325-103">Push content types to a hub</span></span>

<span data-ttu-id="6e325-104">För att göra viktiga innehålls typer mer konsekvent tillgängliga för SharePoint-bibliotek och-listor kan du flytta dem till de nav du väljer.</span><span class="sxs-lookup"><span data-stu-id="6e325-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="6e325-105">Då läggs de automatiskt till i alla nya listor och bibliotek som skapas på de webbplatser som är kopplade till navet och till nya webbplatser som lagts till i navet.</span><span class="sxs-lookup"><span data-stu-id="6e325-105">This automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span>

<span data-ttu-id="6e325-106">För att den här funktionen ska fungera måste innehålls typerna som publiceras redan vara publicerade.</span><span class="sxs-lookup"><span data-stu-id="6e325-106">For this feature to work, The content types being pushed must already be published.</span></span>

<span data-ttu-id="6e325-107">Så här skickar du innehålls typer till nav</span><span class="sxs-lookup"><span data-stu-id="6e325-107">To push content types to hubs</span></span>

1. <span data-ttu-id="6e325-108">Expandera **innehålls tjänster**i administrations centret för SharePoint och klicka sedan på **galleriet innehålls typ**.</span><span class="sxs-lookup"><span data-stu-id="6e325-108">In the SharePoint admin center, expand **Content services**, and then click **Content type gallery**.</span></span>

2. <span data-ttu-id="6e325-109">Klicka på den innehålls typ som du vill skicka till nav.</span><span class="sxs-lookup"><span data-stu-id="6e325-109">Click the content type that you want to push to hubs.</span></span>

3. <span data-ttu-id="6e325-110">Klicka på **Redigera** i kommando fältet.</span><span class="sxs-lookup"><span data-stu-id="6e325-110">Click **Edit** in the command bar.</span></span>
 
4. <span data-ttu-id="6e325-111">Klicka på **Välj nav webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="6e325-111">Click **Choose hub sites**.</span></span>
 
5. <span data-ttu-id="6e325-112">Välj önskade nav webbplatser och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e325-112">Select the desired hub sites and then click **OK**.</span></span>
 
6. <span data-ttu-id="6e325-113">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6e325-113">Click **Save**.</span></span>

<span data-ttu-id="6e325-114">När du försöker skicka en innehålls typ till ett befintligt nav & dess befintliga associerade webbplatser för första gången kan det ta upp till en timme från när navet eller de associerade platserna besöks för att uppdatera inställningarna på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="6e325-114">When pushing a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="6e325-115">Alla nya associationer till navet behöver inte vänta och få inställningarna att synas om några minuter.</span><span class="sxs-lookup"><span data-stu-id="6e325-115">Any new associations to the hub will not require this wait and will have the settings reflected in a few minutes.</span></span> 

<span data-ttu-id="6e325-116">När det här är konfigurerat är innehålls typen med de här inställningarna tillgängliga på alla nyligen associerade webbplatser med navet inom några minuter.</span><span class="sxs-lookup"><span data-stu-id="6e325-116">Once this is configured, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="6e325-117">När du har gjort det får innehålls typen automatiskt lagts till för en ny lista eller ett nytt bibliotek med några minuters uppläggningar.</span><span class="sxs-lookup"><span data-stu-id="6e325-117">Once available, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="6e325-118">En skickad innehålls typ läggs till i ett dokument bibliotek endast om den härleds direkt eller indirekt från dokument innehålls typen och en innehålls typ läggs till i en lista endast om den inte är härledd från dokument innehålls typen direkt eller indirekt.</span><span class="sxs-lookup"><span data-stu-id="6e325-118">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e325-119">Se även</span><span class="sxs-lookup"><span data-stu-id="6e325-119">See also</span></span>



  






