---
title: Hantera appar i Microsoft Hanterat skrivbord
description: Information om hur du uppdaterar verksamhetsbaserade appar som distribueras till Microsoft Hanterat skrivbord enheter
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
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
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>Hantera branschspecifika appar på Microsoft Hanterat skrivbord

<!--Application management -->

Det finns några olika sätt att hantera programuppdateringar för appar som du har introducerat för Microsoft Hanterat skrivbord och distribuerat till dina Microsoft Hanterat skrivbord enheter. Du kan göra appuppdateringar i Microsoft Hanterat skrivbord portal eller Intune. 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>Uppdatera verksamhetsbaserade appar i Microsoft Hanterat skrivbord

**Så här uppdaterar du dina verksamhetsbaserade appar i Microsoft Hanterat skrivbord portalen**
1. Logga in på [Microsoft Hanterat skrivbord administrationsportalen](https://aka.ms/mmdportal).
2. Under **Lager** väljer du **Appar**.  
3. Välj det program du vill uppdatera och välj sedan **Redigera**.
4. Under **Hantera** väljer du **Egenskaper**. 
5. Klicka **på Programpaketfil** och bläddra sedan för att ladda upp en ny programpaketfil.
6. Välj **Programpaketsfil**.
7. Välj mappikonen och bläddra till den uppdaterade programfilens plats. Välj **Öppna**. Programinformationen uppdateras med paketinformationen.
8. Kontrollera att **programversionen återspeglar** det uppdaterade programpaketet. 

Det uppdaterade programmet distribueras till användarnas enheter.

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>Uppdatera verksamhetsbaserade appar i Intune

**Så här uppdaterar du dina verksamhetsbaserade appar i Intune**
1. Logga in på [Azure Portal](https://portal.azure.com).
2. Välj **Alla tjänster**  >  **Intune.** Intune finns i **avsnittet Övervakning +** Hantering.
3. Välj **Klientappar > appar**.
4. Leta upp och välj din app i listan med appar.
5. Välj **Egenskaper i** bladet **Översikt.**
6. Välj **Programpaketsfil**.
7. Välj mappikonen och bläddra till den uppdaterade programfilens plats. Välj **Öppna**. Programinformationen uppdateras med paketinformationen.
8. Kontrollera att **programversionen återspeglar** det uppdaterade programpaketet.

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>Återställa en app till en tidigare version

Om ett fel uppstår när en ny version av ett program har distribuerats kan du återställa till en tidigare version. Processen som beskrivs här är för appar där typ anges **Windows en företagsapp** med MSI eller Windows **(Win 32) – förhandsversion**

**Återställa en verksamhetslinje till en tidigare version**

1. Logga in på [Microsoft Hanterat skrivbord administrationsportalen](https://aka.ms/mmdportal).
2. Under **Lager** väljer du **Appar**.  
3. Välj den app du vill återställa och välj sedan **Redigera**.
4. Under **Hantera** väljer du **Egenskaper**. 
    - För **Windows appprogram med** verksamhetsversionen av MSI väljer du **Appinformation** och sedan Ja under Ignorera **appversion.** 
    - Om **Windows app (Win 32) –** förhandsgranska appar väljer du **Appinformation,** väljer **Identifieringsregler** och sedan Lägg **till.** 
    Om det finns en MSI-regel kontrollerar du att **kontrollen av MSI-produkten** är inställd på **Nej.**
5. [Upload en tidigare version av programkällfilen i](../get-started/deploy-apps.md) Microsoft Hanterat skrivbord administrationsportalen.  

