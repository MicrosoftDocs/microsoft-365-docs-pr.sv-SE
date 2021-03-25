---
title: Anslutning till Power BI för ATP-API:er för Microsoft Defender
ms.reviewer: ''
description: Skapa en Bi-rapport (Power Business Intelligence) överst i Microsoft Defender för slutpunkts-API:er.
keywords: apis, API:er som stöds, Power BI, rapporter
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 696782ca03e5494c3fc5ca08943d1079c5d78f8a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167037"
---
# <a name="create-custom-reports-using-power-bi"></a><span data-ttu-id="a4341-104">Skapa anpassade rapporter med Power BI</span><span class="sxs-lookup"><span data-stu-id="a4341-104">Create custom reports using Power BI</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a4341-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a4341-105">**Applies to:**</span></span>
- [<span data-ttu-id="a4341-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="a4341-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a4341-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a4341-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="a4341-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="a4341-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a4341-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="a4341-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="a4341-110">I det här avsnittet får du lära dig att skapa en Power BI-rapport ovanpå Defender för slutpunkts-API:er.</span><span class="sxs-lookup"><span data-stu-id="a4341-110">In this section you will learn create a Power BI report on top of Defender for Endpoint APIs.</span></span>

<span data-ttu-id="a4341-111">I det första exemplet visas hur du ansluter Power BI till Advanced Hunting API och det andra exemplet visar en anslutning till våra OData-API:er, till exempel Datoråtgärder eller Varningar.</span><span class="sxs-lookup"><span data-stu-id="a4341-111">The first example demonstrates how to connect Power BI to Advanced Hunting API and the second example demonstrates a connection to our OData APIs, such as Machine Actions or Alerts.</span></span>

## <a name="connect-power-bi-to-advanced-hunting-api"></a><span data-ttu-id="a4341-112">Anslut Power BI till API för avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="a4341-112">Connect Power BI to Advanced Hunting API</span></span>

- <span data-ttu-id="a4341-113">Öppna Microsoft Power BI</span><span class="sxs-lookup"><span data-stu-id="a4341-113">Open Microsoft Power BI</span></span>

- <span data-ttu-id="a4341-114">Klicka **på Hämta data** tom  >  **fråga**</span><span class="sxs-lookup"><span data-stu-id="a4341-114">Click **Get Data** > **Blank Query**</span></span>

    ![Bild av skapa en tom fråga](images/power-bi-create-blank-query.png)

- <span data-ttu-id="a4341-116">Klicka på **Avancerad redigerare**</span><span class="sxs-lookup"><span data-stu-id="a4341-116">Click **Advanced Editor**</span></span>

    ![Bild av en öppen avancerad redigerare](images/power-bi-open-advanced-editor.png)

- <span data-ttu-id="a4341-118">Kopiera nedan och klistra in den i redigeraren:</span><span class="sxs-lookup"><span data-stu-id="a4341-118">Copy the below and paste it in the editor:</span></span>

```
    let 
        AdvancedHuntingQuery = "DeviceEvents | where ActionType contains 'Anti' | limit 20",

        HuntingUrl = "https://api.securitycenter.microsoft.com/api/advancedqueries",

        Response = Json.Document(Web.Contents(HuntingUrl, [Query=[key=AdvancedHuntingQuery]])),

        TypeMap = #table(
            { "Type", "PowerBiType" },
            {
                { "Double",   Double.Type },
                { "Int64",    Int64.Type },
                { "Int32",    Int32.Type },
                { "Int16",    Int16.Type },
                { "UInt64",   Number.Type },
                { "UInt32",   Number.Type },
                { "UInt16",   Number.Type },
                { "Byte",     Byte.Type },
                { "Single",   Single.Type },
                { "Decimal",  Decimal.Type },
                { "TimeSpan", Duration.Type },
                { "DateTime", DateTimeZone.Type },
                { "String",   Text.Type },
                { "Boolean",  Logical.Type },
                { "SByte",    Logical.Type },
                { "Guid",     Text.Type }
            }),

        Schema = Table.FromRecords(Response[Schema]),
        TypedSchema = Table.Join(Table.SelectColumns(Schema, {"Name", "Type"}), {"Type"}, TypeMap , {"Type"}),
        Results = Response[Results],
        Rows = Table.FromRecords(Results, Schema[Name]),
        Table = Table.TransformColumnTypes(Rows, Table.ToList(TypedSchema, (c) => {c{0}, c{2}}))

    in Table

```

- <span data-ttu-id="a4341-119">Klicka **på Klar**</span><span class="sxs-lookup"><span data-stu-id="a4341-119">Click **Done**</span></span>

- <span data-ttu-id="a4341-120">Klicka **på Redigera autentiseringsuppgifter**</span><span class="sxs-lookup"><span data-stu-id="a4341-120">Click **Edit Credentials**</span></span>

    ![Bild av autentiseringsuppgifter för redigera0](images/power-bi-edit-credentials.png)

- <span data-ttu-id="a4341-122">Välj **Organisationskonto**  >  **Logga in**</span><span class="sxs-lookup"><span data-stu-id="a4341-122">Select **Organizational account** > **Sign in**</span></span>

    ![Bild av uppsättningsautentiseringsuppgifter1](images/power-bi-set-credentials-organizational.png)

- <span data-ttu-id="a4341-124">Ange dina autentiseringsuppgifter och vänta med att vara inloggad</span><span class="sxs-lookup"><span data-stu-id="a4341-124">Enter your credentials and wait to be signed in</span></span>

- <span data-ttu-id="a4341-125">Klicka **på Anslut**</span><span class="sxs-lookup"><span data-stu-id="a4341-125">Click **Connect**</span></span>

    ![Bild på autentiseringsuppgifter 2](images/power-bi-set-credentials-organizational-cont.png)

- <span data-ttu-id="a4341-127">Resultatet av frågan visas nu som en tabell och du kan börja skapa visualiseringar ovanpå den!</span><span class="sxs-lookup"><span data-stu-id="a4341-127">Now the results of your query will appear as table and you can start build visualizations on top of it!</span></span>

- <span data-ttu-id="a4341-128">Du kan duplicera den här tabellen, byta namn på den och redigera frågan Avancerad sökning inuti så att du får de data du vill ha.</span><span class="sxs-lookup"><span data-stu-id="a4341-128">You can duplicate this table, rename it and edit the Advanced Hunting query inside to get any data you would like.</span></span>

## <a name="connect-power-bi-to-odata-apis"></a><span data-ttu-id="a4341-129">Ansluta Power BI till OData-API:er</span><span class="sxs-lookup"><span data-stu-id="a4341-129">Connect Power BI to OData APIs</span></span>

- <span data-ttu-id="a4341-130">Den enda skillnaden från exemplet ovan är frågan i redigeraren.</span><span class="sxs-lookup"><span data-stu-id="a4341-130">The only difference from the above example is the query inside the editor.</span></span> 

- <span data-ttu-id="a4341-131">Kopiera nedan och klistra in den i redigeraren för att hämta alla **datoråtgärder** från organisationen:</span><span class="sxs-lookup"><span data-stu-id="a4341-131">Copy the below and paste it in the editor to pull all **Machine Actions** from your organization:</span></span>

```
    let

        Query = "MachineActions",

        Source = OData.Feed("https://api.securitycenter.microsoft.com/api/" & Query, null, [Implementation="2.0", MoreColumns=true])
    in
        Source

```

- <span data-ttu-id="a4341-132">Du kan göra samma sak för **Aviseringar** och **Maskiner.**</span><span class="sxs-lookup"><span data-stu-id="a4341-132">You can do the same for **Alerts** and **Machines**.</span></span>

- <span data-ttu-id="a4341-133">Du kan också använda OData-frågor för frågefilter. Mer information finns i [Använda OData-frågor](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="a4341-133">You also can use OData queries for queries filters, see [Using OData Queries](exposed-apis-odata-samples.md)</span></span>


## <a name="power-bi-dashboard-samples-in-github"></a><span data-ttu-id="a4341-134">Exempel på Power BI-instrumentpanel i GitHub</span><span class="sxs-lookup"><span data-stu-id="a4341-134">Power BI dashboard samples in GitHub</span></span>
<span data-ttu-id="a4341-135">Mer information finns i Power [BI-rapportmallar.](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI)</span><span class="sxs-lookup"><span data-stu-id="a4341-135">For more information see the [Power BI report templates](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI).</span></span>

## <a name="sample-reports"></a><span data-ttu-id="a4341-136">Exempelrapporter</span><span class="sxs-lookup"><span data-stu-id="a4341-136">Sample reports</span></span>
<span data-ttu-id="a4341-137">Visa exempel på Microsoft Defender ATP Power BI-rapporter.</span><span class="sxs-lookup"><span data-stu-id="a4341-137">View the Microsoft Defender ATP Power BI report samples.</span></span> <span data-ttu-id="a4341-138">Mer information finns i Bläddra [i kodexempel](https://docs.microsoft.com/samples/browse/?products=mdatp).</span><span class="sxs-lookup"><span data-stu-id="a4341-138">For more information, see [Browse code samples](https://docs.microsoft.com/samples/browse/?products=mdatp).</span></span>


## <a name="related-topic"></a><span data-ttu-id="a4341-139">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="a4341-139">Related topic</span></span>
- [<span data-ttu-id="a4341-140">Defender för slutpunkts-API:er</span><span class="sxs-lookup"><span data-stu-id="a4341-140">Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="a4341-141">Advanced jakt-API</span><span class="sxs-lookup"><span data-stu-id="a4341-141">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="a4341-142">Använda OData-frågor</span><span class="sxs-lookup"><span data-stu-id="a4341-142">Using OData Queries</span></span>](exposed-apis-odata-samples.md)