---
title: Vad är skillnaden mellan skräppost och massutskick av e-post?
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/7/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
description: Kunderna frågar iblandvad är skillnaden mellan skräppost och massmeddelanden? Syftet med det här avsnittet är att förklara skillnaden och att ge information om de olika alternativ som är tillgängliga för både Exchange Online och Exchange Online Protection (EOP).
ms.openlocfilehash: 55924ac5e83ca109fd66d1723cdb7c5f43f20df6
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895041"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a>Vad är skillnaden mellan skräppost och massutskick av e-post?

Kunderna frågar ibland "vad är skillnaden mellan skräppost och massmeddelanden?" Syftet med det här avsnittet är att förklara skillnaden och att ge information om de olika alternativ som är tillgängliga för både Exchange Online och Exchange Online Protection (EOP).
  
 **Vad är skräppost?**
  
Skräppostmeddelanden är "skräppost" meddelanden, som är oönskade (och vanligtvis oönskade) e-postmeddelanden som filtreras av tjänsten. Som standard avvisar tjänsten skräppostmeddelandet baserat på ryktet om den sändande IP-adressen. Men om det passerar IP-inspektion men klassificeras som skräppost av innehållsfiltren skickas meddelandet till mappen Skräppost för de avsedda mottagarna. 
  
> [!NOTE]
> Åtgärden som utförs på innehållsfiltrerade meddelanden kan konfigureras via innehållsfilterprinciper i Administrationscenter för Exchange (EAC), enligt beskrivningen i [Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md). Om du inte håller med om skräppostklassificeringen kan du också rapportera meddelanden som du anser vara skräppost eller icke-skräppost till Microsoft på flera sätt, enligt beskrivningen i [Skicka in skräppost, icke-skräppost och meddelanden om nätfiske till Microsoft för analys](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). 
  
 **Vad är massutskick av e-post?**
  
Massutskick av e-post, även kallat grå e-post, är en typ av e-postmeddelande som är svårare att klassificera. Medan skräppost är ett ständigt hot, bulk e-post består vanligtvis av en annons eller marknadsföring meddelande som sannolikt inte kommer att få skickas upprepade gånger. Mass e-post är efterlyst av vissa användare, och i själva verket kan de ha medvetet registrerat sig för att ta emot dessa meddelanden, medan andra användare kan betrakta dessa typer av meddelanden som spam. Vissa användare vill till exempel ta emot e-postmeddelanden från Contoso Corporation eller inbjudningar till en kommande konferens om cybersäkerhet, medan andra användare anser att sådana e-postmeddelanden är skräppost.
  
## <a name="how-to-manage-bulk-email"></a>Så här hanterar du massutskick av e-post

Hur man hanterar bulk e-post är inte en tydlig klippa beslut, för om alla bulk e-post klassificeras som spam, de användare som vill att det kan klaga och skicka in det som en falsk positiv (icke-spam) meddelande som felaktigt markerades som spam. Å andra sidan, om alla bulk e-post är att släppa igenom, de användare som inte vill ha det kan klaga och skicka in det som en missad spam-meddelande (falskt negativ) som felaktigt kom i sin inkorg.
  
### <a name="enable-bulk-mail-sensitivity-control-in-the-content-filter-policy"></a>Aktivera masssynkänslighetskontroll för e-post i innehållsfilterprincipen

Beroende på företagets policy för massmeddelanden kan administratörer välja ett tröskelvärde för att tilldela massmeddelandet. Inställningen kan konfigureras via innehållsfilterprinciper i EAC. Kolla in Konfigurera principer mot [skräppost i Office 365](configure-your-spam-filter-policies.md) för stegen. Du kan välja en tröskelinställning från 1-9, där 1 markerar de flesta mass-e-post som skräppost, och 9 tillåter de flesta bulk e-post som ska levereras. Tjänsten utför sedan den konfigurerade åtgärden, till exempel att skicka meddelandet till mottagarens skräppostmapp. 
  

