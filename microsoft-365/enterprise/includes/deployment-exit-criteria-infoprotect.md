<a name="crit-infoprotect-step1"></a>
### <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>Obligatoriskt: definierad säkerhets- och informationsskyddsnivå för din organisation

Du har planerat för och avgjort vilka säkerhetsnivåer din organisation behöver. Dessa nivåer definierar en minsta säkerhetsnivå och ytterligare nivåer för känsligare information och den datasäkerhet den kräver.

Som minst använder du tre säkerhetsnivåer:

- Baslinje
- Känslig
- Mycket reglerad

Vid behov kan [Steg 1](../infoprotect-define-sec-infoprotect-levels.md) hjälpa dig med detta krav. 

<a name="crit-infoprotect-step3"></a>
### <a name="required-increased-security-for-microsoft-365-is-configured"></a>Obligatoriskt: Ökad säkerhet för Microsoft 365 har konfigurerats

Du har konfigurerat följande inställningar för [ökad säkerhet för Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):

- Policyer för hantering av hot i Microsoft 365s säkerhetscenter
- Ytterligare inställningar för hela Exchange Online-klientorganisationen
- Delningsprinciper för hela klientorganisationen i administrationscentret för SharePoint Online
- Inställningar i Azure Active Directory (Azure AD)

Du har även [aktiverat Office 365 Avancerat skydd för SharePoint, OneDrive och Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).

Vid behov kan [Steg 3](../infoprotect-configure-increased-security-office-365.md) hjälpa dig med detta krav. 

<a name="crit-infoprotect-step2"></a>
### <a name="optional-classification-is-configured-across-your-environment"></a>Valfritt: Klassificering har konfigurerats i hela din miljö

Du har arbetat med dina juridiska och regelefterlevnadsteam för att utveckla ett lämpligt klassificerings- och märkningsschema för organisationens datastyrning och säkerhetspolicyer. 

Dessa policyer följer konfigurationen och spridningen av:

- Känsliga datatyper
- Bevarande märkning
- Markera som känsligt
- Märkning för Azure Information Protection

Vid behov kan [Steg 2](../infoprotect-configure-classification.md) hjälpa dig med detta krav. 


<a name="crit-infoprotect-step4"></a>
### <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a>Valfritt: Windows-informationsskydd distribueras i hela din miljö

Dina registrerade Windows 10 Enterprise-enheter har en Intune-policy som distribuerats och används som definierar:

- De appar som ska skyddas.
- Skyddsnivån.
- Hur långt skyddet sträcker sig.

Vid behov kan [Steg 4](../infoprotect-deploy-windows-information-protection.md) hjälpa dig med detta krav. 

<a name="crit-infoprotect-step5"></a>
### <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a>Valfritt: Dataförlustskydd i Office 365 har distribuerats

Du har analyserat, testat och introducerat en uppsättning DLP-principer, med platser och regler med villkor och åtgärder, som din organisation behöver för att skydda kund- och andra typer av privata data samt följa branschens och regionala bestämmelser och krav.

Dina anställda som arbetar med säkerhet och efterlevnad använder säkerhets- och efterlevnadspanelen i Office 365 för att övervaka DLP-händelser.

Vid behov kan [Steg 5](../infoprotect-data-loss-prevention.md) hjälpa dig med detta krav. 

<a name="crit-infoprotect-step6"></a>
### <a name="optional-email-encryption-is-configured"></a>Valfritt: E-postkryptering har konfigurerats

Du har konfigurerat följande e-postkryptering efter behov för din organisation:

|||
|:-------|:-----|
| **Krypteringsmetod** | **För e-post som skickats** |
| [Meddelandekryptering i Office 365 (OME)](https://docs.microsoft.com/Office365/SecurityCompliance/ome)  | Utanför organisationen med kryptering |
| [IRM (Information Rights Management)](https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online) | Med både kryptering och behörigheter |
| [Secure/Multipurpose Internet Mail Extensions (S/MIME)](https://docs.microsoft.com/Exchange/policy-and-compliance/smime) | Med både kryptering och digitala signaturer som använder publika krypteringsnycklar |
|||

Vid behov kan [Steg 6](../infoprotect-email-encryption.md) hjälpa dig med detta krav.

<a name="crit-infoprotect-step7"></a>
### <a name="optional-configure-privileged-access-management-in-office-365"></a>Valfritt: Konfigurera behörighetshantering i Office 365

Du har använt informationen i [Konfigurera behörighetshantering i Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) för att aktivera behörighet och skapa en eller flera policyer för behörig åtkomst inom organisationen. Du har konfigurerat dessa principer och just-in-time-åtkomst är aktiverad för åtkomst till känsliga data eller åtkomst till kritiska konfigurationsinställningar.

Vid behov kan [Steg 7](../infoprotect-configure-privileged-access-management.md) hjälpa dig med detta krav. 
