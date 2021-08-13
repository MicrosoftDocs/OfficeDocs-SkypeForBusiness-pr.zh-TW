---
title: 將多個使用者移至試驗集區
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 您可以使用商務用 Skype Server 2019 控制台或商務用 Skype Server 2019 管理命令介面，將多個使用者從舊版集區移至商務用 Skype Server 2019 試驗集區。
ms.openlocfilehash: 689886060f14a47e82865a2ed66bfc3ff495dfdc3b1f44e6c5674294b4d21eb9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300649"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>將多個使用者移至試驗集區

您可以使用商務用 Skype Server 2019 控制台或商務用 Skype Server 2019 管理命令介面，將多個使用者從舊版集區移至商務用 Skype Server 2019 試驗集區。

 **In this article**
  
[使用商務用 Skype Server 2019 控制台移動多位使用者](#sectionSection0)
  
[使用商務用 Skype Server 2019 管理命令介面移動多位使用者](#sectionSection1)
  
[若要使用商務用 Skype Server 2019 管理命令介面同時移動所有使用者](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>使用商務用 Skype Server 2019 控制台移動多位使用者
<a name="sectionSection0"> </a>

1. 開啟商務用 Skype Server 控制台]。
    
2. 按一下 [ **使用者**]，按一下 [ **搜尋**]，然後按一下 [ **尋找**]。
    
3. 選取兩個要移至商務用 Skype Server 2019 集區的使用者。 在此範例中，我們會將使用者移 Chen 陽和聖誕老人聖誕 Hansen。
    
     ![將使用者移至特定的註冊集區](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. 從 [ **動作** ] 功能表中，選取 [ **將選取的使用者移至集** 區]。
    
5. 從下拉式清單中，選取 [商務用 Skype Server 2019 集區]。
    
6. 按一下 [動作]，然後按一下 [將選取的使用者移至集區]。 按一下 ****[確定]。
    
     ![移動使用者、目的地註冊集區] 對話方塊](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. 確認使用者的 [**報名者集** 區] 欄現在包含商務用 Skype Server 2019 集區，這表示使用者已順利移動。 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>使用商務用 Skype Server 2019 管理命令介面移動多位使用者
<a name="sectionSection1"> </a>

1. 開啟商務用 Skype Server 2019 管理命令介面。 
    
2. 在命令列中輸入下列命令，並將 **User1** 和 **使用者2取代為您** 想要移動的特定使用者名稱，然後將 **pool_FQDN** 取代為目的地集區的名稱。 在此範例中，我們會移動使用者 Hao Chen 和 Katie 約旦。 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![PowerShell Get-CsUser Cmdlet 的範例](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. 在命令列輸入下列命令： 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. **註冊機構集** 區的身分識別現在應該指向您在上一個步驟中 **pool_FQDN** 指定的集區。 這個身分識別的出現表示已成功移動使用者。 重複步驟以驗證使用者 **2 是否已** 移動。 
    
     ![PowerShell Get-UsUser 識別指令程式的輸出](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>若要使用商務用 Skype Server 2019 管理命令介面同時移動所有使用者
<a name="sectionSection2"> </a>

在此範例中，所有使用者都已傳回舊版集區 (pool01.contoso.net) 。 使用商務用 Skype Server 2019 管理命令介面，我們會同時將所有使用者同時移至商務用 Skype Server 2019 集區 (pool02.contoso.net) 。
  
1. 開啟商務用 Skype Server 2019 管理命令介面。
    
2. 在命令列輸入下列命令： 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![在管理命令介面中 PowerShell Cmdlet 及結果](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. 針對其中一位試驗使用者執行 **Get-CsUser** 。 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. 每個使用者的 **註冊區集** 區身分識別會指向您在上一個步驟中 pool_FQDN 指定為的集區。 這個身分識別的出現表示已成功移動使用者。 
    
5. 此外，我們可以在商務用 Skype Server 2019 控制台中查看使用者清單，並確認 [註冊機集區] 值現在是否指向商務用 Skype Server 2019 集區。
    
     ![商務用 Skype Server 2019 控制台使用者清單](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

