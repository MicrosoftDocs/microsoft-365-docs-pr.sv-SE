---
title: Distribuera appar till enheter
description: Information om hur du lägger till och distribuerar appar till Microsoft Managed Desktop-enheter.
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation, appar, verksamhetsbaserade appar, verksamhetsbaserade appar
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8bfc53d46bdcb91c16e9f4a1ddbc8ab3f6dfb47e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922032"
---
# <a name="deploy-apps-to-devices"></a>Distribuera appar till enheter
I onboarding till Microsoft Managed Desktop ingår att lägga till och distribuera appar till användarens enheter. När du använder Microsoft Managed Desktop-portalen kan du lägga till och distribuera dina program. 

Den övergripande processen ser ut så här:
1. [Lägga till](#1) appar i Microsoft Managed Desktop-portalen – Det kan vara befintliga verksamhetsbaserade appar (LOB) eller appar från Microsoft Store för företag som du synkroniserat med Intune. 
2. [Skapa Azure Active Directory-grupper (AD) för apptilldelning](#2) – Du använder grupperna för att hantera apptilldelning.
3. [Tilldela dina användare appar](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Steg 1: Lägga till appar i Microsoft Managed Desktop-portalen
Du kan lägga [till Win32- eller Windows MSI-baserade](#lob-apps)appar eller [Microsoft Store](#msfb-apps) för företag-appar till Microsoft Managed Desktop och sedan distribuera dem till Microsoft Managed Desktop-enheter.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32- eller Windows MSI-baserade appar för Microsoft Hanterat skrivbord

Du kan lägga till dina verksamhetsbaserade appar (LOB) i Microsoft Managed Desktop-portalen. Information om krav för appar som installeras på Microsoft Managed Desktop-enheter finns i [Krav för Microsoft Managed Desktop-appar.](../service-description/mmd-app-requirements.md)

I den här proceduren väljer du vilken typ av program du vill lägga till och konfigurerar och laddar sedan upp programkällan. 

**Så här lägger du till din LOB-app eller Windows-app i Microsoft Managed Desktop-portalen**

Du kan logga in på Microsoft Managed Desktop-portalen eller logga in på Intune och sedan söka efter Microsoft Managed Desktop. Vi visar inloggning på Microsoft Managed Desktop-portalen. 

1.    Logga in på [Microsoft Managed Desktop Admin-portalen](https://aka.ms/mmdportal). 
2.    Under **Lager** väljer du **Appar**.
3.    I apparbetsbelastningen väljer du Lägg **till**.
4.    Välj **Verksamhetslinje** **för företagsapp eller Windows-app** **(Win32) i** Lägg till app.
    - Om du valde Verksamhetsbaserade **appar**, se Lägga till en Windows-företagsapp i [Microsoft Intune](/intune/lob-apps-windows) för instruktioner om att lägga till och konfigurera verksamhetsbaserade appar.
    - Om du valde **Windows-app (Win32) finns** instruktioner om hur du lägger till och konfigurerar Windows-appar i [Win32-apphantering.](/intune/apps-win32-app-management)

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Microsoft Store för företag-appar
Om du inte har registrerat dig för Microsoft Store för företag kan du registrera dig när du handlar för appar. När du har dina appar kan du synkronisera dem med Microsoft Hanterat skrivbord. 

**Köpa appar från Microsoft Store för företag**

1. Logga in på [Microsoft Store för företag med](https://businessstore.microsoft.com) ditt administratörskonto för Microsoft Store för företag.
2. Välj **Köp för min grupp**.
3. Använd Sök för att hitta den app du vill använda och välj sedan appen.
4. Välj Skaffa appen på **produktinformationen.** Microsoft Store lägger till appen i **Dina produkter** för din organisation.

**Tvinga fram synkronisering mellan Intune och Microsoft Store för företag**
1. Logga in på [administrationscentret för Microsoft Endpoint Manager.](https://go.microsoft.com/fwlink/?linkid=2109431)
2. Välj **Kopplingar för**  >  **klientorganisationsadministration och token** Microsoft Store för  >  **företag.**
3. Välj **Synkronisera** för att hämta de appar som du har köpt från Microsoft Store till Intune.

**Så här verifierar du att en synkronisering mellan Intune och Microsoft Store för företag är aktiv**
1. Logga in på [Microsoft Store för företag med](https://businessstore.microsoft.com) ditt administratörskonto för Microsoft Store för företag.
2. Välj **Hantera**.
3. Välj **Inställningar** och sedan **Distribuera**.
4. Under **Hanteringsverktyg** kontrollerar du att Intune visas och att statusen är **Aktiv**.  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Steg 2: Skapa Azure AD-grupper

Skapa tre Azure AD-grupper för varje app. I den här tabellen visas de grupper du behöver (Tillgänglig, Obligatoriskt och Avinstallera). 

Apptilldelningstyp |    Gruppanvändning    | Exempel på Azure AD-namn
--- | --- | ---
Kan användas |  Appen kommer att vara tillgänglig från företagsportalappen eller -webbplatsen. | MMD – *appnamn* – tillgänglig
Obligatoriskt |  Appen installeras på enheter i de valda grupperna. | MMD – *appnamn* – obligatoriskt
Avinstallera |  Appen avinstalleras från enheter i de valda grupperna. | MMD – *appnamn* – Avinstallera

Lägg till användarna i de här grupperna för att antingen göra programmet tillgängligt, installera appen eller ta bort appen från sin Microsoft Managed Desktop-enhet. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Steg 3: Tilldela appar till användarna

**Så här tilldelar du appen till användarna**

1. Logga in på [Microsoft Managed Desktop Admin-portalen](https://aka.ms/mmdportal).
2. Välj Appar i fönstret **Hanterat skrivbord.**
3. I apparbetsbelastningen väljer du det program du vill tilldela användare till och väljer **Tilldela användare grupper.**
4. För den specifika appen väljer du en uppgiftstyp (Tillgänglig, Obligatoriskt, Avinstallera) och tilldelar lämplig grupp.
5. I fönstret Tilldela appar väljer du **OK.**


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Steg för att komma igång med Microsoft Managed Desktop

1. [Lägga till och verifiera administratörskontakter i administratörsportalen](add-admin-contacts.md)
2. [Justera villkorsstyrd åtkomst](conditional-access.md)
3. [Koppla licenser](assign-licenses.md)
4. [Distribuera Intune-företagsportalen](company-portal.md)
5. [Aktivera Enterprise State Roaming](enterprise-state-roaming.md)
6. [Konfigurera enheter](set-up-devices.md)
7. [Gör användarna redo att använda enheter](get-started-devices.md)
8. Distribuera program (det här avsnittet)


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->