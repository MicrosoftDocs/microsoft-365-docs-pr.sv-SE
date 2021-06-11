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
description: Lär dig hur du Office skriptinställningar för användare i organisationen.
ms.openlocfilehash: e0cb52c4a8f48ff2310c83ffce61e08a0236ed59
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572315"
---
# <a name="manage-office-scripts-settings"></a>Hantera inställningar för Office-skript

[Office med skript](/office/dev/scripts)kan användare automatisera uppgifter genom att spela in, redigera och köra skript i Excel på webben. Office Skript fungerar med Power Automate och användare kör skript i arbetsböcker med hjälp av kopplingen Excel Online (Företag). Microsoft 365 administratörer kan hantera Office skriptinställningar från Microsoft 365 administrationscenter.

## <a name="before-you-begin"></a>Innan du börjar

- Du måste Office global administratör för att kunna hantera skriptinställningar. Mer information finns i Om [administratörsroller.](../add-users/about-admin-roles.md)

- Se till att användarna i organisationen har en giltig licens för ett Microsoft 365- eller Office 365-kommersiellt abonnemang eller EDU-abonnemang som omfattar åtkomst till Office-skrivbordsprogram, till exempel ett av följande abonnemang:

    - Microsoft 365 Business Standard
    - Microsoft 365-applikationer för affärsverksamhet
    -  Microsoft 365 Apps för företag
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Hantera tillgänglighet Office skript och delning av skript

1. I administrationscentret Microsoft 365 du på fliken Tjänster **Inställningar** \> **Organisationsinställningar.** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank"></a>

2. Välj **Office skript**.

3. Office Skript är aktiverat som standard och alla i organisationen kan komma åt och använda funktionen och dela skript. Om du Office inaktivera skript för organisationen avmarkerar du kryssrutan Låt användare automatisera sina **uppgifter Excel på webben** skript.

4. Om du tidigare har inaktiverat Office-skript för din organisation och du vill aktivera det igen väljer du Låt användare automatisera sina uppgifter i **Excel på webben** och anger sedan vem som kan komma åt och använda funktionen:

    - Om du vill tillåta alla användare i organisationen att komma åt Office och använda skript lämnar du **Alla** (standard) markerat.

    - Om du bara vill tillåta medlemmar i en viss grupp att komma åt och använda Office Scripts väljer du Specifik grupp och anger sedan gruppens namn eller e-postalias för att lägga till den i listan över tillåtna. Du kan bara lägga till en grupp i listan över tillåtna grupper och det måste vara någon av följande typer:
        - Microsoft 365 grupp
        - Distributionsgrupp
        - Säkerhetsgrupp
        - E-postaktiverad säkerhetsgrupp
    
        Mer information om olika typer av grupper finns i [Jämföra grupper.](../create-groups/compare-groups.md)

5. Om du vill ge användare med åtkomst till Office-skript att dela sina skript med andra i organisationen väljer du Låt användare med åtkomst till **Office-skript** dela sina skript med andra i organisationen. Det är inte tillåtet att dela skript utanför en organisation.
 
    > [!NOTE]
    > Om du senare inaktiverar skriptdelning för organisationen kan användarna fortfarande köra skript som har delats tidigare.
 
6. Ange vilka användare som har åtkomst Office skript kan dela sina skript:
    
    - Om du vill tillåta alla användare som har Office att dela sina skript låter du **Alla** (standard) vara markerat.

    - Om du bara vill tillåta medlemmar i en viss grupp med åtkomst till Office Scripts att dela sina skript väljer du Specifik grupp **och** anger sedan namnet eller e-postaliaset för gruppen för att lägga till den i listan över tillåtna. Du kan bara lägga till en grupp i listan över tillåtna grupper och det måste vara någon av följande typer:
        - Microsoft 365 grupp
        - Distributionsgrupp
        - Säkerhetsgrupp
        - E-postaktiverad säkerhetsgrupp
    
        Mer information om olika typer av grupper finns i [Jämföra grupper.](../create-groups/compare-groups.md)

7. Om du vill tillåta att användare kör sina Office-skript i Power Automate-flöden väljer du Låt användare med åtkomst till **Office-skript** köra sina skript med Power Automate . Det gör att användarna kan lägga till flödessteg [med hjälp Excel för Online (Företag) Connectors](/connectors/excelonlinebusiness) **Kör-skriptalternativ.**

    - Om du vill tillåta alla användare som har Office att använda sina skript i flöden lämnar du **Alla** (standard) markerat.

    - Om du bara vill tillåta medlemmar i en viss grupp med åtkomst till Office Scripts att använda sina skript i flöden väljer du Specifik grupp **och** anger sedan namnet eller e-postaliaset för gruppen för att lägga till den i listan över tillåtna. Du kan bara lägga till en grupp i listan över tillåtna grupper och det måste vara någon av följande typer:
        - Microsoft 365 grupp
        - Distributionsgrupp
        - Säkerhetsgrupp
        - E-postaktiverad säkerhetsgrupp

        Mer information om olika typer av grupper finns i [Jämföra grupper.](../create-groups/compare-groups.md)

    - Mer information om hur du Office skript med Power Automate finns i [Köra Office-skript med Power Automate](/office/dev/scripts/develop/power-automate-integration).

8. Välj **Spara**.

    Det kan ta upp till 48 timmar innan ändringar Office inställningarna för skript ska gå i kraft.

## <a name="next-steps"></a>Nästa steg

Eftersom Office-skript fungerar med Power Automate rekommenderar vi att du granskar dina befintliga DLP-principer (Data Loss Prevention) för att säkerställa att organisationens data förblir skyddade medan användare använder Office-skript. Mer information finns i [Principer för skydd mot dataförlust (DLP).](/power-automate/prevent-data-loss)

## <a name="related-content"></a>Relaterat innehåll

[Office den tekniska dokumentationen för skript](/office/dev/scripts/) (länksida)\
[Introduktion till Office skript i Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artikel)\
[Delning Office skript i Excel för webben](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artikel)\
[Spela in, redigera och skapa Office skript i Excel på webben](/office/dev/scripts/tutorials/excel-tutorial) (artikel)
