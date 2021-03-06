---
title: Konfigurera villkorsstyrd åtkomst i Microsoft Defender för Slutpunkt
description: Läs mer om steg som du måste göra i Intune, Microsoft 365 Defender och Azure för att implementera villkorsstyrd åtkomst
keywords: villkorsstyrd åtkomst, villkorsstyrd, åtkomst, enhetsrisk, risknivå, integrering, intune-integrering
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2c9462fa0d4be4d6ff78ba3e5db2cd4fa71fef0b
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339520"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a>Konfigurera villkorsstyrd åtkomst i Microsoft Defender för Slutpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

I det här avsnittet får du vägledning genom alla steg du behöver vidta för att implementera villkorsstyrd åtkomst på rätt sätt.

### <a name="before-you-begin"></a>Innan du börjar
>[!WARNING]
>Det är viktigt att observera att registrerade Azure AD-enheter inte stöds i det här scenariot.</br>
>Endast registrerade Intune-enheter stöds.


Du måste se till att alla dina enheter är registrerade i Intune. Du kan använda något av följande alternativ för att registrera enheter i Intune:


- IT-administratör: Mer information om hur du aktiverar automatisk registrering finns Windows [registrering](/intune/windows-enroll#enable-windows-10-automatic-enrollment)
- Slutanvändare: Mer information om hur du registrerar din Windows 10 i Intune finns i Registrera din [Windows 10 i Intune](/intune/quickstart-enroll-windows-device)
- Alternativ för slutanvändare: Mer information om hur du ansluter till en Azure AD-domän finns i Så här gör du: Planera din implementering av [Azure AD-koppling.](/azure/active-directory/devices/azureadjoin-plan)



Det finns åtgärder du måste vidta i Microsoft 365 Defender, Intune-portalen och Azure AD-portalen.

Det är viktigt att observera de roller som krävs för att komma åt dessa portaler och implementera villkorsstyrd åtkomst:
- **Microsoft 365 Defender** – Du måste logga in på portalen med en global administratörsroll för att aktivera integreringen.
- **Intune** – Du måste logga in på portalen med behörigheten säkerhetsadministratör med hanteringsbehörighet. 
- **Azure AD-portal** – Du måste logga in som global administratör, säkerhetsadministratör eller villkorsstyrd åtkomstadministratör.


> [!NOTE]
> Du behöver en miljö för Microsoft Intune med Intune hanterad och Azure AD-ansluten Windows 10 enheter.

Gör följande för att aktivera villkorsstyrd åtkomst:
- Steg 1: Aktivera Microsoft Intune från Microsoft 365 Defender
- Steg 2: Aktivera Defender för slutpunktsintegrering i Intune
- Steg 3: Skapa efterlevnadsprincipen i Intune
- Steg 4: Tilldela principen 
- Steg 5: Skapa en villkorsbaserad åtkomstprincip i Azure AD


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a>Steg 1: Aktivera Microsoft Intune anslutning
1. I navigeringsfönstret väljer du Ange **Inställningar**  >  **Allmänna**  >  **avancerade funktioner** i  >  **Microsoft Intune**  >  **Slutpunkter.**
2. Ändra inställningen Microsoft Intune till **På**.
3. Klicka **på Spara inställningar.**


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a>Steg 2: Aktivera Defender för slutpunktsintegrering i Intune
1. Logga in på [Azure-portalen](https://portal.azure.com).
2. Välj **Enhetsefterlevnad**  >  **Microsoft Defender ATP**.
3. Ställ **Anslut Windows 10.0.15063+-enheter på Microsoft Defender Avancerat skydd på** **På.**
4. Klicka på **Spara**.


### <a name="step-3-create-the-compliance-policy-in-intune"></a>Steg 3: Skapa efterlevnadsprincipen i Intune
1. I [Azure-portalen](https://portal.azure.com)väljer du **Alla tjänster**, filtrera på **Intune** och väljer **sedan Microsoft Intune**.
2. Välj **Principer för**  >  **enhetsefterlevnad**  >  **Skapa princip**.
3. Ange namn **och** **beskrivning.**
4. I **Plattform** väljer du **Windows 10 och senare**.
5. I inställningarna **för Enhetshälsa** ställer du **in Kräv att enheten är på eller under enhetshotsnivån till** önskad nivå:

   - **Skyddad:** Den här nivån är den säkraste. Enheten kan inte ha befintliga hot och får fortfarande åtkomst till företagets resurser. Om några hot hittas utvärderas enheten som icke-kompatibel.
   - **Låg:** Enheten är kompatibel om det bara finns hot på låg nivå. Enheter med medelhöga eller höga hotnivåer följer inte kraven.
   - **Medel:** Enheten är kompatibel om hoten som finns på enheten är låga eller medelstora. Om hot på hög nivå upptäcks identifieras enheten som icke-kompatibel.
   - **Hög:** Den här nivån är den minst säkra och tillåter alla hotnivåer. Enheter med höga, medelhöga eller låga hotnivåer anses därför vara kompatibla.

6. Välj **OK** och skapa **för** att spara ändringarna (och skapa principen).

### <a name="step-4-assign-the-policy"></a>Steg 4: Tilldela principen
1. I [Azure-portalen](https://portal.azure.com)väljer du **Alla tjänster**, filtrera på **Intune** och väljer **sedan Microsoft Intune**.
2. Välj **Principer för**  >  **enhetsefterlevnad**> välj Microsoft Defender för Endpoints efterlevnadsprincip.
3. Välj **Uppgifter**.
4. Inkludera eller exkludera dina Azure AD-grupper för att tilldela dem principen.
5. Välj Spara om du vill distribuera principen till **grupperna.** Användarenheterna som principen riktar sig till utvärderas för efterlevnad.

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a>Steg 5: Skapa en villkorsbaserad åtkomstprincip i Azure AD
1. I [Azure Portal öppnar](https://portal.azure.com)du **Azure Active Directory**  >  **Ny princip för**  >  **villkorsstyrd åtkomst.**
2. Ange ett **principnamn** och välj **Användare och grupper.** Använd alternativen Inkludera eller Exkludera för att lägga till grupper för principen och välj **Klar**.
3. Välj **Molnappar** och välj vilka appar du vill skydda. Välj till exempel **Välj appar** och välj sedan Välj **Office 365 SharePoint Online** och **Office 365 Exchange Online**. Spara **ändringarna** genom att välja Klar.

4. Välj **Villkor**  >  **Klientappar för** att tillämpa principen för appar och webbläsare. Välj till exempel Ja **och** aktivera sedan **Webbläsar- och** **mobilprogram och skrivbordsklienter**. Spara **ändringarna** genom att välja Klar.

5. Välj **Bevilja för** att använda villkorsstyrd åtkomst baserat på enhetsefterlevnad. Välj till exempel **Bevilja åtkomst**  >  **Kräv att enheten markeras som kompatibel.** Spara **ändringarna** genom att välja Välj.

6. Välj **Aktivera princip** och sedan Skapa **för** att spara ändringarna.

Mer information finns i Tillämpa [efterlevnad för Microsoft Defender för Slutpunkt med villkorsstyrd åtkomst i Intune.](/intune/advanced-threat-protection)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
