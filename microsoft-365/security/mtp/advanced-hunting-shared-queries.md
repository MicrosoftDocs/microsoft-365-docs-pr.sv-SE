---
title: Använda delade frågor i Microsoft 365 Defender Advanced jakt
description: Starta hotet jakt direkt med fördefinierade och delade frågor. Dela dina frågor till allmänheten eller till din organisation.
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, anpassade identifieringar, schema, kusto, GitHub repo, mina frågor, delade frågor
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 48da1a3a64926f44582e7872f0b0ee03240409ca
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844086"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>Använda delade frågor i avancerad jakt

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender



[Avancerade jakt](advanced-hunting-overview.md) frågor kan delas mellan användare i samma organisation. Du kan också hitta frågor som delas offentligt på GitHub. De här frågorna gör det möjligt för dig att snabbt hitta speciella hot om hotet utan att behöva skriva frågor från grunden.

![Bild av delade frågor](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>Spara, ändra och dela en fråga
Du kan spara en ny eller befintlig fråga så att den är tillgänglig för dig eller delas med andra användare i organisationen. 

1. Skapa eller ändra en fråga. 

2. Klicka på den nedrullningsbara List rutan **Spara fråga** och välj **Spara som**.
    
3. Ange ett namn på frågan. 

   ![Bild av hur du sparar en fråga](../../media/advanced-hunting-save-query.png)

4. Välj den mapp där du vill spara frågan.
    - **Delade frågor** – delas till alla användare i organisationen
    - **Mina frågor** – endast tillgängligt för dig
    
5. Välj **Spara**. 

## <a name="delete-or-rename-a-query"></a>Ta bort eller byta namn på en fråga
1. Högerklicka på en fråga som du vill byta namn på eller ta bort.

    ![Bild av en borttagnings fråga](../../media/advanced_hunting_delete_rename.png)

2. Välj **ta bort** och bekräfta borttagning. Eller Välj **Byt namn** och ange ett nytt namn på frågan.

## <a name="create-a-direct-link-to-a-query"></a>Skapa en direkt länk till en fråga
Om du vill skapa en länk som öppnar frågan direkt i den avancerade Frågeredigeraren kan du slutföra frågan och välja **Dela länk**.

## <a name="access-queries-in-the-github-repository"></a>Åtkomst frågor i GitHub-databasen  
Microsofts säkerhets forskare delar regelbundet avancerade frågor i en [angiven offentlig lagrings plats på GitHub](https://aka.ms/hunting-queries). Denna databas är öppen för bidrag. [Delta i GitHub gratis](https://github.com/).

>[!tip]
>Microsofts säkerhets forskare tillhandahåller också avancerade frågor som du kan använda för att hitta aktiviteter och indikatorer som är kopplade till nya hot. Dessa frågor tillhandahålls som en del av [Threat Analytics](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) -rapporterna i Microsoft Defender säkerhets Center.

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
