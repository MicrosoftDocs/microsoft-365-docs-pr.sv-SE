---
title: Hantera åtkomst till e-postprogrammet Microsoft 365 administrationscenter
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
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: d00b6b83-1f14-4e9c-a2c5-dbd9a92816f4
ROBOTS: NOINDEX, NOFOLLOW
description: Läs om hur du väljer vilka mobilappar som användare kan använda för att komma åt e-post, kalender och kontakter.
ms.openlocfilehash: f114aa43b4bbade09d53f415aae4c5c033c20694
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400058"
---
# <a name="manage-email-app-access-in-the-microsoft-365-admin-center"></a>Hantera åtkomst till e-postprogrammet Microsoft 365 administrationscenter

Använd inställningarna för åtkomst till mobil e-post och välj vilka mobilappar som personer i organisationen kan använda för att komma åt sitt arbets- eller skolkonto för att komma åt e-post, kalender och kontakter.
  
> [!IMPORTANT]
> Organisationen har åtkomst till den här inställningen såvida du inte använder Microsoft Intune eller om du har konfigurerat inställningar för hantering av mobila enheter i Exchange administrationscenter. 
  
## <a name="manage-email-app-options"></a>Hantera alternativ för e-postappen

> [!IMPORTANT]
>  Om du inte använder den här funktionen ändras inte användarupplevelsen. De kommer att kunna använda valfri mobilapp för e-post för att komma åt sitt arbets- eller skolkonto för e-post, kalender och kontakter från sina mobila enheter. 
    
1. I administrationscentret går du till sidan **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Tjänster och tillägg</a>. 

2. Markera kryssrutan **på sidan Åtkomstalternativ för mobil** e-post och välj sedan hur användare i organisationen använder e-postappar på sina enheter:
  
Välj alternativet för att ange hur användare i organisationen får åtkomst till sitt arbets- eller skolkonto från sina mobila enheter
  
- **Outlook endast** – användare i organisationen måste använda appen Outlook för Android eller Outlook för iOS på sina mobila enheter. 
    
- **Alla e-postappar** – alla användare i organisationen uppmanas att använda Outlook, men de kan välja att använda valfri e-postapp. 
    
- **Alla e-postappar** – nya användare eller enheter i organisationen uppmanas en gång att använda Outlook, men de kan välja att använda valfri e-postapp. 
    
Mer information finns i Alternativ för [att komma åt e-post från din mobila enhet.](access-email-from-a-mobile-device.md)
  
## <a name="new-user-or-device-is-activated-in-your-organization"></a>Ny användare eller enhet aktiveras i organisationen

När en användare i organisationen lägger till e-post för arbete eller skola i en e-postapp från tredje part eller på en ny enhet får de ett e-postmeddelande från **Microsoft med din organisations räkning.** I e-postmeddelandet får de information om fördelarna med att Outlook-mobilappen och en länk till nedladdningsplatsen. Användarna kan sedan välja om de vill fortsätta använda tredjepartsappen eller välja att använda Outlook mobilappen. Under de 24 timmarna efter att användaren först får det här e-postmeddelandet kommer deras enhet att finnas i karantän, och e-post, kalender och kontaktdata uppdateras inte. Om de väljer att använda Outlook-mobilappen förblir tredjepartsprogrammet i karantän och data synkroniseras bara med Outlook-mobilappen. Om de bestämmer sig för att fortsätta använda programmet från tredje part synkroniseras data direkt. Om ingen åtgärd vidtas under de första 24 timmarna kommer e-postmeddelandet att tas bort från inkorgen och data börjar synkroniseras från servern automatiskt.
  
## <a name="previously-configured-users-in-your-organization"></a>Tidigare konfigurerade användare i organisationen

Om du bestämmer dig för att rekommendera Outlook till alla i organisationen får, förutom den upplevelse som beskrivs ovan för nya användare, även användare som tidigare har anslutit sitt arbets- eller skolkonto för e-post till en app från tredje part ett e-postmeddelande från **Microsoft** på uppdrag av din organisation inom 48 timmar efter att den här inställningen aktiverats. I e-postmeddelandet får de information om fördelarna med att Outlook-mobilappen och en länk till nedladdningsplatsen. Användarna kan sedan välja om de vill fortsätta använda tredjepartsappen eller välja att använda Outlook mobilappen. Under de 24 timmarna efter att användaren först får det här e-postmeddelandet kommer deras enhet att finnas i karantän, och e-post, kalender och kontaktdata uppdateras inte. Om de väljer att använda Outlook-mobilappen förblir tredjepartsprogrammet i karantän och data synkroniseras bara med Outlook-mobilappen. Om de bestämmer sig för att fortsätta använda programmet från tredje part synkroniseras data direkt. Om ingen åtgärd vidtas under de första 24 timmarna kommer e-postmeddelandet att tas bort från inkorgen och data börjar synkroniseras från servern automatiskt. 
  

