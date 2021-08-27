---
title: 將單一使用者移至試驗集區
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
description: 您可以使用商務用 Skype Server 2019 控制台或商務用 Skype Server 2019 管理命令介面，將使用者從舊版集區移至商務用 Skype Server 2019 試驗集區。 在下列範例中，在 [報名者集區] 欄中，pool01.contoso.net 為舊版集區，所有六個使用者都連接至此集區。 使用下列程式，使用商務用 Skype Server 2019 控制台和商務用 Skype Server 管理命令介面，將使用者移至商務用 Skype Server 2019 集區。
ms.openlocfilehash: 987eeec96d28257b995b5e27ce02e282df019980
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596157"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>將單一使用者移至試驗集區

您可以使用商務用 Skype Server 2019 控制台或商務用 Skype Server 2019 管理命令介面，將使用者從舊版集區移至商務用 Skype Server 2019 試驗集區。 在下列範例中，在 [ **報名者集** 區] 欄中， **pool01.contoso.net** 為舊版集區，所有六個使用者都連接至此集區。 使用下列程式，使用商務用 Skype Server 2019 控制台和商務用 Skype Server 管理命令介面，將使用者移至商務用 Skype Server 2019 集區。 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>使用商務用 Skype Server 2019 控制台移動使用者
  
1. 使用 RTCUniversalServerAdmins 群組的成員帳戶、CsAdministrator 成員帳戶或 CsUserAdministrator 系統管理角色的成員帳戶，登入前端伺服器。
    
2. 開啟 **商務用 Skype Server 控制台**]。
    
3. 按一下 [ **使用者**]，按一下 [ **搜尋**]，然後按一下 [ **尋找**]。
    
4. 選取您要移至商務用 Skype Server 2019 集區的使用者。 在這個範例中，將移動使用者 Sara Davis。
    
5. 在 [執行] 功能表上，選取 [將選取的使用者移至集區]。
    
6. 從下拉式清單中，選取 [商務用 Skype Server 2019 集區]。
    
7. 按一下 [動作]，然後按一下 [將選取的使用者移至集區]。 按一下 [確定]。
  
8. 確認使用者的 [**報名者集** 區] 欄現在包含商務用 Skype Server 2019 集區，這表示使用者已順利移動。 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>使用商務用 Skype Server 2019 管理命令介面移動使用者

1. 開啟 [商務用 Skype Server 管理命令介面]。
    
2. 在命令列輸入下列命令： 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. 接著，在命令列輸入下列命令： 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. **RegistrarPool** 身分識別現在會指向商務用 Skype Server 2019 集區。 這個身分識別的出現表示已成功移動使用者。 

    > [!NOTE]
    > 如需 **Get-CsUser** Cmdlet 的詳細資訊，請執行： **Get-Help Get-CsUser 詳細**
  

