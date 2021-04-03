---
title: Redigera eller ange inställningar för programskydd för Windows 10-enheter
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Lär dig hur du skapar eller redigerar principer för programhantering och skyddar arbetsfiler på användarnas personliga Windows 10-enheter.
ms.openlocfilehash: aa270c563e6bdce6fd48f8713d7db3ce23921925
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580023"
---
# <a name="set-or-edit-application-protection-settings-for-windows-10-devices"></a>Ange eller redigera programskyddsinställningar för Windows 10-enheter

Den här artikeln gäller Microsoft 365 Business Premium.

## <a name="edit-an-app-management-policy-for-windows-10"></a>Redigera en princip för programhantering för Windows 10

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.     
2. Välj Principer för enheter i **navigeringsfältet** \> **till vänster.**
1. Välj en befintlig Windows-appprincip och sedan **Redigera**.
1. Välj **Redigera** bredvid den inställning du vill ändra och sedan **Spara**.

## <a name="create-an-app-management-policy-for-windows-10"></a>Skapa en princip för programhantering för Windows 10

Om dina användare har privata Windows 10-enheter som de utför arbetsuppgifter med kan du skydda data även på de enheterna.
  
1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
2. Välj Enheter principer Lägg till **i** \> **navigeringsfältet** \> **till vänster.**
3. I fönstret **Lägg till princip** anger du ett unikt namn för principen. 
4. Välj **Programhantering för Windows 10** under **Principtyp**.
5. Under **Enhetstyp** väljer du antingen **Personlig eller** **Företagsägd**.
6. **Kryptera arbetsfiler** aktiveras automatiskt. 
7. Ange **Hindra användare från att kopiera företagsdata till personliga filer och tvinga dem att spara arbetsfiler i OneDrive för företag** till **På** om du inte vill att användare ska kunna spara filer på sina datorer. 
9. Expandera **Återskapa data på Windows-enheter**. Vi rekommenderar att du aktiverar det **med På**.
    Innan du kan bläddra till certifikatet för dataåterställningsagenten måste du skapa ett. Instruktioner finns i Skapa och verifiera ett certifikat för en dataåterställningsagent för kryptering av [filsystem (EFS).](/windows/security/information-protection/windows-information-protection/create-and-verify-an-efs-dra-certificate)
    
    Som standard krypteras arbetsfiler med en hemlig nyckel som lagras på enheten och som är kopplad till användarens profil. Endast användaren kan öppna och dekryptera filen. Men om en enhet försvinner eller en användare tas bort kan en fil fastna i ett krypterat tillstånd. En administratör kan använda certifikatet för dataåterställningsagenten för att dekryptera filen.
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. Expandera **Skydda ytterligare nätverks- och molnplatser** om du vill lägga till ytterligare domäner eller SharePoint Online-platser för att säkerställa att filer i alla angivna program skyddas. Om du behöver ange mer än ett objekt i ett fält anger du ett semikolon (;) mellan objekten.
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. Bestäm sedan **vem som ska få de här inställningarna** Om du inte vill använda standardsäkerhetsgruppen **Alla användare** väljer du **Ändra** och anger de säkerhetsgrupper som ska få dessa inställningar \> **Välj**.
12. Välj **Lägg till** för att spara principen och tilldela den till enheter.