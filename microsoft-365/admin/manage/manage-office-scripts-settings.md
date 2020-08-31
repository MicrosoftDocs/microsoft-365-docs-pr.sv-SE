---
title: Hantera inställningar för Office-skript
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Lär dig hur du hanterar inställningar för Office-skript för användare i din organisation.
ms.openlocfilehash: 12a80f277f6d17a8e7f5228f6948e70b7a93be11
ms.sourcegitcommit: 97ef8f846939c3d31bb0638edf07bb89463ace0b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/28/2020
ms.locfileid: "47300845"
---
# <a name="manage-office-scripts-settings"></a>Hantera inställningar för Office-skript

Med Office-skript kan användare automatisera uppgifter genom att spela in, redigera och köra skript i Excel på webben. Office-skript fungerar med Power autoautomatisera och användare kör skript i arbets böcker genom att använda kopplingen för Excel Online (företag). Microsoft 365-administratörer kan hantera inställningar för Office-skript från administrations centret för Microsoft 365.

## <a name="before-you-begin"></a>Innan du börjar

- För att hantera inställningar för Office-skript måste du vara global administratör. Mer information finns i [om administratörs roller](../add-users/about-admin-roles.md).

- Se till att användare i din organisation har en giltig licens för en Microsoft 365-eller Office 365-prenumeration som omfattar till gång till Office-program, till exempel något av följande:

    - Microsoft 365 Business Standard
    - Microsoft 365-applikationer för affärsverksamhet
    -  Microsoft 365 Apps för företag
    - Office 365 E3
    - Office 365 E5
    - Office 365 a3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Hantera tillgänglighet för Office-skript och delning av skript

1. I administrations centret för Microsoft 365 går du till fliken **Inställningar** \> **organisations inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> .

2. Välj **Office-skript**.

3. Office-skript är aktiverat som standard och alla i organisationen kan komma åt och använda funktionen och dela skript. Om du vill inaktivera Office-skript för organisationen avmarkerar du kryss rutan **Låt användare automatisera sina uppgifter i Excel på webben** .

4. Om du tidigare har inaktiverat Office-skript för organisationen och vill aktivera det igen väljer du **Låt användare automatisera sina uppgifter i Excel på webben**och sedan ange vem som kan komma åt och använda funktionen:

    - Om du vill att alla användare i organisationen ska kunna komma åt och använda Office-skript måste du lämna **alla** (standard) markerade. 

    - Om du bara vill låta medlemmar i en viss grupp komma åt och använda Office-skript väljer du **specifik grupp**och anger sedan namnet eller e-postaliaset för gruppen för att lägga till den i listan Tillåt. Du kan bara lägga till en grupp i listan över tillåtna och det måste vara en av följande typer:
        - Gruppen Microsoft 365
        - Distributions grupp
        - Säkerhetsgrupp
        - E-postaktiverad säkerhetsgrupp
    
        Mer information om de olika typerna av grupper finns i [jämföra grupper](../create-groups/compare-groups.md).

5. Om du vill tillåta användare att få åtkomst till Office-skript för att dela sina skript med andra i organisationen väljer du **Låt användare med åtkomst till Office-skript dela sina skript med andra i organisationen**. Det går inte att dela skript utanför en organisation.
 
    > [!NOTE]
    > Om du senare stänger av skript delning för din organisation kan användarna fortfarande köra tidigare delade skript.
 
6. Ange vilka användare med åtkomst till Office-skript som kan dela sina skript:
    
    - Om du vill att alla användare ska kunna använda Office-skript för att dela sina skript måste du lämna **alla** (standard) markerade.

    - Om du bara vill tillåta medlemmar i en viss grupp med åtkomst till Office-skript för att dela sina skript kan du välja **specifik grupp**och sedan ange namnet eller e-postaliaset för gruppen för att lägga till det i listan Tillåt. Du kan bara lägga till en grupp i listan över tillåtna och det måste vara en av följande typer:
        - Gruppen Microsoft 365
        - Distributions grupp
        - Säkerhetsgrupp
        - E-postaktiverad säkerhetsgrupp
    
        Mer information om de olika typerna av grupper finns i [jämföra grupper](../create-groups/compare-groups.md).

7. Välj **Spara**.

    Det kan ta upp till 48 timmar innan ändringar i inställningarna för Office-skript träder i kraft.

## <a name="next-steps"></a>Nästa steg

Eftersom Office-skript fungerar med Power autoautomatisera rekommenderar vi att du granskar dina befintliga DLP-principer (data förlust) för att säkerställa att organisationens data förblir skyddade medan användare använder Office-skript. Mer information finns i [principer för data förlust skydd (DLP)](/power-automate/prevent-data-loss).

## <a name="related-content"></a>Relaterat innehåll

[Teknisk dokumentation för Office-skript](/office/dev/scripts/) (länk sida) \
[Introduktion till Office-skript i Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artikel) \
[Dela Office-skript i Excel för webben](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artikel) \
[Spela in, redigera och skapa Office-skript i Excel på webben](/office/dev/scripts/tutorials/excel-tutorial) (artikel)