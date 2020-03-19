---
title: Hantera appar på Microsoft Managed Desktop
description: Information om hur du uppdaterar företagsappar som distribueras till Microsoft Managed Desktop-enheter
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1a6b91ab5b4523f4b980dab0c25af41a9d614189
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42812928"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>Hantera företagsappar på Microsoft Managed Desktop

<!--Application management -->

Det finns ett par sätt att hantera appuppdateringar för appar som du har ombord på Microsoft Managed Desktop och distribuerat till dina Microsoft Managed Desktop-enheter. Du kan göra appuppdateringar i Microsoft Managed Desktop-portalen eller Intune. 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>Uppdatera företagsappar på Microsoft Managed Desktop

**Så här uppdaterar du dina företagsappar i Microsoft Managed Desktop-portalen**
1. Logga in på [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).
2. Välj **Appar**under **Lager**.  
3. Markera den app som du vill uppdatera och välj sedan **Redigera**.
4. Välj **Egenskaper**under **Hantera**. 
5. Klicka på **App paketfil**och bläddra sedan för att ladda upp en ny apppaketfil.
6. Välj **Apppaketfil**.
7. Välj mappikonen och bläddra till platsen för den uppdaterade appfilen. Välj **Öppna**. Appinformationen uppdateras med paketinformationen.
8. Kontrollera att **App-versionen** återspeglar det uppdaterade apppaketet. 

Den uppdaterade appen distribueras till användarens enheter.

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>Uppdatera företagsappar i Intune

**Så här uppdaterar du dina företagsappar i Intune**
1. Logga in på [Azure-portalen](https://portal.azure.com).
2. Välj**Intune för** **alla tjänster** > . Intune finns i avsnittet **Övervakning + hantering.**
3. Välj **klientappar > appar**.
4. Hitta och välj din app i listan över appar.
5. Välj **Egenskaper**i bladet **Översikt** .
6. Välj **Apppaketfil**.
7. Välj mappikonen och bläddra till platsen för den uppdaterade appfilen. Välj **Öppna**. Appinformationen uppdateras med paketinformationen.
8. Kontrollera att **App-versionen** återspeglar det uppdaterade apppaketet.

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>Återställa en app till en tidigare version

Om det finns ett fel som hittades när en ny version av en app distribueras kan du återställa till en tidigare version. Den process som beskrivs här är för appar där typ visas som **Windows MSI-företagsapp** eller **Windows-app (Win 32) - förhandsgranskning**

**Så här återställer du en företagsapp till en tidigare version**

1. Logga in på [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).
2. Välj **Appar**under **Lager**.  
3. Välj den app du behöver för att återställa och välj sedan **Redigera**.
4. Välj **Egenskaper**under **Hantera**. 
    - För **Appappar för Windows MSI** väljer du **Appinformation**och väljer sedan **Ja**under **Ignorera appversion**.
    - För **Windows-appen (Win 32) – förhandsgranska** appar väljer du **Appinformation,** väljer **Identifieringsregler**och väljer sedan **Lägg till**. 
    Om det finns en MSI-regel kontrollerar du att **MSI:s produktversionskontroll** är inställt på **Nej**.
5. [Ladda upp en tidigare version av appkällfilen](../get-started/deploy-apps.md) till Microsoft Managed Desktop Admin portal.  

