---
title: 在商務用 Skype 中建立或修改通話寄存軌道的範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: 在商務用 Skype Server Enterprise Voice 中建立或修改通話公園軌道的範圍表。
ms.openlocfilehash: 77be47597e5bbb674719ac2b3192efdf4217a3dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190429"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a>在商務用 Skype 中建立或修改通話寄存軌道的範圍

在商務用 Skype Server Enterprise Voice 中建立或修改通話公園軌道的範圍表。

通話寄存使用 [軌道式] 進行停車通話。 您必須先設定 [通話公園軌道] 表格, 才能停止並取回通話。 您必須指定貴組織將針對停車通話保留的延伸數位 (軌道式) 範圍, 並指定哪個呼叫駐留器池處理每個範圍, 以定義這些範圍的路線。 當您定義軌道範圍時, 目標是有足夠的 [軌道式], 所以任何一個軌道都不會過快地重複使用, 但卻不是您要限制使用者或其他服務可用的延伸數目。 您可以為部署通話駐留應用程式的每個商務用 Skype 伺服器池建立多個通話駐留軌道範圍。 每個呼叫公園的軌道範圍都必須有全域唯一的名稱, 以及一組唯一的延伸。

> [!IMPORTANT]
> 軌道範圍通常會包含100或更少的軌道式。 每個範圍都可以大許多, 只要它小於每個範圍的10000軌道式, 且每個池子的每個泳池不超過50000的 [軌道式]。 如果範圍太小, 則會更快速地重複使用 [軌道式]。

針對您的軌道範圍, 使用虛擬延伸組塊 (沒有指派使用者或電話的延伸)。

> [!NOTE]
> 在 [通話駐留軌道] 表格中, 將直向內撥 (所做的) 號碼指派為軌道編號, 不受支援。

使用下列其中一個程式來建立或修改通話寄存軌道的範圍。

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>使用商務用 Skype Server [控制台] 來建立或修改停車通話的數位範圍

1. 以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊, 請參閱**委派設定許可權**。

2. 開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。

3. 在左側導覽列中, 按一下 [**語音功能**], 然後按一下 [**通話駐留**]。

4. 在 [**通話駐留**] 頁面上, 執行下列其中一項操作:

   - 若要建立新的軌道範圍, 請按一下 [**新增**]。 在 [**名稱**] 中, 輸入此數位範圍的識別名稱。

     > [!NOTE]
     > 在您將軌道範圍提交至資料庫之後, 您就無法變更此名稱。

   - 若要修改現有的軌道範圍, 請在 [搜尋] 欄位中輸入所有或部分的軌道範圍名稱。 在 [軌道式] 的結果清單中, 按一下您想要的軌道, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。

5. 在 [第一個**數位範圍**] 欄位中, 輸入此通話公園軌道的延伸範圍起始編號, 然後在第二個 [**數位範圍**] 欄位中, 輸入範圍的結束數位。 請注意:

   - 該範圍的起始號碼必須小於或等於範圍的結束號碼。

   - 該範圍的起始號碼值的長度必須等於範圍的結束號碼值長度。

   - 軌道範圍必須是唯一的。 此範圍不得與其他任何範圍重疊。

   - 如果軌道範圍是以字元\*或 # 開頭, 則範圍必須大於100。

   - 有效值: 必須符合正則運算式字串 ([\\* | #]？ [1-9] \d{0,7}) |([1-9] \d{0,8})。 這表示值必須是以字元\*或 # 或數位1到 9 (第一個字元不能是零) 開頭的字串。 如果第一個字元是\*或 #, 則下列字元必須是1到9的數位 (不能是零)。 後續字元可以是從0到9的任何數位, 最多可達七個其他字元 (例如,\*"#6000"、\*"92000"、"95551212" 和 "915551212")。 如果第一個字元不\*是或 #, 則第一個字元必須是數位1到 9 (不能是零), 後面再加上八個字元 (例如, "915551212", "41212", "300")。

   - 每個池子不應超過總計50000的 [軌道式]。 每個軌道範圍通常會包含100或更少的軌道式, 但只要包含超過10000的軌道式, 就能更大。 例如，與其指定起始號碼 7000000 與結束號碼 8000000，請考慮指定起始號碼 7000000 與結束號碼 7000100。

6. 在 [**目的地伺服器的 FQDN**] 中, 按一下主持通話駐留應用程式之應用程式服務的完整功能變數名稱 (FQDN) 或服務識別碼。 在軌道範圍內由 start 編號和結束編號所指定範圍內的所有來電都會路由到這個伺服器或池子。

7. 按一下 [認可]****。

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>若要使用商務用 Skype Server Management Shell 來建立或修改停車通話的數位範圍

1. 登入商務用 Skype Server Management Shell 的電腦是以 RTCUniversalServerAdmins 群組的成員或必要的使用者權利來安裝, 如**委派設定許可權**中所述。

2. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。

3. 使用 [**新-CsCallParkOrbit** ] 建立新的軌道編號範圍。 使用 [**設定] CsCallParkOrbit**來修改現有的軌道編號範圍。

    在命令列上執行:

   ```
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    例如：

   ```
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    下列範例顯示如何修改現有的軌道範圍中的數位,

   ```
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a>另請參閱

[新-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[刪除通話公園軌道範圍](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
