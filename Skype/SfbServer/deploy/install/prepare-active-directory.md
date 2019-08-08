---
title: 為商務用 Skype Server 準備 Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: '摘要: 瞭解如何準備 Active Directory 網域以進行商務用 Skype Server 的安裝。 從 Microsoft 評估中心下載免費試用版商務用 Skype Server, 網址為: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: 85bd8d45cee1144ef355f0a9b0491d24529d6ff3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245794"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a>為商務用 Skype Server 準備 Active Directory
 
**摘要:** 瞭解如何為您的 Active Directory 網域進行準備, 以進行商務用 Skype Server 的安裝。 從[Microsoft 評估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)下載商務用 Skype Server 的免費試用版。
  
商務用 Skype 伺服器與 Active Directory 密切搭配使用。 您必須準備 Active Directory 網域, 才能搭配商務用 Skype 伺服器使用。 這個程式是在部署嚮導中完成, 只會針對網域進行一次。 這是因為程式會建立群組並修改網域, 而您只需要執行一次。 您可以依照任何循序執行步驟1到5。 不過, 您必須在順序中執行步驟6、7和 8, 並在步驟1到5之後, 如圖表中所述。 準備 Active Directory 是8的步驟4。 如需規劃 Active Directory 的詳細資訊, 請參閱商務用 skype [server 2019 的](../../../SfBServer2019/plan/system-requirements.md)[商務用 Skype server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或伺服器需求的環境需求。
  
![概覽圖表](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>準備 Active Directory

商務用 Skype Server 與 Active Directory 網域服務 (AD DS) 緊密整合。 在商務用 Skype Server 第一次安裝之前, 必須準備作用中的 Active Directory。 標題為 [**準備 Active Directory** ] 的部署嚮導區段會準備作用中的 active directory 環境, 以便與商務用 Skype 伺服器搭配使用。
  
> [!NOTE]
> 商務用 Skype Server 使用 (AD DS) 來追蹤並與拓撲中的所有伺服器進行通訊。 每個伺服器都必須加入網域, 才能讓商務用 Skype 伺服器正常運作。 
  
> [!IMPORTANT]
> 針對部署中的每個網域, 只能執行一次準備 Active Directory 程式。 
  
觀看**準備 Active Directory**的影片步驟:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>從 [部署] 嚮導準備 Active Directory

1. 以擁有 Active Directory 網域之架構管理員認證的使用者身分登入。
    
2. 開啟商務用 Skype Server 部署嚮導。
    
    > [!TIP]
    > 如果您想要查看由商務用 Skype Server 部署嚮導所建立的記錄檔, 您可以在執行步驟之 AD DS 使用者的使用者目錄中, 找到執行 [部署嚮導] 的電腦上的日誌檔。 例如, 如果使用者是以網域 (contoso) 的網域管理員身分登入, 則記錄檔案位於: C:\Users\Administrator.Contoso\AppData\Local\Temp。 
  
3. 按一下 [**準備 Active Directory** ] 連結。
    
4. **步驟 1: 準備架構**
    
    是. 若要查看步驟1的先決條件資訊, 請按一下步驟1標題下方的下拉式清單。
    
    乙. 按一下步驟1中的 [**執行**], 啟動 [準備架構] 嚮導。
    
    c-clip. 請注意, 此程式對於每個部署只能執行一次, 然後按一下 **[下一步]**。
    
    希望. 準備好架構之後, 您可以按一下 [**查看記錄**] 來查看記錄。 
    
    e. 按一下 **[完成]** 以關閉 [準備架構] 嚮導, 然後返回 [準備 Active Directory] 步驟。
    
5. **步驟 2: 驗證架構分區的複製**
    
    是. 登入網域的網網域控制站。
    
    乙. 從**伺服器管理員**中的 [**工具**] 下拉式功能表開啟 [ **ADSI 編輯**]。
    
    c-clip. 在 [**動作**] 功能表上, 按一下 **[連線至]**。
    
    希望. 在 [連線**設定**] 對話方塊中的 [**選取已知命名內容**] 底下, 選取 [**架構**], 然後按一下 **[確定]**。
    
    e. 在架構容器底下, 搜尋**CN = ms-SIP-SchemaVersion**。 如果這個物件存在, 且**rangeUpper**屬性的值為 1150, 且**rangeLower**屬性的值是 3, 則架構已成功更新並複製。 如果此物件不存在, 或**rangeUpper**和**rangeLower**屬性的值不是指定的, 則架構並未被修改或未複製。
    
6. **步驟 3: 準備目前的林**
    
    是. 若要查看步驟3的先決條件資訊, 請按一下步驟3標題下方的下拉式清單。
    
    乙. 按一下步驟3中的 [**執行**], 啟動 [準備目前的林] 嚮導。
    
    c-clip. 請注意, 每個部署的程式只應執行一次, 然後按一下 **[下一步]**。
    
    希望. 指定將建立通用群組的網域。 如果伺服器是網域的一部分, 您可以選擇 [**本地域**], 然後按 **[下一步]**。
    
    e. 在林準備好之後, 您可以按一下 [**查看記錄**] 來查看記錄。 
    
    °. 按一下 **[完成]** , 關閉 [準備目前的林] 嚮導, 然後返回 [準備 Active Directory] 步驟。
    
    7. 按一下 [**應用程式**] 頁面上的 [**商務用 Skype Server Management Shell** ] 以啟動 PowerShell。
    
    h. 輸入命令 CsAdForest, 然後按**enter**。
    
    是否. 如果結果是**LC_FORESTSETTINGS_STATE_READY**, 則目錄林已順利進行準備, 如圖所示。
    
     ![驗證林複製。](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **步驟 4: 驗證全域編目的複製**
    
    是. 在網網域控制站 (最好是位於其他網網域控制站的遠端網站中), 在執行目錄林準備的林中, 開啟**Active Directory 使用者和電腦**。
    
    乙. 在**Active Directory 使用者和電腦**中, 展開您的林或子域的功能變數名稱。
    
    c-clip. 按一下左側窗格中的 [**使用者**] 容器, 然後在右側窗格中尋找 [通用群組] **CsAdministrator** 。 如果 CsAdministrator (在以 Cs 開頭的其他新通用群組) 存在, 則表示已成功進行 Active Directory 複製。
    
    希望. 如果群組尚不存在, 您可以強制進行複製, 或等候15分鐘並重新整理右側窗格。 當群組存在時, 複製就完成了。
    
8. **步驟 5: 準備目前的網域**
    
    是. 查看步驟5的先決條件資訊。
    
    乙. 按一下步驟5中的 [**執行**], 啟動 [準備目前的網域] 嚮導。
    
    c-clip. 請注意, 這個程式只能針對部署中的每個網域執行一次, 然後按一下 **[下一步]**。
    
    希望. 準備好網域之後, 您可以按一下 [**查看記錄**] 來查看記錄。 
    
    e. 按一下 **[完成]** , 關閉 [準備目前的網域] 嚮導, 然後返回 [準備 Active Directory] 步驟。
    
    在已找到商務用 Skype Server 物件的每個網域中, 都必須完成這些步驟, 否則服務可能無法啟動。 這包括任何類型的 Active Directory 物件, 例如使用者、連絡人物件、系統管理群組或任何其他類型的物件。 如有需要, 您可以使用 CsUserReplicatorConfiguration-ADDomainNamingCoNtextList 來新增只有商務用 Skype Server 物件的網域。
    
9. **步驟 6: 驗證網域中的複製**
    
    是. 按一下 [**應用程式**] 頁面上的 [**商務用 Skype Server Management Shell** ] 以啟動 PowerShell。
    
    乙. 使用命令 CsAdDomain 驗證網域中的複製。
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > 如果您沒有指定 Domain 參數，則會將此值設定至本機網域。 
  
    針對 contoso. 本地域執行命令的範例:
    
   ```
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > 使用參數 GlobalSettingsDomainController, 您可以指出儲存全域設定的位置。 如果您的設定是儲存在系統容器中 (這通常是將未將全域設定遷移至配置容器的升級部署), 您可以在 AD DS 目錄林的根目錄中定義網網域控制站。 如果全域設定位於 Configuration 容器中 (在全新部署或升級部署作業期間，當設定已經移轉至 Configuration 容器時的常見現象)，您可以在樹系中定義任何網域控制站。 如果您沒有指定此參數, Cmdlet 會假設設定會儲存在配置容器中, 並參照 Active Directory 中的任何網網域控制站。 
  
    c-clip. 如果結果是**LC_DOMAINSETTINGS_STATE_READY**, 則網域已順利複製。
    
10. **步驟 7: 新增使用者以提供對商務用 Skype Server 控制台的系統管理存取權**
    
    是. 使用 Domain Admins 群組成員或 RTCUniversalServerAdmins 群組成員的身分登入。
    
    乙. 開啟 [ **Active Directory 使用者和電腦**], 展開您的網域, 按一下 [**使用者**] 容器, 以滑鼠右鍵按一下 [CSAdministrator], 然後選擇 [**屬性**]。
    
    c-clip. 在 [CSAdministrator 內容] **** 中，按一下 [成員] **** 索引標籤。
    
    希望. 按一下 [**成員**] 索引標籤上的 [**新增**]。 在 [選取使用者、連絡人、電腦、服務帳戶或群組] **** 中，找到 [輸入要選取的物件名稱]****。 輸入要新增到 CSAdministrators 群組的使用者名稱或群組名稱。 按一下 [確定]****。
    
    e. 在 [**成員**] 索引標籤上, 確認您所選取的使用者或群組存在。 按一下 [確定]****。
    
    > [!CAUTION]
    > 商務用 Skype Server 的 [控制台] 是一個以角色為基礎的存取控制工具。 [CsAdministrator] 群組中的成員資格提供使用商務用 Skype Server 控制台的使用者, 以取得所有可用的配置功能。 有些其他的角色是針對特定功能而設計。 如需可用角色的詳細資訊, 請參閱商務用 skype [server 2019 的](../../../SfBServer2019/plan/system-requirements.md)[商務用 Skype server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或伺服器需求的環境需求。 請注意, 您不需要針對商務用 Skype Server 啟用使用者, 就能成為管理群組的成員。 
  
    > [!CAUTION]
    > 若要協助保留安全性與角色式的存取控制完整性, 請將使用者新增至群組, 以定義使用者在管理商務用 Skype Server 部署時所執行的角色。 
  
11. 登出, 然後重新登入 Windows, 以便使用新的商務用 Skype Server 安全群組來更新您的安全權杖, 然後重新開啟 [部署] 嚮導。
    
12. 確認您在 [**準備 Active Directory** ] 旁看到綠色的核取記號, 以確認成功, 如圖所示。
    
     ![準備 Active Directory 已完成。](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>另請參閱
 
[商務用 Skype Server 2015 的 Active Directory 網域服務](../../plan-your-deployment/security/active-directory-domain-services.md)
