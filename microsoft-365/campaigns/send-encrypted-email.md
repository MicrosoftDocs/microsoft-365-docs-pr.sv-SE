---
title: Skicka krypterad e-post
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Läs om hur du skickar krypterad e-post med Outlook.
ms.openlocfilehash: f5184de55ce07d5e669e98afb6e627833071c4ba
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46526882"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>Kryptera eller märk dina konfidentiella e-postmeddelanden

Dina data- och kampanjinformationer är viktiga och ofta konfidentiella. Skydda den här känsliga informationen genom att använda krypterings- och känslighetsetiketter så att du och dina e-postmottagare behandlar informationen med den känslighet som krävs.


## <a name="best-practices"></a>Metodtips

Innan du skickar e-post med konfidentiell eller känslig information bör du överväga att aktivera:

- **Kryptering:** Du kan kryptera din e-post för att skydda sekretessen för informationen i e-postmeddelandet. När du krypterar ett e-postmeddelande konverteras det från läsbar oformaterad text till förvrängd cyphertext. Endast den mottagare som har den privata nyckeln som matchar den offentliga nyckeln som används för att kryptera meddelandet kan dechiffrera meddelandet för läsning. Alla mottagare utan motsvarande privata nyckel ser dock oläslig text. Administratören kan definiera regler för att automatiskt kryptera meddelanden som uppfyller vissa kriterier. Administratören kan till exempel skapa en regel som krypterar alla meddelanden som skickas utanför organisationen eller alla meddelanden som nämner specifika ord eller fraser. Alla krypteringsregler tillämpas automatiskt.
- **Känslighetsetiketter:** Kampanjen kan också ställa in känslighetsetiketter som du kan använda på dina filer och e-post för att hålla dem överensstämde med kampanjens principer för informationsskydd. När du anger en etikett finns etiketten kvar med din e-post, även när den skickas, till exempel genom att visas som en rubrik i meddelandet.

![Diagram över ett e-postmeddelande med bildtexter för etiketter och kryptering](../media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a>Konfigurera

Om du vill kryptera ett meddelande som inte uppfyller en fördefinierad regel eller om administratören inte har konfigurerat några regler kan du använda en mängd olika krypteringsregler innan du skickar meddelandet. Om du vill skicka ett krypterat meddelande från Outlook 2013 eller 2016 eller Outlook 2016 för Mac väljer du **Alternativ > Behörigheter**och väljer sedan det skyddsalternativ du behöver. Du kan också skicka ett krypterat meddelande genom att välja knappen **Skydda** i Outlook på webben. Mer information finns i [Skicka, visa och svara på krypterade meddelanden i Outlook för PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).

## <a name="admin-settings"></a>Administratörsinställningar

Du kan lära dig allt om hur du konfigurerar e-postkryptering vid [e-postkryptering i Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).

### <a name="automatically-encrypt-email-messages"></a>Kryptera e-postmeddelanden automatiskt

Administratörer kan skapa regler för e-postflöde för att automatiskt skydda e-postmeddelanden som skickas och tas emot från din kampanj. Ställ in regler för att kryptera utgående e-postmeddelanden och ta bort kryptering från krypterade meddelanden som kommer inifrån organisationen eller från svar på krypterade meddelanden som skickas från din organisation. 

Du skapar regler för e-postflöde för att kryptera e-postmeddelanden med de nya OME-funktionerna (Message Encryption) för Office 365. Definiera regler för e-postflöde för att utlösa meddelandekryptering med de nya OME-funktionerna med hjälp av Administrationscenter för Exchange (EAC). 

1. Logga in med hjälp av ett arbets- eller skolkonto som har beviljats globala administratörsbehörighet i en webbläsare. 
2. Välj panelen Admin. 
3. Välj **Administrationscenter > Exchange i administrationscentret**. 

Mer information finns i [Definiera regler för e-postflöde för att kryptera e-postmeddelanden](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).

### <a name="brand-your-encryption-messages"></a>Brännmärka dina krypteringsmeddelanden

Du kan också använda kampanjprofilen för att anpassa utseendet och texten i e-postmeddelandena. Mer information finns i [Lägga till organisationens varumärke i dina krypterade meddelanden](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).

