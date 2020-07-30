---
title: Aktivera Microsoft 365 användningsanalyser
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Lär dig hur du börjar samla in data för din klientorganisation med hjälp av microsoft 365 Usage Analytics-mallappen i Power BI.
ms.openlocfilehash: 20228b0e2070065834ce203e22af619480311367
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502955"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Aktivera Microsoft 365 användningsanalyser

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Microsoft 365-användningsanalys är ännu inte tillgängligt för Microsoft 365 US Government Community.
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>Steg för att aktivera Microsoft 365 användningsanalyser

För att komma igång med Microsoft 365-användningsanalys måste du först göra data tillgängliga i Microsoft 365-administrationscentret och sedan starta mallappen i Power BI.
  
### <a name="get-power-bi"></a>Hämta Power BI

Om du inte redan har Power BI kan du [registrera dig för Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347). Välj **Prova gratis** för att registrera dig för en utvärderingsversion eller Köp **nu** för att få Power BI Pro.
  
  
Du kan också öppna **Produkter** och köpa en version av Power BI. 

> [!NOTE]
> Du behöver en Power BI Pro-licens för att installera, anpassa och distribuera en mallapp. Mer information finns i [Förutsättningar](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).

Du behöver en Power BI Pro-licens för att dela ditt innehåll, och de personer du delar det med gör det också, eller så måste innehållet finnas på en arbetsyta med [en Premium-kapacitet](https://docs.microsoft.com/power-bi/service-premium-what-is). 
  
### <a name="enable-the-template-app"></a>Aktivera mallappen

Om du vill aktivera mallappen måste du antingen vara global **administratör,** **rapportläsare,** **Exchange-administratör,** **Skype för företag-administratör**eller **SharePoint-administratör**. 
  
Mer information finns i [Om administratörsroller.](../add-users/about-admin-roles.md) 
  
1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>. 
    
2. Leta reda på **Microsoft 365-användningsanalyskortet** på sidan **Användning** och välj **Kom igång**.
    
3. På panelen Rapporter som öppnas anger du **Gör data tillgängliga för Microsoft 365-användningsanalys för Power BI** till **På** \> **Spara**. 
  
Det här initierar datainsamlingsprocessen och tar mellan 2 och 48 timmar att slutföra beroende på storleken på din klientorganisation. Knappen **Gå till Power BI** aktiveras (ej längre gråmarkerad) när datainsamlingen är klar. 
    
### <a name="initiate-the-template-app"></a>Initiera mallappen

Om du vill starta mallappen måste du antingen vara global **administratör,** **rapportläsare,** **Exchange-administratör,** **Skype för företag-administratör**eller **SharePoint-administratör**. 
  
1. Kopiera klient-ID:et och välj **Gå till Power BI**.
    
2.  Logga in när du kommer till Power BI. Välj Appar->Hämta appar på navigeringsmenyn.    
  
3. I fliken **Program** skriver du Microsoft 365 i sökrutan och väljer sedan **Microsoft 365 användningsanalyser** \> **Skaffa nu**.

    [![Välj Hämta det nu](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  När appen är installerad. Klicka på panelen för att öppna den.

5.  Klicka på **Utforska app** om du vill visa appen med exempeldata. Klicka på **Anslut** om du vill ansluta appen till organisationens data.

6.  När du har klickat på **Anslut**skriver du i klient-ID (utan streck) som du kopierade i steg (1) på skärmen **Anslut till Microsoft 365 användningsanalys** och väljer **Nästa**.
    
7. På nästa skärm väljer du **oAuth2** som **autentiseringsmetod** \> **Logga in**. Om du väljer någon annan autentiseringsmetod misslyckas anslutningen till mallappen.
    
    ![Choose oAuth2 as authentication method](../../media/ac85a360-c278-4c60-8aa3-68f4828f1d96.png)
  
8. När mallappen har instansierats är instrumentpanelen för användningsanalys i Microsoft 365 tillgänglig i Power BI på webben. Första inläsningen av instrumentpanelen tar 2 till 30 minuter.
  
Sammanställningar på klientorganisationsnivån blir tillgängliga i alla rapporter. **Information på användarnivå blir bara tillgänglig efter den 1:a eller 15:e dagen varje kalendermånad efter att du har gått med**. Detta påverkar alla rapporter under Användaraktivitet (Se [Navigera och använda rapporterna i Microsoft 365-användningsanalys](navigate-and-utilize-reports.md) för tips om hur du visar och använder dessa rapporter).
    
## <a name="make-the-collected-data-anonymous"></a>Gör insamlade data anonyma

Du måste vara global administratör för att kunna anonymisera data som samlas in för alla rapporter. Detta döljer identifierbar information som användar-, grupp- och webbplatsnamn i rapporter och i mallappen .
  
1. Gå till **Settings** \> **inställningars organisationsinställningar**i administrationscentret och välj **Rapporter**under **Fliken Tjänster** .
    
2. Välj **Rapporter**och välj sedan att **visa anonyma identifierare**. Den här inställningen tillämpas både på användningsrapporterna och på mallappen.
  
3. Välj **Spara ändringar**.
