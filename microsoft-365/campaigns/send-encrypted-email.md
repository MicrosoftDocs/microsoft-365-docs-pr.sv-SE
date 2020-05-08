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
ms.openlocfilehash: fe0835c7b5b3328114ce7820da3336ca9f300d3e
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165691"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>Kryptera eller märka din känsliga e-post

Dina data- och kampanjinformationer är viktiga och ofta konfidentiella. Skydda den här känsliga informationen genom att använda krypterings- och känslighetsetiketter så att du och dina e-postmottagare behandlar informationen med den känslighet som krävs.


## <a name="best-practices"></a>Metodtips

Innan du skickar e-post med konfidentiell eller känslig information bör du överväga att aktivera:

- **Kryptering:** Du kan kryptera din e-post för att skydda sekretessen för informationen i e-postmeddelandet. När du krypterar ett e-postmeddelande konverteras det från läsbar oformaterad text till förvrängd cyphertext. Endast den mottagare som har den privata nyckeln som matchar den offentliga nyckeln som används för att kryptera meddelandet kan dechiffrera meddelandet för läsning. Alla mottagare utan motsvarande privata nyckel ser dock oläslig text. Administratören kan definiera regler för att automatiskt kryptera meddelanden som uppfyller vissa kriterier. Administratören kan till exempel skapa en regel som krypterar alla meddelanden som skickas utanför organisationen eller alla meddelanden som nämner specifika ord eller fraser. Alla krypteringsregler tillämpas automatiskt.
- **Känslighetsetiketter:** Kampanjen kan också ställa in känslighetsetiketter som du kan använda på dina filer och e-post för att hålla dem kompatibla med kampanjens informationsskyddsprinciper. När du anger en etikett finns etiketten kvar med din e-post, även när den skickas, till exempel genom att visas som en rubrik i meddelandet.

![Diagram över ett e-postmeddelande med bildtexter för etiketter och kryptering](../media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a>Konfigurera

Om du vill kryptera ett meddelande som inte uppfyller en fördefinierad regel eller om administratören inte har ställt in några regler kan du tillämpa en mängd olika krypteringsregler innan du skickar meddelandet. Om du vill skicka ett krypterat meddelande från Outlook 2013 eller 2016 eller Outlook 2016 för Mac väljer du **Alternativ > Behörigheter**och väljer sedan det skyddsalternativ du behöver. Du kan också skicka ett krypterat meddelande genom att välja knappen **Skydda** i Outlook på webben. Mer information finns i [Skicka, visa och svara på krypterade meddelanden i Outlook för PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).

## <a name="admin-settings"></a>Administratörsinställningar

Du kan läsa allt om hur du konfigurerar e-postkryptering vid [e-postkryptering i Office 365](https://docs.microsoft.com/office365/securitycompliance/email-encryption).

### <a name="automatically-encrypt-email-messages"></a>Kryptera e-postmeddelanden automatiskt

Administratörer kan skapa regler för e-postflöde för att automatiskt skydda e-postmeddelanden som skickas och tas emot från din kampanj. Ställ in regler för att kryptera utgående e-postmeddelanden och ta bort kryptering från krypterade meddelanden som kommer inifrån organisationen eller från svar på krypterade meddelanden som skickas från din organisation. 

Du skapar regler för e-postflöde för att kryptera e-postmeddelanden med de nya OME-funktionerna (Message Encryption) för Office 365. Definiera regler för e-postflöde för att utlösa meddelandekryptering med de nya OME-funktionerna med hjälp av Exchange Admin Center (EAC). 

1. Logga in på Office 365 i en webbläsare med hjälp av ett arbets- eller skolkonto som har beviljats globala administratörsbehörighet. 
2. Välj panelen Admin. 
3. Välj **Administrationscenter > Exchange i administrationscentret**. 

Mer information finns i [Definiera regler för e-postflöde för att kryptera e-postmeddelanden i Office 365](https://docs.microsoft.com/office365/securitycompliance/define-mail-flow-rules-to-encrypt-email).

### <a name="brand-your-encryption-messages"></a>Brand dina krypteringsmeddelanden

Du kan också använda kampanjprofilen för att anpassa utseendet och texten i e-postmeddelandena. Mer information finns i [Lägga till organisationens varumärke i dina krypterade meddelanden](https://docs.microsoft.com/office365/securitycompliance/email-encryption).

