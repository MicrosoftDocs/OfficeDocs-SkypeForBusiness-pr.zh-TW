---
title: 在商務用 Skype 中建立或修改通話駐留軌道範圍
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: 在商務用 Skype Server 企業語音中建立或修改通話駐留軌道範圍表。
ms.openlocfilehash: 3962ecf42e704b09f3f28451be667fe714ce4817
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745379"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a>在商務用 Skype 中建立或修改通話駐留軌道範圍

在商務用 Skype Server 企業語音中建立或修改通話駐留軌道範圍表。

通話駐留使用軌道進行停車通話。 您必須先設定通話駐留軌道表格，使用者才能駐留及取回通話。 您必須指定您的組織將保留用於停車通話的分機號碼範圍 (的軌道式) ，並指定處理每個範圍的通話駐留集區，以定義這些範圍的路由。 當您定義軌道範圍時，目標是具有足夠的軌道，因此，任何一個軌道都不會很快地重複使用，但卻不是這麼多的軌道來限制使用者或其他服務可使用的延伸數目。 您可以針對部署通話駐留應用程式的每個商務用 Skype Server 集區，建立多個通話駐留軌道範圍。 每個通話駐留軌道範圍必須具有全域唯一名稱和一組唯一的延伸。

> [!IMPORTANT]
> 軌道範圍通常會包含100或更少的軌道。 每個範圍都可以大量增加，只要小於每個範圍的10000軌道的最大值，且每個集區的每個集數目小於50000的軌道。 如果範圍太小，則軌道的重複使用速度變快。

使用虛擬分機區塊 (未獲指派使用者或電話的分機) 用於軌道範圍。

> [!NOTE]
> 指派直接向內撥號 (，不支援通話駐留軌道表格中的軌道編號) 數位。

使用下列其中一個程序來建立或修改通話駐留軌道範圍。

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>若要使用商務用 Skype Server 控制台建立或修改駐留通話的號碼範圍

1. 以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱＜**Delegate Setup Permissions**＞。

2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。

3. 在左導覽列中，依序按一下 **[語音功能]**、**[通話駐留]**。

4. 在 **[通話駐留]** 頁面上，執行下列其中一項動作：

   - 若要建立新的軌道範圍，可按一下 **[新增]**。在 **[名稱]** 中，輸入此號碼範圍的識別名稱。

     > [!NOTE]
     > 當您將軌道範圍認可至資料庫之後，就無法變更此名稱。

   - 若要修改現有的軌道範圍，可在搜尋欄位中輸入軌道範圍的所有或部分名稱。在軌道的結果清單中，按一下您想要的軌道，接著依序按一下 **[編輯]** 及 **[顯示詳細資料]**。

5. 在第一個 **[號碼範圍]** 欄位中，輸入此項通話駐留軌道分機號碼範圍的開頭號碼，並在第二個 **[號碼範圍]** 欄位中，輸入該範圍的結束號碼。 請注意：

   - 該範圍的起始號碼必須小於或等於範圍的結束號碼。

   - 該範圍的起始號碼值的長度必須等於範圍的結束號碼值長度。

   - 軌道範圍必須是唯一的。此範圍不得與其他任何範圍重疊。

   - 如果軌道範圍的開頭為字元 \* 或 #，則範圍必須大於100。

   - 有效的值：必須符合正則運算式字串 ( [ \\ * | #]？ [1-9] \d {0,7}) | ( [1-9] \d {0,8}) 。 這表示值必須是以字元 \* 或 # 或數位1到9為開頭的字串。 (第一個字元不能是零) 。 如果第一個字元是 \* 或 #，下列字元必須是1到9的數位， (不能是零) 。 後續字元可以是0到9的任何數位，最多可以有七個其他字元 (例如，"#6000"、" \* 92000"、" \* 95551212" 和 "915551212" ) 。 如果第一個字元不是 \* 或 #，則第一個字元必須是1到)  (9 的數位，然後是0到9的數位，都是0到 9 (例如，"915551212"，"41212"，"300" ) 。

   - 每個集區的軌道總數不得超過 50,000 個。每個軌道範圍通常會涵蓋 100 個以下的軌道，但只要總數不超過 10,000 個軌道，可以大一些。例如，與其指定開頭號碼 7000000 與結束號碼 8000000，請考慮指定開始號碼 7000000 與結束號碼 7000100。

6. 在 **[目的地伺服器的 FQDN]** 中，按一下裝載通話保留應用程式的應用程式服務之完整網域名稱 (FQDN) 或服務 ID。保留給軌道範圍中由開始號碼與結束號碼所指定之範圍內的號碼的所有通話，將會轉接至此伺服器或集區。

7. 按一下 **[認可]**。

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>若要使用商務用 Skype Server 管理命令介面來建立或修改駐留通話的號碼範圍

1. 以 **委派安裝許可權** 中所述，以 RTCUniversalServerAdmins 群組成員的身分或必要使用者權限的方式，登入安裝商務用 Skype Server 管理命令介面的電腦。

2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。

3. 使用 **New-CsCallParkOrbit** 來建立新的軌道號碼範圍。使用 **Set-CsCallParkOrbit** 來修改現有的軌道號碼範圍。

    在命令列中執行：

   ```powershell
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    例如：

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    下列範例示範如何修改現有軌道範圍中的號碼，

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a>另請參閱

[新 Get-cscallparkorbit](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Get-cscallparkorbit](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[刪除通話駐留軌道範圍](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)