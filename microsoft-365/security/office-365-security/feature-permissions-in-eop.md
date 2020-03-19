---
title: Funktionsbehörigheter i EOP
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
ms.openlocfilehash: 2129df7faaa977d59f8af8082291520d33bc9cc7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42809344"
---
# <a name="feature-permissions-in-eop"></a>Funktionsbehörigheter i EOP

De behörigheter som krävs för att utföra uppgifter för att hantera Exchange Online Protection (EOP) varierar beroende på vilken funktion du hanterar.

Om du vill konfigurera EOP måste du vara en Global Office 365-administratör eller en Exchange Company-administratör (rollgruppen Organisationshantering).

## <a name="exchange-online-protection-permissions"></a>Behörigheter för Exchange Online Protection

Mer information om vilka behörigheter du behöver för att hantera EOP-funktioner finns i följande tabell. Om mer än en rollgrupp visas för en funktion behöver du bara vara tilldelad en av rollgrupperna för att kunna använda funktionen.

|**Funktion**|**Behörigheter krävs**|
|:-----|:-----|
|Anti-malware|Organisationshantering <br/><br/> Hygien management|
|Anti-spam|Organisationshantering <br/><br/> Hygien management|
|Regler för e-postflöde|Organisationshantering <br/><br/> Hantering av arkivhandlingar|
|Domäner|Organisationshantering <br/><br/> Endast visningsorganisation|
|Avancerat skydd mot hot (ATP)|Organisationshantering <br/><br/> Hygien management|
|Office 365-kontakter|Organisationshantering|
|Meddelandespårning|Organisationshantering <br/><br/> Endast visningsorganisation|
|Organisationskonfiguration|Organisationshantering|
|Karantän|Organisationshantering <br/><br/> Endast visningsorganisation <br/><br/> Hygien management|
|Användare, kontakter och rollgrupper|Organisationshantering <br/><br/> Endast visningsorganisation <br/><br/> Hygien management|
|Distributionsgrupper och säkerhetsgrupper|Organisationshantering <br/><br/> Endast visningsorganisation <br/><br/> Hygien management|
|Visa rapporter|Organisationshantering: Tillgång till e-postskyddsrapporter. <br/><br/> Endast visningsmottagare: Tillgång till e-postskyddsrapporter.  <br/><br/> Efterlevnadshantering: Tillgång till e-postskyddsrapporter och DLP-rapporter (Data Loss Prevention) (om din prenumeration har DLP-funktioner).|
