---
title: Konfigurera en grupp med säkerhetsisolering i en utvecklings-/testmiljö
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 08/14/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom: ''
description: Konfigurera säkerheten och infrastrukturen som gör att dina anställda kan arbeta på distans på valfri plats och när som helst.
ms.openlocfilehash: 62361126ad0b843fd909b98807eeb186f13e75bb
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778351"
---
# <a name="configure-a-team-with-security-isolation-in-a-devtest-environment"></a>Konfigurera en grupp med säkerhetsisolering i en utvecklings-/testmiljö

I den här artikeln får du stegvisa instruktioner för hur du skapar en [grupp med säkerhetsisolering](secure-teams-security-isolation.md) i en utvecklings-/testmiljö.

![Konfiguration av den isolerade gruppen Företagsstrategi.](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config.png)

Använd utvecklings-/testmiljön för att experimentera och finjustera inställningarna efter dina behov innan du distribuerar grupptyperna i produktion.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fas 1: Bygga ut testmiljön i Microsoft 365 Enterprise

Om du bara vill testa känsliga och strikt konfidentiella grupper på ett enkelt sätt med lägsta möjliga krav, följer du anvisningarna i [Enkel baskonfiguration](../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).

Om du vill testa känsliga och strikt konfidentiella grupper i ett simulerat företag, följer du anvisningarna i [Synkronisering av lösenordshash](../enterprise/password-hash-sync-m365-ent-test-environment.md).

>[!Note]
>Att testa känsliga och strikt konfidentiella grupper kräver inte någon simulerad företagstestmiljö som innehåller ett simulerat intranät som är kopplat till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services). Det här är ett alternativ där du kan testa känsliga och strikt konfidentiella grupper, samt experimentera i en miljö som motsvarar en vanlig organisation.
>
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-azure-ad-group-and-users"></a>Fas 2: Skapa och konfigurera grupper och användare i Azure Active Directory (Azure AD)

I den här fasen skapar och konfigurerar du Azure Active Directory-grupper och användare för din fiktiva organisation.
  
Börja med att skapa en säkerhetsgrupp med Microsoft Azure-portalen.
  
1. Gå till Azure-portalen på [https://portal.azure.com](https://portal.azure.com) från en separat flik i webbläsaren. Om det behövs loggar du in med autentiseringsuppgifterna för det globala administratörskontot för din utvärderingsprenumeration eller betalda prenumeration för Microsoft 365 E5.
    
2. I Azure-portalen klickar du på **Azure Active Directory > Grupper**.
    
3. Gå till bladet **Grupper – Alla grupper** och klicka på **+ Ny grupp**.
    
4. På bladet **Grupp**:
    
  - Välj **Säkerhet** i **Grupptyp**.
    
  - Skriv **C-Suite** i **Namn**.
    
  - Välj **Tilldelad** i **Typ av medlemskap**.
      
5. Klicka på **Skapa** och stäng sedan bladet **Grupp**.
    
Konfigurera automatiskt licensiering så att medlemmar i den nya gruppen **C-Suite** automatiskt tilldelas en licens för Microsoft 365 E5.
  
1. Klicka på **Azure Active Directory > Licenser > Alla produkter** i Azure-portalen.
    
2. Välj **Microsoft 365 Enterprise E5** i listan och klicka sedan på **Tilldela**.
    
3. På bladet **Tilldela licens** klickar du på **Användare och grupper**.
    
4. I listan med grupper väljer du gruppen **C-Suite**.
    
5. Klicka på **Välj** och sedan på **Tilldela**.
    
6. Stäng fliken för Azure-portalen i webbläsaren.
    
Därefter [ansluter du med Azure Active Directory Windows PowerShell för Graph-modulen](../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Fyll i organisationsnamn, plats och lösenord samt kör dessa kommandon från Windows PowerShell-kommandotolken eller en ISE (Integrated Script Environment) för att skapa användarkonton och lägga till dem i gruppen C-Suite:
  
```powershell
$orgName="<organization name, such as contoso-test for the contoso-test.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$groupName="C-Suite"
$userNames=@("CEO","CFO","CIO") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> Ett gemensamt lösenord används för automatisering och enklare konfiguration i utvecklings-/testmiljön. Självklart rekommenderas detta inte för produktionsprenumerationer. 
  
Använd stegen för att kontrollera att gruppbaserad licensiering fungerar som den ska.
  
1. Logga in på [Administrationscenter för Microsoft 365](https://admin.microsoft.com).
    
2. Klicka på **Användare**under den nya fliken **Administrationscenter för Microsoft 365** i webbläsaren.
    
3. I listan med användare klickar du på **CEO**.
    
4. I fönstret med egenskaperna för användarkontot **CEO** kontrollerar du att det har tilldelats licensen **Microsoft 365 Enterprise E5** i **Produktlicenser**.
    
## <a name="phase-3-create-your-team"></a>Fas 3: Skapa din grupp

I den här fasen skapar och konfigurerar du en grupp med säkerhetsisolering för medlemmar i chefsledarskap för att samarbeta med företagsstrategi.

Kontrollera att du har aktiverat känslighetsetiketter för att skydda innehåll i Microsoft Teams, Office 365-grupper och SharePoint-webbplatser innan du fortsätter med stegen i [den här artikeln](../compliance/sensitivity-labels-teams-groups-sites.md).

Skapa sedan gruppen:

1. I Teams klickar du på **Teams** till vänster i programmet och sedan på **gå med i eller skapa ett team** längst ned i grupplistan.
2. Klicka på **Skapa team** (första kortet, övre vänstra hörnet).
3. Välj **Skapa ett team från början**.
4. Behåll standardinställningen i listan **Känslighet**.
5. Under **Sekretess**klickar du på **Privat**.
6. Skriv **Företagsstrategi**och klicka sedan på **Skapa** > **Stäng**.

Härnäst ska du begränsa skapandet av privata kanaler till ägare av gruppen företags strategi.

1. Klicka på **Fler alternativ**i teamet och klicka sedan på **Hantera team**.
2. På fliken **Inställningar**, expandera **medlemsbehörigheter**.
3. Avmarkera kryssrutan **Tillåt att medlemmar skapar privata kanaler**.

Sedan behöver du konfigurera en känslighetsetikett med följande inställningar:

- Namnet är företags strategin
- Kryptering är aktiverat
- Gruppen Företagsstrategi har samredigeringsbehörighet

Gör så här:

1. Öppna [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com).
2. Under **Lösningar**klickar du på **Informationsskydd**.
3. Klicka på **Skapa en etikett**.
4. Skriv **Företagsstrategi** som etikettnamn.
5. Skriv **Dokument för chefsledarskapets företagsstrategi** som tips för verktyget och klicka sedan **Nästa**.
6. I listrutan **Kryptering** på sidan **Kryptering** väljer du **Använd**. 
7. Så här lägger du till teambehörigheter:<br>
  a. Klicka på **Tilldela behörigheter**.<br>
  b. Klicka på **Lägg till användare eller grupper**, välj **Företagsstrategi**och klicka sedan på **Lägg till**.<br>
  c. Klicka **Välj behörigheter**.<br>
  d. Välj **Samtidig redigering** från listrutan och klicka sedan på **Spara**.<br>
8. Klicka på **Nästa**.
9. På sidan **Märkning av innehåll** klickar du på **Nästa**.
10. På sidan **Inställningar för webbplatser och grupper** ställer du **inställningar för webbplatser och grupper** till **På**.
11. I listrutan **Sekretess för gruppanslutna teamwebbplatser i Office 365** väljer du **Privat – endast användare kan komma åt webbplatsen**.
12. Under **Ohanterade enheter**väljer du **Blockera åtkomst**.
13. Klicka på **Nästa**.
14. På sidan **Auto-etiketting för Office-program** klickar du på **Nästa**.
15. Klicka på **Skicka** och klicka sedan **Klart**.

Publicera sedan den nya etiketten med följande steg: 

1. I Microsoft 365 Efterlevnadscenter väljer du fliken **Etikettprinciper** på sidan **Informationsskydd**.
2. Klicka på **Publicera etiketter**.
3. På sidan **Välj känslighetsetiketter att publicera** klickar du på **Välj känslighetsetiketter att publicera**.
4. Välj **Företagsstrategi** och klicka sedan på **Lägg till**.
5. Klicka på **Nästa**.
6. På sidan **Publicera till användare och grupper** klickar du på **välja användare och grupper**.
7. Klicka på **Lägg till** och välj sedan **Företagsstrategi**.
8. Klicka på **Lägg till** och sedan på **Klart**.
9. Klicka på **Nästa**.
10. På sidan Principinställningar väljer du kryssrutan **Användare måste ge anledning till att ta bort en etikett eller lägre klassificeringsetikett** och klickar sedan på **Nästa**.
11. Skriv **Företagsstrategi** som principens namn och klicka sedan på **Nästa**.
12. Klicka på **Skicka** och klicka sedan på **Klart**.

Obs! Det kan ta lite tid innan etiketten **Företagsstrategi** blir tillgänglig när den har publicerats.

Använd sedan den nya etiketten i gruppen **Företagsstrategi** och uppdatera den standardtypen av delningslänk för att minska risken för att filer och mappar delas av misstag. 

1. Öppna [SharePoint Online Administrationscenter](https://admin.microsoft.com/sharepoint).
2. Under **Webbplatser**klickar du på **Aktiva webbplatser**.
3. Klicka på webbplatsen **Företagsstrategi**.
4. På fliken **Principer** klickar du på **Redigera** under **Känslighet**.
5. Välj etiketten **Företagsstrategi** och klicka sedan på **Spara**.
6. Klicka på **Redigera** under **Extern delning** på fliken **Principer**.
5. Välj **Endast personer i organisationen**.
6. Avmarkera kryssrutan **Samma som organisationsnivå** under länktypen **Standarddelning** och välj **Personer med befintlig åtkomst**.
7. Klicka på **Spara**.

Konfigurera sedan endast webbplatsdelning för ägare för gruppen **Företagsstrategi**.

1. I team går du till fliken **Allmänt** i gruppen **Företagsstrategi**.
2. I verktygsfältet för teamet klickar du på **Filer**.
3. Klicka på ellipsen och sedan på **Öppna i SharePoint**.
4. Klicka på inställningsikonen i verktygsfältet på den underliggande SharePoint-webbplatsen och klicka sedan på **Webbplatsbehörigheter**.
5. I fönstret webbplatsbehörigheter under **Webbplatsdelning**klickar du på **Ändra hur medlemmar kan dela**.
6. Under **Delningsbehörigheter** väljer du **Endast webbplatsens ägare kan dela filer, mappar och webbplatsen**. Klicka sedan på **Spara**.
7. Stäng fönstren **Behörigheter** och **Inställningar**.

Om du loggar in som medlem i gruppen Företagsstrategi, kommer du att se **Företagsstrategi** i alternativet **Känslighet** i verktygsfältet Start i Word, Excel och PowerPoint. Välj etiketten **Företagsstrategi** från alternativet **Känslighet** om du vill tilldela etiketten till en fil.

Här är den resulterande konfigurationen för gruppen Företagsstrategi.

![Konfiguration av den isolerade gruppen Företagsstrategi.](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config.png)

## <a name="next-step"></a>Nästa steg

När du är redo för distribution kan du läsa de här [konfigurations anvisningar](secure-teams-security-isolation.md).
