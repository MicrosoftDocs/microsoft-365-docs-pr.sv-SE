---
title: Vad är skillnaden mellan skräppost och masse-e-post?
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
description: Kunder frågar iblandvad är skillnaden mellan skräppost och massmeddelanden via e-post? Syftet med det här avsnittet är att förklara skillnaden och att ge information om de olika alternativ som är tillgängliga för både i Exchange Online och Exchange Online Protection (EOP).
ms.openlocfilehash: a427fd7a37ec4a5b9828a0f78a32d6e5fd54d69b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42811858"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a>Vad är skillnaden mellan skräppost och masse-e-post?

Kunderna frågar ibland "vad är skillnaden mellan skräppost och massmeddelanden?" Syftet med det här avsnittet är att förklara skillnaden och att ge information om de olika alternativ som är tillgängliga för både i Exchange Online och Exchange Online Protection (EOP).
  
 **Vad är skräppost?**
  
Skräppostmeddelanden är "spam"-meddelanden, som inte är begärda (och vanligtvis oönskade) e-postmeddelanden som filtreras av tjänsten. Som standard avvisar tjänsten skräppostmeddelandet baserat på ryktet om den sändande IP-adressen. Men om det passerar IP-inspektion men klassificeras som skräppost av innehållsfilter, skickas meddelandet till mappen Skräppost för de avsedda mottagarna. 
  
> [!NOTE]
> Åtgärden som utförs på innehållsfiltrerade meddelanden kan konfigureras via principer för innehållsfilter i Administrationscentret för Exchange (EAC), enligt beskrivningen i [Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md). Om du inte håller med om skräppostklassificeringen kan du också rapportera meddelanden som du anser vara skräppost eller icke-skräppost till Microsoft på flera sätt, enligt beskrivningen i [Skicka in skräppost, icke-skräppost och phishing-bluffmeddelanden till Microsoft för analys](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). 
  
 **Vad är mass-e-post?**
  
Mass-e-post, även kallad grå e-post, är en typ av e-postmeddelande som är svårare att klassificera. Medan skräppost är ett ständigt hot, bulk e-post består vanligtvis av en annons eller marknadsföring meddelande som sannolikt inte kommer att få skickas upprepade gånger. Bulk e-post är efterlyst av vissa användare, och i själva verket kan de medvetet ha registrerat sig för att ta emot dessa meddelanden, medan andra användare kan överväga dessa typer av meddelanden som skräppost. Till exempel, vissa användare vill ta emot reklam e-post från Contoso Corporation eller inbjudningar till en kommande konferens om cybersäkerhet, medan andra användare anser att sådana e-postmeddelanden är spam.
  
## <a name="how-to-manage-bulk-email"></a>Så här hanterar du masse-e-post

Hur man hanterar bulk e-post är inte ett entydigt beslut, för om alla bulk e-post klassificeras som skräppost, de användare som vill att det kan klaga och skicka in det som en falsk positiv (icke-spam) meddelande som felaktigt markerades som spam. Å andra sidan, om alla bulk e-post släpps igenom, de användare som inte vill att det kan klaga och skicka in det som ett missat spam-meddelande (falskt negativt) som felaktigt kom i sin inkorg.
  
### <a name="enable-bulk-mail-sensitivity-control-in-the-content-filter-policy"></a>Aktivera massåtkomstkontroll för e-post i innehållsfilterprincipen

Beroende på företagets policy för massmeddelanden kan administratörer välja ett tröskelvärde för att tilldela massmeddelandet. Inställningen kan konfigureras via principer för innehållsfilter i EAC. Kolla [Konfigurera dina principer](configure-your-spam-filter-policies.md) för skräppostfilter för stegen. Du kan välja en tröskelinställning från 1-9, där 1 markerar mest bulk e-post som skräppost, och 9 tillåter de flesta bulk e-post som ska levereras. Tjänsten utför sedan den konfigurerade åtgärden, till exempel att skicka meddelandet till mottagarens skräppostmapp. 
  

