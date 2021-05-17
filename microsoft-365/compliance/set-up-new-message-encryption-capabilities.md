---
title: Konfigurera nya funktioner för meddelandekryptering
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Läs mer om de nya meddelandekrypteringsfunktionerna i Office 365 som skyddar e-postkommunikationen med personer inom och utanför organisationen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cf37826c3e1e349947ab83fe211f9406a765e5ea
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "52162750"
---
# <a name="set-up-new-message-encryption-capabilities"></a>Konfigurera nya funktioner för meddelandekryptering

Med de nya funktionerna för meddelandekryptering i Office 365 (OME) kan organisationer dela skyddad e-post med vem som helst på valfri enhet. Användarna kan utbyta skyddade meddelanden med andra Microsoft 365-organisationer och icke-kunder med hjälp av Outlook.com, Gmail och andra e-posttjänster.

Följ stegen nedan för att se till att de nya OME-funktionerna är tillgängliga i din organisation.

## <a name="verify-that-azure-rights-management-is-active"></a>Kontrollera att Azure Rights Management är aktivt

De nya OME-funktionerna utnyttjar säkerhetsfunktionerna i [Azure Rights Management Services (Azure RMS)](/azure/information-protection/what-is-information-protection), vilket är den teknik som används av [Azure Information Protection](/azure/information-protection/what-is-azure-rms) för att skydda e-post och dokument via kryptering och åtkomstkontroller.

Det enda som krävs för att använda de nya OME-funktionerna är att [Azure Rights Management](/azure/information-protection/what-is-azure-rms) är aktiverat i klientorganisationen. Om den är det aktiverar Microsoft 365 de nya OME-funktionerna automatiskt och du behöver inte göra någonting.

Azure RMS aktiveras också automatiskt för de flesta abonnemangen, så du behöver förmodligen inte göra något i det här avseendet heller. Se [Aktivera Azure Rights Management](/azure/information-protection/activate-service) för mer information.

>[!IMPORTANT]
>Om du använder Active Directory Rights Management Service (AD RMS) med Exchange Online måste du [migrera till Azure Information Protection](/azure/information-protection/migrate-from-ad-rms-to-azure-rms) innan du kan använda de nya OME-funktionerna. OME är inte kompatibelt med AD RMS.  

Mer information finns i:

- [Vilka prenumerationer behöver jag för att kunna använda de nya OME-funktionerna?](ome-faq.yml#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities-) för att kontrollera om ditt abonnemang innehåller Azure Information Protection (som innehåller Azure RMS-funktionen).
- [Azure Information Protection](https://azure.microsoft.com/services/information-protection/) för information om hur du köper en prenumeration.  

### <a name="manually-activating-azure-rights-management"></a>Aktivera Azure Rights Management manuellt

Om du inaktiverade Azure RMS, eller om det av någon anledning inte aktiverades automatiskt, kan du aktivera det manuellt i:

- **Administrationscenter för Microsoft 365:**: [Aktivera Azure Rights Management från administrationscentret](/azure/information-protection/activate-office365) för anvisningar.
- **Azure-portal**: Se [Aktivera Azure Rights Management från Azure-portalen](/azure/information-protection/activate-azure) för anvisningar.

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a>Konfigurera hantering av klientnyckeln för Azure Information Protection

Det här är ett valfritt steg. Standardinställningen och rekommenderad metod för de flesta organisationer är att låta Microsoft hantera rotnyckeln för Azure Information Protection. I detta fall behöver du inte göra något.

Det finns många orsaker, till exempel krav på efterlevnad, som kan innebära att du måste generera och hantera din egen rotnyckel (kallas även BYOK). Om så är fallet rekommenderar vi att du slutför de steg som krävs innan du konfigurerar de nya OME-funktionerna. Se [Planera och implementera klientnyckeln för Azure Information Protection](/information-protection/plan-design/plan-implement-tenant-key) för mer information.

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a>Verifiera den nya OME-konfigurationen i Exchange Online PowerShell

Du kan kontrollera att Microsoft 365-klientorganisationen är korrekt konfigurerad för att använda de nya OME-funktionerna i [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell).
  
1. [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) med ett konto med behörighet som global administratör i Microsoft 365-klientorganisationen.

2. Kör cmdleten Get-IRMConfiguration.

     Du bör se värdet $True för parametern AzureRMSLicensingEnabled, vilket visar att OME har konfigurerats i klientorganisationen. Om inte, använder du Set-IRMConfiguration för att ange värdet för AzureRMSLicensingEnabled till $True och aktivera OME.

3. Kör cmdleten Test-IRMConfiguration med följande syntax:

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   **Exempel**:

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - Att tillhandahålla avsändarens e-postadress är valfritt, men det tvingar systemet att utföra ytterligare kontroller. Använd e-postadressen till en användare i din Microsoft 365-klientorganisation.

     Resultatet bör likna detta:

     ```text
     Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
     ```

   - Ditt organisationsnamn ersätter *Contoso*.

   - Namnen på standardmallarna kan skilja sig från de som visas ovan. Se [Konfigurera och hantera mallar för Azure Information Protection](/azure/information-protection/configure-policy-templates) för mer information.

4. Kör cmdleten Remove-PSSession för att koppla från Rights Management-tjänsten.

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a>Nästa steg: Definiera e-postflödesregler som använder nya OME-funktioner

Om det finns tidigare konfigurerade e-postflödesregler för att kryptera e-post i organisationen, måste du uppdatera de befintliga reglerna för att kunna använda de nya OME-funktionerna. För nya distributioner måste du skapa nya e-postflödesregler.

>[!IMPORTANT]
>Om du inte uppdaterar befintliga e-postflödesregler fortsätter användarna att ta emot krypterad e-post med det tidigare HTML-formatet för bilagor i stället för det nya smidiga OME-formatet.

E-postflödesreglerna avgör när e-postmeddelanden ska krypteras och villkoren för att ta bort krypteringen. När du anger en åtgärd för en regel krypteras alla meddelanden som matchar regelvillkoren när de skickas.
  
Anvisningar om hur du skapar e-postflödesregler för OME finns i [Definiera e-postflödesregler för att kryptera e-postmeddelanden i Office 365](define-mail-flow-rules-to-encrypt-email.md).

Uppdatera befintliga regler till att använda de nya OME-funktionerna:

1. I administrationscentret för Microsoft 365 går du till **Administrationscenter > Exchange**.
2. Gå till **E-postflöde > Regler** i administrationscentret för Exchange.
3. För varje regel i **Gör följande**:
    - Välj **Ändra meddelandesäkerheten**.
    - Välj **Använd Meddelandekryptering i Office 365 och rättighetsskydd**.
    - Välj en RMS-mall i listan.
    - Välj **Spara**.
    - Välj **OK**.