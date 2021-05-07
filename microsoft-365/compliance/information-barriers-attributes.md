---
title: Attribut för informationsbarriärsprinciper
description: Den här artikeln är en referens för de Azure Active Directory användarkontoattribut som du kan använda för att definiera informationsbarriärsegment.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee410bf455e770087da7999ad2019c17419a8e00
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162122"
---
# <a name="attributes-for-information-barrier-policies"></a>Attribut för informationsbarriärsprinciper

Vissa attribut i Azure Active Directory användas för att segmentera användare. När segmenten har definierats kan de segmenten användas som filter för informationsbarriärprinciper. Du kan till exempel använda **Avdelning** för att definiera segment av användare efter avdelning i din organisation (under förutsättning att det inte finns några enskilda anställda som arbetar för två avdelningar samtidigt).

Den här artikeln beskriver hur du använder attribut med informationsbarriärer och innehåller en lista över attribut som kan användas. Mer information om informationsbarriärer finns i följande resurser:

- [Informationsbarriärer](information-barriers.md)
- [Definiera principer för informationsbarriärer i Microsoft Teams](information-barriers-policies.md)
- [Redigera (eller ta bort) informationsbarriärpolicyer](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>Hur du använder attribut i informationsbarriärprinciper

Attributen som visas i den här artikeln kan användas för att definiera eller redigera användarsegment. Dina definierade segment fungerar som parametrar (så kallade *UserGroupFilter-värden)* i [informationsbarriärprinciper.](information-barriers-policies.md)

1. Bestäm vilket attribut du vill använda för att definiera segment. (Se avsnittet [Referens](#reference) i den här artikeln.)

2. Kontrollera att användarkontona har värden ifyllda för de attribut du valde i steg 1. Visa användarkontoinformation och redigera användarkonton om det behövs för att inkludera attributvärden. 

    - Om du vill redigera flera konton (eller använda PowerShell för att redigera ett enda konto) går du till [Konfigurera användarkontoegenskaper med Office 365 PowerShell.](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)

    - Om du vill redigera ett enda konto kan [du gå till Lägga till eller uppdatera en användares profilinformation med hjälp Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

3. [Definiera segment med PowerShell](information-barriers-policies.md#define-segments-using-powershell), ungefär som i följande exempel:

    |**Exempel**|**Cmdlet**|
    |:----------|:---------|
    | Definiera ett segment som kallas Segment1 med hjälp av attributet Department | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"` |
    | Definiera ett segment som kallas SegmentA med attributet MemberOf (anta att det här attributet innehåller gruppnamn, till exempel "BlueGroup") | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"` |
    | Definiera ett segment med namnet DayAttributrs med ExtensionAttribute1 (anta att det här attributet innehåller befattningar, till exempel "DayTrader") | `New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > När du definierar segment använder du samma attribut för alla dina segment. Om du till exempel definierar vissa segment med *hjälp av Avdelning* definierar du alla segment med hjälp av *Avdelning*. Definiera inte vissa segment med hjälp av *Avdelning och* andra med hjälp *av MemberOf*. Kontrollera att segmenten inte överlappar. varje användare ska tilldelas exakt ett segment.

## <a name="reference"></a>Referens

I följande tabell visas de attribut som du kan använda med informationsbarriärer.

|**Azure Active Directory <br/> (LDAP-visningsnamn)**|**Exchange egenskapsnamn**|
|:---------------------------------------------------------------|:-------------------------|
| Co | Co |
| Company | Company |
| Department | Department |
| ExtensionAttribute1 | CustomAttribute1 |
| ExtensionAttribute2 | CustomAttribute2 |
| ExtensionAttribute3 | CustomAttribute3 |
| ExtensionAttribute4 | CustomAttribute4 |
| ExtensionAttribute5 | CustomAttribute5 |
| ExtensionAttribute6 | CustomAttribute6 |
| ExtensionAttribute7 | CustomAttribute7 |
| ExtensionAttribute8 | CustomAttribute8 |
| ExtensionAttribute9 | CustomAttribute9 |
| ExtensionAttribute10 | CustomAttribute10 |
| ExtensionAttribute11 | CustomAttribute11 |
| ExtensionAttribute12 | CustomAttribute12 |
| ExtensionAttribute13 | CustomAttribute13 |
| ExtensionAttribute14 | CustomAttribute14 |
| ExtensionAttribute15 | CustomAttribute15 |
| MSExchExtensionCustomAttribute1 | ExtensionCustomAttribute1 |
| MSExchExtensionCustomAttribute2 | ExtensionCustomAttribute2 |
| MSExchExtensionCustomAttribute3 | ExtensionCustomAttribute3 |
| MSExchExtensionCustomAttribute4 | ExtensionCustomAttribute4 |
| MSExchExtensionCustomAttribute5 | ExtensionCustomAttribute5 |
| MailNickname | Alias |
| PhysicalDeliveryOfficeName | Office |
| PostalCode | PostalCode |
| ProxyAddresses | EmailAddresses |
| StreetAddress | StreetAddress |
| TargetAddress | ExternalEmailAddress |
| Användningsbeläggning | Användningsbeläggning |
| UserPrincipalName | UserPrincipalName |
| E-post | WindowsEmailAddress |
| Beskrivning | Beskrivning |
| MemberOf | MemberOfGroup |

## <a name="resources"></a>Resurser

- [Definiera principer för informationsbarriärer i Microsoft Teams](information-barriers-policies.md)
- [Felsökning av informationsbarriärer](information-barriers-troubleshooting.md)
- [Informationsbarriärer](information-barriers.md)