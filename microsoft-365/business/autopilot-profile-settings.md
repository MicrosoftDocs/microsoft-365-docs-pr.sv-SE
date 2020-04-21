---
title: Om AutoPilot-profilinställningar
f1.keywords:
- NOCSH
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
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: AutoPilot-profiler hjälper dig att styra hur Windows installeras på användarenheter. Profilerna innehåller standardinställningar och valfria inställningar som hoppa över Cortana-installation.
ms.openlocfilehash: 5c2ec3f4c3e0ebc4ea545d11f819c897f414ad52
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627423"
---
# <a name="about-autopilot-profile-settings"></a>Om AutoPilot-profilinställningar

## <a name="autopilot-profile-settings"></a>Profilinställningar för AutoPilot

Du kan använda AutoPilot-profiler för att styra hur Windows är installerat på användarenheter. Profilerna innehåller följande inställningar.
  
 **Standardfunktioner för AutoPilot (obligatoriskt) som konfigureras automatiskt:**
  
|**Inställning**|**Beskrivning**|
|:-----|:-----|
|Hoppa över Cortana-, OneDrive- och OEM-registrering  <br/> |Hoppar över installationen av konsumentappar som Cortana och personliga OneDrive-konton. Enhetsanvändaren kan installera dessa senare så länge användaren är en lokal administratör på enheten. Den ursprungliga tillverkarregistreringen hoppas över eftersom enheten hanteras av Microsoft 365 Business Premium.  <br/> |
|Inloggning med företagets varumärke  <br/> |Om ditt företag har sidan [Lägg till ditt företags varumärke på inloggningssidan för Microsoft 365](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a)får enhetsanvändaren den upplevelsen när du loggar in.  <br/> |
|Automatisk MDM-registrering med konfigurerade AAD-konton  <br/> |Användaridentiteten hanteras av Azure Active Directory och användarna loggar in på Windows och Microsoft 365 med sina Microsoft 365 Business Premium-autentiseringsuppgifter.  <br/> |
   
 **Valfria inställningar**
  
|**Inställning**|**Beskrivning**|
|:-----|:-----|
|Hoppa över sekretessinställningar (av som standard)  <br/> |Om alternativet **På** har valts ser enhetens användare inte licensavtalet för enheten och Windows när användaren loggar in första gången.  <br/> |
|Tillåt inte användaren att bli lokal administratör  <br/> |Om alternativet **På** har valts kan enhetens användare inte installera personliga appar som till exempel Cortana.<br/> |
   
