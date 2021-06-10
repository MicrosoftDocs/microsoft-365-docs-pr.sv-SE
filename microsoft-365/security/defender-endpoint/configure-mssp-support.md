---
title: Konfigurera support för tjänstleverantör för hanterad säkerhet
description: Konfigurera MSSP-integreringen med Microsoft Defender för slutpunkten genom att vidta nödvändiga åtgärder
keywords: hanterad säkerhetstjänstleverantör, mssp, konfigurera, integrering
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6786d423d20ec90c12d2ea712003acc787ed599d
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165255"
---
# <a name="configure-managed-security-service-provider-integration"></a>Konfigurera integrering med hanterad säkerhetstjänstleverantör

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)
 
[!include[Prerelease information](../../includes/prerelease.md)]

Du måste vidta följande konfigurationssteg för att aktivera mssp-integrering (Managed Security Service Provider).

>[!NOTE]
>Följande termer används i den här artikeln för att skilja mellan tjänsteleverantören och tjänstekonsumenten:
> - MSSP: Säkerhetsorganisationer som erbjuder att övervaka och hantera säkerhetsenheter för en organisation.
> - MSSP-kunder: Organisationer som engagerar sig i mssp-tjänster.

Integreringen gör att MSSP kan utföra följande åtgärder:

- Få åtkomst till MSSP-kundens Microsoft Defender Säkerhetscenter portal
- Få e-postaviseringar och 
- Hämta aviseringar via säkerhetsinformation och händelsehanteringsverktyg (SIEM)

Innan MSSP:er kan utföra de här åtgärderna måste MSSP-kunden bevilja åtkomst till sin Defender för Slutpunktsklientorganisation så att MSSP kan komma åt portalen. 
 

Normalt sett använder MSSP-kunder de inledande konfigurationsstegen för att bevilja MSSP-åtkomst Windows Defender central klientorganisation för säkerhet. När åtkomst har beviljats kan andra konfigurationssteg utföras av antingen kunden för MSSP eller mssp.


I allmänhet måste du vidta följande konfigurationssteg:


- **Ge MSSP åtkomst till Microsoft Defender Säkerhetscenter** <br>
Den här åtgärden måste utföras av MSSP-kunden. Det ger MSSP-åtkomst till MSSP-kundens Defender för slutpunktsklientorganisationen.
 

- **Konfigurera aviseringsaviseringar som skickas till MSSP:er** <br>
Den här åtgärden kan vidtas av antingen MSSP-kunden eller MSSP. Då får MSSP:er veta vilka aviseringar de behöver ta itu med för MSSP-kunden.

- **Hämta aviseringar från MSSP-kundens klientorganisation till SIEM-systemet** <br> Den här åtgärden vidtas av MSSP. Med den kan MSSP hämta aviseringar i SIEM-verktyg.

- **Hämta aviseringar från MSSP-klientens klientorganisation med API:er** <br>
Den här åtgärden vidtas av MSSP. Det gör att MSSP kan hämta aviseringar med API:er.

## <a name="multi-tenant-access-for-mssps"></a>Åtkomst med flera klientorganisationen för MSSP:er
Information om hur du implementerar en delegerad åtkomst med flera innehavare finns i Åtkomst för flera innehavare [för tjänstleverantörer av hanterade säkerhetstjänster.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440)



## <a name="related-topics"></a>Relaterade ämnen
- [Bevilja MSSP åtkomst till portalen](grant-mssp-access.md)
- [Få åtkomst till MSSP-kundportalen](access-mssp-portal.md)
- [Konfigurera varningsaviseringar](configure-mssp-notifications.md)
- [Hämta varningar från kundens klientorganisation](fetch-alerts-mssp.md)

