---
title: 在商務用 Skype 中建立或修改群組呼叫收取號碼範圍
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
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: 在商務用 Skype Server 企業語音中建立或修改群組呼叫收取號碼範圍。
ms.openlocfilehash: 661efa69d7c7a3264872c4d83b94372d8d9951f1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60738919"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>在商務用 Skype 中建立或修改群組呼叫收取號碼範圍

在商務用 Skype Server 企業語音中建立或修改群組呼叫收取號碼範圍。

群組呼叫收取是以通話駐留應用程式為基礎。 當您部署群組呼叫收取時，您必須使用指定為呼叫收取群組號碼的電話號碼範圍來設定通話駐留軌道表格。 這些群組號碼是使用者在撥打其他使用者所撥打之來電時所撥打的號碼。

與通話駐留軌道號碼類似，來電收取群組數目必須是未獲指派使用者或電話的虛擬分機。 您部署群組呼叫收取的每個前端集區，都可以有一或多個呼叫收取群組號碼範圍。 群組號碼範圍在您的部署中必須是全域唯一的，而且必須被指派為 **GroupPickup** 類型。

使用下列程式可建立或修改通話駐留軌道表格中的呼叫收取群組號碼範圍。

> [!NOTE]
> 您必須使用商務用 Skype Server 管理命令介面，來建立、修改、移除和查看「通話駐留軌道」表格中的群組呼叫收取號碼範圍。 在商務用 Skype Server 控制台中無法使用群組呼叫收取號碼範圍。

呼叫收取群組號碼範圍必須符合下列規則：

- 該範圍的起始號碼必須小於或等於範圍的結束號碼。

- 該範圍的起始號碼值的長度必須等於範圍的結束號碼值長度。

- 號碼範圍必須是唯一的。 此範圍不得與其他任何範圍重疊。

- 如果號碼範圍開頭為字元 \* 或 #，則範圍必須大於100。

- 有效的值：必須符合正則運算式字串 ( [ \\ * | #]？ [1-9] \d {0,7}) | ( [1-9] \d {0,8}) 。 這表示值必須是以字元 \* 或 # 或數位1到9為開頭的字串。 (第一個字元不能是零) 。 如果第一個字元是 \* 或 #，下列字元必須是1到9的數位， (不能是零) 。 後續字元可以是0到9的任何數位，最多可以有七個其他字元 (例如，"#6000"、" \* 92000"、" \* 95551212" 和 "915551212" ) 。 如果第一個字元不是 \* 或 #，則第一個字元必須是1到)  (9 的數位，然後是0到9的數位，都是0到 9 (例如，"915551212"，"41212"，"300" ) 。

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>若要建立或修改呼叫收取群組範圍

1. 以 **委派安裝許可權** 中所述，以 RTCUniversalServerAdmins 群組成員的身分或必要使用者權限的方式，登入安裝商務用 Skype Server 管理命令介面的電腦。

2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。

3. 使用 **get-cscallparkorbit** 來建立新的呼叫收取群組號碼範圍。 使用 **get-cscallparkorbit** 可修改現有的呼叫收取號碼範圍。

    在命令列中執行：

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    例如：

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    下列範例顯示如何將號碼範圍從通話駐留軌道變更為呼叫收取群組。

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > 若最初指定的類型不正確，而且群組範圍尚未使用中，請使用此 Cmdlet 變更指派給號碼範圍的類型。 如果您將號碼範圍從 Fea-callpark-app-no-version 變更為 GroupPickup，反之亦然，而且號碼範圍已在使用中，則通話駐留或群組通話收取會停止該號碼範圍的工作。 例如，如果您將號碼範圍從 Fea-callpark-app-no-version 變更為 GroupPick，則通話駐留應用程式無法再將此範圍的軌道式用於寄存通話。

## <a name="see-also"></a>另請參閱

[新 Get-cscallparkorbit](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Get-cscallparkorbit](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[刪除通話駐留軌道範圍](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)