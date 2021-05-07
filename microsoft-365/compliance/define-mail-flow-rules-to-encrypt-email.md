---
title: Definiera e-postflödesregler för att kryptera e-postmeddelanden
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig att skapa e-postflödesregler (transportregler) för att kryptera och dekryptera meddelanden Meddelandekryptering i Office 365.
ms.openlocfilehash: 63b1b0ba3b13f5beecd049a8ef81d6355855626f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "52162395"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages"></a>Definiera e-postflödesregler för att kryptera e-postmeddelanden

Som administratör för e Exchange Online kan du skapa e-postflödesregler (kallas även transportregler) för att skydda e-postmeddelanden som du skickar och tar emot. Du kan konfigurera regler för att kryptera alla utgående e-postmeddelanden och ta bort kryptering från krypterade meddelanden från organisationen eller från svar på krypterade meddelanden som skickas från organisationen. Du kan använda Exchange (EAC) eller PowerShell Exchange Online skapa dessa regler. Förutom de övergripande krypteringsreglerna kan du också välja att aktivera eller inaktivera enskilda alternativ för meddelandekryptering för slutanvändare.

Du kan inte kryptera inkommande e-post från avsändare utanför organisationen.

Om du nyligen har migrerat från Active Directory RMS till Azure Information Protection måste du granska befintliga e-postflödesregler för att säkerställa att de fortsätter att fungera i den nya miljön. Om du vill dra nytta av de nya OME-funktionerna (Meddelandekryptering i Office 365) som är tillgängliga via Azure Information Protection måste du även uppdatera dina befintliga e-postflödesregler. Annars fortsätter användarna att ta emot krypterad e-post som använder det tidigare HTML-formatet för bifogade filer i stället för det nya, sömlösa OME-formatet. Om du inte har konfigurerat OME ännu, se [Konfigurera Meddelandekryptering i Office 365 funktioner](set-up-new-message-encryption-capabilities.md) för information.

Mer information om de komponenter som utgör e-postflödesregler och hur e-postflödesregler fungerar finns i E-postflödesregler [(transportregler) i Exchange Online.](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) Mer information om hur e-postflödesregler fungerar med Azure Information Protection finns i [Konfigurera Exchange Online-postflödesregler för Azure Information Protection-etiketter.](/azure/information-protection/deploy-use/configure-exo-rules)

> [!IMPORTANT]
> För hybridmiljöer Exchange lokala användare endast skicka och ta emot krypterad e-post med OME om e-posten dirigeras via Exchange Online. Om du vill konfigurera OME i en hybrid-Exchange-miljö måste du först konfigurera [hybrid](/Exchange/exchange-hybrid) med hjälp av hybridkonfigurationsguiden och sedan konfigurera e-post så att den flödar från [Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-1-configure-mail-to-flow-from-office-365-to-your-on-premises-email-server) till e-postservern och konfigurera e-post så att den flödar från e-postservern [till Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365). När du har konfigurerat e-posten så att den Office 365 e-post kan du konfigurera e-postflödesregler för OME med hjälp av den här vägledningen.

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>Skapa e-postflödesregler för att kryptera e-postmeddelanden med de nya OME-funktionerna

Du kan definiera e-postflödesregler som utlöser meddelandekryptering med de nya OME-funktionerna med hjälp av EAC.

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>Använd EAC för att skapa en regel för att kryptera e-postmeddelanden med de nya OME-funktionerna

1. Använd ett arbets- eller skolkonto som har beviljats global administratörsbehörighet i en webbläsare och logga [in på Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Välj **panelen** Admin.

3. Välj Microsoft 365 administrationscenter i **administrationscentret** \> **för Exchange**.

4. I EAC går du till **E-postflödesregler** \>  och väljer **Ny** ny ikon Skapa en ![ ny ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **regel.** Mer information om hur du använder EAC finns Exchange [administrationscenter i Exchange Online](/exchange/exchange-admin-center).

5. Ange **ett** namn för regeln i Namn, till exempel Kryptera e-post för DrToniRamos@hotmail.com.

6. Välj **ett villkor i Använd** den här regeln om och ange ett värde om det behövs. Om du till exempel vill kryptera meddelanden som kommer till DrToniRamos@hotmail.com:

   1. Välj **mottagaren är i Använd** den här regeln **om**.

   2. Välj ett befintligt namn i kontaktlistan eller skriv en ny e-postadress i **kryssrutan** namn.

      - Om du vill välja ett befintligt namn markerar du det i listan och klickar sedan på **OK.**

      - Om du vill ange ett nytt namn skriver du en e-postadress **i kryssrutan namn** och markerar sedan kryssrutan namn **som** \> **OK.**

7. Om du vill lägga till fler villkor **väljer du Fler** alternativ och sedan Lägg **till** villkor och väljer i listan.

   Om du till exempel bara vill använda regeln om  mottagaren finns utanför organisationen väljer du Lägg till villkor och sedan Mottagaren är **extern/intern** \> **Utanför organisationen** \> **OK.**

8. Aktivera kryptering med de nya OME-funktionerna genom  att göra följande och välja Ändra meddelandesäkerhet och sedan **Tillämpa Meddelandekryptering i Office 365 och rättighetsskydd.**  Välj en RMS-mall i listan, **välj Spara** och välj sedan **OK.**
  
  Listan med mallar innehåller alla standardmallar och alternativ samt eventuella anpassade mallar som du har skapat för användning Office 365. Om listan är tom, kontrollera att du har Meddelandekryptering i Office 365 med de nya funktionerna enligt beskrivningen i Konfigurera [nya Meddelandekryptering i Office 365 funktioner.](set-up-new-message-encryption-capabilities.md) Mer information om standardmallar finns i Konfigurera [och hantera mallar för Azure Information Protection.](/information-protection/deploy-use/configure-policy-templates) Mer information om alternativet **Vidarebefordra inte finns i** alternativet Vidarebefordra inte för [e-postmeddelanden.](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails) Mer information om alternativet **som endast är krypterat** finns i [Alternativet Endast kryptera för e-postmeddelanden.](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

  Du kan välja **att lägga till** en åtgärd om du vill ange en annan åtgärd.

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>Använda EAC för att uppdatera en befintlig e-postflödesregel för att använda de nya OME-funktionerna

1. Använd ett arbets- eller skolkonto som har beviljats global administratörsbehörighet i en webbläsare och logga [in på Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Välj **panelen** Admin.

3. Välj Microsoft 365 administrationscenter i **administrationscentret** \> **för Exchange**.

4. Gå till E-postflödesregler **i** \> EAC.

5. I listan över e-postflödesregler väljer du den regel som du vill ändra och använder de nya OME-funktionerna. Välj sedan **Redigera** ![ redigera-ikonen ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .

6. För att aktivera kryptering med de nya OME-funktionerna gör du följande och väljer Ändra meddelandesäkerhet och sedan **Apply Meddelandekryptering i Office 365 and rights protection**.  Välj en RMS-mall i listan, välj **Spara** och välj sedan **OK.**

   Listan med mallar innehåller alla standardmallar och alternativ samt eventuella anpassade mallar som du har skapat för användning Office 365. Om listan är tom bör du kontrollera att du har Meddelandekryptering i Office 365 med de nya funktioner som beskrivs i Konfigurera nya Meddelandekryptering i Office 365-funktioner som bygger på [Azure Information Protection.](set-up-new-message-encryption-capabilities.md) Mer information om standardmallar finns i Konfigurera [och hantera mallar för Azure Information Protection.](/information-protection/deploy-use/configure-policy-templates) Mer information om alternativet Vidarebefordra inte finns i alternativet [Vidarebefordra inte för e-postmeddelanden.](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails) Mer information om alternativet som endast är krypterat finns i [Alternativet Kryptera endast för e-postmeddelanden.](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

   Du kan välja **att lägga till** en åtgärd om du vill ange en annan åtgärd.

7. I listan **Gör följande tar** du bort alla åtgärder som är tilldelade till Ändra **meddelandets säkerhet** Använd den tidigare versionen av \> **OME.**

8. Välj **Spara**.

## <a name="create-mail-flow-rules-to-remove-encryption-for-email-messages-with-the-new-ome-capabilities"></a>Skapa e-postflödesregler för att ta bort kryptering för e-postmeddelanden med de nya OME-funktionerna

Du kan definiera e-postflödesregler för att utlösa borttagning av meddelandekryptering med de nya OME-funktionerna med hjälp av EAC.

### <a name="use-the-eac-to-create-a-rule-to-remove-encryption-from-email-messages-with-the-new-ome-capabilities"></a>Använd EAC för att skapa en regel för att ta bort kryptering från e-postmeddelanden med de nya OME-funktionerna

Du kan ta bort kryptering som är tillgänglig för din organisation. Det innebär all e-post med kryptering som tillämpas av organisationen eller all e-post som skyddas med krypteringsbegränsningar.

1. Använd ett arbets- eller skolkonto som har beviljats global administratörsbehörighet i en webbläsare och logga [in på Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Välj **panelen** Admin.

3. Välj Microsoft 365 administrationscenter i **administrationscentret** \> **för Exchange**.

4. I EAC går du till **E-postflödesregler** \>  och väljer **Ny** ny ikon Skapa en ![ ny ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **regel.** Mer information om hur du använder EAC finns Exchange [administrationscenter i Exchange Online](/exchange/exchange-admin-center).

5. Ange **ett** namn för regeln i Namn, till exempel Ta bort kryptering från utgående e-post.

6. I **Använd den här regeln** om väljer du de villkor där kryptering ska tas bort från meddelanden. Lägg **till Avsändaren finns** inom \> **organisationen** _eller_ Mottagaren **finns** \> **i organisationen**.

7. I **Gör följande väljer du** Ändra **meddelandets säkerhet Ta** bort Meddelandekryptering i Office 365 och \> **rättighetsskydd**.

8. Välj **Spara**.

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>Skapa e-postflödesregler Meddelandekryptering i Office 365 funktioner utan de nya funktionerna

Om du ännu inte har flyttat organisationen till de nya OME-funktionerna rekommenderar Microsoft att du gör en plan för att flytta till de nya OME-funktionerna så snart det är lämpligt för din organisation. Instruktioner finns i [Konfigurera nya Meddelandekryptering i Office 365 funktioner som bygger på Azure Information Protection.](set-up-new-message-encryption-capabilities.md) Annars kan du [Meddelandekryptering i Office 365 definiera e-postflödesregler som inte använder de nya OME-funktionerna.](legacy-information-for-message-encryption.md#defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities)

## <a name="related-topics"></a>Relaterade ämnen

[Kryptering i Office 365](encryption.md)

[Konfigurera nya funktioner för meddelandekryptering i Office 365](set-up-new-message-encryption-capabilities.md)

[Lägga till profilering i krypterade meddelanden](add-your-organization-brand-to-encrypted-messages.md)

[E-postflödesregler (transportregler) i Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

[E-postflödesregler (transportregler) i Exchange Online Protection](../security/defender-365-security/mail-flow-rules-transport-rules-0.md)
