---
title: Om AutoPilot-profilinställningar
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Med AutoPilot-profiler kan du styra hur Windows installeras på användarenheter. Profilerna innehåller standardinställningar och valfria inställningar som hoppa över Cortana-installation.
ms.openlocfilehash: 86f8718131f0a0b93e18e65e39e02e7d65aded1a
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578516"
---
# <a name="about-autopilot-profile-settings"></a>Om AutoPilot-profilinställningar

## <a name="autopilot-profile-settings"></a>AutoPilot-profilinställningar

Du kan använda AutoPilot-profiler för att styra hur Windows installeras på användarenheter. Profilerna innehåller följande inställningar.
  
 **Standardfunktioner för AutoPilot (obligatoriskt) som konfigureras automatiskt:**
  
|**Inställning**|**Beskrivning**|
|:-----|:-----|
|Hoppa över Cortana, OneDrive och OEM-registrering  <br/> |Hoppar över installationen av konsumentappar som Cortana och personliga OneDrive-konton. Enhetens användare kan installera dem senare om användaren är lokal administratör på enheten. Tillverkarregistreringen hoppas över eftersom enheten hanteras av Microsoft 365 Business Premium.  <br/> |
|Inloggning med företagets varumärke  <br/> |Om ditt företag har en inloggningssida för Lägg till ditt företag på inloggningssidan för [Microsoft 365](../admin/setup/customize-sign-in-page.md)får enhetsanvändaren den upplevelsen när de loggar in.  <br/> |
|Automatisk MDM-registrering med konfigurerade AAD-konton  <br/> |Användaridentiteten hanteras av Azure Active Directory och användarna loggar in på Windows och Microsoft 365 med inloggningsuppgifterna för Microsoft 365 Business Premium.  <br/> |
   
 **Valfria inställningar**
  
|**Inställning**|**Beskrivning**|
|:-----|:-----|
|Hoppa över sekretessinställningar (av som standard)  <br/> |Om alternativet **På** har valts ser enhetens användare inte licensavtalet för enheten och Windows när användaren loggar in första gången.  <br/> |
|Tillåt inte användaren att bli lokal administratör  <br/> |Om alternativet **På** har valts kan enhetens användare inte installera personliga appar som till exempel Cortana.<br/> |
