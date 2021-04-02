---
title: Visa och hantera regler för anpassad identifiering i Microsoft Defender ATP
ms.reviewer: ''
description: Lär dig hur du visar och hanterar anpassade identifieringsregler
keywords: anpassade identifieringar, visa, hantera, aviseringar, redigera, köra på begäran, identifieringsregler, avancerad sökning, sökning, fråga, svarsåtgärder, mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b36521ada55fa3d60538beb981d487b153e7b1f9
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498747"
---
# <a name="view-and-manage-custom-detection-rules"></a>Visa och hantera anpassade identifieringsregler

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Hantera dina befintliga [anpassade identifieringsregler för](custom-detection-rules.md) att säkerställa att de effektivt hittar hot och vidtar åtgärder. Lär dig hur du visar listan med regler, kontrollerar deras tidigare körningar och granskar aviseringarna som de har utlöst. Du kan även köra en regel på begäran och ändra den.

## <a name="required-permissions"></a>Behörighet som krävs

För att skapa eller hantera anpassade identifieringar [måste din roll](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) ha behörighet att hantera **säkerhetsinställningar.**

## <a name="view-existing-rules"></a>Visa befintliga regler

Om du vill visa alla befintliga anpassade identifieringsregler går du **till Inställningar**  >  **anpassade identifieringar**. På sidan visas alla regler med följande körningsinformation:

- **Senaste körningen**– när en regel senast körts för att söka efter frågematchningar och generera aviseringar
- **Status för senaste körningen**– om en regel kördes som den ska
- **Nästa körning**– nästa schemalagda körning
- **Status**– om en regel har aktiverats eller inaktiverats

## <a name="view-rule-details-modify-rule-and-run-rule"></a>Visa regeldetaljer, ändra regel och köra regel

Om du vill visa omfattande information om en anpassad identifieringsregel väljer du namnet på regeln i listan med regler **i Inställningar**  >  **Anpassade identifieringar.** En sida om den valda regeln visar följande information:

- Allmän information om regeln, inklusive information om aviseringen, körningsstatus och omfattning
- Lista med utlösta aviseringar
- Lista över utlösande åtgärder

![Sidan Anpassad identifieringsregel](images/atp-custom-detection-rule-details.png)<br>
*Sidan Anpassad identifieringsregel*

Du kan också utföra följande åtgärder på regeln från den här sidan:

- **Kör**– kör regeln direkt. Den här åtgärden återställer också intervallet för nästa körning.
- **Redigera**– ändra regeln utan att ändra frågan
- **Ändra fråga**– redigera frågan under avancerad sökning
- **Aktivera**  /  **Inaktivera –** aktivera regeln eller hindra den från att köras
- **Ta** bort – inaktivera regeln och ta bort den

>[!TIP]
>Om du snabbt vill visa information och vidta åtgärder för ett objekt i en tabell använder du urvalskolumnen [&#10003;] till vänster om tabellen.

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över anpassade identifieringar](overview-custom-detections.md)
- [Skapa identifieringsregler](custom-detection-rules.md)
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Visa och ordna aviseringar](alerts-queue.md)
