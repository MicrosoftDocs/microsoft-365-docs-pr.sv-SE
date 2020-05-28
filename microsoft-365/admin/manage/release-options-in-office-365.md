---
title: Ställ in alternativen standard eller riktad utgåva
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
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
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Lär dig hur du konfigurerar utgivningsalternativet för nya produkt- och featuresuppdateringar i administrationscentret för Microsoft 365.
ms.openlocfilehash: 4b26a3e95b11feb5c6a5894702b86e74f82bde03
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399698"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a>Ställ in alternativen standard eller riktad utgåva

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Med Microsoft 365 får du nya produktuppdateringar och funktioner när de blir tillgängliga i stället för att göra kostsamma uppdateringar med några års mellanrum. Du kan styra hur organisationen ska få tillgång till uppdateringarna. Du kan till exempel registrera dig för en tidig version, så att organisationen blir bland de första som får uppdateringarna. Du kan ange att bara vissa personer ska ta emot uppdateringarna. Du kan också välja att behålla standardschemat för nya versioner och få uppdateringarna senare. I den här artikeln beskrivs de olika frisläppningsalternativen och hur du kan använda dem för din organisation.
  
> [!IMPORTANT]
> De Microsoft 365-uppdateringar som beskrivs i den här artikeln gäller Microsoft 365, SharePoint Online och Exchange Online. De gäller inte för Skype för företag och relaterade tjänster. Dessa utgivningsalternativ är riktade, bästa möjliga sätt att släppa ändringar till Microsoft 365 men kan inte garanteras hela tiden eller för alla uppdateringar. 
  
## <a name="how-it-works---release-validation"></a>Så här fungerar det - versionsvalidering

Alla nya versionen testas och valideras först av funktionsteamet, sedan av hela Microsoft 365-funktionsteamet, följt av hela Microsoft. Efter intern testning och validering är nästa steg en **Riktad version** (tidigare kallad första version) till kunder som anmält sig för detta. För varje version samlar Microsoft in feedback och validerar kvalitet genom att övervaka viktig användningsstatistik. Det här arbetssättet med progressiv validering är avsedd att göra den version som släpps till allmänheten så robust som möjligt. Versionerna beskrivs i bilden nedan. 
  
![Släpp valideringsringar för Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
För viktiga uppdateringar meddelas kunderna inledningsvis av [Microsoft 365-översikten](https://products.office.com/business/office-365-roadmap). När en uppdatering närmar sig utrullningen kommuniceras den via [ditt Microsoft 365 Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).

> [!NOTE]
> Du behöver ett Microsoft 365- eller Azure AD-konto för att komma åt ditt meddelandecenter via [administrationscentret](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center). Microsoft 365-hemabonnemangsanvändare har inget administrationscenter.


## <a name="standard-release"></a>Standardversion

Det här är standardalternativet där du och dina användare får de senaste uppdateringarna när de släpps brett till alla kunder.
  
En god praxis är att lämna majoriteten av användarna i **Standard release** och IT-proffs och avancerade användare i **Riktad utgåva** för att utvärdera nya funktioner och förbereda team för att stödja företagsanvändare och chefer. 
  
> [!NOTE]
> Om du växlar från riktad version tillbaka till standardversionen kan det hända att vissa användare förlorar åtkomst till funktioner som inte har inkluderats i standardversionen än. 
  
## <a name="targeted-release"></a>Riktad version

Om du väljer det här alternativet kan du och andra användare i organisationen vara bland de första att ta del av de allra senaste uppdateringarna och bidra till att utforma produkter genom att ge återkoppling i ett tidigt skede. Du kan välja om du vill att bara vissa personer, eller alla i organisationen ska få dessa tidiga uppdateringar.
  
> [!IMPORTANT]
> Stora eller komplexa uppdateringar kan genomföras under en längre tid, så att inga användare påverkas negativt. Det finns ingen garanti för att en versionsuppdatering ska följa en exakt tidslinje. 
  
### <a name="targeted-release-for-entire-organization"></a>Riktad version för hela organisationen

Om du [konfigurerar utgivningsalternativet i administrationscentret](#set-up-the-release-option-in-the-admin-center) för det här alternativet får alla användare upplevelsen riktad. Om organisationen har fler än 300 användare rekommenderar vi att en provprenumeration används för det här alternativet. Kontakta Microsoft om du behöver information om provprenumerationer. 
  
### <a name="targeted-release-for-selected-users"></a>Riktad version för valda användare

Om du [konfigurerar utgivningsalternativet i administrationscentret](#set-up-the-release-option-in-the-admin-center) för det här alternativet kan du definiera specifika användare, vanligtvis avancerade användare, för att få tidig åtkomst till funktioner och funktioner. 
  
## <a name="benefits-of-targeted-release"></a>Fördelar med Riktad version

Riktad utgåva gör det möjligt för administratörer, ändringshanterare eller någon annan som ansvarar för Microsoft 365-uppdateringar att förbereda sig för de kommande ändringarna genom att låta dem:
  
- Testa och validera nya uppdateringar innan de släpps till alla användare i organisationen.
    
- Förbereda användarmeddelanden och dokumentation innan uppdateringar släpps i hela världen.
    
- Förbereda den interna supporten på kommande ändringar.
    
- Genomföra efterlevnads- och säkerhetsgranskningar.
    
- Använda funktionskontroller och styra när användare får uppdateringar.
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>Konfigurera utgivningsalternativet i administrationscentret

Du kan ändra hur din organisation tar emot Microsoft 365-uppdateringar genom att följa dessa steg. Du måste vara global administratör i Microsoft 365 för att kunna anmäla dig.
  
> [!IMPORTANT]
> Det kan ta upp till 24 timmar innan ändringarna nedan börjar gälla i Microsoft 365. Om organisationen tidigare har använt riktad version och du vill inaktivera detta kan det hända att vissa användare förlorar tillgång till funktioner som inte ingår i standardversionen än. 
  
1. Gå till **Settings**  >  **inställningen Inställningars organisationsorganisation**i administrationscentret och välj **Utgivningsinställningar**under fliken **Organisationsprofil** .

5. Om du vill inaktivera riktad frisättning väljer du **Standardversion**och väljer sedan **Spara ändringar**. 
    
6. Om du vill aktivera riktad publicering för alla användare i organisationen väljer du **Riktad version för alla**och väljer sedan Spara **ändringar**. 
    
7. Om du vill aktivera riktad publicering för vissa personer i organisationen väljer du **Riktad version för valda användare**och väljer sedan Spara **ändringar**. 
    
8. Välj **Välj användare** om du vill lägga till användare en i taget eller Ladda upp **användare** om du vill lägga till dem i grupp.
    
9. När du är klar med att lägga till användare väljer du **Spara ändringar**.


  
## <a name="learn-more"></a>Mer information

Upptäck hur du [hanterar meddelanden](https://docs.microsoft.com/office365/admin/manage/message-center) i ditt [Microsoft 365-meddelandecenter](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) för att få aviseringar om kommande uppdateringar och utgåvor från Microsoft 365.
