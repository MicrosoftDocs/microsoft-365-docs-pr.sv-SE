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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Läs om hur du börjar samla in data för din klient genom att använda mallappen Microsoft 365 Usage Analytics i Power BI.
ms.openlocfilehash: 249fadce15ca2e4c979d6e1930ff0d14ccd9bc08
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42808008"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Aktivera Microsoft 365 användningsanalyser

Microsoft 365 användninganalytics är också tillgänglig för Microsoft 365 US Government Community.
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>Steg för att aktivera Microsoft 365 användningsanalyser

Om du vill komma igång med Microsoft 365-användningsanalys måste du först göra data tillgängliga i administrationscentret för Microsoft 365 och sedan initiera mallappen i Power BI.
  
### <a name="get-power-bi"></a>Hämta Power BI

Om du inte redan har Power BI kan du [registrera dig för Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347). Välj **Prova gratis** att registrera dig för en utvärderingsversion, eller Köp **nu** för att få Power BI Pro.
  
  
Du kan också öppna **Produkter** och köpa en version av Power BI. 

> [!NOTE]
> Du behöver en Power BI Pro-licens för att installera, anpassa och distribuera en mallapp. Mer information finns i [Förutsättningar](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).

Du behöver en Power BI Pro-licens för att dela ditt innehåll, och de personer du delar det med gör också, eller innehållet måste vara på en arbetsyta i [premiumkapacitet](https://docs.microsoft.com/power-bi/service-premium-what-is). 
  
### <a name="enable-the-template-app"></a>Aktivera mallappen

Om du vill aktivera mallappen måste du vara antingen en **global administratör,** **rapportläsare,** **Exchange-administratör,** **Skype för företag-administratör**eller **SharePoint-administratör.** 
  
Mer information finns i [Om administratörsroller.](../add-users/about-admin-roles.md) 
  
1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>. 
    
2. Leta reda på **Microsoft 365-användningsanalyskortet** på sidan **Användning** och välj **Kom igång**.
    
3. På panelen Rapporter som öppnas anger **du Gör data tillgängliga för Microsoft 365-användningsanalys för Power BI** på **Spara** \> **Save**. 
  
Det här initierar datainsamlingsprocessen och tar mellan 2 och 48 timmar att slutföra beroende på storleken på din klientorganisation. Knappen **Gå till Power BI** aktiveras (ej längre gråmarkerad) när datainsamlingen är klar. 
    
### <a name="initiate-the-template-app"></a>Starta mallappen

Om du vill initiera mallappen måste du vara antingen en **global administratör,** **rapportläsare,** **Exchange-administratör,** **Skype för företag-administratör**eller **SharePoint-administratör.** 
  
1. Kopiera klient-ID:t och välj **Gå till Power BI**.
    
2.  Logga in när du kommer till Power BI. Välj Appar >Hämta appar på navigeringsmenyn.    
  
3. I fliken **Program** skriver du Microsoft 365 i sökrutan och väljer sedan **Microsoft 365 användningsanalyser** \> **Skaffa nu**.

    [![Välj Hämta den nu](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  När appen har installerats. Klicka på panelen för att öppna den.

5.  Klicka på **Utforska app** om du vill visa appen med exempeldata. Klicka på **Anslut** om du vill ansluta appen till organisationens data.

6.  När du har klickat på **Anslut**till **Microsoft 365 användninganalytics-** -skriver du i \> klient-ID:t som du kopierade i steg (1) **Nästa**.
    
7. På nästa skärm väljer du **oAuth2** som **autentiseringsmetod** \> **Logga in**. Om du väljer någon annan autentiseringsmetod misslyckas anslutningen till mallappen.
    
    ![Choose oAuth2 as authentication method](../../media/ac85a360-c278-4c60-8aa3-68f4828f1d96.png)
  
8. När mallappen har instansierats kommer instrumentpanelen för användningsanalys för Microsoft 365 att vara tillgänglig i Power BI på webben. Första inläsningen av instrumentpanelen tar 2 till 30 minuter.
  
Sammanställningar på klientorganisationsnivån blir tillgängliga i alla rapporter. **Information på användarnivå blir bara tillgänglig efter den 1:a eller 15:e dagen varje kalendermånad efter att du har gått med**. Detta påverkar alla rapporter under Användaraktivitet (Se [Navigera och använd rapporterna i Microsoft 365 användningsanalys](navigate-and-utilize-reports.md) för tips om hur du visar och använder dessa rapporter).
    
## <a name="make-the-collected-data-anonymous"></a>Gör insamlade data anonyma

Du måste vara global administratör för att kunna anonymisera data som samlas in för alla rapporter. Detta döljer identifierbar information som användar-, grupp- och webbplatsnamn i rapporter och i mallappen .
  
1. I administrationscentret går **Settings** \> du till fliken **Inställningar**och väljer **Rapporter**under **Fliken Tjänster** .
    
2. Välj **Rapporter**och välj sedan **visa anonyma identifierare**. Den här inställningen tillämpas både på användningsrapporterna och på mallappen.
  
3. Välj **Spara ändringar**.
