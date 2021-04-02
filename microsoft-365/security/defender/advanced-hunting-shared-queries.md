---
title: Använda delade frågor i Microsoft 365 Defender avancerad sökning
description: Börja sök hot omedelbart med fördefinierade och delade frågor. Dela dina frågor offentligt eller med din organisation.
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, custom detections, schema, kusto, github repo, my queries, shared queries
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: fbc5b4c53487bceab5786a7ce75a56741a3c9cb2
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499721"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>Använda delade frågor för avancerad sökning

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender



[Avancerade sökfrågor](advanced-hunting-overview.md) kan delas mellan användare i samma organisation. Du kan också hitta frågor som delats offentligt på GitHub. Med de här frågorna kan du snabbt söka efter specifika hot utan att behöva skriva frågor från grunden.

![Bild på delade frågor](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>Spara, ändra och dela en fråga
Du kan spara en ny eller befintlig fråga så att den bara är tillgänglig för dig eller delas med andra användare i organisationen. 

1. Skapa eller ändra en fråga. 

2. Klicka på **listrutan** Spara fråga och välj **Spara som**.
    
3. Ange ett namn för frågan. 

   ![Bild av att spara en fråga](../../media/advanced-hunting-save-query.png)

4. Välj den mapp där du vill spara frågan.
    - **Delade frågor –** delas för alla användare i organisationen
    - **Mina frågor –** endast tillgänglig för dig
    
5. Välj **Spara**. 

## <a name="delete-or-rename-a-query"></a>Ta bort eller byta namn på en fråga
1. Högerklicka på en fråga som du vill byta namn på eller ta bort.

    ![Bild av borttagningsfråga](../../media/advanced_hunting_delete_rename.png)

2. Välj **Ta bort** och bekräfta borttagningen. Eller välj **Byt** namn och ange ett nytt namn för frågan.

## <a name="create-a-direct-link-to-a-query"></a>Skapa en direktlänk till en fråga
Om du vill skapa en länk som öppnar frågan direkt i den avancerade frågeredigeraren för sökning slutför du frågan och väljer **Dela länk**.

## <a name="access-queries-in-the-github-repository"></a>Åtkomstfrågor på GitHub-lagringsplatsen  
Microsoft-säkerhetsvakterna delar regelbundet avancerade sökfrågor på en [angiven offentlig lagringsplats på GitHub.](https://aka.ms/hunting-queries) Lagringsplatsen är öppen för bidrag. Delta genom [att kostnadsfritt ansluta till GitHub.](https://github.com/)

>[!tip]
>Microsoft-säkerhetsvakter erbjuder också avancerade sökfrågor som du kan använda för att hitta aktiviteter och indikatorer som är associerade med nya hot. Dessa frågor tillhandahålls som en del av rapporterna [över hotanalyser](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) i Microsoft Defender Säkerhetscenter.

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)