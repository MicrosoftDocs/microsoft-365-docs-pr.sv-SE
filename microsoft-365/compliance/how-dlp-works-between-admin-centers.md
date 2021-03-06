---
title: Hur DLP fungerar med säkerhets- & säkerhets- och efterlevnadscenter & Exchange administrationscenter
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Läs om hur DLP i Säkerhets- & efterlevnadscenter fungerar med DLP- och e-postflödesregler (transportregler) i Exchange administrationscenter.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a7cd4eaafbd334c8886e0e6aa72d8c0e4c53a81e
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300058"
---
# <a name="how-dlp-works-between-the-microsoft-365-compliance-center-and-exchange-admin-center"></a>Hur DLP fungerar mellan efterlevnadscentret Microsoft 365 och Exchange administrationscenter

I Microsoft 365 kan du skapa en DLP-princip (Data Loss Prevention) i två olika administrationscenter:
  
- I **Microsoft 365 efterlevnadscenter** kan du skapa en enda DLP-princip för att skydda innehåll i SharePoint, OneDrive, Exchange, Teams och nu Slutpunkt-enheter. Vi rekommenderar att du skapar en DLP-princip här. Mer information finns i Referens [för dataförlustskydd.](data-loss-prevention-policies.md)
    
- I Exchange **kan du skapa** en DLP-princip för att endast skydda innehåll i Exchange. Den här principen kan Exchange e-postflödesregler (kallas även transportregler), vilket innebär att det finns fler alternativ för hantering av e-post. Mer information finns i [DLP i Exchange administrationscenter.](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
    
DLP-information som skapats i dessa administrationscenter fungerar sida vid sida – i det här avsnittet förklaras hur.
  
![DLP-sidor i Säkerhets- och efterlevnadscenter Exchange administrationscenter](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>Hur DLP i säkerhets- & säkerhets- och efterlevnadscenter fungerar med DLP- och e-postflödesregler i Exchange administrationscenter

När du har skapat en DLP-princip i Säkerhets- & säkerhets- och efterlevnadscenter distribueras principen till alla platser som ingår i principen. Om principen innehåller Exchange Online synkroniseras principen där och tillämpas på exakt samma sätt som en DLP-princip som skapas Exchange administrationscentret. 
  
Om du har skapat DLP-principer i administrationscentret för Exchange kommer de principerna att fortsätta att fungera sida vid sida med eventuella principer för e-post som du skapar i Säkerhets- och & efterlevnadscenter. Observera dock att regler som skapats Exchange administratörscenter har företräde. Alla Exchange e-postflödesregler bearbetas först, och sedan bearbetas DLP-& säkerhets- och efterlevnadscentret.
  
Det innebär följande:
  
- Meddelanden som blockeras av Exchange genomsöks inte av DLP-regler som skapats i Säkerhets- och & säkerhets- och efterlevnadscenter.

- Meddelanden som ligger i karantän Exchange genom e-postflödesregler eller andra filter körs innan DLP genomsöks inte av DLP.
    
- Om en Exchange-e-postflödesregel ändrar ett meddelande på ett sätt som gör att det matchar en DLP-princip i Säkerhets- och efterlevnadscenter för & – som att lägga till externa användare – identifierar DLP-reglerna den här och tillämpar principen efter behov.
    
Observera även att Exchange-postflödesregler som använder åtgärden "stoppa bearbetning" inte påverkar bearbetningen av D & LP-regler i säkerhets- och efterlevnadscentret – de bearbetas fortfarande.
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>Principtips i Säkerhets- & Säkerhets- och efterlevnadscenter Exchange administrationscentret

Principtips kan antingen fungera med DLP-principer och e-postflödesregler som skapats i administrationscentret för Exchange eller med DLP-principer som skapats i säkerhets- och &-efterlevnadscentret, men inte båda. Det beror på att dessa principer lagras på olika platser, men principtips kan endast ritas från en enda plats.
  
Om du har konfigurerat principtips i administrationscentret för Exchange visas inga principtips som du konfigurerar i säkerhets- och efterlevnadscentret för & i Outlook på webben och Outlook 2013 eller senare förrän du stänger av tipsen i administrationscentret för Exchange. Det säkerställer att dina Exchange-postflödesregler fortsätter att fungera tills du väljer att växla över till Säkerhets- & efterlevnadscenter.
  
Observera att även om principtips bara kan ritas från en enda plats skickas alltid e-postaviseringar, även om du använder DLP-principer i både Säkerhets- och efterlevnadscenter & och administrationscentret för Exchange.
