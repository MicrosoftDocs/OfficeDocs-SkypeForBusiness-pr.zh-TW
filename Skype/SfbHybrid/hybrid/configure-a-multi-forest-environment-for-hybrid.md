---
title: 部署資源樹系拓撲
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 下列各節 descrbie 如何設定資源/使用者樹系模型中有多個樹系的環境，以提供混合式案例中的功能。
ms.openlocfilehash: 146537c6b2ff51d6e2a68c0f4fbb59dfee55b1b6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625775"
---
# <a name="deploy-a-resource-forest-topology"></a>部署資源樹系拓撲

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 
下列各節說明如何設定資源/使用者樹系模型中有多個樹系的環境，以提供混合式案例中的功能。 
  
![混合式的多樹系環境](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>拓撲需求

支援多個使用者樹系。 請記住下列事項： 
    
- 如需在混合式設定中支援的 Lync Server 和商務用 Skype Server 版本，請參閱[規劃混合](plan-hybrid-connectivity.md)式連線。
    
- Exchange Server 可以部署在一個或多個樹系中，也可能包含商務用 Skype Server 的樹系。 請確認您已套用最新的累計更新。
    
- 如需與 Exchange Server 共存的詳細資訊，包括在內部部署和線上的各種組合中支援準則及限制，請參閱[Plan to 整合商務用 Skype 和 Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)中的[功能支援](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)。
    
  
## <a name="user-homing-considerations"></a>使用者主頁考慮

位於內部部署商務用 Skype 使用者可以在內部部署或線上上進行 Exchange。 Teams 使用者應使用 Exchange Online 以取得最佳體驗;不過，這不是必要的。 在這兩種情況下，不需要在內部部署 Exchange 執行商務用 Skype。
  
## <a name="configure-forest-trusts"></a>設定樹系信任

在資源樹系拓撲中，主控商務用 Skype Server 的資源樹系必須信任每個包含使用者帳戶的帳戶樹系，該樹系都可以存取該拓撲。 

如果您有多個使用者樹系，若要啟用跨樹系驗證，則必須為每個樹系信任啟用名稱尾碼路由。 如需相關指示，請參閱 [管理樹系信任](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772440(v=ws.11))。 

如果您已在另一個樹系中部署 Exchange Server，且 Exchange 供應商務用 Skype 使用者的功能，則主控 Exchange 的樹系必須信任主控商務用 Skype Server 的樹系。 例如，如果 Exchange 已部署在帳戶樹系中，則需要使用帳戶與商務用 Skype 樹系之間的雙向信任。
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>將帳戶同步處理到主控商務用 Skype 的樹系中

假設商務用 Skype Server 部署在一個樹系中 (資源樹系) ，但為一或多個其他樹系中的使用者提供功能 (帳戶樹系) 。 在此情況下，其他樹系中的使用者必須表示為已部署商務用 Skype Server 樹系中已停用的使用者物件。

您必須使用身分識別管理產品（例如 Microsoft Identity Manager），以將帳戶樹系中的使用者布建及同步處理至部署商務用 Skype Server 的樹系中。 使用者必須同步處理到主控商務用 Skype Server 為停用的使用者物件的樹系中。 無法將使用者同步處理成 Active Directory contact 物件，因為 Azure Active Directory 連線不會將連絡人正確同步處理到 Azure AD，以搭配 Skype 使用。
  
不論任何多樹系設定，主控商務用 Skype Server 的樹系也可以為存在於相同樹系中的任何已啟用使用者提供功能。
  
若要取得適當的身分識別同步處理，必須同步處理下列屬性： 
  
|**使用者樹系**|**資原始目錄樹**|
|:-----|:-----|
|選擇的帳戶連結屬性  <br/> |選擇的帳戶連結屬性  <br/> |
|mail  <br/> |mail  <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
[選取的帳戶連結屬性](/azure/active-directory/hybrid/plan-connect-design-concepts)將會做為來源錨點使用。 如果您想要使用不同且不可變的屬性，您可以這樣做;只須確定編輯 AD FS 宣告規則，並在 AAD 連線設定期間選取屬性。
  
請勿同步處理樹系之間的 Upn。 您必須針對每個使用者樹系使用唯一的 UPN，因為您無法在多個樹系上使用相同的 UPN。 因此，有兩種可能性：同步處理 UPN 或不同步處理。 
  
- 如果每個使用者樹系的唯一 UPN 未同步處理至資源樹系中關聯的已停用物件，則 [單一登入] (SSO) 至少會在初始登入嘗試時中斷 (假定使用者選取了儲存密碼的選項) 。 在商務用 Skype 用戶端中，我們假設 SIP/UPN 值相同。 因為此案例中的 SIP 位址是 user@company.com，但使用者樹系中已啟用之物件的 UPN 實際上是 user@contoso.company.com，所以初始登入嘗試會失敗，且系統會提示使用者輸入認證。 輸入正確的 UPN 後，就會針對使用者樹系中的網域控制站完成驗證要求，而且登入會成功。
    
- 如果每個使用者樹系的唯一 UPN 已同步處理至資源樹系中關聯的已停用物件，則 AD FS 驗證會失敗。 比對規則會在資源樹系中的物件上找到 UPN，該物件已停用，且無法用於驗證。 
    
## <a name="create-a-microsoft-365-organization"></a>建立 Microsoft 365 組織

您將需要布建 Microsoft 365 組織，以用於部署。 如需詳細資訊，請參閱 [Microsoft 雲端供應專案的訂閱、授權、帳戶及承租人](/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings)。 
  
## <a name="configure-active-directory-federation-services"></a>設定 Active Directory Federation Services

當您有租使用者之後，您必須在每個使用者樹系中設定 Active Directory Federation Services (AD FS) 。 這假設您有每個樹系 (UPN) 的 SIP 及 SMTP 位址和使用者主體名稱。 AD FS 是選用的，可在這裡用來取得單一登入 (SSO) 。 也支援具有密碼同步處理的 DirSync，也可以用來取代 AD FS。 
  
僅測試具有符合 SIP/SMTP 和 Upn 的部署。 不符合 SIP/SMTP/upn 的功能可能會導致功能降低，例如 Exchange 整合和 SSO 的問題。 
  
除非您針對每個樹系的使用者使用唯一的 SIP/SMTP/UPN，但不論 AD FS 部署於何處，仍然可以執行 SSO 問題： 
  
- 在每個使用者樹系中部署 AD FS 伺服器樹系的資源/使用者樹系之間的單向或雙向信任，所有使用者都共用一般 SIP/SMTP 網域，但是每個使用者樹系都有唯一的 UPN。 
    
- 只在資源樹系中部署 AD FS 伺服器樹系的資源/使用者樹系之間的雙向信任，所有使用者都共用一般 SIP/SMTP 網域，但是每個使用者樹系都有唯一的 UPN。 
    
在每個使用者樹系中放置一個 AD FS 伺服器陣列，並針對每個樹系使用唯一的 SIP/SMTP/UPN，我們會解決這兩個問題。 在驗證嘗試期間，只會搜尋該特定使用者樹系中的帳戶，並將其配對。 這將協助提供更順暢的驗證程式。 
  
此部署將是 Windows Server 2012 R2 AD FS 的標準部署，在繼續之前，應正常運作。 如需相關指示，請參閱 how [To INSTALL AD FS 2012 R2 for Microsoft 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx)。 
  
部署之後，您必須編輯宣告規則，使其符合先前所選取的來源錨點。 在 [AD FS MMC] 的 [信賴憑證者信任] 底下，以滑鼠右鍵按一下 [ **Microsoft 365 身分識別平臺**] 或 [ **Microsoft Office 365 身分識別平臺**]，然後選取 [**編輯宣告規則**]。 編輯第一個規則，並將 ObjectSID 變更為 **employeeNumber**。 
  
![多樹系編輯規則畫面](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>設定 AAD 連線

在資源樹系拓撲中，資源樹系和任何 (帳戶樹系) 中的使用者屬性都必須已同步處理至 Azure AD。 Microsoft 建議 Azure AD 連線同步處理及合併 *所有* 已啟用使用者帳戶的樹系和包含商務用 Skype 的樹系的使用者身分識別。 如需詳細資訊，請參閱[針對商務用 Skype 和 Teams 設定 Azure AD 連線](configure-azure-ad-connect.md)。

請注意，Azure AD 連線不會在帳戶和資源樹系之間的內部部署上提供同步處理。 必須使用 Microsoft Identity Manager 或類似的產品來設定，如前文所述。
  
完成和 Azure AD 連線合併時，如果您在元節中查看物件，您應該會看到類似下列的內容： 
  
![多樹系元節物件畫面](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
綠色的醒目提示屬性已從 Microsoft 365 合併，黃色來自使用者樹系，而藍色則來自資源樹系。 
  
在此範例中，Azure AD 連線已識別從 Microsoft 365 的使用者和資源樹系物件的 sourceAnchor 和 cloudSourceAnchor，在本例中為 1101-------------------- Azure AD 連線使用者是否可以將此物件合併至您的上方。 
  
如需詳細資訊，請參閱[將您的內部部署目錄與 Azure Active Directory 整合](/azure/active-directory/hybrid/whatis-hybrid-identity)。 
  
Azure AD 連線應以預設值安裝，但不包括下列各項： 
  
1. 已部署並運作單一登入與 AD FS：選取 [不 **設定**]。
    
2. 連線您的目錄：新增所有網域。
    
3. 在內部部署目錄中識別使用者：選取 **跨越多個目錄的使用者識別碼**，然後選取 **ObjectSID** 及 **msExchangeMasterAccountSID** 屬性。
    
4. 在 Azure AD 中識別使用者：來源錨點：選取您在閱讀 [ [選取好的 sourceAnchor 屬性](/azure/active-directory/hybrid/plan-connect-design-concepts#selecting-a-good-sourceanchor-attribute)、使用者主體名稱- **userPrincipalName** 後所選擇的屬性。
    
5.  選用功能：選取是否已部署 Exchange 混合式。
    
    > [!NOTE]
    >  如果您只有 Exchange Online，由於 CNAME 重新導向，所以自動探索時發生 OAuth 失敗的問題。 若要修正此錯誤，您需要從商務用 Skype Server 管理命令介面執行下列 Cmdlet，以設定 Exchange 自動探索 URL：
    >
    > ```powershell
    > Set-CsOAuthConfiguration -ExchangeAutoDiscoverURL https://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    > ```
    
6.  AD fs 伺服器陣列：選取 [**使用現有的 Windows Server 2012 R2 AD fs 伺服器** 陣列]，然後輸入 AD fs 伺服器的名稱。
    
7.  完成該嚮導並執行必要的驗證。
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>設定商務用 Skype Server 的混合式連接

遵循設定商務用 Skype 混合式的最佳作法。 如需詳細資訊，請參閱 [規劃混合](plan-hybrid-connectivity.md) 式連線和 [設定混合](configure-hybrid-connectivity.md)式連線。 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>設定 Exchange Server 的混合式連接

如有必要，請遵循設定 Exchange 混合式的最佳作法。 如需詳細資訊，請參閱[Exchange Server 混合式部署](/exchange/exchange-hybrid)。 
