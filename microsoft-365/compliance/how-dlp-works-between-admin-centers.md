---
title: Hur DLP fungerar med säkerhets- & säkerhets- och efterlevnadscenter & Exchange administrationscenter
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/19/2019
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
ms.openlocfilehash: c5249279e1dd04447235aae813128cf458adde03
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162988"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a>Så fungerar DLP mellan Säkerhets- och efterlevnadscenter och administrationscentret för Exchange

I Office 365 kan du skapa en DLP-princip (Data Loss Prevention) i två olika administrationscenter:
  
- I **Säkerhets- & efterlevnadscenter** kan du skapa en enda DLP-princip för att skydda innehåll i SharePoint, OneDrive, Exchange och Microsoft Teams. Om det är möjligt rekommenderar vi att du skapar en DLP-princip här. Mer information finns i Referens [för dataförlustskydd.](data-loss-prevention-policies.md)
    
- I Exchange **kan du skapa** en DLP-princip för att endast skydda innehåll i Exchange. Den här principen kan Exchange e-postflödesregler (kallas även transportregler), vilket innebär att det finns fler alternativ för hantering av e-post. Mer information finns i [DLP i Exchange administrationscenter.](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
    
DLP-information som skapats i dessa administrationscenter fungerar sida vid sida – i det här avsnittet förklaras hur.
  
![DLP-sidor i Säkerhets- och efterlevnadscenter Exchange administrationscenter](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>Hur DLP i säkerhets- & säkerhets- och efterlevnadscenter fungerar med DLP- och e-postflödesregler i Exchange administrationscenter

När du har skapat en DLP-princip i Säkerhets- & säkerhets- och efterlevnadscenter distribueras principen till alla platser som ingår i principen. Om principen innehåller Exchange Online synkroniseras principen där och tillämpas på exakt samma sätt som en DLP-princip som skapas Exchange administrationscentret. 
  
Om du har skapat DLP-principer i administrationscentret för Exchange kommer de principerna att fortsätta att fungera sida vid sida med eventuella principer för e-post som du skapar i Säkerhets- och & efterlevnadscenter. Observera dock att regler som skapats Exchange administratörscenter har företräde. Alla Exchange e-postflödesregler bearbetas först, och sedan bearbetas DLP-& säkerhets- och efterlevnadscentret.
  
Det innebär följande:
  
- Meddelanden som blockeras av Exchange genomsöks inte av DLP-regler som skapats i Säkerhets- och & säkerhets- och efterlevnadscenter.
    
- Om en Exchange-e-postflödesregel ändrar ett meddelande på ett sätt som gör att det matchar en DLP-princip i Säkerhets- och efterlevnadscenter för & – som att lägga till externa användare – identifierar DLP-reglerna den här och tillämpar principen efter behov.
    
Observera även att Exchange-postflödesregler som använder åtgärden "stoppa bearbetning" inte påverkar bearbetningen av D & LP-regler i säkerhets- och efterlevnadscentret – de bearbetas fortfarande.
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>Principtips i Säkerhets- & Säkerhets- och efterlevnadscenter Exchange administrationscentret

Principtips kan antingen fungera med DLP-principer och e-postflödesregler som skapats i administrationscentret för Exchange eller med DLP-principer som skapats i säkerhets- och &-efterlevnadscentret, men inte båda. Det beror på att dessa principer lagras på olika platser, men principtips kan endast ritas från en enda plats.
  
Om du har konfigurerat principtips i administrationscentret för Exchange visas inte principtips som du konfigurerar i säkerhets- och efterlevnadscentret för & för användare i Outlook på webben och Outlook 2013 eller senare förrän du inaktiverar tipsen i administrationscentret för Exchange. Det säkerställer att dina Exchange-postflödesregler fortsätter att fungera tills du väljer att växla över till Säkerhets- & efterlevnadscenter.
  
Observera att även om principtips bara kan ritas från en enda plats skickas alltid e-postaviseringar, även om du använder DLP-principer i både Säkerhets- och efterlevnadscenter & och administrationscentret för Exchange.
