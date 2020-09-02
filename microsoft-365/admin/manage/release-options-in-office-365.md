---
title: Ställ in standard-eller riktade versions alternativ
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
description: Lär dig hur du konfigurerar alternativet släpp för nya produkt-och funktions uppdateringar i Microsoft 365 Admin Center.
ms.openlocfilehash: 110cefa646f7c42c6979a97ca617b015a100866e
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324542"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a>Ställ in standard-eller riktade versions alternativ

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

> [!IMPORTANT]
> De Microsoft 365-uppdateringar som beskrivs i den här artikeln gäller Microsoft 365, SharePoint Online och Exchange Online. De här versions alternativen är inriktade på bästa möjliga sätt att släppa ändringar i Microsoft 365 men kan inte garanteras alls eller för alla uppdateringar. De gäller inte Microsoft 365-appar, Skype för företag, Microsoft Teams och tillhörda tjänster. Information om versions alternativ för Microsoft 365-appar finns i [Översikt över uppdaterings kanaler för microsoft 365-appar](https://docs.microsoft.com/deployoffice/overview-update-channels).

Med Microsoft 365 får du nya produkt uppdateringar och funktioner när de blir tillgängliga i stället för att göra dyra uppdateringar. Du kan styra hur organisationen ska få tillgång till uppdateringarna. Du kan till exempel registrera dig för en tidig version, så att organisationen blir bland de första som får uppdateringarna. Du kan ange att bara vissa personer ska ta emot uppdateringarna. Du kan också välja att behålla standardschemat för nya versioner och få uppdateringarna senare. I den här artikeln beskrivs de olika utgivnings alternativen och hur du kan använda dem i din organisation.

## <a name="how-it-works---release-validation"></a>Så här fungerar det - versionsvalidering

Alla nya versioner testas först och bekräftas av funktions teamet och sedan av hela Microsoft 365 Feature team, följt av alla Microsoft. Efter intern testning och validering är nästa steg en **Riktad version** (tidigare kallad första version) till kunder som anmält sig för detta. För varje version samlar Microsoft in feedback och validerar kvalitet genom att övervaka viktig användningsstatistik. Det här arbetssättet med progressiv validering är avsedd att göra den version som släpps till allmänheten så robust som möjligt. Versionerna beskrivs i bilden nedan. 
  
![Utgivning av verifierings samtal för Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
För viktiga uppdateringar meddelas kunderna från början av [Microsoft 365-översikten](https://products.office.com/business/office-365-roadmap). Som en uppdatering blir närmare att lanseras kommunicerar den via ditt [Microsoft 365-meddelande Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).

> [!NOTE]
> Du behöver ett Microsoft 365-eller Azure AD-konto för att komma åt ditt meddelande Center via [administrations centret](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center). Användare av Microsoft 365 Home plan har inte ett administrations Center.


## <a name="standard-release"></a>Standardversion

Det här är standard alternativet där du och användarna får de senaste uppdateringarna när de släpps brett till alla kunder.
  
En bra idé är att lämna de flesta användare i **standard versionen** och IT-proffs och kraftfulla användare i **riktad version** för att utvärdera nya funktioner och förbereda team för företags användare och chefer. 
  
> [!NOTE]
> Om du växlar från riktad version tillbaka till standardversionen kan det hända att vissa användare förlorar åtkomst till funktioner som inte har inkluderats i standardversionen än. 
  
## <a name="targeted-release"></a>Riktad version

Om du väljer det här alternativet kan du och andra användare i organisationen vara bland de första att ta del av de allra senaste uppdateringarna och bidra till att utforma produkter genom att ge återkoppling i ett tidigt skede. Du kan välja om du vill att bara vissa personer, eller alla i organisationen ska få dessa tidiga uppdateringar.
  
> [!IMPORTANT]
> Stora eller komplexa uppdateringar kan genomföras under en längre tid, så att inga användare påverkas negativt. Det finns ingen garanti för att en versionsuppdatering ska följa en exakt tidslinje. 
  
### <a name="targeted-release-for-entire-organization"></a>Riktad version för hela organisationen

Om du [har konfigurerat alternativet släpp i administrations centret](#set-up-the-release-option-in-the-admin-center) för det här alternativet får alla dina användare den riktade versionen. Om organisationen har fler än 300 användare rekommenderar vi att en provprenumeration används för det här alternativet. Kontakta Microsoft om du behöver information om provprenumerationer. 
  
### <a name="targeted-release-for-selected-users"></a>Riktad version för valda användare

Om du [har aktiverat alternativet släpp i administrations centret](#set-up-the-release-option-in-the-admin-center) för det här alternativet kan du definiera särskilda användare, vanligt vis Power-användare, för att få tidig åtkomst till funktioner och funktioner. 
  
## <a name="benefits-of-targeted-release"></a>Fördelar med Riktad version

Riktad version gör det möjligt för administratörer, byta chef eller någon annan ansvarig för Microsoft 365-uppdateringar för att förbereda inför kommande ändringar genom att låta dem:
  
- Testa och validera nya uppdateringar innan de släpps till alla användare i organisationen.
    
- Förbereda användarmeddelanden och dokumentation innan uppdateringar släpps i hela världen.
    
- Förbereda den interna supporten på kommande ändringar.
    
- Genomföra efterlevnads- och säkerhetsgranskningar.
    
- Använda funktionskontroller och styra när användare får uppdateringar.
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>Konfigurera alternativet släpp i administrations centret

Du kan ändra hur organisationen får Microsoft 365-uppdateringar genom att följa de här stegen. Du måste vara global administratör i Microsoft 365 för att välja.
  
> [!IMPORTANT]
> Det kan ta upp till 24 timmar innan ändringarna nedan börjar gälla i Microsoft 365. Om organisationen tidigare har använt riktad version och du vill inaktivera detta kan det hända att vissa användare förlorar tillgång till funktioner som inte ingår i standardversionen än. 
  
1. I administrations centret går du till inställningen **Inställningar**  >  **organisation**och väljer sedan **Inställningar för version**under fliken **organisations profil** .

5. Stäng mål versionen genom att välja **Standard version**och sedan **Spara ändringar**. 
    
6. Aktivera mål version för alla användare i organisationen genom att välja **riktad version för**alla och sedan **Spara ändringar**. 
    
7. Aktivera mål version för vissa personer i organisationen genom att välja **riktad version för valda användare**och sedan **Spara ändringar**. 
    
8. Välj **Välj användare** för att lägga till användare en i taget eller **Ladda upp användare** för att lägga till dem i bulk.
    
9. När du är klar med att lägga till användare väljer du **Spara ändringar**.


  
## <a name="learn-more"></a>Mer information

Upptäck hur du [hanterar meddelanden](https://docs.microsoft.com/office365/admin/manage/message-center) i [Microsoft 365 meddelande Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) för att få aviseringar om kommande Microsoft 365-uppdateringar och-utgåvor.
