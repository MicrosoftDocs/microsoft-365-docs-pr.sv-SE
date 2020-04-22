---
title: Använda delade frågor i avancerad jakt på Microsoft Threat Protection
description: Starta hotjakt omedelbart med fördefinierade och delade frågor. Dela dina frågor till allmänheten eller till din organisation.
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, anpassade identifieringar, schema, kusto, github repo, mina frågor, delade frågor
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 3fd497ce1733dd4770b9bbc8f699bbccf3237fbd
ms.sourcegitcommit: b8a9994b26a6d9865212f5b1871286e719d1608e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43781523"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>Använda delade frågor i avancerad jakt

**Gäller:**
- Microsoft Hotskydd



[Avancerade jaktfrågor](advanced-hunting-overview.md) kan delas mellan användare i samma organisation. Du kan också hitta frågor som delas offentligt på GitHub. Med de här frågorna kan du snabbt driva specifika hotjaktsscenarier utan att behöva skriva frågor från grunden.

![Bild av delade frågor](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>Spara, ändra och dela en fråga
Du kan spara en ny eller befintlig fråga så att den bara är tillgänglig för dig eller delas med andra användare i organisationen. 

1. Skapa eller ändra en fråga. 

2. Klicka på listrutan **Spara fråga** och välj **Spara som**.
    
3. Ange ett namn på frågan. 

   ![Bild av att spara en fråga](../../media/advanced-hunting-save-query.png)

4. Markera den mapp där du vill spara frågan.
    - **Delade frågor** – delas med alla användare som organisationen
    - **Mina frågor** – endast tillgängliga för dig
    
5. Välj **Spara**. 

## <a name="delete-or-rename-a-query"></a>Ta bort eller byta namn på en fråga
1. Högerklicka på en fråga som du vill byta namn på eller ta bort.

    ![Bild av borttagningsfrågan](../../media/advanced_hunting_delete_rename.png)

2. Välj **Ta bort** och bekräfta borttagning. Du kan också välja **Byt namn** och ange ett nytt namn för frågan.

## <a name="access-queries-in-the-github-repository"></a>Komma åt frågor i GitHub-databasen  
Microsofts säkerhetsforskare delar regelbundet avancerade jaktfrågor i ett [angivet offentligt arkiv på GitHub](https://aka.ms/hunting-queries). Databasen är öppen för bidrag. För att [bidra, gå med GitHub gratis](https://github.com/).

>[!tip]
>Microsofts säkerhetsforskare tillhandahåller också avancerade jaktfrågor som du kan använda för att hitta aktiviteter och indikatorer som är kopplade till nya hot. Dessa frågor tillhandahålls som en del av [hotanalysrapporterna](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) i Microsoft Defender Security Center.

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
