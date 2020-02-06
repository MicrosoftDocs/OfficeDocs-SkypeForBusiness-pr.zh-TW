---
title: 將多個使用者移至 [試驗] 池
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
description: 您可以使用商務用 Skype Server 2019 控制台或商務用 Skype Server 2019 管理命令介面，從舊版池中將多個使用者移至您的商務用 skype Server 2019 試用版。
ms.openlocfilehash: 62cf398a55be9c17526e8d607642db236ae57a3f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813271"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>將多個使用者移至 [試驗] 池

您可以使用商務用 Skype Server 2019 控制台或商務用 Skype Server 2019 管理命令介面，從舊版池中將多個使用者移至您的商務用 skype Server 2019 試用版。

 **本文內容**
  
[使用商務用 Skype Server 2019 的 [控制台] 移動多個使用者](#sectionSection0)
  
[使用商務用 Skype Server 2019 管理命令介面來移動多位使用者](#sectionSection1)
  
[使用商務用 Skype Server 2019 管理命令介面，同時移動所有使用者](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>使用商務用 Skype Server 2019 的 [控制台] 移動多個使用者
<a name="sectionSection0"> </a>

1. 開啟商務用 Skype Server 的 [控制台]。
    
2. 按一下 [**使用者**]，按一下 [**搜尋**]，然後按一下 [**尋找**]。
    
3. 選取兩個您要移至商務用 Skype Server 2019 池的使用者。 在這個範例中，我們會將使用者唐到 [陽入] 和 [Claus Hansen]。
    
     ![將使用者移至特定登錄器集區](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. 從 [**動作**] 功能表中，選取 [**將選取的使用者移至資源庫**]。
    
5. 從下拉式清單中，選取 [商務用 Skype Server 2019] 池。
    
6. 按一下 [**動作**]，然後按一下 [**將選取的使用者移至資源庫**]。 按一下 [確定]****。
    
     ![移動使用者，[目的地登錄器集區] 對話方塊](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. 確認使用者的 [**註冊機構池**] 欄現在包含商務用 Skype Server 2019 pool，這表示使用者已順利移動。 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>使用商務用 Skype Server 2019 管理命令介面來移動多位使用者
<a name="sectionSection1"> </a>

1. 開啟商務用 Skype Server 2019 管理命令介面。 
    
2. 在命令列中，輸入下列內容，並將 [ **User1** **] 和 [** 使用者 2] 替換為您想要移動的特定使用者名稱，然後將**pool_FQDN**取代為目的地池的名稱。 在這個範例中，我們會將使用者 Hao 唐和她約旦。 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![PowerShell Get-CsUser Cmdlet 的範例](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. 在命令列中，輸入下列內容： 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. **註冊機構池**標識現在應該指向您在上一個步驟中指定為**pool_FQDN**的池。 此身分識別的狀態會確認使用者已順利移動。 重複步驟，**確認已移動到您的操作**者。 
    
     ![PowerShell Get-UsUser -Identity Cmdlet 的輸出](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>使用商務用 Skype Server 2019 管理命令介面，同時移動所有使用者
<a name="sectionSection2"> </a>

在這個範例中，所有使用者都已回到舊版資源（pool01.contoso.net）。 使用商務用 Skype Server 2019 管理命令介面，我們會同時將所有使用者移至商務用 Skype Server 2019 （pool02.contoso.net）。
  
1. 開啟商務用 Skype Server 2019 管理命令介面。
    
2. 在命令列中，輸入下列內容： 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![管理命令介面中的 PowerShell Cmdlet 與結果](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. 針對其中一個試驗使用者執行**move-csuser** 。 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. 每個使用者的**註冊機構池**標識現在會指向您在上一個步驟中指定為**pool_FQDN**的池。 此身分識別的狀態會確認使用者已順利移動。 
    
5. 此外，我們還可以在商務用 Skype Server 2019 的 [控制台] 中查看使用者清單，並確認 [註冊機構] 池值現在會指向 [商務用 Skype Server 2019] 池。
    
     ![商務用 Skype Server 2019 的 [控制台] 使用者清單](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

