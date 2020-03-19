---
title: Använda delade frågor i Microsoft Threat Protection avancerad jakt
description: Börja hotjakt omedelbart med fördefinierade och delade frågor. Dela dina frågor till allmänheten eller till din organisation.
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetri, custom detections, schema, kusto, github repo, my queries, shared queries
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
ms.openlocfilehash: 7ff46226e2535ed9826a61afa857e38b03c06ce1
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42808278"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>Använda delade frågor i avancerad jakt

**Gäller:**
- Skydd av Hot mot Microsoft



[Avancerade jaktfrågor](advanced-hunting-overview.md) kan delas mellan användare i samma organisation. Du kan också hitta frågor som delas offentligt på GitHub. Med de här frågorna kan du snabbt fortsätta med specifika hotjaktsscenarier utan att behöva skriva frågor från grunden.

![Bild av delade frågor](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>Spara, ändra och dela en fråga
Du kan spara en ny eller befintlig fråga så att den bara är tillgänglig för dig eller delas med andra användare i organisationen. 

1. Skapa eller ändra en fråga. 

2. Klicka på listrutan **Spara fråga** och välj **Spara som**.
    
3. Ange ett namn för frågan. 

   ![Bild av att spara en fråga](../../media/advanced-hunting-save-query.png)

4. Markera mappen där du vill spara frågan.
    - **Delade frågor** – delas med alla användare i organisationen
    - **Mina frågor** – endast tillgängliga för dig
    
5. Välj **Spara**. 

## <a name="delete-or-rename-a-query"></a>Ta bort eller byta namn på en fråga
1. Högerklicka på en fråga som du vill byta namn på eller ta bort.

    ![Bild av borttagningsfrågan](../../media/advanced_hunting_delete_rename.png)

2. Välj **Ta bort** och bekräfta borttagning. Eller välj **Byt namn** och ange ett nytt namn för frågan.

## <a name="access-queries-in-the-github-repository"></a>Komma åt frågor i GitHub-databasen  
Microsofts säkerhetsforskare delar regelbundet avancerade jaktfrågor i en [utsedd offentlig databas på GitHub](https://github.com/microsoft/MTP-AHQ). Den här databasen är öppen för bidrag. För att [bidra, gå med GitHub gratis](https://github.com/).

>[!tip]
>Microsofts säkerhetsforskare tillhandahåller också avancerade jaktfrågor som du kan använda för att hitta aktiviteter och indikatorer som är associerade med nya hot. Dessa frågor tillhandahålls som en del av [hotanalysrapporterna](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) i Microsoft Defender Security Center.

## <a name="related-topics"></a>Relaterade ämnen
- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Jaga hot mellan enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
