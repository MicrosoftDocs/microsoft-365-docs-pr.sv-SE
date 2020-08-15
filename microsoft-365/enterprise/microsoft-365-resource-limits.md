---
title: Resurs begränsningar i Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: I den här artikeln hittar du information om resurs begränsningar för de olika programmen i Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6053740d41b02461432243c8527391a4f8ae22ea
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694743"
---
# <a name="resource-limits"></a>Resurs begränsningar

Resurs gränser tillämpas med kvoter (gränser) och begränsning. Azure Active Directory (Azure AD) och de enskilda Microsoft 365-tjänsterna använder båda. Gränser är tjänstespecifika och förändras när nya funktioner läggs till. Information om de aktuella gränserna för de olika tjänsterna finns i följande avsnitt:

- [Azure AD-tjänst begränsningar och restriktioner](https://docs.microsoft.com/azure/azure-resource-manager/management/azure-subscription-service-limits)
- [Begränsningar för Exchange Online](https://technet.microsoft.com/library/exchange-online-limits.aspx)
- [Begränsningar för Exchange Online Protection](https://technet.microsoft.com/library/exchange-online-protection-limits.aspx)
- [Program begränsningar och begränsningar för SharePoint Online](https://support.office.com/article/SharePoint-Online-software-boundaries-and-limits-8F34FF47-B749-408B-ABC0-B605E1F6D498)
- [Skype för Business-begränsningar](https://technet.microsoft.com/library/skype-for-business-online-limits.aspx)
- [Stöd för Yammer REST API och hastighet](https://developer.yammer.com/docs/rest-api-rate-limits)
- [Fil storleks begränsningar i Sway](https://support.office.com/article/File-size-limits-in-Sway-4db21bc6-b42b-499f-9272-66e089db109f)

Utöver dessa gränser används flera olika begränsnings mekanismer i hela Azure AD och Microsoft 365. Begränsning av tjänsten är särskilt viktigt, eftersom nätverks resurserna i Microsofts Data Center är optimerade för de breda kunder som använder tjänsterna. Begränsnings mekanismer är bland annat:

- Azure AD-och Microsoft 365-funktioner användarens nivå begränsning, som begränsar antalet transaktioner eller samtidiga samtal (med skript eller kod) som kan utföras av en enskild användare.
- En standard princip för PowerShell-begränsning tilldelas varje klient organisation när han eller hon skapas. Dessa inställningar påverkar andra objekt, till exempel det högsta antalet samtidiga PowerShell-sessioner som kan öppnas av en enda administratör.
- Varje Exchange Online-kund har en standard princip för Exchange Web Services (EWS) som är justerad för EWS-klient operationer och begränsning som gäller för alla Outlook-klienter.
