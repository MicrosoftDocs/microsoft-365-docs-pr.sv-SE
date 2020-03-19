---
title: Konfigurera principen för skräppost för utgående
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: Skräppostfiltrering är alltid aktiverat om du använder tjänsten för att skicka utgående e-post, vilket skyddar organisationer som använder tjänsten och deras avsedda mottagare.
ms.openlocfilehash: 0fa5ec23eee6144864f16b52d452d02f38b554d7
ms.sourcegitcommit: 4986032867b8664a215178b5e095cbda021f3450
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "42810742"
---
# <a name="configure-the-outbound-spam-policy"></a>Konfigurera principen för skräppost för utgående

Skräppostfiltrering är alltid aktiverat om du använder tjänsten för att skicka utgående e-post, vilket skyddar organisationer som använder tjänsten och deras avsedda mottagare. I likhet med inkommande filtrering består utgående skräppostfiltrering av anslutningsfiltrering och innehållsfiltrering och gör att vissa specifika kontroller kan hantera utgående meddelanden. Principtyper för utgående skräppostfilter:

- Standard: Standardprincipen för skräppostfilter används för att konfigurera skräppostfilterinställningar för hela företaget. Denna politik kan inte döpas om och är alltid på.

- Anpassad: Principer för anpassade skräppostfilter kan vara detaljerade och tillämpas på specifika användare, grupper eller domäner i organisationen. Anpassade principer har alltid företräde framför standardprincipen. Du kan ändra i vilken ordning dina anpassade principer körs genom att ändra prioriteten för varje anpassad princip. Endast principen högsta prioritet (dvs. nummer närmast 0) gäller dock om användaren matchar flera principer.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?
<a name="sectionSection0"> </a>

- Beräknad tid att slutföra: 5 minuter

- Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna. Information om vilka behörigheter du behöver finns i "Skräppostposten i [funktionsbehörigheterna i Exchange](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) Online-avsnittet.

- Du kan också göra procedurerna i det här avsnittet i fjärrutslag i PowerShell. Använd cmdleten [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy) för att granska dina inställningar och [ange värdenOut-boundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy) för att redigera dina utgående skräppostprincipinställningar.

  Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Information om hur du ansluter till Exchange Online Protection PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

## <a name="use-the-security--compliance-center-scc-to-edit-the-default-outbound-spam-policy"></a>Använd Security & Compliance Center (SCC) för att redigera standardpolicyn för utgående skräppost

Använd följande procedur för att redigera standardpolicyn för skräppost:

### <a name="to-configure-the-default-outbound-spam-policy"></a>Så här konfigurerar du standardprincipen för utgående skräppost

1. I SCC, navigera till **Threat Management** \> **Policy** \> **Anti-spam**

2. Expandera avsnittet **Utgående skräppostfilterprincip (alltid PÅ)** och klicka på **Redigera princip**.

3. Expandera avsnittet **Meddelanden** och markera följande kryssrutor för utgående meddelanden och välj sedan Lägg till **personer** om du vill lägga till en associerad e-postadress eller adresser i den medföljande dialogrutan. (Dessa kan vara distributionslistor om de löser som giltiga SMTP-destinationer):

   - **Skicka en kopia av alla misstänkta utgående e-postmeddelanden till följande e-postadress eller adresser:** Det här är meddelanden som markeras som skräppost av filtret (oavsett SCL-klassificering). De avvisas inte av filtret men dirigeras genom leveranspoolen med högre risk. Separera flera adresser med semikolon. Observera att de angivna mottagarna kommer att få meddelandena som en hemlig kopia (Hemlig kopia) (fälten Från och Till är den ursprungliga avsändaren och mottagaren).

   - **Skicka ett meddelande till följande e-postadress när en avsändare blockeras skicka utgående skräppost:** Separera flera adresser med ett semikolon.

   När en betydande mängd skräppost eller andra sändningsavvikelser upptäcks från en viss användare är användaren begränsad från att skicka e-postmeddelanden och ett meddelande skickas till de angivna e-postadresserna.

   Domänens administratör, som har angetts med den här inställningen, informeras om att utgående meddelanden blockeras för den här användaren.  Information om hur meddelandet ser ut finns [i Exempelmeddelande när en avsändare blockeras när den skickar utgående skräppost](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md).

   > [!NOTE]
   > En systemavisering genereras också som anger att användaren har begränsats. Mer information om aviseringen och hur du återställer användaren finns i [Ta bort en användare från portalen Begränsade användare när du har skickat skräppost.](removing-user-from-restricted-users-portal-after-spam.md)

4. Expandera avsnittet **Mottagaregränser** för att ange det maximala antalet mottagare som en användare kan skicka till, per timme för interna och externa mottagare tillsammans med det maximala antalet per dag.

   > [!NOTE]
   > Det maximala antalet för alla indata är 10000. Mer information finns i [mottagnings- och sändningsgränser i Exchange online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)

7. Ange vilken **åtgärd** som ska vidtas när en användare överskrider de angivna gränserna.  De åtgärder som är möjliga är följande:

   - **Begränsa användaren från att skicka e-post till följande dag**.  När någon sändningsgräns har överskridits (intern, extern eller daglig) genereras en avisering för administratören och användaren kommer inte att kunna skicka ytterligare e-post förrän följande dag, baserat på UTC-tid. Det finns inget sätt för administratören att åsidosätta det här blocket.

   - **Begränsa användaren från att skicka e-post**.  När någon sändningsgräns har överskridits (intern, extern eller daglig) genereras en avisering för administratören och användaren kommer inte att kunna skicka ytterligare e-post förrän administratören tar bort begränsningen.  I dessa fall visas användaren på [sidan Begränsade användare](removing-user-from-restricted-users-portal-after-spam.md).  När användaren har tagits bort från listan begränsas den inte igen för den dagen.

   - **Ingen åtgärd/avisering bara**. När någon sändningsgräns har överskridits (intern, extern eller daglig) genereras en avisering för administratören, men ingen åtgärd vidtas för att begränsa användaren.

6. Expandera avsnittet **Gäller för** och skapa sedan en villkorsbaserad regel för att ange de användare, grupper och domäner som den här principen ska tillämpas på. Du kan skapa flera villkor om de är unika.  Observera att användarna måste uppfylla alla villkor när flera villkor anges.  

   - Om du vill välja användare väljer du **Avsändaren är**. I den efterföljande dialogrutan väljer du en eller flera avsändare från företaget i användarväljarlistan och klickar sedan på Lägg till. Om du vill lägga till avsändare som inte finns i listan skriver du deras e-postadresser och klickar sedan på Kontrollera namn. När du är klar med dina val klickar du på ok för att återgå till huvudskärmen.

   - Om du vill välja grupper väljer du **Avsändaren är medlem i**. Markera eller ange sedan grupperna i den efterföljande dialogrutan. Klicka på ok för att återgå till huvudskärmen.

   - Om du vill välja domäner väljer du **Avsändningsdomänen är**. Lägg sedan till domänerna i den efterföljande dialogrutan. Klicka på ok för att återgå till huvudskärmen.

   Du kan skapa undantag i regeln. Du kan till exempel filtrera meddelanden från alla domäner utom för en viss domän. Klicka på Lägg till undantag och skapa sedan undantagsvillkor som liknar det sätt som du skapade de andra villkoren.

   Att tillämpa en utgående skräppostprincip på en grupp stöds endast för e-postaktiverade säkerhetsgrupper.

7. Klicka på **Spara**.

## <a name="to-create-a-custom-policy-for-a-specific-set-of-users"></a>Så här skapar du en anpassad princip för en viss uppsättning användare

1. I SCC, navigera till **Threat Management** \> **Policy** \> **Anti-spam**

2. Klicka på knappen **Skapa en utgående princip.**

3. Expandera avsnittet **Meddelanden** och markera följande kryssrutor för utgående meddelanden och välj sedan Lägg till **personer** om du vill lägga till en associerad e-postadress eller adresser i den medföljande dialogrutan.

4. Expandera avsnittet **Mottagaregränser** för att ange det maximala antalet mottagare som en användare kan skicka till, per timme för interna och externa mottagare och maximalt antal per dag.

7. Ange vilken **åtgärd** som ska vidtas när en användare överskrider de angivna gränserna.

6. Expandera avsnittet **Gäller för** och skapa en villkorsbaserad regel för att ange de användare, grupper och domäner som den här principen ska tillämpas på. Du kan skapa flera villkor om de är unika.  

8. Klicka på **spara**

## <a name="for-more-information"></a>Mer information

[Ta bort en användare från portalen Begränsade användare efter att ha skickat skräppost](https://docs.microsoft.com/office365/SecurityCompliance/removing-user-from-restricted-users-portal-after-spam)

[Högriskleveranspool för utgående meddelanden](high-risk-delivery-pool-for-outbound-messages.md)

[Vanliga frågor om skydd mot skräppost](anti-spam-protection-faq.md)
