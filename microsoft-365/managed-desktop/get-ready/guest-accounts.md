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
ms.openlocfilehash: d29b9d6bdc30d981b273d95925ba740bc92304c4
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694251"
---
# <a name="prerequisites-for-guest-accounts"></a>Förutsättningar för gästkonton

Microsoft Hanterat skrivbord kräver följande inställningar i Azure AD-organisationen för gästkontoåtkomst. Du kan justera de här inställningarna i [Azure-portalen](https://portal.azure.com) under **Externa identiteter/inställningar för externt samarbete:**

-   För **begränsningar av gäst inbjudningar** som angetts för medlemsanvändare och användare som tilldelats specifika administratörsroller kan du bjuda in **gästanvändare, bland annat gäster med medlemsbehörigheter**
-   Välj **något av följande** alternativ för Begränsningar för samarbete:
    -   Om du väljer **Tillåt att inbjudningar skickas till valfri domän (mest inkluderande)** krävs ingen annan konfiguration.
    -   Om du väljer **Neka inbjudningar till** de angivna domänerna kontrollerar du att Microsoft.com inte finns i måldomänerna.
    -   Om du väljer Tillåt endast inbjudningar till de angivna domänerna **(mest restriktiva)** kontrollerar du att Microsoft.com *visas* i måldomänerna.

Om du anger begränsningar som interagerar med de här inställningarna ska du se till att utesluta Azure Active Directory **för den moderna arbetsplatsen-tjänsten.** Om du till exempel har en princip för villkorsstyrd åtkomst som förhindrar gästkonton från att komma åt Intune-portalen ska du utesluta gruppen **Tjänstkonton** för modern arbetsplats från den här principen.

## <a name="steps-to-get-ready"></a>Steg för att förbereda dig

1. Läs [Förutsättningar för Microsoft Hanterat skrivbord](prerequisites.md).
2. Använd [verktygen för beredskapsbedömning](readiness-assessment-tool.md).
3. [Krav för gästkonton](guest-accounts.md) (den här artikeln)
4. [Nätverkskonfiguration för Microsoft Hanterat skrivbord](network.md)
5. [Förbereda certifikat och nätverksprofiler för Microsoft Hanterat skrivbord](certs-wifi-lan.md)
6. [Förbereda åtkomst till lokala resurser för Microsoft Hanterat skrivbord](authentication.md)
7. [Appar i Microsoft Hanterat skrivbord](apps.md)
8. [Förbereda mappade enheter för Microsoft Hanterat skrivbord](mapped-drives.md)
9. [Förbereda utskriftsresurser för Microsoft Hanterat skrivbord](printing.md)
