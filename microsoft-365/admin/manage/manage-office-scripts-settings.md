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
description: Läs om hur du Office skriptinställningar för användare i organisationen.
ms.openlocfilehash: e0cb52c4a8f48ff2310c83ffce61e08a0236ed59
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572315"
---
# <a name="manage-office-scripts-settings"></a>Hantera inställningar för Office-skript

[Office skript gör](/office/dev/scripts)det möjligt för användare att automatisera uppgifter genom att spela in, redigera och köra skript i Excel på webben. Office Skript fungerar med Power Automate och användare kör skript på arbetsböcker med hjälp av Excel Online (Business) -anslutningen. Microsoft 365 administratörer kan hantera Office skriptinställningar från Microsoft 365 administrationscenter.

## <a name="before-you-begin"></a>Innan du börjar

- Om du Office skriptinställningar måste du vara global administratör. Mer information finns i [Om administratörsroller](../add-users/about-admin-roles.md).

- Se till att användare i organisationen har en giltig licens för en Microsoft 365- eller Office 365-abonnemang eller EDU-plan som innehåller åtkomst till Office-skrivbordsappar, till exempel något av följande planer:

    - Microsoft 365 Business Standard
    - Microsoft 365-applikationer för affärsverksamhet
    - Microsoft 365-applikationer för företag
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Hantera tillgänglighet Office skript och delning av skript

1. Gå Microsoft 365 administrationscentret i Inställningar  \> **fliken** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Organisationsinställningar.</a>

2. Välj **Office skript**.

3. Office Skript är aktiverat som standard och alla i organisationen kan komma åt och använda funktionen och dela skript. Om du vill Office skript för din organisation **avmarkera** du kryssrutan Låt användarna automatisera sina uppgifter Excel på webben skript.

4. Om du tidigare har inaktiverat Office Scripts för din organisation och vill aktivera den igen väljer **du Låt användarna automatisera sina uppgifter i Excel på webben** och anger sedan vem som kan komma åt och använda funktionen:

    - Om du vill att alla användare i organisationen ska kunna komma åt och Office skript lämnar **du** Alla (standard) markerade.

    - Om du bara vill att medlemmar i en viss grupp ska kunna komma åt och använda Office Scripts väljer **du Specifik grupp** och anger sedan gruppens namn eller e-postalias för att lägga till den i listan över tillåtna. Du kan bara lägga till en grupp i listan över tillåtna och det måste vara en av följande typer:
        - Microsoft 365 grupp
        - Distributionsgrupp
        - Säkerhetsgrupp
        - E-postaktiverad säkerhetsgrupp
    
        Mer information om de olika typerna av grupper finns i [Jämföra grupper](../create-groups/compare-groups.md).

5. Om du vill att användare med åtkomst till Office Scripts ska kunna dela sina skript med andra i organisationen väljer **du Låt användare med åtkomst till Office Scripts dela sina skript med andra i organisationen**. Det är inte tillåtet att dela skript utanför en organisation.
 
    > [!NOTE]
    > Om du senare inaktiverar skriptdelning för din organisation kan användarna fortfarande köra tidigare delade skript.
 
6. Ange vilka användare med åtkomst till Office skript som kan dela sina skript:
    
    - Om du vill att alla användare med Office skript ska kunna dela sina skript **lämnar du** Alla (standard) markerade.

    - Om du bara vill att medlemmar i en viss grupp med åtkomst till Office Scripts ska kunna dela sina skript väljer du **Specifik grupp** och anger sedan gruppens namn eller e-postalias för att lägga till det i listan över tillåtna. Du kan bara lägga till en grupp i listan över tillåtna och det måste vara en av följande typer:
        - Microsoft 365 grupp
        - Distributionsgrupp
        - Säkerhetsgrupp
        - E-postaktiverad säkerhetsgrupp
    
        Mer information om de olika typerna av grupper finns i [Jämföra grupper](../create-groups/compare-groups.md).

7. Om du vill tillåta användare att köra sina Office-skript i Power Automate-flöden väljer **du Låt användare med åtkomst till Office Scripts köra sina skript med Power Automate**. Detta gör det möjligt för användare att lägga [till flödessteg Excel skriptalternativet Business( Business) Connector's](/connectors/excelonlinebusiness) **Run.**

    - Om du vill att alla användare med Office skript ska kunna använda sina skript i flöden **lämnar du** Alla (standard) markerade.

    - Om du bara vill att medlemmar i en viss grupp med åtkomst till Office Scripts ska kunna använda sina skript i flöden väljer **du Specifik grupp** och anger sedan gruppens namn eller e-postalias för att lägga till det i listan över tillåtna. Du kan bara lägga till en grupp i listan över tillåtna och det måste vara en av följande typer:
        - Microsoft 365 grupp
        - Distributionsgrupp
        - Säkerhetsgrupp
        - E-postaktiverad säkerhetsgrupp

        Mer information om de olika typerna av grupper finns i [Jämföra grupper](../create-groups/compare-groups.md).

    - Mer information om hur du Office använda Power Automate med Office [skript med Power Automate](/office/dev/scripts/develop/power-automate-integration).

8. Välj **Spara**.

    Det kan ta upp till 48 timmar innan ändringar Office skriptinställningarna träder i kraft.

## <a name="next-steps"></a>Nästa steg

Eftersom Office-skript fungerar med Power Automate rekommenderar vi att du granskar dina befintliga DLP-principer (Data Loss Prevention) för att säkerställa att organisationens data förblir skyddade medan användarna använder Office skript. Mer information finns i [DLP-principer (Data Loss Prevention).](/power-automate/prevent-data-loss)

## <a name="related-content"></a>Relaterat innehåll

[Office teknisk dokumentation för skript](/office/dev/scripts/) (länksida)\
[Introduktion till Office skript i Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artikel)\
[Dela Office skript Excel för webben](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artikel)\
[Spela in, redigera och Office skript i Excel på webben](/office/dev/scripts/tutorials/excel-tutorial) (artikel)
