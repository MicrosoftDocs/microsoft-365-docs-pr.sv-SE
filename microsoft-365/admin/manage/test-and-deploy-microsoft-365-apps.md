---
title: Testa och distribuera Microsoft 365-appar
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
ms.custom: AdminSurgePortfolio
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Hitta, testa och distribuera Microsoft-och Microsoft partner-appar för användare och grupper i din organisation från portalen för integrerade program i administrations centret för Microsoft 365.
ms.openlocfilehash: b0dc6277461ff03e8aae2e820543f8e5d9e2303c
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790196"
---
# <a name="test-and-deploy-microsoft-365-apps-in-the-microsoft-365-admin-center"></a>Testa och distribuera Microsoft 365-appar i administrations centret för Microsoft 365

Administrations centret för Microsoft 365 ger dig flexibilitet att distribuera Microsoft-och Microsoft-partner-appar från en enda plats. Möjligheten att hitta, testa och helt distribuera köpta och licensierade appar från Microsoft och Microsoft-partners från den integrerade program-portalen är en kombination av de möjligheter och fördelar som organisationen kräver för att hålla företags tjänsterna uppdaterade regelbundet och effektivt.  

Mer information om hur du köper och licensierar Microsoft 365-appar för din organisation finns i blogg inlägget som heter [Hantera och distribuera microsoft 365-program från microsoft 365 Admin Center](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324).
  
## <a name="manage-apps-in-the-integrated-apps-portal"></a>Hantera program i portalen för integrerade appar

Genom att välja integrerade appar i Microsoft 365 Admin Center kan du hantera testning och distribution av köpta och licensierade Microsoft-och Microsoft partner-appar. 

1. Välj **Inställningar** i administrations centret i det vänstra navigerings fältet och välj **integrerade appar**. 

2. Välj en app med **status** för **fler program tillgängliga**.

3. Välj **distribuera** högst upp på sidan bredvid meddelandet som refererar till väntande distribution.

    För vissa appar måste du lägga till användare innan du kan välja **distribuera**.

    a. Välj **Lägg till användare**, Välj **fullständig distribution** och välj sedan **hela organisationen** eller **specifika användare/grupper**.

    Specifika användare/grupper kan vara en Microsoft 365-grupp, en säkerhets grupp eller en distribuerad grupp.

    Du kan också välja **testa distribution** om du föredrar att vänta med att distribuera appen till hela organisationen.

    b. Välj **Uppdatera**, **klart** och nu kan du välja **distribuera** på fliken **Översikt** .  

4. Granska program informationen och välj sedan **distribuera**. 

5. Välj **klar** på sidan **distributionen är klar** . 

    Granska informationen om testet eller fullständig distribution på fliken **Översikt** .

## <a name="find-published-apps-for-testing-and-full-deployment"></a>Hitta publicerade program för testning och fullständig distribution 

Du kan söka efter, testa och distribuera publicerade appar som inte redan visas i listan på sidan integrerade appar. Genom att köpa och licensiera appar från administrations centret kan du lägga till Microsoft-och Microsoft-partner-appar i din lista från en och samma plats.

1. Välj **Inställningar** i administrations centret i det vänstra navigerings fältet och välj **integrerade appar**. 

2. Välj **Hämta program** ovanför listan med program.

3. Välj den app du vill distribuera på sidan **Microsoft 365-program** för publicerade appar genom att välja **Skaffa det nu**.

4. Godkänn behörigheterna och välj sedan **Continue**.

5. Välj **distribuera** högst upp på sidan bredvid meddelandet som refererar till väntande distribution.

    För vissa appar måste du lägga till användare innan du kan välja **distribuera**.

    a. Välj **Lägg till användare**, Välj **fullständig distribution** och välj sedan **hela organisationen** eller **specifika användare/grupper**.

    Specifika användare/grupper kan vara en Microsoft 365-grupp, en säkerhets grupp eller en distribuerad grupp.

    Du kan också välja **testa distribution** om du föredrar att vänta med att distribuera appen till hela organisationen.

    b. Välj **Uppdatera**, **klar** och nu kan du välja **distribuera** på fliken **Översikt** .  

6. Granska program informationen och välj sedan **distribuera**. 

7. Välj **klar** på sidan **distributionen är klar** . 

    Granska informationen om testet eller fullständig distribution på fliken **Översikt** .

I Microsoft 365 Admin Center är varje distribuerad program **status** **OK** med en **distributions typ** för **test distribution**, **fullständig distribution** eller **anpassad** samt det datum då du distribuerade appen.

> [!NOTE]
> Om ett program redan har distribuerats från någon annan plats än den integrerade program portalen är **distributions typen** **anpassat.**

## <a name="unsupported-scenarios"></a>Scenarier som inte stöds

Följande scenarier stöds för närvarande inte för distribution från den integrerade program-portalen:

- Programmet eller tillägget har länkats till fler än ett program som tjänst (SaaS).
- SaaS-appen är länkad till program och tillägg, men har inte en associerad AADid.
- Två SaaS-appar delar samma AADid och de är båda länkade till appar eller tillägg.
  