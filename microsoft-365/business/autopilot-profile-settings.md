---
title: Om AutoPilot-profilinställningar
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: AutoPilot profiler hjälper dig att styra hur Windows installeras på användarens enheter. Profilerna innehåller standard och valfria inställningar som att hoppa över installationen av Cortana.
ms.openlocfilehash: adc8112861b67fd96a91ff24dc155aeb0c394532
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34071869"
---
# <a name="about-autopilot-profile-settings"></a>Om AutoPilot-profilinställningar

## <a name="autopilot-profile-settings"></a>AutoPilot-profilinställningar

Du kan styra hur Windows installeras på användarenheter med hjälp av AutoPilot-profiler. Profilerna innehåller följande inställningar.
  
 **Standardfunktioner för AutoPilot (obligatoriskt) som konfigureras automatiskt:**
  
|**Inställning**|**Beskrivning**|
|:-----|:-----|
|Hoppa över Cortana, OneDrive och OEM-registrering  <br/> |Hoppar över installationen av konsumentappar som Cortana och personliga OneDrive-konton. Enhetens användare kan installera dem senare om användaren är lokal administratör på enheten. OEM-registreringen hoppas över eftersom enheten hanteras av Microsoft 365 Business.  <br/> |
|Inloggning med företagets varumärke  <br/> |Om ditt företag har en [Lägg till företagets varumärke till sidan Office 365 Logga In](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), få enhet användare som erfarenheter när du loggar in.  <br/> |
|Automatisk MDM-registrering med konfigurerade AAD-konton  <br/> |Användaridentiteten hanteras av Azure Active Directory och användarna loggar in i Windows och Office 365 med sina autentiseringsuppgifter för Microsoft 365 Business.  <br/> |
   
 **Valfria inställningar**
  
|**Inställning**|**Beskrivning**|
|:-----|:-----|
|Hoppa över sekretessinställningar (av som standard)  <br/> |Om alternativet **På** har valts ser enhetens användare inte licensavtalet för enheten och Windows när användaren loggar in första gången.  <br/> |
|Tillåt inte användaren att bli lokal administratör  <br/> |Om alternativet **På** har valts kan enhetens användare inte installera personliga appar som till exempel Cortana.  <br/> |
   
