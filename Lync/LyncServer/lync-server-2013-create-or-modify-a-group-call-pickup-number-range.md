---
title: Lync Server 2013：建立或修改群組呼叫收取號碼範圍
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
ms.openlocfilehash: bdf2ee113682ccee44d2329de68dfa87ea5824be
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改群組呼叫收取號碼範圍

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-30_

使用下列程式可建立或修改通話駐留軌道表格中的呼叫收取群組號碼範圍。

<div>


> [!NOTE]  
> 您必須使用 Lync Server 管理命令介面來建立、修改、移除及查看通話駐留軌道表格中的群組呼叫收取號碼範圍。 在 Lync Server 控制台中無法使用群組呼叫收取號碼範圍。



</div>

<div>


> [!IMPORTANT]  
> 必須為呼叫收取群組號碼範圍指派 GroupPickup 類型。 只有當使用者所指派的群組號碼是類型 GroupPickup 時，才會為使用者啟用群組呼叫收取。



</div>

呼叫收取群組號碼範圍必須符合下列規則：

  - 該範圍的起始號碼必須小於或等於範圍的結束號碼。

  - 該範圍的起始號碼值的長度必須等於範圍的結束號碼值長度。

  - 號碼範圍必須是唯一的。 此範圍不得與其他任何範圍重疊。

  - 如果號碼範圍開頭為字元 \* \# ，或範圍必須大於100。

  - 有效的值：必須符合正則運算式字串 (\[ \\ \* | \# \] ？ \[1-9 \] \\ d {0,7}) | (\[ 1-9 \] \\ d {0,8}) 。 這表示值必須是以字元 \* 或 \# 數位1到9為開頭的字串 (第一個字元不能是零) 。 如果第一個字元是 \* 或 \# ，下列字元必須是1到9的數位， (不能是零) 。 後續字元可以是0到9的任何數位，最多可以有七個其他字元 (例如，" \# 6000"、" \* 92000"、" \* 95551212" 及 "915551212" ) 。 如果第一個字元不是 \* 或 \# ，第一個字元必須是數位1到 9 (它不能是零) ，然後是八個字元，每個數位都是0到 9 (例如，"915551212"，"41212"，"300" ) 。

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a>若要建立或修改呼叫收取群組範圍

1.  以[Lync server 2013 的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述，登入安裝了 Lync Server 管理命令介面的電腦，以作為 RTCUniversalServerAdmins 群組的成員或必要的使用者權限。

2.  啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  使用**get-cscallparkorbit**來建立新的呼叫收取群組號碼範圍。 使用**get-cscallparkorbit**可修改現有的呼叫收取號碼範圍。
    
    在命令列中執行：
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    例如：
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    下列範例顯示如何將號碼範圍從通話駐留軌道變更為呼叫收取群組。
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > 若最初指定的類型不正確，而且群組範圍尚未使用中，請使用此 Cmdlet 變更指派給號碼範圍的類型。 如果您將號碼範圍從 Fea-callpark-app-no-version 變更為 GroupPickup，反之亦然，而且號碼範圍已在使用中，則通話駐留或群組通話收取會停止該號碼範圍的工作。 例如，如果您將號碼範圍從 Fea-callpark-app-no-version 變更為 GroupPick，則通話駐留應用程式無法再將此範圍的軌道式用於寄存通話。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中刪除通話駐留軌道範圍](lync-server-2013-delete-a-call-park-orbit-range.md)  


[新 Get-cscallparkorbit](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[Get-cscallparkorbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

