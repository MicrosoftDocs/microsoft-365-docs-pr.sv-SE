---
title: Skapa och hantera roller för rollbaserad åtkomstkontroll
description: Skapa roller och definiera de behörigheter som tilldelas till rollen som en del av den rollbaserade implementeringen av åtkomstkontroll i Microsoft Defender Säkerhetscenter
keywords: användarroller, roller, åtkomst till rbac
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
ms.openlocfilehash: 932fd6ecd7dca66f4cb587b226474109c788c341
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073986"
---
# <a name="create-and-manage-roles-for-role-based-access-control"></a>Skapa och hantera roller för rollbaserad åtkomstkontroll

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-roles-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="create-roles-and-assign-the-role-to-an-azure-active-directory-group"></a>Skapa roller och tilldela rollen till en Azure Active Directory grupp

I följande steg får du veta hur du skapar roller i Microsoft Defender Säkerhetscenter. Den förutsätter att du redan har Azure Active Directory användargrupper.

1. Logga in på [Microsoft Defender Säkerhetscenter](https://securitycenter.windows.com/) konto med en säkerhetsadministratör eller global administratörsroll tilldelad.

2. I navigeringsfönstret väljer du **Inställningar > Roller**.

3. Välj **Lägg till objekt.**

4. Ange det rollnamn, den beskrivning och de behörigheter som du vill tilldela rollen.

5. Välj **Nästa** för att tilldela rollen till en Azure AD-säkerhetsgrupp.

6. Använd filtret för att välja den Azure AD-grupp som du vill lägga till den här rollen i.

7. **Spara och stäng**.

8. Använd konfigurationsinställningarna.

> [!IMPORTANT]
> När du har skapat roller måste du skapa en enhetsgrupp och ge åtkomst till enhetsgruppen genom att tilldela den till en roll som du just har skapat.

### <a name="permission-options"></a>Behörighetsalternativ

- **Visa data**
    - **Säkerhetsåtgärder** – visa alla data i säkerhetsåtgärder i portalen
    - **Hot och hantering av säkerhetsrisker** – Hantering av hot och säkerhetsrisker data i portalen

- **Aktiva åtgärdsåtgärder**
    - **Säkerhetsåtgärder** – Vidta svarsåtgärder, godkänna eller stänga väntande åtgärder, hantera tillåtna/blockerade listor för automatisering och indikatorer
    - **Hot och hantering av säkerhetsrisker – Undantagshantering** – Skapa nya undantag och hantera aktiva undantag
    - **Hot och hantering av säkerhetsrisker - Åtgärdshantering** - Skicka in nya begäran om åtgärder, skapa ärenden och hantera befintliga åtgärdsaktiviteter

- **Undersökning av aviseringar** – Hantera aviseringar, initiera automatiska undersökningar, köra genomsökningar, samla in undersökningspaket, hantera enhetstaggar och ladda ned endast bärbara körbara filer (PE) 

- **Hantera systeminställningar för portal** - Konfigurera lagringsinställningar, SIEM och hot-API-inställningar (gäller globalt), avancerade inställningar, automatiska filuppladdningar, roller och enhetsgrupper

    > [!NOTE]
    > Den här inställningen är endast tillgänglig i rollen Microsoft Defender för slutpunktsadministratör (standard).

- **Hantera säkerhetsinställningar i Säkerhetscenter** – Konfigurera inställningar för aviseringssäkerhet, hantera mapp undantas för automatisering, onboard och offboard-enheter, och hantera e-postaviseringar, hantera utvärderingslabb

- **Funktioner för livesvar**
    - **Grundläggande** kommandon:
        - Starta en svarssession i livesändning
        - Utföra skrivskyddade svarskommandon på en fjärrenhet (exklusive filkopiering och körning)
    - **Avancerade** kommandon:
        - Ladda ned en fil från fjärrenheten via livesvar
        - Ladda ned PE- och icke-PE-filer från filsidan
        - Upload en fil till fjärrenheten
        - Visa ett skript från filbiblioteket
        - Köra ett skript på fjärrenheten från filbiblioteket

Mer information om tillgängliga kommandon finns i Undersöka [enheter med Live Response.](live-response.md)
  
## <a name="edit-roles"></a>Redigera roller

1. Logga in på [Microsoft Defender Säkerhetscenter](https://securitycenter.windows.com/) konto med rollen Säkerhetsadministratör eller Global administratör tilldelad.

2. I navigeringsfönstret väljer du **Inställningar > Roller**.

3. Välj den roll som du vill redigera.

4. Klicka på **Redigera**.

5. Ändra informationen eller grupperna som har tilldelats rollen. 

6. Klicka **på Spara och stäng**.

## <a name="delete-roles"></a>Ta bort roller

1. Logga in på [Microsoft Defender Säkerhetscenter](https://securitycenter.windows.com/) konto med rollen Säkerhetsadministratör eller Global administratör tilldelad.

2. I navigeringsfönstret väljer du **Inställningar > Roller**.

3. Välj den roll du vill ta bort.

4. Klicka på listrutan och välj Ta **bort roll.**

## <a name="related-topic"></a>Relaterat ämne

- [Grundläggande behörigheter för åtkomst till portalen](basic-permissions.md)
- [Skapa och hantera enhetsgrupper](machine-groups.md)
