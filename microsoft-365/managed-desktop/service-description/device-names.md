---
title: Enhetsnamn
description: Hur Microsoft Managed Desktop hanterar enhetsnamn
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: adf4809e0d8dc29f170475435b19092abf2062fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893982"
---
# <a name="device-names"></a>Enhetsnamn

Microsoft Hanterat skrivbord använder Windows Autopilot, Azure Active Directory och Microsoft Intune. För att de här tjänsterna ska kunna samarbeta smidigt måste enheterna ha konsekventa och standardiserade namn. Microsoft Managed Desktop använder ett standardiserat namnformat (av formuläret *MMD-%RAND11)* när enheter registreras. Windows Autopilot tilldelar dessa namn. Mer information om Autopilot finns i [First-run-upplevelsen med Autopilot och registreringsstatussidan.](../get-started/esp-first-run.md)

## <a name="automated-name-changes"></a>Automatiserade namnändringar

Om en enhet byter namn senare byter Microsoft Managed Desktop automatiskt namn på den till ett nytt namn i standardiserat format. Den här processen sker var fjärde timme. Namnändringen sker nästa gång användaren startar om enheten.

> [!IMPORTANT]
> Om din miljö är beroende av specifika enhetsnamn (t.ex. för att stödja en viss nätverkskonfiguration) bör du undersöka olika alternativ för att ta bort beroendet innan du registrerar dig i Microsoft Managed Desktop. Om du måste behålla namnsambandet kan [](../working-with-managed-desktop/admin-support.md) du skicka en begäran via administratörsportalen för att inaktivera namnändringsfunktionen och använda önskat namnformat.