---
title: Behörigheter för funktioner i EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/30/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Vilka behörigheter som krävs för att utföra uppgifter för att hantera Microsoft Exchange Online Protection (EOP) varierar beroende på vilken funktion du hanterar.
ms.openlocfilehash: 146bf34f157eb30e680ad9e0c3e53501d6e7b425
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638124"
---
# <a name="feature-permissions-in-eop"></a>Behörigheter för funktioner i EOP

De behörigheter som krävs för att utföra uppgifter för att hantera Exchange Online Protection (EOP) varierar beroende på vilken funktion du hanterar.

Om du vill konfigurera EOP måste du vara global administratör eller exchange-företagsadministratör (rollgruppen Organisationshantering).

## <a name="exchange-online-protection-permissions"></a>Behörigheter för Exchange Online Protection

Mer information om vilka behörigheter du behöver för att hantera EOP-funktioner finns i följande tabell. Om mer än en rollgrupp visas för en funktion behöver du bara vara tilldelad en av rollgrupperna för att kunna använda funktionen.

|**Funktion**|**Behörigheter krävs**|
|:-----|:-----|
|Anti-malware|Organisationshantering <br/><br/> Hygien management|
|Anti-spam|Organisationshantering <br/><br/> Hygien management|
|Regler för e-postflöde|Organisationshantering <br/><br/> Hantering av arkivhandlingar|
|Domäner|Organisationshantering <br/><br/> Endast visningsorganisation|
|Avancerat skydd mot hot (ATP)|Organisationshantering <br/><br/> Hygien management|
|Microsoft 365-kontakter|Organisationshantering|
|Meddelandespårning|Organisationshantering <br/><br/> Endast visningsorganisation|
|Organisationskonfiguration|Organisationshantering|
|Karantän|Organisationshantering <br/><br/> Endast visningsorganisation <br/><br/> Hygien management|
|Användare, kontakter och rollgrupper|Organisationshantering <br/><br/> Endast visningsorganisation <br/><br/> Hygien management|
|Distributionsgrupper och säkerhetsgrupper|Organisationshantering <br/><br/> Endast visningsorganisation <br/><br/> Hygien management|
|Visa rapporter|Organisationshantering: Tillgång till e-postskyddsrapporter. <br/><br/> Endast visningsmottagare: Tillgång till e-postskyddsrapporter.  <br/><br/> Efterlevnadshantering: Tillgång till e-postskyddsrapporter och DLP-rapporter (Data Loss Prevention) (om din prenumeration har DLP-funktioner).|
