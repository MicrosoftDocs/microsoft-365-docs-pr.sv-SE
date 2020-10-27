---
title: Distribuera appar till enheter
description: Information om hur du lägger till och distribuerar program till Microsoft Managed Station ära datorer.
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation, appar, branschspecifika appar, LOB-appar
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eb8b984550f301af9d99e738f6db4623aa2cc86
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769112"
---
# <a name="deploy-apps-to-devices"></a>Distribuera appar till enheter
Del av registrering på Microsoft Managed Desktop inkluderar att lägga till och distribuera appar till din användares enheter. När du använder Microsoft Managed Desktop Portal kan du lägga till och distribuera dina appar. 

Den övergripande processen ser ut så här:
1. [Lägga till program till Microsoft Managed Desktop Portal](#1) -det här kan vara befintliga LOB-appar (Line-of Business) eller appar från Microsoft Store för företag som du har synkroniserat med Intune. 
2. [Skapa Azure Active Directory-grupper (AD) för program tilldelning](#2) – Använd de här grupperna för att hantera program tilldelning.
3. [Tilldela appar till dina användare](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Steg 1: Lägg till program till Microsoft Managed Desktop Portal
Du kan lägga till [Win32-eller Windows MSI-baserade appar](#lob-apps)eller [Microsoft Store för företag-program](#msfb-apps) till Microsoft Managed Desktop, och sedan distribuera dem till Microsoft Managed Station ära enheter.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32-eller Windows MSI-baserade program till Microsoft Managed Desktop

Du kan lägga till dina program för branschspecifika affärer (LOB) på Microsoft Managed Desktop Portal. Information om kraven för program som är installerade på Microsoft-hanterade Station ära enheter finns i [Microsoft Managed Desktop program krav](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).

I den här proceduren väljer du vilken typ av program du vill lägga till och konfigurerar sedan program källan. 

**Så här lägger du till ett LOB-program eller Windows-appen på Microsoft Managed Desktop Portal**

Du kan logga in på Microsoft Managed Desktop portal eller logga in i Intune och sedan söka efter Microsoft Managed Desktop. Vi kommer att visa att du loggar in på Microsoft Managed Desktop Portal. 

1.    Logga in på [administrations portalen för Microsoft Managed Desktop](https://aka.ms/mmdportal). 
2.    Under **lager** väljer du **appar** .
3.    I apparnas arbets belastning väljer du **Lägg till** .
4.    I **Lägg till app** väljer du **line of Business-appen** eller **Windows-programmet (Win32)** .
    - Om du valde **branschspecifika program** kan du läsa [lägga till en Windows line of Business-app i Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) för instruktioner om hur du lägger till och konfigurerar branschspecifika appar.
    - Om du valde **Windows-programmet (Win32)** kan du läsa om hur du lägger till och konfigurerar Windows-appar i [Win32 program hantering](https://docs.microsoft.com/intune/apps-win32-app-management) .

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Microsoft Store för företag-appar
Om du inte har registrerat dig för Microsoft Store för företag kan du registrera dig när du handlar med appar. När du har dina appar kan du synkronisera dem med Microsoft Managed Desktop. 

**Så här köper du program från Microsoft Store för företag**

1. Logga in på [Microsoft Store för företag](https://businessstore.microsoft.com) med ditt administratörs konto för Microsoft Store för företag.
2. Välj **butik för min grupp** .
3. Använd Sök funktionen för att hitta den app du vill använda och välj appen.
4. På produkt uppgifterna väljer du **Hämta appen** . Microsoft Store lägger till appen till **dina produkter** för din organisation.

**Så här tvingar du en synkronisering mellan Intune och Microsoft Store för företag**
1. Logga in i [administrations centret för Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Välj **Tenant administration**  >  **anslutningar för innehavaradministration och tokens**  >  **Microsoft Store för företag** .
3. Välj **Synkronisera** för att få de program som du har köpt från Microsoft Store till Intune.

**Så här kontrollerar du att synkronisering mellan Intune och Microsoft Store för företag är aktiv**
1. Logga in på [Microsoft Store för företag](https://businessstore.microsoft.com) med ditt administratörs konto för Microsoft Store för företag.
2. Välj **Hantera** .
3. Välj **Inställningar** och sedan **fördela** .
4. Kontrol lera att Intune visas under **hanterings verktyg** och att statusen är **aktive** rad.  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Steg 2: Skapa Azure AD-grupper

Skapa tre Azure AD-grupper för varje app. I den här tabellen visas de grupper som behövs (tillgängliga, obligatoriska och avinstallationer). 

Typ av tilldelnings program |    Grupp användning    | Exempel på Azure AD-namn
--- | --- | ---
Kan användas |  Programmet kommer att vara tillgängligt från företags portalen eller webbplatsen. | MMD – *program namn* – tillgängligt
Obligatoriskt |  Programmet är installerat på enheter i de valda grupperna. | MMD – *program namn* – obligatoriskt
Avinstallera |  Programmet avinstalleras från enheter i de valda grupperna. | MMD – *program namn* – avinstallera

Lägg till användare i de här grupperna för att antingen göra programmet tillgängligt, installera programmet eller ta bort programmet från Microsoft Managed Desktop-enheten. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Steg 3: tilldela appar till dina användare

**Så här tilldelar du appen till användarna**

1. Logga in på [administrations portalen för Microsoft Managed Desktop](https://aka.ms/mmdportal).
2. Välj **appar** i fönstret hanterad skriv bord.
3. I apparnas arbets belastning väljer du den app du vill tilldela användare och väljer **Tilldela användar grupper** .
4. För det specifika programmet väljer du en tilldelnings typ (tillgänglig, nödvändig, avinstallation) och tilldelar lämplig grupp.
5. I fönstret tilldela appar väljer du **OK** .


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Steg för att komma igång med Microsoft Managed Desktop

1. [Lägga till och verifiera administratörskontakter i administratörsportalen](add-admin-contacts.md)
2. [Justera villkorsstyrd åtkomst](conditional-access.md)
3. [Koppla licenser](assign-licenses.md)
4. [Distribuera Intune-företagsportalen](company-portal.md)
5. [Aktivera Enterprise State Roaming](enterprise-state-roaming.md)
6. [Konfigurera enheter](set-up-devices.md)
7. [Gör användarna redo att använda enheter](get-started-devices.md)
8. Distribuera appar (det här avsnittet)


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
