---
title: Api för att lägga till eller ta bort maskintaggar
description: Lär dig hur du använder API:t för att lägga till eller ta bort maskintaggar för att lägga till eller ta bort en tagg för en dator i Microsoft Defender för Slutpunkt.
keywords: apis, graph api, API som stöds, taggar, maskintaggar
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 98dd513cc66683ff1b95f66d6d7b89916ce54bab
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199783"
---
# <a name="add-or-remove-machine-tags-api"></a>Api för att lägga till eller ta bort maskintaggar

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-beskrivning

Lägger till eller tar bort en tagg till en viss [dator.](machine.md)

## <a name="limitations"></a>Begränsningar

1. Du kan publicera på datorer som senast sågs enligt din konfigurerade lagringstid.

2. Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.


## <a name="permissions"></a>Behörigheter

En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i [Använda Defender för slutpunkts-API:er](apis-intro.md)

Behörighetstyp |    Behörighet    |    Visningsnamn för behörighet
:---|:---|:---
Program |    Machine.ReadWrite.All |    "Läsa och skriva all maskininformation"
Delegerat (arbets- eller skolkonto) | Machine.ReadWrite | Maskininformation för läsning och skrivning

>[!Note]
> När du skaffar en token med hjälp av användarautentiseringsuppgifter:
>
>- Användaren måste ha minst följande rollbehörighet: "Hantera säkerhetsinställning". Mer information finns i [Skapa och hantera roller.](user-roles.md)
>- Användaren måste ha åtkomst till datorn baserat på datorns gruppinställningar (mer information finns i [Skapa och](machine-groups.md) hantera datorgrupper)

## <a name="http-request"></a>HTTP-begäran

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
```

## <a name="request-headers"></a>Begäran om rubriker

Namn | Skriv | Beskrivning
:---|:---|:---
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt.**
Innehållstyp | sträng | application/json. **Obligatoriskt.**

## <a name="request-body"></a>Begärans brödtext

Ange följande parametrar för ett JSON-objekt i begärans brödtext:

Parameter |    Skriv    | Beskrivning
:---|:---|:---
Värde |    Sträng |    Taggnamnet. **Obligatoriskt.**
Åtgärd    | Uppräkning |    Lägg till eller ta bort. Tillåtna värden är: "Lägg till" eller "Ta bort". **Obligatoriskt.**


## <a name="response"></a>Svar

Om svaret lyckas returnerar den här metoden 200 – OK-svarskod och den uppdaterade datorn i svarstexten.

## <a name="example"></a>Exempel

**Begäran**

Här är ett exempel på en begäran som lägger till en maskintagg.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- Om du vill ta bort datortaggen ställer du in åtgärden på Ta bort i stället för Lägg till i begärans brödtext.
