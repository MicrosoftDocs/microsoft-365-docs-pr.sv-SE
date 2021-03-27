---
title: Aktivera säkerhetsstandarder
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur säkerhetsstandarder kan skydda organisationen från identitetsrelaterade attacker genom att ange förkonfigurerade säkerhetsinställningar.
ms.openlocfilehash: ea36ba45af26a767b08ee1e75931dca54dacea64
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398302"
---
# <a name="turn-on-security-defaults"></a>Aktivera säkerhetsstandarder

Säkerhetsstandarder hjälper till att skydda organisationen från identitetsrelaterade attacker genom att tillhandahålla förkonfigurerade säkerhetsinställningar som Microsoft hanterar för din organisations räkning. De här inställningarna omfattar aktivering av multifaktorautentisering (MFA) för alla administratörer och användarkonton. För de flesta organisationer erbjuder säkerhetsstandarder en bra nivå av ytterligare inloggningssäkerhet.

Mer information om säkerhetsstandarder och de principer de tillämpar finns i [Vad är standardinställningar för säkerhet?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

Om prenumerationen skapades den 22 oktober 2019 eller efter den 22 oktober 2019 kan säkerhetsstandarder ha aktiverats automatiskt. Kontrollera inställningarna &mdash; för att bekräfta.

Så här aktiverar du säkerhetsstandardvärden i Azure Active Directory (Azure AD) eller kontrollerar om de redan är aktiverade:

1. Logga in på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrationscentret för Microsoft 365 med autentiseringsuppgifter</a> som global administratör.

2. I den vänstra rutan väljer **du Visa alla.** Under **Administratörscentra** väljer du **sedan Azure Active Directory.**

3. I den vänstra rutan i **administrationscentret för Azure Active Directory väljer** du Azure Active **Directory.**

4. I den vänstra menyn på Instrumentpanelen går du till **avsnittet Hantera** och väljer **Egenskaper**.

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="Skärmbild av administrationscentret för Azure Active Directory som visar platsen för menyobjektet Egenskaper.":::

5. Längst ned på sidan **Egenskaper** väljer du **Hantera säkerhetsstandarder.**

6. I det högra fönstret visas standardinställningen **Aktivera** säkerhet. Om **Ja** har valts är säkerhetsstandardvärden redan aktiverade och inga ytterligare åtgärder krävs. Om säkerhetsstandarder inte är aktiverade, väljer du **Ja** för att aktivera dem och väljer sedan **Spara**.

> [!NOTE]
> Om du har använt villkorsstyrda åtkomstprinciper måste du inaktivera dem innan du använder säkerhetsstandarder.
>
> Du kan använda antingen säkerhetsstandarder eller villkorsstyrda åtkomstprinciper, men du kan inte använda båda samtidigt.

## <a name="consider-using-conditional-access"></a>Överväg att använda villkorsstyrd åtkomst

Om organisationen har komplexa säkerhetskrav eller om du behöver mer detaljerad kontroll över dina säkerhetsprinciper bör du överväga att använda villkorsstyrd åtkomst i stället för säkerhetsstandarder för att uppnå ett liknande eller högre säkerhetsbeteende. 

Med villkorsstyrd åtkomst kan du skapa och definiera principer som reagerar på inloggningshändelser och begär ytterligare åtgärder innan en användare beviljas åtkomst till ett program eller en tjänst. Villkorsstyrda principer kan vara detaljerade och specifika så att användarna kan vara produktiva var och när som helst, men även skydda organisationen.

Standardinställningar för säkerhet är tillgängliga för alla kunder, medan villkorsstyrd åtkomst kräver en licens för något av följande abonnemang:

- Azure Active Directory Premium P1 eller P2
- Microsoft 365 Business Premium
- Microsoft 365 E3 eller E5
- Enterprise Mobility & Security E3 eller E5

Om du vill använda villkorsstyrd åtkomst för att konfigurera principer som motsvarar dem som aktiverats som säkerhetsstandard tar du en del av följande steg-för-steg-guider:

- [Kräv MFA för administratörer](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [Kräv MFA för Azure-hantering](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)
- [Blockera äldre autentisering](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)
- [Kräv MFA för alla användare](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [Kräv Azure AD MFA-registrering](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) – kräver Azure AD Identity Protection, som är en del av Azure Active Directory Premium P2

Mer information om villkorsstyrd åtkomst finns i [Vad är villkorsstyrd åtkomst?](/azure/active-directory/conditional-access/overview) Mer information om hur du skapar principer för villkorsstyrd åtkomst finns [i Skapa en princip för villkorsstyrd åtkomst.](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy)

> [!NOTE]
> Om du har ett abonnemang eller en licens som tillhandahåller villkorsstyrd åtkomst men ännu inte har skapat några principer för villkorsstyrd åtkomst får du använda säkerhetsstandarder. Du måste dock inaktivera säkerhetsstandarder innan du kan använda villkorsstyrda åtkomstprinciper.
