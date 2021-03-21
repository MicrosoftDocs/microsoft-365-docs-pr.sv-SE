---
title: Metodtips för konfiguration av EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Följ de här rekommendationerna för fristående Exchange Online Protection (EOP) så att du kan konfigurera dig själv och undvika vanliga konfigurationsfel.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6a6a9fd0dfc654ca37fdd5168b3ecc0c4486f9d0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924462"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>Rekommendationer för konfiguration av fristående EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
-  [Exchange Online Protection fristående](exchange-online-protection-overview.md)

Följ de här rekommendationerna för fristående Exchange Online Protection (EOP) så att du kan konfigurera dig själv och undvika vanliga konfigurationsfel. Den här artikeln förutsätter att du redan har slutfört installationen. Om du inte har slutfört EOP-konfigurationen kan du [gå till Konfigurera EOP-tjänsten.](set-up-your-eop-service.md)

## <a name="use-a-test-domain"></a>Använda en testdomän

Vi rekommenderar att du använder en testdomän, underdomän eller låg volymdomän för att prova på tjänstfunktioner innan du implementerar dem på flernivådomäner eller produktionsdomäner.

## <a name="synchronize-recipients"></a>Synkronisera mottagare

Om din organisation har befintliga användarkonton i en lokal Active Directory-miljö kan du synkronisera dessa konton till Azure Active Directory i molnet. Vi rekommenderar att du använder katalogsynkronisering. Mer information om fördelarna med att använda katalogsynkronisering och stegen för att konfigurera den finns i Hantera [e-postanvändare i EOP.](manage-mail-users-in-eop.md)

## <a name="recommended-settings"></a>Rekommenderade inställningar

Vi ger säkerhetsadministratörer möjlighet att anpassa säkerhetsinställningarna så att de uppfyller organisationens behov. Även om det som regel finns det två säkerhetsnivåer i EOP och Microsoft Defender för Office 365 som vi rekommenderar: Standard och Strikt. De här inställningarna visas i Rekommenderade [inställningar för EOP och Microsoft Defender för Office 365-säkerhet.](recommended-settings-for-eop-and-office365-atp.md)

### <a name="miscellaneousnon-policy-settings"></a>Diverse-/icke-principinställningar

De här inställningarna omfattar ett antal funktioner som ligger utanför säkerhetsprinciperna.

****

|Namn på säkerhetsfunktion|Standard|Strikt|Kommentar|
|---|---|---|---|
|[Konfigurera SPF för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Ja|Ja||
|[Använd DKIM för att validera utgående e-post som skickas från din egna domän i Office 365](use-dkim-to-validate-outbound-email.md)|Ja|Ja||
|[Använda DMARC för att validera e-post i Office 365](use-dmarc-to-validate-email.md)|Ja|Ja|Används `action=quarantine` för Standard och `action=reject` Strikt.|
|Distribuera tillägget [Rapportmeddelande eller tillägget](enable-the-report-message-add-in.md) [Rapportfiske](enable-the-report-phish-add-in.md) för att förbättra slutanvändarrapportering av misstänkt e-post|Ja|Ja||
|Schemalägga rapporter om skadlig programvara och skräppost|Ja|Ja||
|Automatisk vidarebefordran till externa domäner bör inte förhindras eller övervakas|Ja|Ja||
|Enhetlig granskning ska vara aktiverad|Ja|Ja||
|[IMAP-anslutning till postlåda](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Inaktiverad|Inaktiverad||
|[POP-anslutning till postlåda](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Inaktiverad|Inaktiverad||
|Autentiserad SÄNDNING VIA SMTP|Inaktiverad|Inaktiverad|Autentiserad SMTP-klientinskickning (kallas även SMTP-klientinskickning eller SMTP AUTH) krävs för att POP3- och IMAP4-klienter ska kunna skicka e-post.|
|EWS-anslutning till postlåda|Inaktiverad|Inaktiverad||
|[PowerShell-anslutning](/powershell/exchange/disable-access-to-exchange-online-powershell)|Inaktiverad|Inaktiverad|Tillgängligt för postlådeanvändare och e-postanvändare (användarobjekt som returneras [av cmdlet:en Get-User).](/powershell/module/exchange/get-user)|
|Använda [förfalskningsinformation för](learn-about-spoof-intelligence.md) att lägga till avsändare i listan över tillåtna avsändare|Ja|Ja||
|[Katalogbaserat gränsblockering (DBEB)](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|Aktiverad|Aktiverad|Domäntyp = Auktoritativ|
|[Konfigurera multifaktorautentisering för alla administratörskonton](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)|Aktiverad|Aktiverad||
|

## <a name="troubleshooting"></a>Felsökning

Felsöka allmänna problem och trender med hjälp av rapporterna i administrationscentret. Hitta data som gäller en enskild punkt om ett meddelande med hjälp av verktyget för meddelandespårning. Mer information om rapportering finns [i Rapportering och meddelandespårning i Exchange Online Protection.](reporting-and-message-trace-in-exchange-online-protection.md) Läs mer om verktyget för meddelandespårning i [Meddelandespårning i Säkerhets- & Säkerhets- och efterlevnadscenter.](message-trace-scc.md)

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>Rapportera falska positiva resultat och falska negativa resultat till Microsoft

För att förbättra filtreringen av skräppost i tjänsten för alla bör du rapportera falska positiva meddelanden (bra e-postmeddelanden som markerats som dåliga) och falska negativa (felaktigt e-postmeddelande tillåts) till Microsoft för analys. Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="create-mail-flow-rules"></a>Skapa e-postflödesregler

Skapa e-postflödesregler (kallas även transportregler) eller anpassade filter för att uppfylla dina affärsbehov.

När du distribuerar en ny regel till produktion väljer du ett av testlägena först för att se effekten av regeln. När du är nöjd med att regeln fungerar på det sätt som är avsett kan du ändra regelläget till **Framtvinga.**

När du distribuerar nya regler kan du lägga till den ytterligare åtgärden i **Generera incidentrapport** för att övervaka regeln i praktiken.

I hybridmiljöer där organisationen innehåller både lokal Exchange och Exchange Online bör du tänka på de villkor som du använder i e-postflödesregler. Om du vill att reglerna ska gälla för hela organisationen ska du se till att använda villkor som är tillgängliga i både lokal Exchange och i Exchange Online. De flesta villkor är tillgängliga i båda miljöerna, men det finns några som bara är tillgängliga i den ena miljön eller den andra. Mer information finns i [E-postflödesregler (transportregler) i Exchange Online.](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)