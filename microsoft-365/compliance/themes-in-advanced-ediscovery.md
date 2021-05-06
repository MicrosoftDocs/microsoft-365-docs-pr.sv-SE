---
title: Teman – eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Använd teman i Advanced eDiscovery ordna uppsättningar genom att hitta det mest framträdande temat i varje dokument.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3dfc0dca0c6ed62e3ce8384efa2fd3ea407c3ce8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/26/2020
ms.locfileid: "52161617"
---
# <a name="themes-in-advanced-ediscovery"></a>Teman i Advanced eDiscovery

Hur skriver en person ett dokument? De börjar oftast med en eller flera idéer som de vill förmedla i dokumentet och skriver med ord som passar idéerna. Ju vanligare en idé är, desto vanligare är de ord som är relaterade till den idén. Det här informerar även om hur personer använder dokument. Det som är viktigt att förstå när du läser ett dokument är de idéer som dokumentet försöker förmedla, vilka idéer som visas var, och vilka relationer mellan idéerna är.

Det kan utökas till hur en person vill använda en uppsättning dokument. De vill se vilka idéer som finns i uppsättningarna och vilka dokument som talar om dessa idéer. Dessutom, om de hittar ett visst dokument av intresse, vill de kunna se dokument som diskutera liknande idéer.

Funktionen Teman i Advanced eDiscovery försöker efterlikna hur människor skäl  till dokument genom att analysera de teman som diskuteras i en granskningsuppsättning och tilldela ett tema till dokument i granskningsuppsättningen. I Advanced eDiscovery teman går ett steg längre och identifierar det *mest framträdande temat* i varje dokument. Det mest framträdande temat är det som visas oftast i ett dokument.

## <a name="how-does-themes-work"></a>Hur fungerar teman?

Med funktionen Teman analyseras dokument med text i en granskningsuppsättning för att tolka vanliga teman som visas i alla dokument i granskningsuppsättningen. Advanced eDiscovery tilldelar dessa teman till de dokument där de visas. Det etiketterar också varje tema med de ord som används i de dokument som är representativa för temat. Eftersom ett dokument kan innehålla olika typer av ämnen, Advanced eDiscovery ofta flera teman för dokument. Temat som visas mest framträdande i ett dokument har angetts som dess mest framträdande tema.
