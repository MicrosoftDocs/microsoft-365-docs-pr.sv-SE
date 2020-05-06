---
title: Distribuera appar till enheter
description: Information om hur du lägger till och distribuerar appar på Microsoft Managed Desktop-enheter.
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation, appar, företagsspecifika appar, LOB-appar
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9fd6efc56441cfbe8a05404319246c5e0bbe10ab
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046334"
---
# <a name="deploy-apps-to-devices"></a>Distribuera appar till enheter
En del av introduktionen till Microsoft Managed Desktop är att lägga till och distribuera appar på användarens enheter. När du använder Microsoft Managed Desktop-portalen kan du lägga till och distribuera dina appar. 

Den övergripande processen ser ut så här:
1. [Lägg till appar i Microsoft Managed Desktop-portalen](#1) – Det kan vara befintliga LOB-appar (line-of-business) eller appar från Microsoft Store för företag som du har synkroniserat med Intune. 
2. [Skapa Azure Active Directory (AD) grupper för apptilldelning](#2) - Du använder dessa grupper för att hantera apptilldelning.
3. [Tilldela appar till användarna](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Steg 1: Lägga till appar i Microsoft Managed Desktop-portalen
Du kan lägga till [Win32- eller Windows MSI-baserade appar](#lob-apps)eller [Microsoft Store för företag-appar](#msfb-apps) på Microsoft Managed Desktop och sedan distribuera dem på Microsoft Managed Desktop-enheter.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32- eller Windows MSI-baserade appar till Microsoft Managed Desktop

Du kan lägga till dina LOB-appar (line-of-business) i Microsoft Managed Desktop-portalen. Information om krav för appar som är installerade på Microsoft Hanterade stationära enheter finns i [microsofts appkrav för hanterade skrivbord](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).

I den här proceduren väljer du vilken typ av app du vill lägga till och konfigurerar och laddar sedan upp appkällan. 

**Så här lägger du till din LOB-app eller Windows-app i Microsoft Managed Desktop-portalen**

Du kan logga in på Microsoft Managed Desktop-portalen eller logga in på Intune och sedan söka efter Microsoft Managed Desktop. Vi visar inloggning på Microsoft Managed Desktop-portalen. 

1.    Logga in på [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal). 
2.    Under **Lager**väljer du **Appar**.
3.    Välj **Lägg till**i arbetsbelastningen Appar .
4.    Välj **Line-of-business-app** eller **Windows-app (Win32) i** **Lägg till**app .
    - Om du har valt **Line-of-business-app**läser du [Lägga till en Windows-business-app i Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) för instruktioner om hur du lägger till och konfigurerar affärsappar.
    - Om du har valt **Windows-app (Win32)** läser du [Win32-apphanteringen](https://docs.microsoft.com/intune/apps-win32-app-management) för instruktioner om hur du lägger till och konfigurerar Windows-appar.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Microsoft Store för företag-appar
Om du inte har registrerat dig hos Microsoft Store för företag kan du registrera dig när du handlar för appar. När du har dina appar kan du synkronisera dem med Microsoft Managed Desktop. 

**Så här köper du appar från Microsoft Store för företag**

1. Logga in på [Microsoft Store för företag](https://businessstore.microsoft.com) med ditt Microsoft Store för företag-administratörskonto.
2. Välj **Handla för min grupp**.
3. Använd Sök för att hitta den app du vill ha och välj appen.
4. På produktinformationen väljer du **Hämta appen**. Microsoft Store lägger till appen i **Dina produkter** för din organisation.

**Så här tvingar du fram en synkronisering mellan Intune och Microsoft Store för företag**
1. Logga in på [Azure Portal](https://portal.azure.com/) som Intune Admin eller Global Admin för din klientorganisation
2. Välj **Alla tjänster > Intune**. Intune finns i avsnittet Övervakning + Hantering.
3. Välj **Klientappar**i fönstret Intune och välj sedan **Microsoft Store för företag**.
4. Välj **Aktivera** om du vill synkronisera dina Microsoft Store för företag-appar med Intune.
    - Om du inte redan har gjort det kan du registrera och koppla ditt Microsoft Store för företag-konto till Intune
    - Välj det språk som appar från Microsoft Store för företag ska visas i Intune-konsolen
    - Välj **Synkronisera om** du vill synkronisera dina Microsoft Store för företag-appar med Intune.
    - Kontrollera att synkroniseringen mellan Microsoft Store för företag och Intune är aktiv (nästa steg). 

**Så här kontrollerar du att en synkronisering mellan Intune och Microsoft Store för företag är aktiv**
1. Logga in på [Microsoft Store för företag](https://businessstore.microsoft.com) med ditt Microsoft Store för företag-administratörskonto.
2. Välj **Hantera**.
3. Välj **Inställningar** och välj sedan **Distribuera**.
4. Kontrollera att Intune visas under **Hanteringsverktyg**och att statusen är **Aktiv**.  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Steg 2: Skapa Azure AD-grupper

Skapa tre Azure AD-grupper för varje app. I den här tabellen beskrivs de grupper du behöver (Tillgänglig, Obligatorisk och Avinstallera). 

Typ av apptilldelning |    Gruppanvändning    | Exempel på Azure AD-namn
--- | --- | ---
Kan användas |  Appen kommer att vara tillgänglig från Company Portal app eller webbplats. | MMD – *appnamn* – Tillgängligt
Obligatoriskt |  Appen installeras på enheter i de valda grupperna. | MMD – *appnamn* – Obligatoriskt
Avinstallera |  Appen avinstalleras från enheter i de valda grupperna. | MMD – *appnamn* – Avinstallera

Lägg till användarna i dessa grupper för att antingen göra appen availabe, installera appen eller ta bort appen från sin Microsoft Managed Desktop-enhet. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Steg 3: Tilldela appar till användarna

**Så här tilldelar du appen till användarna**

1. Logga in på [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).
2. Välj **Appar**i fönstret Hanterade skrivbord .
3. I arbetsbelastningen Appar väljer du den app som du vill tilldela användare till och väljer **Tilldela användargrupper**.
4. För den specifika appen väljer du en tilldelningstyp (Tillgänglig, Obligatorisk, Avinstallera) och tilldelar lämplig grupp.
5. Välj **OK**i fönstret Tilldela appar .


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Steg för att komma igång med Microsoft Managed Desktop

1. [Lägga till och verifiera administratörskontakter i administratörsportalen](add-admin-contacts.md)
2. [Justera villkorsstyrd åtkomst](conditional-access.md)
3. [Tilldela licenser](assign-licenses.md)
4. [Distribuera Intune-företagsportalen](company-portal.md)
5. [Aktivera Enterprise State Roaming](enterprise-state-roaming.md)
6. [Konfigurera enheter](set-up-devices.md)
7. [Gör användarna redo att använda enheter](get-started-devices.md)
8. Distribuera appar (det här avsnittet)


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
