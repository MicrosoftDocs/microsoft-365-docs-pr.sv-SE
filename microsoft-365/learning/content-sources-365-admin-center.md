---
title: Konfigurera utbildningsinnehållskällor för Microsoft Viva Learning (förhandsversion) i Administrationscenter för Microsoft 365
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/12/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Lär dig hur du konfigurerar utbildningsinnehållskällor för Microsoft Viva Learning (förhandsversion) i Administrationscenter för Microsoft 365.
ms.openlocfilehash: ac9ec6196f758d3ed02d3a102fef80b8a7adeeaa
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288929"
---
# <a name="configure-learning-content-sources-for-microsoft-viva-learning-preview-in-the-microsoft-365-admin-center"></a>Konfigurera utbildningsinnehållskällor för Microsoft Viva Learning (förhandsversion) i Administrationscenter för Microsoft 365

> [!NOTE]
> Informationen i den här artikeln gäller en förhandsversion av en produkt som kan komma att ändras väsentligt innan den släpps till kommersiellt bruk. 

Administratörerna för Administrationscenter för Microsoft 365 - antingen för sig själv eller genom att tilldela rollen som kunskapsadministratör till valda personer i organisationen – kan hantera inställningar för Viva Learning (förhandsversion) och kan konfigurera källor för utbildningsinnehåll.

Administratören väljer vilka andra källor för utbildningsinnehåll (till exempel SharePoint eller andra innehållsleverantörskällor som stöds) som är tillgängliga för användare av Viva Learning (förhandsversion). Administratören konfigurerar sedan dessa källor för att se till att innehållet är tillgängligt för sökning och identifiering och kan bläddras bland de anställda som använder Viva Learning (förhandsversion).

> [!NOTE]
>  Användarna loggar in på andra program än Microsoft och LinkedIn Learning Pro i en webbläsare eller ett inbäddat visningsprogram. Den konfigurerade inlärningen omfattas av separata licens-, sekretess- och tjänstvillkor mellan din organisation och tredje part, och inte villkoren för Viva Learning (förhandsversion). Innan du väljer den här typen av utbildning bör du kontrollera att organisationen och användarna har ett avtal.

## <a name="assign-the-knowledge-admin-role-optional"></a>Tilldela knowledge admin-rollen (valfritt)

Du måste vara global Microsoft 365 för att utföra de här uppgifterna.

> [!TIP]
> Kunskapsadministratören bör vara måttligt teknisk och ha befintliga autentiseringsuppgifter som SharePoint-administratör, helst någon som är väl insatt inom utbildning, utbildning eller medarbetarupplevelse inom organisationen.

### <a name="add-a-knowledge-admin"></a>Lägga till en kunskapsadministratör

Följ de här stegen om du vill lägga till en kunskapsadministratör för Viva Learning (förhandsversion):

1. I det vänstra navigeringsfältet i Administrationscenter för Microsoft 365 du till **Roller.**

2. På sidan **Roller** på fliken **Azure AD** väljer du **Knowledge Administrator**.
 
3. På panelen **Knowledge Administrator** väljer du Tilldelade **administratörer och** sedan Lägg **till**.

     ![Sidan Roller i Administrationscenter för Microsoft 365 visar panelen Knowledge Administrator för att lägga till en användare.](../media/learning/learning-add-knowledge-admin-1.png)

3. På panelen **Lägg till administratörer** väljer du den person du väljer för rollen och väljer sedan Lägg **till**.

     ![Sidan Roller i Administrationscenter för Microsoft 365 visar panelen Lägg till administratörer för att lägga till en användare.](../media/learning/learning-add-knowledge-admin-2.png)

### <a name="remove-a-knowledge-admin"></a>Ta bort en kunskapsadministratör

Om du vill ta bort en kunskapsadministratör för Viva Learning (förhandsversion) gör du så här:

1. I det vänstra navigeringsfältet i Administrationscenter för Microsoft 365 du till **Roller.**

2. På sidan **Roller** går du till **fliken Azure AD** och väljer sedan **Kunskapsadministratör.**
 
3. På panelen **Kunskapsadministratör** på fliken **Tilldelade administratörer väljer** du Ta **bort** och sedan den person du vill ta bort från rollen. Bekräfta genom att välja Ta **bort**.

     ![Sidan Roller i Administrationscenter för Microsoft 365 visar panelen Tilldelade administratörer för att ta bort en användare.](../media/learning/learning-remove-knowledge-admin-1.png)

## <a name="configure-settings-for-the-learning-content-sources"></a>Konfigurera inställningar för källor för utbildningsinnehåll

Du måste vara global Microsoft 365 eller kunskapsadministratör för att kunna utföra de här uppgifterna.

Om du vill konfigurera inställningar för innehållskällor för inlärning i Viva Learning du följande steg:

1. I det vänstra navigeringsfältet i Administrationscenter för Microsoft 365 går du till **Inställningar**  >  **Organisationsinställningar**.

2. På sidan **Organisationsinställningar** på fliken **Tjänster väljer** du **Viva Learning (förhandsversion)**.

     ![Inställningar sidan i Administrationscenter för Microsoft 365 där Learning visas.](../media/learning/learning-sharepoint-configure1.png)

3. På panelen **Viva Learning (förhandsversion)** väljer du de utbildningsinnehållskällor du vill konfigurera för organisationen och väljer sedan **Spara**.

     ![Learning på fliken Administrationscenter för Microsoft 365 med alternativ för innehållskällor.](../media/learning/learning-sharepoint-configure2.png)

En del av alla utbildningskällor är aktiverade som standard. Följande utbildningskällor omfattar:

- LinkedIn Learning (kostnadsfritt innehåll)
- Microsoft Learn
- Microsoft 365 Utbildning

> [!NOTE]
> Kostnadsfritt LinkedIn-innehåll tillhandahålls till användare enligt sekretesspolicyn och användaravtalet för LinkedIn. LinkedIn tar emot användarens IP-adress, eventuella cookies som tidigare ställts in av LinkedIn, och ställer in en ny cookie för att spåra användningen av kostnadsfritt innehåll. Användarna behöver inte logga in med LinkedIn för att få kostnadsfritt innehåll.<br><br>
För LinkedIn premiuminnehåll behöver organisationen en prenumeration för ditt team för att få åtkomst till innehållet. Användarna måste logga in på LinkedIn för att få åtkomst till inlärningen, som tillhandahålls i villkoren för din organisations och din organisations användningsvillkor med LinkedIn.<br><br> För icke-Microsoft-innehåll (med undantag för kostnadsfritt LinkedIn-innehåll) ska du se till att din organisation har en prenumeration för användarna att komma åt innehållet med ett arbetskonto innan de ansluter det till Viva Learning (förhandsversion). Användarnas personliga prenumerationer på icke-Microsoft-utbildningsleverantörer kommer inte att integreras med Viva Learning (förhandsversion). Användarna loggar in på andra program än Microsoft och LinkedIn Learning Pro i en webbläsare eller ett inbäddat visningsprogram. Om användarna navigerar till innehåll där de inte har en organisationsprenumeration kan de se en leverantörssida där de kan registrera sig för en enskild prenumeration. All utbildning som inte tillhör Microsoft tillhandahålls enligt villkoren som inte tillhör Microsoft och inte som en del av Viva Learning. 

Om du vill aktivera eller inaktivera en källa för utbildningsinnehåll markerar du kryssrutan bredvid källan. Om en källa är aktiverad visas en bockmarkering.

## <a name="third-party-content-providers"></a>Tredjepartsleverantörer av innehåll 

Uppsättningen tillgängliga anslutna utbildningsleverantörer kan ändras när som helst. Fler leverantörer ansluter allt eftersom programmet växer. Tillgängliga leverantörer kan också välja att avbryta sin anslutning med Viva Learning (förhandsversion).

### <a name="skillsoft-as-a-content-source"></a>Skillsoft som innehållskälla  

För Viva Learning (förhandsversion) hamnar användare som har Skillsoft aktiverat och väljer att visa Skillsoft-innehåll på en Percipio-sida där de uppmanas att ange organisationens Percipio-webbplatsnamn. När användarna matar in organisationens webbplatsnamn dirigeras de till sidan för att logga in på din organisations Percipio-webbplats. Användarna loggar in med sina befintliga autentiseringsuppgifter och ser innehållet som de ursprungligen valde. Användarna uppmanas att ange Percipio-webbplatsens namn endast en gång, tills deras webbläsarcache har rensats. För att effektivisera den här upplevelsen för användarna rekommenderar vi att du inkluderar percipiowebbplatsnamnet i den interna kommunikation som du skickar om Viva Learning (förhandsversion).

Det här är tänkt som en tillfällig upplevelse för förhandsversionen och vi arbetar med Skillsoft för att möjliggöra en klientspecifik integrering för allmän tillgänglighet, vilket kringgår steget som kräver att användarna anger organisationens Percipio-webbplatsnamn. 

### <a name="details-on-microsoft-substrate"></a>Information om Microsoft – Microsoft  

För data som du kopierar till Viva Learning (förhandsversion) från en tjänst utanför Microsoft (utbildningsleverantör eller utbildningshanteringssystem) kan du inte direkt extrahera, korrigera eller ta bort dessa data i Viva Learning (förhandsversion). Vi uppdaterar de data du importerar från leverantörer som inte är Microsoft-leverantörer snabbt för att återspegla ändringar och borttagningar i källdata som inte kommer från Microsoft.

Du måste arbeta med leverantören av tjänsten som inte är Microsoft för att få åtkomst till, korrigera, ta bort eller extrahera data under licensen, tjänsten eller sekretessvillkoren för icke-Microsoft-tjänsten. Ändringarna som görs där återspeglas i de data som bearbetats för din användning i Viva Learning (förhandsversion) när datauppdateringscyklerna för tjänster som inte är Microsoft och Viva Learning (förhandsversion) har slutförts. Om du stänger av anslutningen mellan Viva Learning (förhandsversion) och en tjänst som inte är en Microsoft-tjänst tas alla data du tidigare importerat från den tjänsten bort. 

## <a name="next-step"></a>Nästa steg

[Konfigurera SharePoint som källa för utbildningsinnehåll för Microsoft Viva Learning (förhandsversion)](configure-sharepoint-content-source.md)