---
title: Lync Server 2013：建立或修改通話駐留軌道範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Call Park orbit range
ms:assetid: 549ec118-eee5-4333-9416-80929ec057e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398361(v=OCS.15)
ms:contentKeyID: 48184142
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fe04aea0cc0d6ab38b0bfa9597b420d608c7597
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-call-park-orbit-range-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改通話駐留軌道範圍

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

使用下列其中一個程序來建立或修改通話駐留軌道範圍。

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>使用 Lync Server 控制台建立或修改駐留通話的號碼範圍

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱[在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，依序按一下 **[語音功能]**、**[通話駐留]**。

4.  在 **[通話駐留]** 頁面上，執行下列其中一項動作：
    
      - 若要建立新的軌道範圍，可按一下 **[新增]**。在 **[名稱]** 中，輸入此號碼範圍的識別名稱。
        
        <div>
        

        > [!NOTE]  
        > 當您將軌道範圍認可至資料庫之後，就無法變更此名稱。

        
        </div>
    
      - 若要修改現有的軌道範圍，可在搜尋欄位中輸入軌道範圍的所有或部分名稱。在軌道的結果清單中，按一下您想要的軌道，接著依序按一下 **[編輯]** 及 **[顯示詳細資料]**。

5.  在第一個 **[號碼範圍]** 欄位中，輸入此項通話駐留軌道分機號碼範圍的開頭號碼，並在第二個 **[號碼範圍]** 欄位中，輸入該範圍的結束號碼。
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>該範圍的起始號碼必須小於或等於範圍的結束號碼。</P>
    > <LI>
    > <P>該範圍的起始號碼值的長度必須等於範圍的結束號碼值長度。</P>
    > <LI>
    > <P>軌道範圍必須是唯一的。此範圍不得與其他任何範圍重疊。</P>
    > <LI>
    > <P>如果軌道範圍開頭為 * 或 #，則範圍必須大於 100。</P>
    > <LI>
    > <P>有效的值：必須符合正則運算式字串 ( [ \* | #]？ [1-9] \d {0,7}) | ( [1-9] \d {0,8}) 。 這表示值必須是開頭為字元 * 或 # 或數字 1 至 9 的字串 (第一個字元不得為零)。 如果第一個字元是 * 或 #，則後續字元必須是數字 1 至 9 (不得為零)。 後續字元可以是0到9的任何數位，最多可以有七個其他字元 (例如，"#6000"、"*92000"、"* 95551212" 和 "915551212" ) 。 如果第一個字元不是 * 或 #，則第一個字元必須是數字 1 至 9 (不得為零)，後面最多接著八個字元，每一個字元都是數字 0 至 9 (例如，"915551212"、"41212"、"300")。</P>
    > <LI>
    > <P>每個集區的軌道總數不得超過 50,000 個。每個軌道範圍通常會涵蓋 100 個以下的軌道，但只要總數不超過 10,000 個軌道，可以大一些。例如，與其指定開頭號碼 7000000 與結束號碼 8000000，請考慮指定開始號碼 7000000 與結束號碼 7000100。</P></LI></UL>

    
    </div>

6.  在 **[目的地伺服器的 FQDN]** 中，按一下裝載通話保留應用程式的應用程式服務之完整網域名稱 (FQDN) 或服務 ID。保留給軌道範圍中由開始號碼與結束號碼所指定之範圍內的號碼的所有通話，將會轉接至此伺服器或集區。

7.  按一下 **[認可]**。

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>使用 Windows PowerShell 建立或修改駐留通話的號碼範圍

1.  以[Lync server 2013 的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述，登入安裝了 Lync Server 管理命令介面的電腦，以作為 RTCUniversalServerAdmins 群組的成員或必要的使用者權限。

2.  啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  使用 **New-CsCallParkOrbit** 來建立新的軌道號碼範圍。 使用 **Set-CsCallParkOrbit** 來修改現有的軌道號碼範圍。
    
    在命令列中執行：
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    例如：
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    下列範例示範如何修改現有軌道範圍中的號碼，
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

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

