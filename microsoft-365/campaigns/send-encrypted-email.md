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
description: Lär dig hur du skickar krypterad e-post med hjälp av Outlook.
ms.openlocfilehash: d17abccd645b4dfdf933906dc90175be51f95c9a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044222"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>Kryptera eller märk dina konfidentiella e-postmeddelanden

Dina data och kampanjinformation är viktig och ofta konfidentiell. Skydda den här känsliga informationen genom att använda krypterings- och känslighetsetiketter så att du och dina e-postmottagare kan behandla informationen med den känslighet som krävs.

## <a name="best-practices"></a>Metodtips

Innan du skickar e-post med konfidentiell eller känslig information bör du överväga att aktivera:

- **Kryptering:** Du kan kryptera din e-post för att skydda informationen i e-postmeddelandet. När du krypterar ett e-postmeddelande konverteras det från läsbar oformaterad text till kodad cyfertext. Endast mottagaren som har den privata nyckeln som matchar den offentliga nyckeln som används för att kryptera meddelandet kan dechiffrera meddelandet för läsning. Alla mottagare utan motsvarande privat nyckel ser däremot ochiffrbar text. Administratören kan definiera regler för att automatiskt kryptera meddelanden som uppfyller vissa villkor. Din administratör kan till exempel skapa en regel som krypterar alla meddelanden som skickas utanför organisationen eller alla meddelanden som nämner specifika ord eller fraser. Alla krypteringsregler tillämpas automatiskt.
- **Känslighetsetiketter:** Din kampanj kan också konfigurera känslighetsetiketter som du kan använda för dina filer och e-post för att hålla dem kompatibla med informationsskyddsprinciperna för din kampanj. När du anger en etikett finns etiketten kvar med ditt e-postmeddelande, även när det skickas – till exempel genom att visas som ett sidhuvud i meddelandet.

![Diagram över ett e-postmeddelande med bildtexter för etiketter och kryptering](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a>Konfigurera

Om du vill kryptera ett meddelande som inte uppfyller en fördefinierad regel eller administratören inte har angett några regler kan du använda en mängd olika krypteringsregler innan du skickar meddelandet. Om du vill skicka ett krypterat meddelande från Outlook 2013 eller 2016 eller Outlook 2016 för Mac väljer du **Alternativ >** Behörigheter och sedan det skyddsalternativ du behöver. Du kan också skicka ett krypterat meddelande genom att välja **knappen** Skydda i Outlook på webben. Mer information finns i [Skicka, visa och svara på krypterade meddelanden i Outlook för PC.](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)

## <a name="admin-settings"></a>Administratörsinställningar

Du kan lära dig allt om att konfigurera e-postkryptering i [E-postkryptering i Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)

### <a name="automatically-encrypt-email-messages"></a>Kryptera e-postmeddelanden automatiskt

Administratörer kan skapa e-postflödesregler för att automatiskt skydda e-postmeddelanden som skickas och tas emot från kampanjen. Konfigurera regler för att kryptera alla utgående e-postmeddelanden och ta bort kryptering från krypterade meddelanden som kommer från din organisation eller från svar på krypterade meddelanden som skickas från organisationen.

Du kan skapa e-postflödesregler för att kryptera e-postmeddelanden med den nya funktionen meddelandekryptering i Office 365 (OME). Definiera e-postflödesregler för att utlösa meddelandekryptering med de nya OME-funktionerna med hjälp av administrationscentret för Exchange (EAC). 

1. Logga in i en webbläsare som använder ett arbets- eller skolkonto som har beviljats global administratörsbehörighet.
2. Välj panelen Admin.
3. I administrationscentret väljer du **Administrationscenter > Exchange.**

Mer information finns i Definiera [e-postflödesregler för att kryptera e-postmeddelanden.](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)

### <a name="brand-your-encryption-messages"></a>Profilera krypteringsmeddelanden

Du kan också använda kampanjmärket om du vill anpassa utseendet och texten i e-postmeddelandena. Mer information finns i [Lägga till organisationens varumärke i krypterade meddelanden.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)
