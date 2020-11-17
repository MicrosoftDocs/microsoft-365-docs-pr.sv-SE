---
title: Importera en termuppsättning med ett SKOS-baserat format
description: Läs mer om att importera en termuppsättning med ett SKOS-baserat format
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
ms.collection: enabler-strategic
search.appverid: ''
localization_priority: Priority
ms.openlocfilehash: 96ffa22880aa9bcb70c0f7159ac7587c911b375b
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087361"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="a1547-103">Importera en termuppsättning med ett SKOS-baserat format</span><span class="sxs-lookup"><span data-stu-id="a1547-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="a1547-104">Du kan importera en termuppsättning med ett SKOS-baserat format.</span><span class="sxs-lookup"><span data-stu-id="a1547-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="a1547-105">Mer information om formatet finns i [SKOS-formatreferens för SharePoint-taxonomi](skos-format-reference.md).</span><span class="sxs-lookup"><span data-stu-id="a1547-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span>

<span data-ttu-id="a1547-106">Vi rekommenderar att du endast importerar filer med färre än 20 000 termer.</span><span class="sxs-lookup"><span data-stu-id="a1547-106">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="a1547-107">Större filer kan göra att verifiering och import tar längre tid.</span><span class="sxs-lookup"><span data-stu-id="a1547-107">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="a1547-108">Öppna **Innehållstjänster** i administrationscenter för SharePoint och klicka sedan på **Termlagring**.</span><span class="sxs-lookup"><span data-stu-id="a1547-108">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="a1547-109">Välj den termgrupp där du vill importera termuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="a1547-109">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="a1547-110">Klicka på **Importera termuppsättning** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="a1547-110">In the command bar, click **Import term set**.</span></span>
 
4.  <span data-ttu-id="a1547-111">Om du vill ladda ned en exempelfil och använda den som en mall klickar du på **sample-metadata.ttl** för att hämta en exempelfil som använder det SKOS-baserade formatet.</span><span class="sxs-lookup"><span data-stu-id="a1547-111">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>
 
5.  <span data-ttu-id="a1547-112">Skapa importfilen innehållandes de termuppsättningar och termer du vill importera.</span><span class="sxs-lookup"><span data-stu-id="a1547-112">Create the import file that contains the term sets & terms you wish to import.</span></span>

6.  <span data-ttu-id="a1547-113">Under **Filformat** väljer du **SKOS (\*.ttl)**.</span><span class="sxs-lookup"><span data-stu-id="a1547-113">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7.  <span data-ttu-id="a1547-114">Klicka på **Bläddra**, leta upp och lägg till din importfil.</span><span class="sxs-lookup"><span data-stu-id="a1547-114">Click **Browse** and navigate to and add your import file.</span></span>

8.  <span data-ttu-id="a1547-115">Klicka på **Importera**.</span><span class="sxs-lookup"><span data-stu-id="a1547-115">Click **Import**.</span></span> <span data-ttu-id="a1547-116">Stäng inte panelen förrän importen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="a1547-116">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="a1547-117">Vid import av filen visas ett meddelande om att importen lyckades och termlagringsplatsen uppdateras. Du kan nu gå till de nyskapade termuppsättningarna.</span><span class="sxs-lookup"><span data-stu-id="a1547-117">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1547-118">Se även</span><span class="sxs-lookup"><span data-stu-id="a1547-118">See also</span></span>

[<span data-ttu-id="a1547-119">Introduktion till hanterade metadata</span><span class="sxs-lookup"><span data-stu-id="a1547-119">Introduction to managed metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata)

[<span data-ttu-id="a1547-120">Översikt för dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="a1547-120">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="a1547-121">Importera termuppsättningar (webbplatsnivå)</span><span class="sxs-lookup"><span data-stu-id="a1547-121">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)