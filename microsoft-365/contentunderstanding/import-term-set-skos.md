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
ms.openlocfilehash: 8a1b61088d0a1594bf1a71542158ade389cce2ab
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288521"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="d6eb5-103">Importera en termuppsättning med ett SKOS-baserat format</span><span class="sxs-lookup"><span data-stu-id="d6eb5-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="d6eb5-104">Du kan importera en termuppsättning med ett SKOS-baserat format.</span><span class="sxs-lookup"><span data-stu-id="d6eb5-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="d6eb5-105">Mer information om formatet finns i [SKOS-formatreferens för SharePoint-taxonomi](skos-format-reference.md).</span><span class="sxs-lookup"><span data-stu-id="d6eb5-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span> <span data-ttu-id="d6eb5-106">Den här funktionen kräver en [SharePoint Syntex](index.md) licens.</span><span class="sxs-lookup"><span data-stu-id="d6eb5-106">This feature requires a [SharePoint Syntex](index.md) license.</span></span>

<span data-ttu-id="d6eb5-107">Vi rekommenderar att du endast importerar filer med färre än 20 000 termer.</span><span class="sxs-lookup"><span data-stu-id="d6eb5-107">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="d6eb5-108">Större filer kan göra att verifiering och import tar längre tid.</span><span class="sxs-lookup"><span data-stu-id="d6eb5-108">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="d6eb5-109">Öppna **Innehållstjänster** i administrationscenter för SharePoint och klicka sedan på **Termlagring**.</span><span class="sxs-lookup"><span data-stu-id="d6eb5-109">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="d6eb5-110">Välj den termgrupp där du vill importera termuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="d6eb5-110">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="d6eb5-111">Klicka på **Importera termuppsättning** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="d6eb5-111">In the command bar, click **Import term set**.</span></span>

4. <span data-ttu-id="d6eb5-112">Om du vill ladda ned en exempelfil och använda den som en mall klickar du på **sample-metadata.ttl** för att hämta en exempelfil som använder det SKOS-baserade formatet.</span><span class="sxs-lookup"><span data-stu-id="d6eb5-112">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>

5. <span data-ttu-id="d6eb5-113">Skapa importfilen innehållandes de termuppsättningar och termer du vill importera.</span><span class="sxs-lookup"><span data-stu-id="d6eb5-113">Create the import file that contains the term sets & terms you wish to import.</span></span>

6. <span data-ttu-id="d6eb5-114">Under **Filformat** väljer du **SKOS (\*.ttl)**.</span><span class="sxs-lookup"><span data-stu-id="d6eb5-114">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7. <span data-ttu-id="d6eb5-115">Klicka på **Bläddra**, leta upp och lägg till din importfil.</span><span class="sxs-lookup"><span data-stu-id="d6eb5-115">Click **Browse** and navigate to and add your import file.</span></span>

8. <span data-ttu-id="d6eb5-116">Klicka på **Importera**.</span><span class="sxs-lookup"><span data-stu-id="d6eb5-116">Click **Import**.</span></span> <span data-ttu-id="d6eb5-117">Stäng inte panelen förrän importen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="d6eb5-117">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="d6eb5-118">Vid import av filen visas ett meddelande om att importen lyckades och termlagringsplatsen uppdateras. Du kan nu gå till de nyskapade termuppsättningarna.</span><span class="sxs-lookup"><span data-stu-id="d6eb5-118">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6eb5-119">Se även</span><span class="sxs-lookup"><span data-stu-id="d6eb5-119">See also</span></span>

[<span data-ttu-id="d6eb5-120">Introduktion till hanterade metadata</span><span class="sxs-lookup"><span data-stu-id="d6eb5-120">Introduction to managed metadata</span></span>](/sharepoint/managed-metadata)

[<span data-ttu-id="d6eb5-121">Översikt för dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="d6eb5-121">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="d6eb5-122">Importera termuppsättningar (webbplatsnivå)</span><span class="sxs-lookup"><span data-stu-id="d6eb5-122">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)
