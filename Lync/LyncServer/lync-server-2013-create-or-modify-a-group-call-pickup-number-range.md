---
title: Lync Server 2013：建立或修改群組呼叫挑選編號範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5a644cb6008976894c88de570aa9cb6530e10c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改群組呼叫挑選號碼範圍

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-30_

使用下列程式來建立或修改 [通話駐留軌道] 表格中的 [通話挑選] 群組編號範圍。

<div>


> [!NOTE]  
> 您必須使用 Lync Server 管理命令介面來建立、修改、移除及查看 [通話寄存軌道] 表格中的 [群組呼叫挑選號碼] 範圍。 在 Lync Server [控制台] 中無法使用 [群組呼叫挑選號碼] 範圍。



</div>

<div>


> [!IMPORTANT]  
> 必須為呼叫挑選群組編號範圍指派 GroupPickup 類型。 只有在指派給使用者的群組號碼為 GroupPickup 時，才會啟用群組呼叫挑選。



</div>

呼叫挑選群組編號範圍必須符合下列規則：

  - 該範圍的起始號碼必須小於或等於範圍的結束號碼。

  - 該範圍的起始號碼值的長度必須等於範圍的結束號碼值長度。

  - 號碼範圍必須是唯一的。此範圍不得與其他任何範圍重疊。

  - 如果數位範圍是以字元\*開頭，或\#範圍必須大於100。

  - 有效值：必須符合正則運算式字串（\[\\\*|\#\]？\[1-9\]\\d{0,7}） |（\[1-9\]\\d{0,8}）。 這表示值必須是以字元\*或\#數位1到9（第一個字元不能是零）開頭的字串。 如果第一個字元是\*或\#，則下列字元必須是1到9的數位（不能是零）。 後續字元可以是從0到9的任何數位，最多可達七個其他\#字元（例如，\*"6000"，\*"92000"，"95551212"，"915551212"）。 如果第一個字元不\*是或\#，則第一個字元必須是數位1到9（不能是零），然後再加上最多八個字元（例如，"915551212"，"41212"，"300"）。

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a>建立或修改通話挑選群組範圍

1.  登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組的成員的電腦，或使用[Lync server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者許可權。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  使用 [**新-CsCallParkOrbit** ] 建立呼叫挑選群組編號的新範圍。 使用 [**設定] CsCallParkOrbit**來修改現有的電話挑選號碼範圍。
    
    在命令列上執行：
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    例如：
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    下列範例示範如何將通話駐留軌道式的數位範圍變更為呼叫挑選群組。
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您最初指定的類型不正確，且尚未使用群組範圍，請使用這個 Cmdlet 來變更指派給數位範圍的類型。 如果您將數位範圍從 CallPark 變更為 GroupPickup 或反之，而數位範圍已在使用中，則通話駐留或群組通話拾取將會停止處理該數位範圍。 例如，如果您將數位範圍從 CallPark 變更為 GroupPick，則通話駐留應用程式將無法再使用該轉到寄存通話的範圍。

    
    </div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中刪除通話駐留軌道範圍](lync-server-2013-delete-a-call-park-orbit-range.md)  


[新-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

