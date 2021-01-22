---
title: Använda delade frågor i Microsoft 365 Defender avancerad sökning
description: Börja med att sök hot direkt med fördefinierade och delade frågor. Dela dina frågor till allmänheten eller till din organisation.
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, anpassade identifieringar, schema, kusto, github-lagring, mina frågor, delade frågor
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 7dcf446b5e1014d411fc8af08dd15506a2b04e49
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932196"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>Använda delade frågor för avancerad sökning

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender



[Avancerade sökfrågor](advanced-hunting-overview.md) kan delas mellan användare i samma organisation. Du kan också hitta frågor som delas offentligt på GitHub. Med de här frågorna kan du snabbt söka efter specifika hot utan att behöva skriva frågor från grunden.

![Bild på delade frågor](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>Spara, ändra och dela en fråga
Du kan spara en ny eller befintlig fråga så att den bara är tillgänglig för dig eller delas med andra användare i organisationen. 

1. Skapa eller ändra en fråga. 

2. Klicka på **listrutan** Spara fråga och välj **Spara som.**
    
3. Ange ett namn för frågan. 

   ![Bild av hur du sparar en fråga](../../media/advanced-hunting-save-query.png)

4. Välj den mapp där du vill spara frågan.
    - **Delade frågor –** delas för alla användare i organisationen
    - **Mina frågor –** endast tillgängliga för dig
    
5. Välj **Spara**. 

## <a name="delete-or-rename-a-query"></a>Ta bort eller byta namn på en fråga
1. Högerklicka på en fråga som du vill byta namn på eller ta bort.

    ![Bild av borttagningsfråga](../../media/advanced_hunting_delete_rename.png)

2. Välj **Ta bort** och bekräfta borttagningen. Eller välj **Byt** namn och ange ett nytt namn för frågan.

## <a name="create-a-direct-link-to-a-query"></a>Skapa en direktlänk till en fråga
För att skapa en länk som öppnar frågan direkt i den avancerade frågeredigeraren för sökfrågor slutför du frågan och väljer **Dela länk.**

## <a name="access-queries-in-the-github-repository"></a>Åtkomstfrågor på GitHub-databasen  
Microsoft-säkerhet som regelbundet delar avancerade sökningsfrågor på en [angiven offentlig lagringsplats på GitHub.](https://aka.ms/hunting-queries) Lagringsplatsen är öppen för bidrag. Delta kostnadsfritt [i GitHub.](https://github.com/)

>[!tip]
>Microsoft säkerhet är en säkerhetsrisk som även erbjuder avancerade sökningsfrågor som du kan använda för att hitta aktiviteter och indikatorer som är associerade med nya hot. Dessa frågor tillhandahålls som en del av rapporterna [om hotanalyser](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) i Microsoft Defender Säkerhetscenter.

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
