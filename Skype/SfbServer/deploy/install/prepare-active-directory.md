---
title: 商務用 Skype Server：準備 Active Directory
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 摘要：瞭解如何準備您的 Active Directory 網域，以安裝商務用 Skype Server。 從 Microsoft 評估中心下載免費試用版商務用 Skype Server，網址如下： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。
ms.openlocfilehash: 40225e6efdf848c34d2b7184e4d8863182ef78494e179e27c4fa8ca322f7349d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300289"
---
# <a name="skype-for-business-server-prepare-active-directory"></a>商務用 Skype Server：準備 Active Directory
 
**摘要：** 瞭解如何準備您的 Active Directory 網域，以安裝商務用 Skype Server。 從[Microsoft 評估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)下載商務用 Skype Server 的免費試用版。
  
商務用 Skype Server 與 Active Directory 密切搭配使用。 您必須準備作用中的 Active Directory 網域，才能使用商務用 Skype Server。 此程式是在部署嚮導中完成，只對網域執行一次。 這是因為程式會建立群組並修改網域，而您只需要執行一次。 您可以依任何循序執行步驟1到5。 不過，您必須依序執行步驟6、7和8，並在步驟1到5之後進行，如圖表中所述。 準備 Active Directory 是步驟4之8。 如需規劃 Active Directory 的詳細資訊，請參閱商務用 Skype Server 2019 商務用 Skype Server 或[伺服器需求](../../../SfBServer2019/plan/system-requirements.md)[的環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。
  
![一覽表圖表](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>準備 Active Directory

商務用 Skype Server 與 Active Directory 網域服務 (AD DS) 緊密整合。 在您第一次安裝商務用 Skype Server 之前，必須準備好 Active Directory。 在 [**準備 active directory** ] 的部署嚮導區段中，準備好 active directory 環境以用於商務用 Skype Server。
  
> [!NOTE]
> 商務用 Skype Server 會使用 (AD DS) 追蹤拓撲中的所有伺服器並與其通訊。 這些伺服器中的大部分都必須加入網域，這樣商務用 Skype Server 才能正常運作。 請記住，Edge 和反向 Proxy 等伺服器應該不會加入網域。
  
> [!IMPORTANT]
> 針對部署中的每個網域，應只執行一次 [準備 Active Directory] 程式。 
  
觀賞 **準備 Active Directory** 的影片步驟：
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>從部署嚮導準備 Active Directory

1. 以具有 Active Directory 網域之架構管理員認證的使用者身分登入。
    
2. 開啟商務用 Skype Server 部署嚮導。
    
    > [!TIP]
    > 如果您想要查看由商務用 Skype Server 部署嚮導所建立的記錄檔，您可以在執行該步驟的 AD DS 使用者的使用者目錄中，找到這些記錄檔所建立的「部署」嚮導所在的電腦。 例如，如果使用者以網域中的網域管理員身分登入，則記錄檔位於： C:\Users\Administrator.Contoso\AppData\Local\Temp。 
  
3. 按一下 [ **準備 Active Directory** ] 連結。
    
4. **步驟1：準備架構**
    
    a. 透過按一下步驟1標題底下的下拉式清單，查看步驟1可以存取的必要條件資訊。
    
    b. 按一下 [步驟 1] 中的 [ **執行** ]，以啟動 [準備架構] 嚮導。
    
    c. 請注意，每個部署的程式都應該只執行一次，然後按 **[下一步]**。
    
    d. 做好架構準備之後，您可以按一下 [ **查看記錄** 檔] 來查看記錄檔。 
    
    e. 按一下 **[完成]** 以關閉 [準備架構] 嚮導，並回到 [準備 Active Directory] 步驟。
    
5. **步驟2：驗證架構分割區的複寫**
    
    a. 登入網域的網域控制站。
    
    b. 在 [**伺服器管理員**] 的 [**工具**] 下拉式功能表中開啟 **ADSI 編輯器**。
    
    c. 在 [動作] 功能表上，按一下 [連線至]。
    
    d. 在 **[選取熟知的命名內容]** 的 **[連線設定]** 對話方塊中，選取 **[架構]**，然後按一下 **[確定]**。
    
    e. 在架構容器底下，搜尋 **CN = ms-**----SIP-SchemaVersion。 如果此物件存在，且 **rangeUpper** 屬性的值是1150，而 **rangeLower** 屬性的值是3，則表示已成功更新及複製架構。 如果此物件不存在，或 **rangeUpper** 及 **rangeLower** 屬性的值不是指定的，則未修改或尚未複製架構。
    
6. **步驟3：準備目前的樹系**
    
    a. 透過按一下 [步驟 3] 標題底下的下拉式清單，查看步驟3可存取的必要條件資訊。
    
    b. 按一下步驟3中的 [ **執行** ]，以啟動 [準備目前的樹系] 嚮導。
    
    c. 請注意，此程式在每次部署中應只執行一次，然後按 **[下一步]**。
    
    d. 指定通用群組會建立所在的網域。 如果伺服器是網域的一部分，您可以選擇 [ **本機網域**]，然後按 **[下一步]**。
    
    e. 準備好樹系之後，您可以按一下 [ **查看記錄** 檔] 以查看記錄檔。 
    
    f. 按一下 **[完成]** ，以關閉 [準備目前的樹系] 嚮導，並回到 [準備 Active Directory] 步驟。
    
    g. 從 [**應用程式**] 頁面上，按一下 [**商務用 Skype Server 管理命令** 介面]，以啟動 PowerShell。
    
    h. 輸入命令 Get-CsAdForest，然後按 **enter**。
    
    i. 如果結果是 **LC_FORESTSETTINGS_STATE_READY**，樹系已經順利做好準備，如圖所示。
    
     ![驗證樹系複寫。](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **步驟4：驗證通用類別目錄的複寫**
    
    a. 在網域控制站上 (首選于從其他網域控制站的遠端網站) ，在執行樹系準備的樹系中，開啟 [ **Active Directory 使用者和電腦**]。
    
    b. 在 [ **Active Directory 使用者及電腦**] 中，展開樹系或子域的功能變數名稱。
    
    c. 按一下左側窗格中的 [ **使用者** ] 容器，然後在右側窗格中尋找通用群組 **CsAdministrator** 。 如果有 CsAdministrator (其他以 Cs) 開頭的新通用群組，則表示已成功進行 Active Directory 複寫。
    
    d. 如果這些群組尚未存在，您可以強制複寫，或等候15分鐘，然後重新整理右側窗格。 當群組存在時，就會完成複寫。
    
8. **步驟5：準備目前的網域**
    
    a. 請參閱步驟5的必要條件資訊。
    
    b. 按一下步驟5中的 [ **執行** ]，以啟動 [準備目前的網域] 嚮導。
    
    c. 請注意，應只對部署中的每個網域執行一次此程式，然後按 **[下一步]**。
    
    d. 準備好網域之後，您可以按一下 [ **查看記錄** 檔] 來查看記錄檔。 
    
    e. 按一下 **[完成]** 以關閉 [準備目前的網域] 嚮導，並回到 [準備 Active Directory] 步驟。
    
    在找到商務用 Skype Server 物件的每個網域中，必須完成這些步驟，否則服務可能無法啟動。 這包括任何類型的 Active Directory 物件，例如，使用者、連絡人物件、系統管理群組或任何其他類型的物件。 如有需要，您可以使用 Set-CsUserReplicatorConfiguration ADDomainNamingCoNtextList 僅新增包含商務用 Skype Server 物件的網域。
    
9. **步驟6：確認網域中的複寫**
    
    a. 從 [**應用程式**] 頁面上，按一下 [**商務用 Skype Server 管理命令** 介面]，以啟動 PowerShell。
    
    b. 使用命令 Get-CsAdDomain 來驗證網域內的複寫。
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > 如果您沒有指定 Domain 參數，這個值會設為本機網域。 
  
    在 contoso 中執行命令的範例。本地域：
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > 使用參數 GlobalSettingsDomainController，您可以指定儲存全域設定的位置。 如果您的設定儲存在系統容器中 (在一般情況下，如果升級部署尚未將全域設定遷移至設定容器) ，您可以在 AD DS 樹系的根目錄中定義網域控制站。 如果全域設定位於 Configuration 容器中 (在全新部署或升級部署作業期間，當設定已經移轉至 Configuration 容器時的常見現象)，您可以在樹系中定義任何網域控制站。 如果您未指定此參數，Cmdlet 會假設設定儲存在設定容器中，並參照至 Active Directory 中的任何網域控制站。 
  
    c. 如果結果是 **LC_DOMAINSETTINGS_STATE_READY**，則網域已成功複寫。
    
10. **步驟7：新增使用者以供應商務用 Skype Server 控制台的系統管理存取權**
    
    a. 使用 Domain Admins 群組成員或 RTCUniversalServerAdmins 群組成員的身分登入。
    
    b. 開啟 [ **Active Directory 使用者及電腦**]，展開網域，按一下 [ **使用者** ] 容器，以滑鼠右鍵按一下 [CSAdministrator]，然後選擇 [ **屬性**]。
    
    c. 在 **[CSAdministrator 內容]** 中，按一下 **[成員]** 索引標籤。
    
    d. 在 [成員] 索引標籤上，按一下 [新增]。 在 [選取使用者、連絡人、電腦、服務帳戶或群組] 中，找到 [輸入要選取的物件名稱]。 輸入要新增到 CSAdministrators 群組的使用者名稱或群組名稱。 按一下 [確定]。
    
    e. 在 [ **成員** ] 索引標籤上，確認您選取的使用者或群組是否存在。 按一下 ****[確定]。
    
    > [!CAUTION]
    > 商務用 Skype Server 控制台是以角色為基礎的存取控制工具。 CsAdministrator 群組中的成員資格會提供使用者使用商務用 Skype Server 控制台完全控制權，以供所有可用的配置功能使用。 有些其他的角色是針對特定功能而設計。 如需可用角色的詳細資訊，請參閱[商務用 Skype Server 2019 商務用 Skype Server 或伺服器需求](../../../SfBServer2019/plan/system-requirements.md)[的環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。 請注意，您不需要為商務用 Skype Server 啟用使用者，就能成為管理群組的成員。 
  
    > [!CAUTION]
    > 若要協助保留安全性和角色型存取控制完整性，請將使用者新增至定義使用者在管理商務用 Skype Server 部署時所執行之角色的群組。 
  
11. [登出]，然後重新登入 Windows，以便使用新的商務用 Skype Server 安全性群組來更新您的安全性權杖，然後重新開啟部署嚮導。
    
12. 請確認您已在 [ **準備 Active Directory** ] 旁邊的綠色旁核取記號，以確認成功，如圖所示。
    
     ![準備 Active Directory 已完成。](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>另請參閱
 
[商務用 Skype Server 2015 的 Active Directory 網域服務](../../plan-your-deployment/security/active-directory-domain-services.md)
