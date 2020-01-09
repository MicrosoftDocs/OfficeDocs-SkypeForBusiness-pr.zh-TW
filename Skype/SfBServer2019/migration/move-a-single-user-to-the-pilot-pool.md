---
title: 將單一使用者移至 [試驗] 池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 您可以使用商務用 Skype Server 2019 控制台或商務用 Skype Server 2019 管理命令介面，從舊版池中將使用者移至您的商務用 skype Server 2019 試用版文件庫。 在下列範例中，在 [註冊機構池] 欄中，pool01.contoso.net 是舊版池，且所有六個使用者都已連線到此池。 使用下列程式將使用者移至商務用 Skype 2019 Server 2019 的 [商務用 Skype] 伺服器的 [控制台] 和 [商務用 Skype 伺服器管理] 命令介面。
ms.openlocfilehash: 8964dd3dc868c22cd14389ba70b88d32b6bd145a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40988958"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>將單一使用者移至 [試驗] 池

您可以使用商務用 Skype Server 2019 控制台或商務用 Skype Server 2019 管理命令介面，從舊版池中將使用者移至您的商務用 skype Server 2019 試用版文件庫。 在下列範例中，在 [**註冊機構池**] 欄中， **pool01.contoso.net**是舊版池，且所有六個使用者都已連線到此池。 使用下列程式將使用者移至商務用 Skype 2019 Server 2019 的 [商務用 Skype] 伺服器的 [控制台] 和 [商務用 Skype 伺服器管理] 命令介面。 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>使用商務用 Skype Server 2019 [控制台] 移動使用者
  
1. 使用 RTCUniversalServerAdmins 群組成員的帳戶或 CsAdministrator 或 CsUserAdministrator 系統管理角色的成員登入前端伺服器。
    
2. 開啟**商務用 Skype Server**的 [控制台]。
    
3. 按一下 [**使用者**]，按一下 [**搜尋**]，然後按一下 [**尋找**]。
    
4. 選取您要移至商務用 Skype Server 2019 文件庫的使用者。 在這個範例中，我們將移動 [使用者 Sara Davis]。
    
5. 在 [**動作**] 功能表上，選取 [**將選取的使用者移至資源庫**]。
    
6. 從下拉式清單中，選取 [商務用 Skype Server 2019] 池。
    
7. 按一下 [**動作**]，然後按一下 [**將選取的使用者移至資源庫**]。 按一下 [確定]****。
  
8. 確認使用者的 [**註冊機構池**] 欄現在包含商務用 Skype Server 2019 pool，這表示使用者已順利移動。 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>使用商務用 Skype Server 2019 管理命令介面來移動使用者

1. 開啟商務用 Skype Server 管理命令介面。
    
2. 在命令列中，輸入下列內容： 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. 接著，在命令列中輸入下列內容： 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. **RegistrarPool**身分識別現在會指向商務用 Skype Server 2019 池。 此身分識別的狀態會確認使用者已順利移動。 

    > [!NOTE]
    > 如需**move-csuser** Cmdlet 的詳細資料，請執行： **Get-help move-csuser-詳細**資訊
  

