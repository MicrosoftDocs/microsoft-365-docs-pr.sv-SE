---
title: Konfigurera aviseringsaviseringar som skickas till MSSP:er
description: Konfigurera aviseringsaviseringar som skickas till MSSP:er
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
ms.openlocfilehash: 67f7081e72b5ecc8bdb077f0537cf0cf92df38b9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166059"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a>Konfigurera aviseringsaviseringar som skickas till MSSP:er 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)


>[!NOTE]
>Det här steget kan utföras av antingen MSSP-kunden eller MSSP. MSSP måste ges rätt behörighet för att konfigurera detta för MSSP-kundens räkning.

När åtkomst till portalen har beviljats kan aviseringsregler skapas så att e-postmeddelanden skickas till MSSP när aviseringar som är associerade med klientorganisationen skapas och anger att villkoren uppfylls.

 
Mer information finns i [Skapa regler för aviseringsmeddelanden.](configure-email-notifications.md#create-rules-for-alert-notifications)
 

Dessa kryssrutor måste vara markerade:
- **Inkludera organisationsnamn** – kundnamnet läggs till i e-postaviseringar
- **Inkludera klientspecifik portallänk** – URL för aviseringslänk har klientspecifik parameter (tid=target_tenant_id) som ger direkt åtkomst till målklientorganisationens portal


## <a name="related-topics"></a>Relaterade ämnen
- [Bevilja MSSP-åtkomst till portalen](grant-mssp-access.md)
- [Få åtkomst till kundportalen för MSSP](access-mssp-portal.md)
- [Hämta aviseringar från kundklientorganisationen](fetch-alerts-mssp.md)
