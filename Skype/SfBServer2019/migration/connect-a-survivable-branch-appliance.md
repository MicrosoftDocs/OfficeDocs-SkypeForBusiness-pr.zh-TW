---
title: 連線 Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 每個 Survivable 分支裝置（SBA）都與一個前端池相關聯，可充當 SBA 的備份註冊機構。 當您將前端池移至商務用 Skype Server 2019 時，當池已升級至商務用 Skype Server 2019 之後，就必須從 SBA 中解除連線，SBA 才能與升級的前 E 重新關聯nd pool。 這涉及從拓撲產生器中的舊版拓撲刪除 SBA，然後將 SBA 新增至商務用 Skype Server 2019 拓撲。 必須先將駐留在舊版 SBA 的使用者移到另一個前端池，然後才能從拓撲結構中移除 SBA。 將 SBA 新增至商務用 Skype Server 2019 拓撲之後，這些使用者就可以移回 SBA。 下列步驟摘要如下所示：
ms.openlocfilehash: daeb061936ece02767e3299d2358d8e16ba09218
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813731"
---
# <a name="connect-a-survivable-branch-appliance"></a>連線 Survivable Branch Appliance

每個 Survivable 分支裝置（SBA）都與一個作為 SBA 備份註冊機構的前端池相關聯。 當頂層池遷移到商務用 Skype Server 2019 時，必須在池升級時解除與前端池中的 SBA。 在將池遷移到商務用 Skype Server 2019 之後，SBA 可以與已升級的前端池重新關聯。 這涉及從拓撲產生器中的舊版拓撲刪除 SBA，然後將 SBA 新增至商務用 Skype Server 2019 拓撲。 必須先將駐留在舊版 SBA 的使用者移到另一個前端池，然後才能從拓撲結構中移除 SBA。 將 SBA 新增至商務用 Skype Server 2019 拓撲之後，這些使用者就可以移回 SBA。 下列步驟摘要如下所示：
  
1. 將駐留在舊版 SBA 的分支使用者移至另一個前端池。
    
2. 從舊版拓撲中移除 SBA，將現有的前端池與備份註冊機構中斷連線。
    
3. 在商務用 Skype Server 2019 拓撲中新增 SBA，並將這個新的 [前端] 池設定為備份註冊機構。 
    
4. 將分支使用者移至新的商務用 Skype Server 2019 SBA。
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>將舊版 SBA 分支網站新增至您的拓撲

1. 開啟**拓撲**建立器。
    
2. 在左窗格中，以滑鼠右鍵按一下 [**分支網站**]，然後按一下 [**新增分支網站**]。
    
3. 在 [**定義新分支網站**] 對話方塊中，按一下 [**名稱**]，然後輸入分支網站的名稱。
    
4. 可選按一下 [**描述**]，然後為分支網站輸入有意義的描述。
    
5. 按一下 **[下一步]**。
    
6. 可選在 [下一步**定義分支網站**] 對話方塊中，執行下列任何一項操作： 
    
    1. 按一下 [**城市**]，然後輸入分支網站所在城市的名稱。
    
    2. 按一下 [**狀態/地區**]，然後輸入分支網站所在的狀態或地區名稱。
    
    3. 按一下 [**國家/地區碼**]，然後輸入分支網站所在國家/地區的兩位數電話號碼。
    
7. 按一下 **[下一步]**，然後，如果您是在此網站使用 Survivable 分支裝置或伺服器，請務必清除 [**當此嚮導關閉時，開啟新的 Survivable 嚮導]** 核取方塊。 按一下 **[完成]**。
    
8. 若要將舊版 SBA 與商務用 Skype Server 2019 （前端端池）關聯：
    
    1. 展開已建立的分支網站。 
    
    2. 以滑鼠右鍵按一下舊版版本，然後按一下 [**新增**]。
    
    3. 按一下 [ **Survivable 分支裝置**]。
    
9. 依照嚮導中開啟的指示進行。 如需有關嚮導專案的資訊，請參閱    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Survivable 分支裝置只能與監視存放區建立關聯。 
  
10. 如果您不是在此網站使用 Survivable 分支裝置或伺服器，請清除 [在**關閉此嚮導時開啟新的 Survivable 嚮導]** 核取方塊，然後按一下 **[完成**]。
    
11. 針對您要新增到拓撲結構中的每個分支網站，重複上述步驟。
    

