---
title: 在商務用 Skype 中建立或修改群組呼叫裝貨號碼範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: 在商務用 Skype Server Enterprise Voice 中建立或修改群組呼叫挑選號碼範圍。
ms.openlocfilehash: 98fc59f12165e6299fafc5ed79797e6d25d151e3
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767876"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>在商務用 Skype 中建立或修改群組呼叫裝貨號碼範圍

在商務用 Skype Server Enterprise Voice 中建立或修改群組呼叫挑選號碼範圍。

[群組呼叫挑選] 是以 [通話駐留] 應用程式為基礎。 當您部署群組呼叫挑選時，您必須設定 [通話公園軌道] 表格，並將指定為 [呼叫挑選] 群組號碼的電話號碼範圍。 這些群組號碼是使用者撥打電話給另一個使用者所撥打的電話號碼。

如同通話公園軌道編號，呼叫挑選群組的號碼必須是沒有指派給他們的使用者或電話的虛擬延伸。 您在其中部署 [群組呼叫挑選] 的每個前端池都可以有一或多個呼叫挑選群組編號範圍。 群組編號範圍在您的部署中必須是全域唯一的，而且必須指派為**GroupPickup**類型。

使用下列程式來建立或修改 [通話駐留軌道] 表格中的 [通話挑選] 群組編號範圍。

> [!NOTE]
> 您必須使用商務用 Skype Server Management Shell 來建立、修改、移除及查看 [通話公園軌道] 表格中的 [群組呼叫挑選號碼] 範圍。 在商務用 Skype Server [控制台] 中無法使用 [群組呼叫挑選號碼] 範圍。

呼叫挑選群組編號範圍必須符合下列規則：

- 該範圍的起始號碼必須小於或等於範圍的結束號碼。

- 該範圍的起始號碼值的長度必須等於範圍的結束號碼值長度。

- 號碼範圍必須是唯一的。此範圍不得與其他任何範圍重疊。

- 如果數位範圍是以字元\*或 # 開頭，則範圍必須大於100。

- 有效值：必須符合正則運算式字串（[\\* | #]？ [1-9] \d{0,7}） |（[1-9] \d{0,8}）。 這表示值必須是以字元\*或 # 或數位1到9（第一個字元不能是零）開頭的字串。 如果第一個字元是\*或 #，則下列字元必須是1到9的數位（不能是零）。 後續字元可以是從0到9的任何數位，最多可達七個其他字元（例如，\*"#6000"、\*"92000"、"95551212" 和 "915551212"）。 如果第一個字元不\*是或 #，則第一個字元必須是數位1到9（不能是零），後面再加上八個字元（例如，"915551212"，"41212"，"300"）。

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>建立或修改通話挑選群組範圍

1. 登入商務用 Skype Server Management Shell 的電腦是以 RTCUniversalServerAdmins 群組的成員或必要的使用者權利來安裝，如**委派設定許可權**中所述。

2. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。

3. 使用 [**新-CsCallParkOrbit** ] 建立呼叫挑選群組編號的新範圍。 使用 [**設定] CsCallParkOrbit**來修改現有的電話挑選號碼範圍。

    在命令列上執行：

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    例如：

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    下列範例示範如何將通話駐留軌道式的數位範圍變更為呼叫挑選群組。

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > 如果您最初指定的類型不正確，且尚未使用群組範圍，請使用這個 Cmdlet 來變更指派給數位範圍的類型。 如果您將數位範圍從 CallPark 變更為 GroupPickup 或反之，而數位範圍已在使用中，則通話駐留或群組通話拾取將會停止處理該數位範圍。 例如，如果您將數位範圍從 CallPark 變更為 GroupPick，則通話駐留應用程式將無法再使用該轉到寄存通話的範圍。

## <a name="see-also"></a>另請參閱

[新-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[刪除通話公園軌道範圍](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
