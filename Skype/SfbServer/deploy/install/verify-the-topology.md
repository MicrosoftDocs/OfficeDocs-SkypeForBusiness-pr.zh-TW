---
title: 在商務用 Skype Server 中驗證拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: '摘要: 瞭解如何驗證商務用 Skype 伺服器拓撲和 Active Directory 伺服器是否如預期運作。 從 Microsoft 評估中心下載免費試用版商務用 Skype Server, 網址為: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: 6c7d7a67cab2cbd383ee26eb64f478985bcc4b27
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245515"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>在商務用 Skype Server 中驗證拓撲
 
**摘要:** 瞭解如何驗證商務用 Skype 伺服器拓撲和 Active Directory 伺服器是否如預期運作。 從[Microsoft 評估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)下載商務用 Skype Server 的免費試用版。
  
在拓撲中發佈拓朴並安裝商務用 Skype Server system 元件之後, 您就可以開始確認拓朴是否如期運作。 這包括驗證設定是否已傳播到所有的 Active Directory 伺服器, 讓整個網域在網域中都能知道商務用 Skype。 您可以依照任何循序執行步驟1到5。 不過, 您必須在順序中執行步驟6、7和 8, 並在步驟1到5之後, 如圖表中所述。 驗證拓撲是8的步驟8。
  
![概覽圖表。](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>測試前端池部署

最後一個步驟是測試 [前端] 池, 並確認商務用 Skype 用戶端可以彼此通訊。 
  
### <a name="add-users-and-verify-client-connectivity"></a>新增使用者並驗證用戶端連線性

1. 使用 Active Directory 電腦和使用者將商務用 Skype Server 部署 (在其中安裝商務用 Skype 伺服器控制台) 的系統管理員角色的 Active Directory 使用者物件新增至**CSAdministrator**群組。
    
    > [!IMPORTANT]
    > 如果您沒有將適當的使用者和群組新增至 CsAdministors 群組, 當您開啟商務用 Skype Server 的 [控制台] 時, 會收到錯誤訊息 [未授權]: 由於角色式存取控制 (RBAC) 授權失敗, 存取遭到拒絕." 
  
2. 如果使用者物件目前已登入, 請先登出後再登入, 以註冊新的群組指派。
    
    > [!NOTE]
    > 使用者帳戶不能是執行商務用 Skype 伺服器的任何伺服器的本機系統管理員。 
  
3. 使用系統管理帳戶登入已安裝商務用 Skype Server 控制台的電腦。
    
4. 啟動商務用 Skype Server 的 [控制台], 然後在出現提示時提供認證。 商務用 Skype Server 的 [控制台] 會顯示部署資訊。
    
5. 在左側導覽列中, 按一下 [**拓撲**], 然後確認 [服務狀態] 會以綠色箭號顯示電腦, 且已部署並線上的每個商務用 Skype Server 角色旁邊都有綠色的核取記號。 
    
6. 在左側導覽列中, 按一下 [**使用者**], 然後按一下 [**啟用使用者**]。 
    
7. 在 [**新的商務用 Skype Server 使用者**] 頁面上, 按一下 [**新增**]。
    
8. 若要定義您想要尋找之物件的搜尋參數, 您可以在 [**從 Active Directory 中選取**] 頁面上選取 [**搜尋**], 然後按一下 [**新增篩選**] (選擇性)。 您也可以選取 [ **ldap 搜尋**], 然後輸入 ldap 運算式來篩選或限制將傳回的物件。 在您決定搜尋選項之後, 按一下 [**尋找**]。
    
9. 在 [搜尋結果] 窗格中, 選取您要新增的使用者, 然後按一下 **[確定]**。
    
10. 在 [**新的商務用 Skype Server 使用者**] 頁面上, 您所選取的使用者會顯示在 [**使用者**] 顯示幕中。 在 [**指派使用者至池中**] 清單中, 選取使用者應該駐留的伺服器。
    
    以下是您可以用來設定物件的選項清單。
    
    - **產生使用者的 SIP URI**
    
    - **$**
    
    - **行 URI**
    
    - **會議原則**
    
    - **用戶端版本原則**
    
    - **PIN 原則**
    
    - **外部存取原則**
    
    - **存檔原則**
    
    - **位置原則**
    
    - **用戶端原則**
    
    若要測試基本功能, 請在 [**產生使用者的 SIP URI** ] 設定 ([設定] 中的其他選項使用預設設定) 中, 選取您想要的選項, 然後按一下 [**啟用**], 如圖所示。
    
     ![在 [控制台] 中啟用使用者。](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. 隨即會顯示 [摘要] 頁面, 其中顯示 [**已啟用**] 欄中的核取記號, 表示使用者已設定。 [ **SIP 位址**] 欄會顯示使用者登入設定所需的位址。
    
     ![已將使用者新增至商務用 Skype Server 的 [控制台]。](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. 將一位使用者登入加入網域的電腦, 以及另一個使用者到網域中的另一部電腦。
    
13. 在兩個用戶端電腦上安裝商務用 Skype 用戶端, 然後確認這兩個使用者都可以登入商務用 Skype Server, 並可互相傳送即時消息。
    

