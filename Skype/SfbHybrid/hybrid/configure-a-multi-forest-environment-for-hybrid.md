---
title: 部署資源林拓撲
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 下列各節提供如何設定在資源/使用者目錄林模型中有多個目錄林的環境, 以提供混合式案例中的商務用 Skype 功能的指導方針。
ms.openlocfilehash: 7ef895648c044dc5d1f3f907ad4f75d950a4253a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185479"
---
# <a name="deploy-a-resource-forest-topology"></a>部署資源林拓撲
 
下列各節提供如何設定在資源/使用者目錄林模型中有多個目錄林的環境, 以提供混合式案例中的商務用 Skype 功能的指導方針。 
  
![混合式多林環境](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>拓撲需求

支援多個使用者目錄林。 請記住下列事項: 
    
- 在混合式設定中, 如需 Lync Server 和商務用 Skype Server 的支援版本, 請參閱在[商務用 Skype server 和 Office 365 之間規劃混合式連接](plan-hybrid-connectivity.md)的[伺服器版本需求](plan-hybrid-connectivity.md#server-version-requirements)。
    
- Exchange Server 可以部署在一個或多個林中, 這些目錄林中可能包含或不包含商務用 Skype Server 的林。 請確定您已套用最新的累加更新。
    
- 如需與 Exchange Server 共存的詳細資料, 包括各種內部部署和線上結合的支援準則與限制, 請參閱規劃中的[功能支援](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support),[以整合商務用 Skype 與 Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)。
    
  
## <a name="user-homing-considerations"></a>使用者引導的考慮

駐留在內部部署的商務用 Skype 使用者可以將 Exchange 駐留在內部部署或線上。 商務用 Skype Online 使用者應該使用 Exchange Online 來獲得最佳體驗;不過, 這不是必要的。 在任何情況下, 都不需要在內部部署中實現商務用 Skype。
  
## <a name="configure-forest-trusts"></a>設定林信任

在資原始目錄林拓朴中, 託管商務用 Skype Server 的資原始目錄林必須信任每個帳戶目錄林, 其中包含可存取該帳戶的使用者帳戶。 如果您有多個使用者目錄林, 若要啟用跨目錄林驗證, 請務必針對這些目錄林信任啟用名稱尾碼路由。 如需相關指示, 請參閱[管理林信任](https://technet.microsoft.com/en-us/library/cc772440.aspx)。 如果您已在另一個目錄林中部署 Exchange 伺服器, 且它供應商務用 Skype 使用者的功能, 那麼託管 Exchange 的林就必須信任託管商務用 Skype 伺服器的目錄林。 例如, 如果 Exchange 是部署在帳戶目錄林中, 這會在該設定中有效表示客戶與商務用 Skype 目錄林之間的雙向信任。
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>將帳戶同步處理到主持商務用 Skype 的林中

當商務用 Skype Server 部署在一個目錄林中 (資原始目錄林中), 但在一或多個其他目錄林 (帳戶目錄林) 中提供給使用者的功能, 其他林中的使用者必須在您的 Skype 適用的林中以停用的使用者物件表示已部署商務伺服器。 必須部署並設定身分識別管理產品 (例如 Microsoft 身分識別管理員), 才能將帳戶林的使用者設定並同步處理到部署商務用 Skype Server 的林中。 使用者必須同步處理到主持商務用 Skype Server 的林中, 即已停用的使用者物件。 使用者無法同步處理為 Active Directory 連絡人物件, 因為 Azure Active Directory Connect 將無法正確同步處理連絡人至 Azure AD, 以便與 Skype 搭配使用。
  
無論任何多重目錄林設定為何, 託管商務用 Skype 伺服器的林也可以提供任何位於相同林中的已啟用使用者的功能。
  
若要取得正確的身分識別同步處理, 必須同步處理下列屬性: 
  
|**使用者目錄林**|**資原始目錄林**|
|:-----|:-----|
|[選取的帳戶] 連結屬性  <br/> |[選取的帳戶] 連結屬性  <br/> |
|郵遞  <br/> |郵遞  <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
所[選的帳戶連結屬性](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-design-concepts/)將會用來做為來源錨點。 如果您想要使用不同且不可變的屬性, 您可以執行此動作。只要確認編輯 AD FS 聲明規則, 並在 AAD 連線設定期間選取屬性即可。
  
請勿在目錄林之間同步處理 Upn。 我們在測試期間發現我們需要針對每個使用者林使用唯一的 UPN, 因為您無法在多個目錄林使用相同的 UPN。 因此, 我們會提供兩種可能的方式, 以同步處理 UPN 或無法同步處理。 
  
- 如果每個使用者樹林中的唯一 UPN 沒有與資原始目錄林中的相關聯停用物件同步處理, 單一登入 (SSO) 至少會中斷初始登入 (假設使用者已選取儲存密碼的選項)。 在商務用 Skype 用戶端中, 我們假設 SIP/UPN 值相同。 由於這個案例中的 SIP 位址是 user@company.com, 但使用者林中已啟用物件的 UPN 事實上是 user@contoso.company.com, 所以初始登入嘗試將會失敗, 且系統會提示使用者輸入認證。 輸入正確/實際的 UPN 後, 驗證要求會針對使用者林中的網網域控制站完成, 且登入成功。
    
- 如果每個使用者林中的唯一 UPN 已同步處理至資原始目錄林中的關聯停用物件, 則 AD FS 驗證將會失敗。 [相符規則] 會在已停用且無法用於驗證的資原始目錄林中, 找到該物件上的 UPN。 
    
## <a name="create-an-office-365-tenant"></a>建立 Office 365 租使用者

您必須先將 Office 365 租使用者提供給您的部署使用。 如需詳細資訊, 請參閱[Microsoft 雲端服務的訂閱、授權、帳戶和](https://docs.microsoft.com/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings)租使用者。 
  
## <a name="configure-active-directory-federation-services"></a>設定 Active Directory Federation Services

當您擁有租使用者之後, 您將需要在每個使用者目錄林中設定 Active Directory Federation Services (AD FS)。 這假設您有每個目錄林都有唯一的 SIP 與 SMTP 位址及使用者主體名稱 (UPN)。 AD FS 是選擇性的, 在這裡使用, 以取得單一登入 (SSO)。 也支援使用密碼同步處理的 DirSync, 也可以用來取代 AD FS。 
  
僅測試具有相符 SIP/SMTP 與 Upn 的部署。 不具備相符的 SIP/SMTP/Upn, 可能會導致功能下降, 例如 Exchange 整合與 SSO 的問題。 
  
除非您針對每個目錄林中的使用者使用唯一的 SIP/SMTP/UPN, 否則無論 AD FS 部署在哪裡, 您仍然可以執行 SSO 問題: 
  
- 在每個使用者林中部署 AD FS 場之資源/使用者目錄林之間的單向或雙向信任, 所有使用者都共用公用 SIP/SMTP 網域, 但每個使用者林都有唯一的 UPN。 
    
- 只有在資原始目錄林中部署了 AD FS 場的資源/使用者林之間的雙向信任, 所有使用者才會共用公用 SIP/SMTP 網域, 但每個使用者林都有唯一的 UPN。 
    
透過將 AD FS 伺服器陣列放在每個使用者林中, 並針對每個目錄林使用唯一的 SIP/SMTP/UPN, 我們就能解決這兩個問題。 在驗證嘗試期間, 只會搜尋特定使用者林中的帳戶並進行相符。 這將協助提供更順暢的驗證程式。 
  
這將是 Windows Server 2012 R2 AD FS 的標準部署, 在繼續進行之前, 必須先進行工作。 如需相關指示, 請參閱[如何安裝適用于 Office 365 的 AD FS 2012 R2](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx)。 
  
部署之後, 您必須編輯宣告規則, 以符合先前選取的來源錨點。 在 AD FS MMC 中的 [信賴方信任] 底下, 以滑鼠右鍵按一下 [ **Microsoft Office 365 身分識別平臺**], 然後按一下 [**編輯聲明規則**]。 編輯第一個規則, 然後將 ObjectSID 變更為 [ **employeeNumber**]。 
  
![多目錄林編輯規則畫面](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>設定 AAD Connect

在資原始目錄林拓朴中, 您必須將來自資原始目錄林和任何帳戶目錄林的使用者屬性同步處理到 Azure AD。 若要這麼做, 最簡單且建議的方式是讓 Azure AD Connect 從已啟用使用者帳戶的*所有*目錄林以及包含商務用 Skype 的林, 同步處理及合併使用者身分識別。 如需詳細資訊, 請參閱針對[商務用 Skype 與團隊設定 AZURE AD Connect](configure-azure-ad-connect.md)。

請注意, AAD Connect 不會提供帳戶與資原始目錄林之間內部部署的同步處理。 必須使用 Microsoft 身分識別管理員或類似的產品來分別設定, 如前文所述。
  
完成併合並 AAD 連線後, 如果您在元節中查看物件, 就會看到類似以下的內容: 
  
![多林元節物件畫面](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
綠色醒目提示的屬性已從 Office 365 合併, 黃色來自使用者林, 而藍色則來自資原始目錄林。 
  
這是測試使用者, 您可以看到 AAD Connect 已識別來自 Office 365 的使用者和資原始目錄林物件的 sourceAnchor 和 cloudSourceAnchor, 這是1101我們先前選取的 employeeNumber。 然後, 就能將這個物件合併至上述內容。 
  
如需詳細資訊, 請參閱[將您的內部部署目錄與 Azure Active Directory 整合](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)。 
  
AAD Connect 應該使用預設值進行安裝, 但下列動作除外: 
  
1. 單一登入與已部署且正常運作的 AD FS: 選取 [**不要設定**]。
    
2. 連接您的目錄: 新增所有網域。
    
3. 在內部部署目錄中找出使用者: 選取**多個目錄**中都存在的使用者身分識別, 然後選取 [ **ObjectSID** ] 和 [ **msExchangeMasterAccountSID** ] 屬性。
    
4. 在 Azure AD 中識別使用者: 來源錨點: 選取您在閱讀[選取好的 sourceAnchor 屬性](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-design-concepts/)(使用者主體名稱- **userPrincipalName**) 後所選取的屬性。
    
5.  選用的功能: 選取您是否已部署 Exchange 混合式。
    
    > [!NOTE]
    >  如果您只有 Exchange Online, 則在自動探索期間由於 CNAME 重新導向, 可能會發生 OAuth 失敗的問題。 若要修正此錯誤, 您需要從商務用 Skype Server Management Shell 執行下列 Cmdlet 來設定 Exchange 自動探索 URL:
  
    CsOAuthConfiguration-ExchangeAutoDiscoverURL HTTPs://<span>autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    
6.  AD FS 伺服器陣列: 選取 [**使用現有的 Windows Server 2012 R2 AD FS 伺服器**陣列], 然後輸入 AD FS 伺服器的名稱。
    
7.  完成嚮導並執行必要的驗證。
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>設定商務用 Skype Server 的混合式連線性

遵循設定商務用 Skype 混合式的最佳做法。 如需詳細資訊, 請參閱[規劃混合式連線性](plan-hybrid-connectivity.md)並[設定混合式連線性](configure-hybrid-connectivity.md)。 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>設定 Exchange Server 的混合式連線性

如有需要, 請遵循設定 Exchange 混合式的最佳做法。 如需詳細資訊, 請參閱[Exchange 伺服器混合式部署](https://docs.microsoft.com/en-us/exchange/exchange-hybrid)。 
  

