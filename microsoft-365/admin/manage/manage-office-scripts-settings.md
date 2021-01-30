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
description: Lär dig hur du hanterar inställningar för Office-skript för användare i organisationen.
ms.openlocfilehash: 75d0a9d9e98652fc11eab7e8a7d6c826be031f6e
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058429"
---
# <a name="manage-office-scripts-settings"></a>Hantera inställningar för Office-skript

Med Office-skript kan användare automatisera uppgifter genom att spela in, redigera och köra skript i Excel på webben. Office-skript fungerar med Power Automate och användare kör skript på arbetsböcker med hjälp av Excel Online-kopplingen (företag). Microsoft 365-administratörer kan hantera inställningar för Office-skript från administrationscentret för Microsoft 365.

## <a name="before-you-begin"></a>Innan du börjar

- Du måste vara global administratör för att kunna hantera inställningar för Office-skript. Mer information finns i Om [administratörsroller.](../add-users/about-admin-roles.md)

- Se till att användarna i organisationen har en giltig licens för kommersiella Microsoft 365- eller Office 365-abonnemang eller EDU-abonnemang som omfattar åtkomst till Office-skrivbordsprogram, till exempel något av följande abonnemang:

    - Microsoft 365 Business Standard
    - Microsoft 365-applikationer för affärsverksamhet
    -  Microsoft 365 Apps för företag
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Hantera tillgängligheten för Office-skript och delning av skript

1. Gå till fliken Inställningar för organisationsinställningar  i administrationscentret för Microsoft 365. \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank"></a>

2. Välj **Office-skript.**

3. Office-skript är aktiverat som standard och alla i organisationen kan komma åt och använda funktionen och dela skript. Om du vill inaktivera Office-skript för organisationen avmarkerar du kryssrutan Låt användare **automatisera sina uppgifter i Excel på** webben.

4. Om du tidigare har inaktiverat Office-skript för organisationen och du vill aktivera det igen väljer du Låt användare automatisera sina uppgifter i **Excel** på webben och anger sedan vem som kan komma åt och använda funktionen:

    - Om du vill ge alla användare i organisationen åtkomst till och använda Office-skript lämnar du **Alla** (standardinställningen) markerad.

    - Om du bara vill ge medlemmar i en viss grupp åtkomst till och använda Office-skript väljer du Specifik grupp och anger sedan namnet eller e-postaliaset för gruppen för att lägga till den i listan över tillåtna grupper. Du kan bara lägga till en grupp i listan över tillåtna grupper och det måste vara någon av följande typer:
        - Microsoft 365-grupp
        - Distributionsgrupp
        - Säkerhetsgrupp
        - E-postaktiverad säkerhetsgrupp
    
        Mer information om de olika typerna av grupper finns i [Jämför grupper.](../create-groups/compare-groups.md)

5. Om du vill låta användare med åtkomst till Office-skript dela sina skript med andra i organisationen väljer du Låt användare med åtkomst till **Office-skript** dela sina skript med andra i organisationen. Det går inte att dela skript utanför en organisation.
 
    > [!NOTE]
    > Om du senare inaktiverar skriptdelning för organisationen kan användarna fortfarande köra skript som delats tidigare.
 
6. Ange vilka användare som har åtkomst till Office-skript kan dela sina skript:
    
    - Om du vill tillåta att alla användare med åtkomst till Office-skript kan dela sina skript lämnar du **Alla** (standardinställningen) markerad.

    - Om du bara vill låta medlemmar i en viss grupp med åtkomst till Office-skript dela sina skript väljer du Specifik grupp och anger sedan namnet eller e-postaliaset för gruppen för att lägga till den i listan över tillåtna. Du kan bara lägga till en grupp i listan över tillåtna grupper och det måste vara någon av följande typer:
        - Microsoft 365-grupp
        - Distributionsgrupp
        - Säkerhetsgrupp
        - E-postaktiverad säkerhetsgrupp
    
        Mer information om de olika typerna av grupper finns i [Jämför grupper.](../create-groups/compare-groups.md)

7. Om du vill tillåta användare att köra Office-skript i Power Automate-flöden väljer du Låt användare med åtkomst till Office-skript köra sina skript **med Power Automate.** På så sätt kan användarna lägga till flödessteg med [körskriptalternativet för Excel Online (företag).](/connectors/excelonlinebusiness) 

    - Om du vill tillåta alla användare med åtkomst till Office-skript att använda sina skript i flöden lämnar du **Alla** (standardinställningen) markerad.

    - Om du bara vill låta medlemmar i en viss grupp med åtkomst till Office-skript använda sina skript i flöden väljer du Specifik grupp och anger sedan namnet eller e-postaliaset för gruppen för att lägga till den i listan över tillåtna. Du kan bara lägga till en grupp i listan över tillåtna grupper och det måste vara någon av följande typer:
        - Microsoft 365-grupp
        - Distributionsgrupp
        - Säkerhetsgrupp
        - E-postaktiverad säkerhetsgrupp

        Mer information om de olika typerna av grupper finns i [Jämför grupper.](../create-groups/compare-groups.md)

    - Mer information om hur du använder Office-skript med Power Automate, inklusive hur principer för skydd mot dataförlust kan påverkas, finns i Köra Office-skript med [Power Automate.](/office/dev/scripts/develop/power-automate-integration)

8. Välj **Spara**.

    Det kan ta upp till 48 timmar innan ändringarna av inställningarna för Office-skript verkställs.

## <a name="next-steps"></a>Nästa steg

Eftersom Office Scripts fungerar med Power Automate rekommenderar vi att du granskar befintliga DLP-principer (dataförlustskydd) för att säkerställa att organisationens data skyddas när användarna använder Office-skript. Mer information finns i [DLP-principer (Data Loss Prevention).](/power-automate/prevent-data-loss)

## <a name="related-content"></a>Relaterat innehåll

[Teknisk dokumentation för Office Scripts](/office/dev/scripts/) (länksida)\
[Introduktion till Office-skript i Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artikel)\
[Dela Office-skript i Excel för webben](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artikeln)\
[Spela in, redigera och skapa Office-skript i Excel på webben](/office/dev/scripts/tutorials/excel-tutorial) (artikel)
