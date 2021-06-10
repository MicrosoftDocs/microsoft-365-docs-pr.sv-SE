---
title: Lägga till vårdnadshavare till ett Advanced eDiscovery ärende
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
description: Lär dig hur du använder det inbyggda dokumenthanteringsverktyget i Advanced eDiscovery att koordinera arbetsflödena och identifiera relevanta datakällor i ett ärende.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9468fb889e9115b3652d1dba8a6c6632bb367fe3
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/31/2020
ms.locfileid: "52161708"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a>Lägga till vårdnadshavare till ett Advanced eDiscovery ärende

Använd det inbyggda dokumenthanteringsverktyget i Advanced eDiscovery för att samordna arbetsflödena med att hantera dokumentare och identifiera relevanta, dokumentbaserade datakällor som är associerade med ett ärende. När du lägger till en vårdnadshavare kan systemet automatiskt identifiera och placera ett förvaringsställe på Exchange postlåda och OneDrive för företag konto. Under identifieringen av din undersökning kan du även identifiera andra datakällor (till exempel postlådor, webbplatser eller Teams) som en vårdnadshavare har åtkomst till eller bidragit till. I det här fallet kan du använda verktyget för systemhantering för att associera dessa datakällor med en specifik vårdnadshavare. När du har lagt till biblioteksassistenter till ett ärende och associerar andra datakällor med dem, kan du snabbt bevara data och söka i de ursprungliga data.

Du kan lägga till och hantera projektionerna i Advanced eDiscovery fall i fyra steg:

1. Identifiera de inserna.

2. Välj geografiska dataplatser.

3. Konfigurera inställningar för att hålla på/

4. Granska de spåarna och slutför processen.

   [![Fliken Källor i Advanced eDiscovery fall ](../media/AeD-Sources-Tab.png)](../media/AeD-Sources-Tab.png#lightbox)

## <a name="make-sure-you-have-the-necessary-permissions"></a>Kontrollera att du har de behörigheter som krävs

Du måste vara medlem i rollgruppen för eDiscovery Manager för att kunna lägga till biblioteksansvariga i ett ärende. Då har du rätt behörighet att lägga till läsare i ett ärende och skapa plats för de aktuella datakällorna. Mer information finns i [Tilldela eDiscovery-behörigheter](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions).

## <a name="step-1-identify-custodians"></a>Steg 1: Identifiera identifierare

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com) och logga in med ett användarkonto som har tilldelats lämpliga eDiscovery-behörigheter.

2. I det vänstra navigeringsfönstret i Microsoft 365 kompatibilitetscenter klickar du på **Visa alla** och sedan på **eDiscovery > Advanced**.

3. På **Advanced eDiscovery** klickar du på **fliken Ärenden** och väljer sedan det ärende du vill lägga till objekt för.

4. Klicka på **fliken Datakällor** och sedan på Lägg **till datakälla Lägg till** nya  >  **biblioteksarier**.

5. Lägg till en eller flera användare i organisationen som vårdnadshavare för ärendet genom att skriva den första delen av en persons namn eller alias. När du har hittat rätt person väljer du personens namn för att lägga till personen i listan.

## <a name="step-2-choose-custodian-data-locations"></a>Steg 2: Välj plats för data i rättor

När du har valt dokumentadministratörer försöker systemet automatiskt identifiera och verifiera dessa användare och deras datakällor. När de har lagt till brevlådor i listan innehåller verktyget automatiskt den primära postlådan och OneDrive för varje vårdnadshavare. Du kan välja att inte inkludera dessa datakällor när du lägger till bibliotek i ärendet.

Förutom en vårdnadshavares postlåda och OneDrive-konto kan du också koppla andra dataplatser till en vårdnadshavare, till exempel SharePoint-webbplats eller en Microsoft-grupp där den som är vårdnadshavare är medlem. På så sätt kan du bevara, samla in, analysera och granska innehåll i andra datakällor som är kopplade till de aktuella datauppgifterna.

Så här avmarkerar du den primära postlådan OneDrive konto för en vårdnadshavare:

1. Utöka den som försöker ta sin plats med sina data och visa de primära dataplatser som automatiskt har kopplats till varje enskild person.

2. Välj **Rensa** bredvid **Postlåda eller** **OneDrive** om du vill ta bort en vårdnadshavares postlåda eller OneDrive-konto från att associeras som en dataplats för den här den här objekten.

   ![Konfigurera platser att koppla till en vårdnadshavare](../media/ConfigureCustodianLocations.png)

Så här kopplar du andra postlådor, Teams, eller Yammer grupper till en viss användare:

1. Utöka en vårdnadshavare för att visa följande tjänster för att associera dataplatser med den som ska göra det. Klicka **på** Redigera bredvid en tjänst för att lägga till en dataplats.

   - **Exchange**: Används för att koppla andra postlådor till den som inte är ensam. Skriv in namnet eller aliaset (minst tre tecken) i sökrutan för användarpostlådor eller distributionsgrupper. Välj de postlådor som du vill tilldela till den som är användare och klicka sedan på **Lägg till**.

   - **SharePoint:** Används för att koppla SharePoint-webbplatser till den som är vårdnadshavare. Välj en webbplats i listan eller sök efter en webbplats genom att skriva en URL i sökrutan. Välj de webbplatser som du vill tilldela till den som är användare och klicka sedan på **Lägg till**.

   - **Teams**: Används för att tilldela den Microsoft Teams den som den som för närvarande är medlem i. Välj de team som du vill tilldela till användare och klicka sedan på Lägg **till**. När du har lagt till ett team identifierar och identifierar systemet automatiskt SharePoint webbplats- och grupppostlådan som är kopplad till den gruppen och tilldelar dem till den insmfördelaren.

   - **Yammer**: Används för att tilldela de Yammer grupper som den som för närvarande är medlem i. Markera de grupper som du vill tilldela till den som är användare och klicka sedan på **Lägg till**. När du har lagt till ett team identifierar och letar systemet automatiskt upp den SharePoint-webbplats och grupppostlåda som är kopplad till den gruppen och tilldelar dem till den insmfördelaren.

   > [!NOTE]
   > Du kan använda **platsväljarna Exchange** och **SharePoint** för att associera andra grupper eller Yammer-grupper (att en vårdnadshavare inte är medlem) till en vårdnadshavare. Du måste lägga till både postlådan och webbplatsen som är kopplad till varje grupp eller Yammer grupp.

2. Du kan visa det totala antalet postlådor, webbplatser, Teams och Yammer-grupper tilldelade till varje vårdnadshavare genom att utöka alla användare i tabellen. När du har färdigställt de tilldelade dataplatserna för varje enskild användare kommer de här associationerna att underhållas och användas under samlingen, bearbetningen och granskningsstegen i Advanced eDiscovery arbetsflödet.

3. När du har lagt till konfigurering av deras dataplatser klickar **du** på Nästa för att **gå till sidan Inställningar för förvaring.**  

## <a name="step-3-configure-hold-settings"></a>Steg 3: Konfigurera inställningar för att hålla ned

 När du har färdigställt de biblioteken och deras dataplatser kan du välja att placera vissa eller alla de inserare i förvaring. När du placerar en vårdnadshavare i förvaring behålls allt innehåll på alla innehållsplatser som är kopplade till den vårdnadshavare som äger platsen tills du tar bort det bort från platsen eller tills du tar bort den som äger platsen. I vissa fall kan det vara bra att lägga till dagianer till ett ärende utan att sätta dem i förvaring.

Så här placerar du de sövade biblioteken och datakällorna i förvaring:

1. På sidan **Inställningar för** förvaring kan du markera kryssrutan under Kolumnen Håll om du vill att enskilda användare ska kunna ta **del av** det.

   Du kan också markera att alla brevlådor  är förincheckade genom att markera kryssrutan Håll ned högst upp i kolumnen.

2. Kontrollera att den som har behörighet att hålla i markeringar och klicka sedan på **Nästa.**

   > [!NOTE]
   > Om du inte lägger ett förvaringsvärde på en källknöjare, läggs den som är den som är associerad med de associerade datakällorna till i ärendet, men innehållet i datakällorna bevaras inte av det håll som är kopplat till ärendet.

## <a name="step-4-review-the-custodians-and-complete-the-process"></a>Steg 4: Granska de andrerna och slutför processen

Innan du lägger till licenserna i ärendet kan du granska listan över biblioteksarier, de dataplatser som tilldelats dem och inställningarna för att hålla kvar.

1. Verifiera och granska alla datakällor och inställningen för förvaring som gäller för varje enskild person i tabellen. Om det behövs går du tillbaka till **sidorna Identifiera identifierare** eller **inställningar för håll** för att göra ändringar.

2. Klicka **på Skicka** om du vill lägga till vårdnadshavare och deras dataplatser i ärendet, och tillämpa alla inställningar för för infalloläge.

   De nya bibliotekserna läggs till i ärendet och visas på **fliken Datakällor.**

   [![Informaterade på fliken Datakällor ](../media/DataSourcesTab.png)](../media/DataSourcesTab.png#lightbox)
