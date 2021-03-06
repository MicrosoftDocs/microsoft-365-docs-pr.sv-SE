---
title: Konfigurera alternativen Standard eller Riktad version
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
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
description: Lär dig hur du konfigurera versionsalternativ för nya produkter och uppdateringar av funktioner Microsoft 365 administrationscentret.
ms.openlocfilehash: 5060e2dc99355d89928ec91c96b7d25e2016c7c4
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593951"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a>Konfigurera alternativen Standard eller Riktad version

> [!IMPORTANT]
> De Microsoft 365 uppdateringar som beskrivs i den här artikeln gäller Microsoft 365, SharePoint Online och Exchange Online. De här versionsalternativen är en metod som ger bästa möjliga sätt att Microsoft 365 ändringar, men kan inte alltid garanteras för alla uppdateringar. De gäller inte för Microsoft 365, Skype för företag, Microsoft Teams och relaterade tjänster. Mer information om versionsalternativ för Microsoft 365 program finns i [Översikt över uppdateringskanaler för Microsoft 365 Appar](/deployoffice/overview-update-channels).

Med Microsoft 365 får du nya produktuppdateringar och funktioner allt eftersom de blir tillgängliga i stället för att göra dyra uppdateringar med några års hjälp. Du kan styra hur organisationen ska få tillgång till uppdateringarna. Du kan till exempel registrera dig för en tidig version, så att organisationen blir bland de första som får uppdateringarna. Du kan ange att bara vissa personer ska ta emot uppdateringarna. Du kan också välja att behålla standardschemat för nya versioner och få uppdateringarna senare. I den här artikeln förklaras de olika versionsalternativen och hur du kan använda dem för din organisation.

## <a name="how-it-works---release-validation"></a>Så här fungerar det - versionsvalidering

Alla nya versioner testas och valideras först av funktionsteamet och sedan av hela Microsoft 365, följt av hela Microsoft. Efter intern testning och validering är nästa steg en **Riktad version** (tidigare kallad första version) till kunder som anmält sig för detta. För varje version samlar Microsoft in feedback och validerar kvalitet genom att övervaka viktig användningsstatistik. Det här arbetssättet med progressiv validering är avsedd att göra den version som släpps till allmänheten så robust som möjligt. Versionerna beskrivs i bilden nedan. 
  
![Versionsvalideringsringar för Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
Kunder meddelas först om större uppdateringar via [översikten Microsoft 365](https://products.office.com/business/office-365-roadmap). När en uppdatering är nära att lanseras meddelas den via ditt Microsoft 365 [Meddelandecenter.](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)

> [!NOTE]
> Du behöver ett Microsoft 365 eller ett Azure AD-konto för att få åtkomst till meddelandecentret via [administrationscentret.](/office365/admin/admin-overview/about-the-admin-center) Microsoft 365 har ett administrationscenter för hemabonnemanget.


## <a name="standard-release"></a>Standardversion

Det här är standardalternativet där du och användarna får de senaste uppdateringarna när de släpps för alla kunder.
  
En bra metod är att lämna de flesta användare i  **Standard-** och IT-proffs och avancerade användare i en riktad version som ger möjlighet att utvärdera nya funktioner och förbereda team som ger support till företagsanvändare och chefer. 
  
> [!NOTE]
> Om du växlar från riktad version tillbaka till standardversionen kan det hända att vissa användare förlorar åtkomst till funktioner som inte har inkluderats i standardversionen än. 
  
## <a name="targeted-release"></a>Riktad version

Om du väljer det här alternativet kan du och andra användare i organisationen vara bland de första att ta del av de allra senaste uppdateringarna och bidra till att utforma produkter genom att ge återkoppling i ett tidigt skede. Du kan välja om du vill att bara vissa personer, eller alla i organisationen ska få dessa tidiga uppdateringar.
  
> [!IMPORTANT]
> Stora eller komplexa uppdateringar kan genomföras under en längre tid, så att inga användare påverkas negativt. Det finns ingen garanti för att en versionsuppdatering ska följa en exakt tidslinje. 
  
### <a name="targeted-release-for-entire-organization"></a>Riktad version för hela organisationen

Om du [ställer in alternativet Version i administrationscentret](#set-up-the-release-option-in-the-admin-center) för det här alternativet får alla användare den riktade versionen. Om organisationen har fler än 300 användare rekommenderar vi att en provprenumeration används för det här alternativet. Kontakta Microsoft om du behöver information om provprenumerationer. 
  
### <a name="targeted-release-for-selected-users"></a>Riktad version för valda användare

Om du [ställer in](#set-up-the-release-option-in-the-admin-center) alternativet Version i administrationscentret för det här alternativet kan du definiera specifika användare, vanligtvis avancerade användare, för att få tidig åtkomst till funktioner. 
  
## <a name="benefits-of-targeted-release"></a>Fördelar med Riktad version

Riktad version gör att administratörer, ändringshanterare och alla andra som ansvarar för Microsoft 365 kan förbereda sig för kommande ändringar genom att låta dem:
  
- Testa och validera nya uppdateringar innan de släpps till alla användare i organisationen.
    
- Förbereda användarmeddelanden och dokumentation innan uppdateringar släpps i hela världen.
    
- Förbereda den interna supporten på kommande ändringar.
    
- Genomföra efterlevnads- och säkerhetsgranskningar.
    
- Använda funktionskontroller och styra när användare får uppdateringar.
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>Konfigurera alternativet för släppta versioner i administrationscentret

Du kan ändra hur organisationen får e Microsoft 365 genom att följa de här stegen. Du måste vara global administratör för Microsoft 365 registrera dig.
  
> [!IMPORTANT]
> Det kan ta upp till 24 timmar innan nedanstående ändringar verkställs Microsoft 365. Om organisationen tidigare har använt riktad version och du vill inaktivera detta kan det hända att vissa användare förlorar tillgång till funktioner som inte ingår i standardversionen än. 
  
1. I administrationscentret går du till fliken **Inställningar**  >  **organisationsinställning och** under fliken **Organisationsprofil** väljer du **Inställningar för släppta inställningar.**

5. Om du vill inaktivera riktad version väljer **du Standard** och sedan **Spara ändringar.** 
    
6. Om du vill aktivera den riktade versionen för alla användare i organisationen väljer du **Riktad version för alla** och sedan Spara **ändringar.** 
    
7. Om du vill aktivera riktad version för vissa användare i organisationen väljer du **Riktad version för valda användare** och sedan Spara **ändringar.** 
    
8. Välj **Välj användare** för att lägga till en användare i taget eller välj Upload **lägga** till dem i grupp.
    
9. När du har lagt till alla användare väljer du **Spara ändringar.**
  
## <a name="next-steps"></a>Nästa steg

Upptäck hur du [hanterar meddelanden](/office365/admin/manage/message-center) i [meddelandecentret Microsoft 365 du](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) vill få aviseringar om kommande Microsoft 365 uppdateringar och versioner.

## <a name="related-content"></a>Relaterat innehåll

[Delta i Office Insider Program](https://insider.office.com/join/windows) (artikel)
