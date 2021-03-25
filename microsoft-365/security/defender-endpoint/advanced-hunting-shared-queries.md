---
title: Använda delade frågor för avancerad sökning
description: Börja sök hot omedelbart med fördefinierade och delade frågor. Dela dina frågor offentligt eller med din organisation.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, custom detections, schema, kusto, github repo, my queries, shared queries
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9788594eaab29aba54c634e79c7aa00d6148aacd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075466"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>Använda delade frågor för avancerad sökning

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

[Avancerade sökfrågor](advanced-hunting-overview.md) kan delas mellan användare i samma organisation. Du kan också hitta frågor som delats offentligt på GitHub. Med de här frågorna kan du snabbt söka efter specifika hot utan att behöva skriva frågor från grunden.

![Bild på delade frågor](images/atp-advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>Spara, ändra och dela en fråga
Du kan spara en ny eller befintlig fråga så att den bara är tillgänglig för dig eller delas med andra användare i organisationen.

1. Skriv en ny fråga eller läs in en befintlig fråga under **Delade frågor** eller **Mina frågor.**

2. Välj **Spara** eller **Spara som** bland alternativen för Att spara. Du undviker att skriva över en befintlig fråga genom att **välja Spara som**.

3. Ange ett namn för frågan.

   ![Bild av att spara en fråga](images/advanced-hunting-save-query.png)

4. Välj den mapp där du vill spara frågan.
    - **Delade frågor –** delas för alla användare i organisationen
    - **Mina frågor –** endast tillgänglig för dig
    
5. Välj **Spara**.

## <a name="delete-or-rename-a-query"></a>Ta bort eller byta namn på en fråga
1. Högerklicka på en fråga som du vill byta namn på eller ta bort.

    ![Bild av borttagningsfråga](images/atp_advanced_hunting_delete_rename.png)

2. Välj **Ta bort** och bekräfta borttagningen. Eller välj **Byt** namn och ange ett nytt namn för frågan.

## <a name="create-a-direct-link-to-a-query"></a>Skapa en direktlänk till en fråga
Om du vill skapa en länk som öppnar frågan direkt i den avancerade frågeredigeraren för sökning slutför du frågan och väljer **Dela länk**.

## <a name="access-queries-in-the-github-repository"></a>Åtkomstfrågor på GitHub-lagringsplatsen  
Microsoft-säkerhetsvakterna delar regelbundet avancerade sökfrågor på en [angiven offentlig lagringsplats på GitHub.](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries) Lagringsplatsen är öppen för bidrag. Delta genom [att kostnadsfritt ansluta till GitHub.](https://github.com/) 

>[!TIP]
>Microsoft-säkerhetsvakter erbjuder också avancerade sökfrågor som du kan använda för att hitta aktiviteter och indikatorer som är associerade med nya hot. Dessa frågor tillhandahålls som en del av rapporterna [över hotanalyser](threat-analytics.md) i Microsoft Defender Säkerhetscenter.

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Förstå schemat](advanced-hunting-schema-reference.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över anpassade identifieringar](overview-custom-detections.md)
