---
title: Skydda filer i team med känslighetsetiketter
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 'Sammanfattning: Använd känslighetsetiketter för att skydda filer i team med höga krav på konfidentialitet.'
ms.openlocfilehash: c36daef7f28ad8bd3306fd7f3f7f1558a3594e68
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637622"
---
# <a name="protect-files-in-teams-with-sensitivity-labels"></a>Skydda filer i team med känslighetsetiketter


Till skillnad från en känslighetsetikett för strikt reglerade data som alla kan tillämpa på valfri fil behöver ett team med höga konfidentialitetskrav en egen etikett eller underetikett så att tilldelade filer:

- Krypteras individuellt.
- Innehåller anpassade behörigheter så att bara medlemmar i teamet kan öppna dem.

För att åstadkomma den här extra säkerhetsnivån för filer i den underliggande SharePoint-webbplatsen för ett team måste du konfigurera en anpassad känslighetsetikett som antingen är en egen etikett eller en underetikett för den allmänna etiketten för strikt reglerade data. Bara teammedlemmarna kommer att se den anpassade etiketten eller underetiketten i sin lista med etiketter.

Använd en känslighetsetikett när du behöver ett litet antal etiketter får både global användning och enskilda privata team. 

Använd en underetikett för känslighet när du har ett stort antal etiketter eller vill ordna etiketter för team med höga konfidentialitetskrav under strikt reglerade-etiketten.

Använd [de här instruktionerna](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) till att konfigurera en separat etikett eller en underetikett med följande inställningar:

- Namnet på etiketten eller underetiketten innehåller teamets namn
- Kryptering är aktiverat
- Microsoft 365-gruppen för teamet har medförfattarbehörighet

När den nya etiketten eller underetiketten har skapats kan du publicera den för dina användare, som sedan kan tillämpa den på filer, antingen lokalt innan de laddas upp till teamet eller senare när filen lagras i teamet.

Här är konfigurationen för teamet med höga konfidentialitetskrav som använder känslighetsetiketter för filkryptering och behörigheter.

![Skydd på baslinjenivå för ett offentligt team.](../../media/highly-confidential-team-dlp-sensitivity-labels.png)


## <a name="see-also"></a>Se även

[Skydda filer i Microsoft Teams](secure-files-in-teams.md)
  
[Införande av moln- och hybridlösningar](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
