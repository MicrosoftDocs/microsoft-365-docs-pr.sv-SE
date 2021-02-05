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
description: Lär dig hur du börjar samla in data för klientorganisationen med hjälp av mallappen Microsoft 365 Användningsanalys i Power BI.
ms.openlocfilehash: 98ae107b6777ac97d0be3b37847117c6e20be63d
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114243"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Aktivera Microsoft 365 användningsanalyser

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Microsoft 365 användningsanalyser är ännu inte tillgängliga för Microsoft 365 US Government Community.
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>Steg för att aktivera Microsoft 365 användningsanalyser

För att komma igång med Microsoft 365 användningsanalyser måste du först göra data tillgängliga i administrationscentret för Microsoft 365 och sedan starta mallappen i Power BI.
  
### <a name="get-power-bi"></a>Hämta Power BI

Om du inte redan har Power BI kan du [registrera dig för Power BI Pro.](https://go.microsoft.com/fwlink/p/?linkid=845347) Välj **Prova gratis** för att registrera dig för en utvärderingsversion eller Köp **nu** för att skaffa Power BI Pro.
  
  
Du kan också öppna **Produkter** och köpa en version av Power BI. 

> [!NOTE]
> Du behöver en Power BI Pro-licens för att installera, anpassa och distribuera en mallapp. Mer information finns i [Förutsättningarna.](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)

Om du vill dela dina data måste både du och de personer som du delar data med ha en Power BI Pro-licens, eller så måste innehållet finnas på en arbetsyta i en [Power BI Premium-tjänst.](https://docs.microsoft.com/power-bi/service-premium-what-is) 
  
### <a name="enable-the-template-app"></a>Aktivera mallappen

Du måste vara global administratör för att kunna aktivera **mallappen.**
  
Mer information [finns i artikeln om](../add-users/about-admin-roles.md) administratörsroller. 
  
1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>. 
    
2. Leta upp **Microsoft** **365** användningsanalyskortet på sidan Användning och välj **Kom igång.**
    
3. På panelen Rapporter som öppnas ställer du in **Gör data tillgängliga för Microsoft 365 användningsanalyser för Power BI** till **Spara.** \>  
  
Datainsamlingsprocessen slutförs om två till 48 timmar beroende på klientorganisationens storlek. Knappen **Gå till Power BI** aktiveras (ej längre gråmarkerad) när datainsamlingen är klar. 
    
### <a name="start-the-template-app"></a>Starta mallappen

För att kunna starta mallappen måste du vara global **administratör,** **rapportläsare,** **Exchange-administratör,** Skype för företag-administratör eller **SharePoint-administratör.**  
  
1. Kopiera klientorganisations-ID:t **och välj Gå till Power BI.**
    
2.  Logga in när du kommer till Power BI. Välj **sedan** -> **Appar– hämta appar** från navigeringsmenyn.    
  
3. I fliken **Program** skriver du Microsoft 365 i sökrutan och väljer sedan **Microsoft 365 användningsanalyser** \> **Skaffa nu**.

    [![Välj Skaffa nu](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  När appen har installerats. Välj panelen för att öppna den.

5.  Välj **Utforska app** för att visa appen med exempeldata. Välj **Anslut** för att ansluta appen till organisationens data.

6.  Välj **Anslut** på skärmen Anslut till **Microsoft 365** användningsanalyser, skriv sedan in klientorganisations-ID:t (utan streck) som du kopierade i steg (1) och välj **Nästa.**
    
7. På nästa skärm väljer du **OAuth2** som **inloggningsmetod för** \> **autentisering.** Om du väljer någon annan autentiseringsmetod kommer anslutningen till mallappen att misslyckas.
    
    ![Välj Microsoft-konto som autentiseringsmetod](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. Efter att mallappen instansierats blir instrumentpanelen för Microsoft 365 användningsanalyser tillgänglig i Power BI på webben. Första inläsningen av instrumentpanelen tar 2 till 30 minuter.
  
Sammanställningar på klientorganisationsnivå blir tillgängliga i alla rapporter efter att du har valt att delta. **Information på användarnivå blir bara tillgänglig runt den 5:e i nästa kalendermånad efter att du har anmäla dig.** Det här påverkar alla rapporter under Användaraktivitet (se Navigera och använd rapporterna i [Microsoft 365](navigate-and-utilize-reports.md) användningsanalyser för tips om hur du visar och använder rapporterna).
    
## <a name="make-the-collected-data-anonymous"></a>Gör insamlade data anonyma

Du måste vara global administratör för att kunna anonymisera data som samlas in för alla rapporter. Det här innebär att identifierbar information som användare, grupp och webbplatsnamn i rapporter och mallappen döljs.
  
1. Gå till inställningar för organisationens **inställningar** i \> **administrationscentret** och välj Rapporter under fliken **Tjänster.** 
    
2. Välj **Rapporter** och välj sedan att visa **anonyma identifierare.** Den här inställningen tillämpas både på användningsrapporterna och på mallappen.
  
3. Välj **Spara ändringar**.
