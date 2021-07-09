---
title: Få åtkomst Microsoft 365 Defender mssp-kundportalen
description: Få åtkomst Microsoft 365 Defender mssp-kundportalen
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
ms.openlocfilehash: 8583b28adecd892ec6875faa934fd7ab08e5db11
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339592"
---
# <a name="access-the-microsoft-365-defender-mssp-customer-portal"></a>Få åtkomst Microsoft 365 Defender mssp-kundportalen

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
>Dessa steg riktar sig till MSSP. 

Som standard kommer MSSP-kunder åt Microsoft Defender Säkerhetscenter klientorganisation via följande URL: `https://securitycenter.windows.com` .
 

MssP:er måste emellertid använda en klientspecifik URL i följande format: för åtkomst till  `https://securitycenter.windows.com?tid=customer_tenant_id` mssp-kundportalen. 

I allmänhet måste MSSP:er läggas till i var och en av de Azure AD för MSSP-kunder som de tänker hantera.


Använd följande steg för att hämta klientorganisations-ID för MSSP-kunder och använd sedan ID:t för att få åtkomst till den klientspecifika URL:en:

1. Som MSSP loggar du in på Azure AD med dina autentiseringsuppgifter. 

2. Växla katalog till MSSP-kundens klientorganisation.

3.  Välj **Azure Active Directory > Egenskaper**. Klientorganisations-ID finns i fältet Katalog-ID. 

4. Få åtkomst till MSSP-kundportalen genom att `customer_tenant_id` ersätta värdet i följande URL: `https://securitycenter.windows.com?tid=customer_tenant_id` .


## <a name="related-topics"></a>Relaterade ämnen
- [Bevilja MSSP åtkomst till portalen](grant-mssp-access.md)
- [Konfigurera varningsaviseringar](configure-mssp-notifications.md)
- [Hämta varningar från kundens klientorganisation](fetch-alerts-mssp.md)
