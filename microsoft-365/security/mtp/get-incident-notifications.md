---
title: Få incident meddelanden i Microsoft 365 Defender
description: Lär dig hur du skapar regler för att få e-postaviseringar för händelser i Microsoft 365 Defender
keywords: incident, e-post, e-Notfications, konfigurera, användare, post låda, e-post, incidenter
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 3af1dcfec165c88a18cbc0d8cbf6866bb6398adc
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668363"
---
# <a name="get-incident-notifications-by-email"></a>Få incident meddelanden via e-post

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!IMPORTANT]
> Funktionen e-postaviseringar för incidenter finns för närvarande i offentlig för hands version. Viss information om den här funktionen kan komma att ändras innan du är tillgänglig. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.

**Gäller för:**
- Microsoft 365 Defender

Du kan ställa in Microsoft 365 Defender för att meddela dig via e-post varje gång det uppstår nya tillbud eller nya uppdateringar till befintliga incidenter. 

Du kan välja att få aviseringar baserat på allvarlighets graden och per enhets grupp. Du kan också välja att bara få ett meddelande vid den första uppdateringen per olycka.

Du kan lägga till eller ta bort mottagare i e-postaviseringar. Nya mottagare meddelas om incidenter när de har lagts till. 

E-postmeddelandet innehåller viktig information om händelsen, till exempel namn, allvarlighets grad och kategorier, bland annat. Du kan även gå direkt till incidenter så att du kan påbörja undersökningen omedelbart. Mer information om hur du undersöker problem finns i [undersöka incidenter i Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).

>[!NOTE]
>Du måste ha behörigheten Hantera säkerhets inställningar för att konfigurera inställningar för e-postaviseringar. Om du har valt att använda grundläggande behörighets hantering kan användare med rollen som säkerhets administratör eller global administratör konfigurera e-postaviseringar åt dig. <br> <br>
Om din organisation använder rollbaserad åtkomst kontroll (RBAC) kan du välja att bara skapa, redigera, ta bort och ta emot meddelanden baserat på de enhets grupper som du får hantera.

## <a name="create-rules-for-incident-notifications"></a>Skapa regler för problem meddelanden

Skapa en ny regel och anpassa inställningarna för e-postaviseringar om du vill ställa in ett första meddelande.

1. I navigerings fönstret väljer du **Inställningar** för  >  **incident epost meddelanden**.
2. Välj **Lägg till objekt**.
3. Ge regeln ett namn i **namn** och ange en **Beskrivning**.

    ![Fönstret Skapa regel för e-notifs](../../media/incidentemailnotif1.png) 
4. Välj **Nästa** för att gå till **aviserings inställningar**. Här kan du ange:
    - **Aviserings allvarlighets grad** – Välj aviseringens allvarlighets grad som kommer att utlösa en incident avisering. Om du till exempel bara vill bli informerad om problem med hög allvarlighets grad väljer du High.
    - **Enhets gruppens omfattning** – den här List rutan visar alla enhets grupper som användaren kan komma åt. Välj vilka enhets grupper som du vill skapa incident regler för.
    - **Meddela bara vid den första förekomsten per händelse** – om du väljer det här alternativet skickas ett e-postmeddelande endast för den första aviseringen som matchar dina andra val. Senare uppdateringar eller larm som rör händelsen utlöser inte ett meddelande.
    - **Inkludera organisationens namn** -visar om kund namnet visas i e-postmeddelandet eller inte.
    - **Inkludera klient organisationens specifika Portal länk** -lägger till en länk med klient organisationens ID för att tillåta åtkomst till en viss klient organisation.
    
    ![Fönstret medd. inställningar för notifs e-post](../../media/incidentemailnotif2.png)
5. Välj **Nästa** för att gå till avsnittet **mottagare** . Här kan du ange e-postadresser som får e-postaviseringar om incidenten. Välj **Lägg till en mottagare** efter varje e-postadress.

    ![Fönstret Lägg till mottagare för e-notifs](../../media/incidentemailnotif3.png) 

6. Välj **sedan nästa** för att gå till **gransknings regel** så att du kan se alla inställningar som är associerade med den nya regeln. Mottagarna kommer att få eventuella problem meddelanden via e-post baserat på inställningarna.

## <a name="see-also"></a>Se även
- [Incidenter översikt i Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [Prioritera incidenter i Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [Undersök incidenter i Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

