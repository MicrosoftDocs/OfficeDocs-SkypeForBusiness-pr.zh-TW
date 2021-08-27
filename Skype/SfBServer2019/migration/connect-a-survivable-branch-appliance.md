---
title: 連線 Survivable Branch Appliance
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 每個 Survivable Branch 裝置 (SBA) 都會與前端集區相關聯，以充當 SBA 的備份註冊機。 當前端集區遷移至商務用 Skype Server 2019 時，在升級集區時，必須解除 SBA 與前端集區的關聯，將集區遷移至商務用 Skype Server 2019 後，即可將 SBA 重新與已升級的前端集區產生關聯。 這包括在拓撲產生器中從舊版拓撲刪除 SBA，然後將 SBA 新增至商務用 Skype Server 2019 拓撲。 位於舊版 SBA 的使用者必須先移至另一個前端集區，然後才能從拓撲中移除 SBA。 將 SBA 新增至商務用 Skype Server 2019 拓撲之後，就可以將這些使用者移回 SBA。 這些步驟的摘要如下：
ms.openlocfilehash: c431451503efd23039b4c358488bfc5bce03ba65
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588045"
---
# <a name="connect-a-survivable-branch-appliance"></a>連線 Survivable Branch Appliance

每個 Survivable Branch 裝置 (SBA) 都與一部前端集區相關聯，以充當 SBA 的備份註冊機。 當前端集區遷移至商務用 Skype Server 2019 時，當集區升級時，SBA 必須與前端集區解除關聯。 將集區遷移至商務用 Skype Server 2019 之後，SBA 可以與已升級的前端集區重新產生關聯。 這包括在拓撲產生器中從舊版拓撲刪除 SBA，然後將 SBA 新增至商務用 Skype Server 2019 拓撲。 位於舊版 SBA 的使用者必須先移至另一個前端集區，然後才能從拓撲中移除 SBA。 將 SBA 新增至商務用 Skype Server 2019 拓撲之後，這些使用者便可移回 SBA。 這些步驟的摘要如下：
  
1. 將駐留在舊版 SBA 的分支使用者移至另一個前端集區。
    
2. 從舊版拓撲中移除 SBA，以中斷現有前端集區的備份註冊機的連線。
    
3. 將 SBA 新增至商務用 Skype Server 2019 拓撲，並將這個新的前端集區設定為備份註冊機。 
    
4. 將分支使用者移至新的商務用 Skype Server 2019 SBA。
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>將舊版 SBA 分支網站新增至您的拓撲

1. 開啟 **拓撲** 產生器。
    
2. 在左窗格中，以滑鼠右鍵按一下 [ **分支網站**]，然後按一下 [ **新增分支網站**]。
    
3. 在 [ **定義新的分支網站** ] 對話方塊中，按一下 [ **名稱**]，然後輸入分支網站的名稱。
    
4.  (選用) 按一下 [ **描述**]，然後為分支網站輸入有意義的描述。
    
5. 按 **[下一步]**。
    
6.  (選用) 在下一個 [ **定義新的分支網站** ] 對話方塊中，執行下列其中一項： 
    
    1. 按一下 [ **城市**]，然後輸入分支網站所在位置的城市名稱。
    
    2. 按一下 [ **省/地區**]，然後輸入分支網站所在位置的省或地區名稱。
    
    3. 按一下 [ **國家/地區碼**]，然後輸入分支網站所在國家/地區的兩位數呼叫碼。
    
7. 按 **[下一步]**，然後在此網站使用 Survivable 分支裝置或伺服器時，請務必清除 [ **當此嚮導關閉時開啟新的 Survivable 嚮導]** 核取方塊。 按一下 **[完成]**。
    
8. 若要將舊版 SBA 關聯至商務用 Skype Server 2019 前端集區：
    
    1. 展開已經建立的分支網站。 
    
    2. 以滑鼠右鍵按一下 [舊版版本]，然後按一下 [ **新增**]。
    
    3. 按一下 [ **Survivable 分支裝置**]。
    
9. 依照嚮導中開啟的指示進行。 如需嚮導專案的詳細資訊，請參閱    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](/previous-versions/office/lync-server-2013/lync-server-2013-define-a-survivable-branch-appliance-or-server). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Survivable 分支裝置只可與監控存放區產生關聯。 
  
10. 如果您未使用此網站的 Survivable 分支裝置或伺服器，請清除 [在 **此嚮導關閉時開啟新的 Survivable 嚮導]** 核取方塊，然後按一下 **[完成]**。
    
11. 針對您要新增至拓撲的每一個分支網站重複上述步驟。
