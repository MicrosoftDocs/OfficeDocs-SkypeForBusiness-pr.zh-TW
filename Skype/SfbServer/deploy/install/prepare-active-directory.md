---
title: 準備 Active Directory skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 摘要： 了解如何準備 Skype 安裝 Business Server 的 Active Directory 網域。 下載 Microsoft 評估管理中心，從 Business Server Skype 免費試用版： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。
ms.openlocfilehash: 9a17ae327322b364935d0b965676d26fdce2cffb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018174"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a>準備 Active Directory skype for Business Server
 
**摘要：** 了解如何準備 Skype 安裝 Business Server 的 Active Directory 網域。 從[Microsoft 評估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Business Server 下載 Skype 免費試用版。
  
Skype 商務 Server 密切與 Active Directory 中。 您必須先準備 Active Directory 網域，才能使用 Skype for Business Server。 此程序完成部署精靈] 中，且只為網域一次完成。 這是因為和處理程序會建立群組，並修改的網域，您需要執行動作的唯一一次。 您可以執行步驟 1 到 5，以任何順序。 不過，您必須先執行步驟 6、 7 和 8 順序，並在步驟 1 到 5 之後，在圖表中所述。 準備 Active Directory 是 8 的步驟 4。 如需規劃 Active Directory 的詳細資訊，請參閱[Skype for Business 伺服器環境的需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或[Skype for Business Server 2019 的伺服器需求](../../../SfBServer2019/plan/system-requirements.md)。
  
![概觀圖表](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>準備 Active Directory

Skype 商務 Server 緊密整合與 Active Directory 網域服務 (AD DS)。 Skype for Business Server 可以安裝第一次之前，必須準備 Active Directory。 [] 區段中的 [部署精靈] 標題為 [**準備 Active Directory**會將使用的 Active Directory 環境與 Skype 準備 Business Server。
  
> [!NOTE]
> Skype 商務伺服器來追蹤並彼此的所有伺服器的拓撲中使用 (AD DS)。 大部分的這些伺服器必須加入網域，以便 Skype for Business Server 可以正常運作。 請記住，例如 Edge 和反向 Proxy 伺服器不應加入網域。
  
> [!IMPORTANT]
> 準備 Active Directory 程序應該執行的部署中的每個網域的僅一次。 
  
觀賞影片步驟**準備 Active**directory:
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>從 [部署精靈準備 Active Directory

1. 使用者身分登入 Schema Admins 與 Active Directory 網域的認證。
    
2. 開啟 Skype for Business Server 部署精靈]。
    
    > [!TIP]
    > 如果您想要檢閱記錄檔所建立的 Skype for Business Server 部署精靈，您可以在何處部署精靈已執行，執行步驟的 AD DS 使用者的使用者目錄中的電腦上找到他們。 例如，如果使用者以登入網域系統管理員的網域，contoso.local，記錄檔位於： C:\Users\Administrator.Contoso\AppData\Local\Temp。 
  
3. 按一下 [**準備 Active Directory** ] 連結。
    
4. **步驟 1： 準備架構**
    
    a. 檢閱步驟 1，可以在 [步驟 1 標題下方按一下下拉式清單來存取的必要條件資訊。
    
    b. 按一下 [啟動 [準備架構] 精靈的步驟 1 中的 [**執行**]。
    
    c. 記下應該針對每個部署中，只有一次執行程序，並再按 [**下一步**。
    
    d. 一旦已備妥結構描述，您可以檢視記錄檔]，即可**檢視記錄檔**。 
    
    e. 按一下 [**完成**] 以關閉 [準備架構精靈] 中，並回到 [準備 Active Directory 的步驟。
    
5. **步驟 2： 驗證架構分割的複寫**
    
    a. 登入網域的網域控制站。
    
    b. **伺服器管理員**] 中的 [**工具**] 下拉式清單功能表中，開啟 [ **Adsi 編輯器**]。
    
    c. 在 [動作] 功能表上，按一下 [連線至]。
    
    d. 在 **[選取熟知的命名內容]** 的 **[連線設定]** 對話方塊中，選取 **[架構]**，然後按一下 **[確定]**。
    
    e. 在 [架構] 容器中下, 搜尋**CN = ms RTC-SIP SchemaVersion**。 如果此物件存在， **rangeUpper**屬性的值是 1150年和**rangeLower**屬性的值為 3，結構描述已成功地更新，且複寫。 如果此物件不存在或**rangeUpper**和**rangeLower**屬性的值不是以指定，結構描述未修改或未進行複寫。
    
6. **步驟 3： 準備目前樹系**
    
    a. 檢閱步驟 3，也可以在 [步驟 3 標題下方按一下下拉式清單來存取的必要條件資訊。
    
    b. 按一下 [啟動準備目前樹系精靈的步驟 3 中的 [**執行**]。
    
    c. 記下程序應該只執行一次部署中，每，然後按 [**下一步**。
    
    d. 指定要在其中建立萬用群組的網域。 如果伺服器是屬於網域，您可以選擇**本機網域**，然後按一下 [**下一步**。
    
    e. 一旦已準備樹系，您可以檢視記錄檔]，即可**檢視記錄檔**。 
    
    f. 按一下 [**完成**] 以關閉 [準備目前樹系] 精靈中，並回到 [準備 Active Directory 的步驟。
    
    g. 從 [**應用程式**] 頁面上，啟動 PowerShell，請按一下 [ **Skype for Business Server 管理命令介面**]。
    
    h。 輸入命令 Get-csadforest，然後按**Enter**。
    
    我。 如果結果是**lc_forestsettings_state_ready 這個**，樹系成功已準備，如圖所示。
    
     ![確認樹系複寫。](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **步驟 4： 確認複寫的通用類別目錄**
    
    a. 網域控制站上 （最好是中的遠端網站的其他網域控制站），在樹系準備先前執行的樹系中，開啟 [ **Active Directory 使用者和電腦**]。
    
    b. 在 [ **Active Directory 使用者和電腦**，展開 [樹系或子網域的網域名稱。
    
    c. 按一下 [**使用者**] 容器，在左側窗格中，並尋找在右側窗格中的萬用群組**CsAdministrator** 。 如果出現 CsAdministrator （之間開頭 Cs 其他新萬用群組），Active Directory 複寫是否已順利完成。
    
    d. 如果群組還不存在，您可以強制執行複寫，或等候 15 分鐘，然後重新整理右側邊窗格。 群組存在時，複寫已完成。
    
8. **步驟 5： 準備目前的網域**
    
    a. 檢閱步驟 5 的必要條件資訊。
    
    b. 按一下 [步驟 5，以啟動 [準備目前的網域] 精靈中的 [**執行**]。
    
    c. 記下程序應該只能執行一次在部署中，每個網域，然後按 [**下一步**。
    
    d. 一旦準備的網域，您可以檢視記錄檔]，即可**檢視記錄檔**。 
    
    e. 按一下 [**完成**] 以關閉 [準備目前的網域] 精靈中，並回到 [準備 Active Directory 的步驟。
    
    這些步驟必須先完成其中 Skype for 找不到商務伺服器物件，否則服務可能會每個網域中不會啟動。 這包括任何 Active Directory 物件，例如使用者、 連絡人物件、 系統管理群組或任何其他類型的物件類型。 如有需要您可以使用 Set CsUserReplicatorConfiguration ADDomainNamingContextList 僅為新增網域與 Skype 商務伺服器物件。
    
9. **步驟 6： 確認網域中的複寫**
    
    a. 按一下 [ **Skype for Business Server 管理命令介面**從 [**應用程式**] 頁面來啟動 PowerShell。
    
    b. 若要確認網域內的複寫使用 Get-csaddomain] 命令。
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > 如果您沒有指定 Domain 參數，這個值會設為本機網域。 
  
    執行 [contoso.local 網域] 命令的範例：
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > 藉由使用 GlobalSettingsDomainController 的參數，您可以指出儲存全域設定。 如果您的設定儲存在系統容器 （這是一般升級尚未全域設定移轉至組態容器的部署） 中，您會在您的 AD DS 樹系根中定義的網域控制站。 如果全域設定位於 Configuration 容器中 (在全新部署或升級部署作業期間，當設定已經移轉至 Configuration 容器時的常見現象)，您可以在樹系中定義任何網域控制站。 如果您未指定此參數，指令程式會假設此設定會儲存在 [Configuration] 容器，且是指在 Active Directory 中的任何網域控制站。 
  
    c. 如果結果是**LC_DOMAINSETTINGS_STATE_READY**，網域已成功複寫。
    
10. **步驟 7： 新增使用者提供的管理存取權 skype for Business Server Control Panel**
    
    a. 使用 Domain Admins 群組成員或 RTCUniversalServerAdmins 群組成員的身分登入。
    
    b. 開啟 [ **Active Directory 使用者和電腦**，展開您的網域、 按一下 [**使用者**] 容器，以滑鼠右鍵按一下 CSAdministrator，選擇 [**屬性**。
    
    c. 在 **[CSAdministrator 內容]** 中，按一下 **[成員]** 索引標籤。
    
    d. 在 [成員]**** 索引標籤上，按一下 [新增]****。 在 [選取使用者、連絡人、電腦、服務帳戶或群組]**** 中，找到 [輸入要選取的物件名稱]****。 輸入要新增到 CSAdministrators 群組的使用者名稱或群組名稱。 按一下 [確定]****。
    
    e. 在 [**成員**] 索引標籤，確認使用者或群組，您所選取存在。 按一下 [確定]****。
    
    > [!CAUTION]
    > Skype for Business Server Control Panel 是角色型存取控制的工具。 以 CsAdministrator 群組成員資格授與使用 Skype for Business Server 控制台中的所有可用的組態函式的完全控制權的使用者。 有些其他的角色是針對特定功能而設計。 如需可用的角色的詳細資訊，請參閱[Skype for Business 伺服器環境的需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或[Skype for Business Server 2019 的伺服器需求](../../../SfBServer2019/plan/system-requirements.md)。 請注意，使用者沒有要啟用 Skype for Business Server 才能進行管理群組的成員。 
  
    > [!CAUTION]
    > 為了協助保留安全性和角色型存取控制完整性，請將使用者新增至定義了使用者在 Skype for Business Server 部署的管理，執行何種角色群組。 
  
11. 登出，並使新的 Skype for Business Server 安全性群組，更新您的安全性權杖，然後登入 Windows，然後重新開啟 [部署精靈。
    
12. 確認您看到**準備 Active Directory**以確認成功旁的綠色核取記號，如圖所示。
    
     ![準備 Active Directory 已完成。](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>另請參閱
 
[Skype 商務 Server 2015 的 active Directory 網域服務](../../plan-your-deployment/security/active-directory-domain-services.md)
