---
title: Förutsättningar för gästkonton
description: Konfigurationsriktlinjer för gästkonton och hur du justerar dem
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: bbf679a01716fc48d37b241d69740f50a985f048
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574613"
---
# <a name="prerequisites-for-guest-accounts"></a>Förutsättningar för gästkonton

För Microsoft Managed Desktop krävs följande inställningar i Azure AD-organisationen för gästkontoåtkomst. Du kan justera de här inställningarna i [Azure-portalen](https://portal.azure.com) under **Externa identiteter/externt samarbete:**

-   **Administratörer och användare med rollen som gäst inbjudna kan bjuda in inställda** på **Ja**
-   Välj **något av följande** alternativ för Begränsningar för samarbete:
    -   Om du väljer **Tillåt att inbjudningar skickas till valfri domän (mest inkluderande)** krävs ingen annan konfiguration.
    -   Om du väljer **Neka inbjudningar till** de angivna domänerna kontrollerar du att Microsoft.com inte finns i måldomänerna.
    -   Om du väljer Tillåt endast inbjudningar till de angivna domänerna **(mest restriktiva)** kontrollerar du att Microsoft.com *visas* i måldomänerna.

Om du anger begränsningar som interagerar med de här inställningarna ska du se till att utesluta Azure Active Directory **Modern Workplace-tjänstkonton.** Om du till exempel har en princip för villkorsstyrd åtkomst som förhindrar gästkonton från att komma åt Intune-portalen ska du utesluta gruppen **Tjänstkonton** för modern arbetsplats från den här principen.

## <a name="steps-to-get-ready"></a>Steg för att förbereda dig

1. Granska [kraven för Microsoft Managed Desktop](prerequisites.md).
2. Använda [utvärderingsverktyg för beredskap .](readiness-assessment-tool.md)
3. [Krav för gästkonton](guest-accounts.md) (den här artikeln)
4. [Nätverks konfiguration för Microsoft Hanterat skrivbord](network.md)
5. [Förbereda certifikat och nätverks profiler för Microsoft Hanterat skrivbord](certs-wifi-lan.md)
6. [Förbereda lokala resurser till gång för Microsoft Hanterat skrivbord](authentication.md)
7. [Appar på Microsoft Hanterat skrivbord](apps.md)
8. [Förbereda mappade enheter för Microsoft Hanterat skrivbord](mapped-drives.md)
9. [Förbereda skrivarresurser för Microsoft Hanterat skrivbord](printing.md)