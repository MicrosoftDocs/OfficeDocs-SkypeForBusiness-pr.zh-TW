---
title: Lync Server 2013：建立或修改通話公園軌道的範圍
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
ms.openlocfilehash: bf215caacd0e380a14429bd2d34791048878fc96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-call-park-orbit-range-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改通話駐留軌道的範圍

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

使用下列其中一個程式來建立或修改通話寄存軌道的範圍。

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>使用 Lync Server [控制台] 來建立或修改停車通話的數位範圍

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**語音功能**]，然後按一下 [**通話駐留**]。

4.  在 [**通話駐留**] 頁面上，執行下列其中一項操作：
    
      - 若要建立新的軌道範圍，請按一下 [**新增**]。 在 [**名稱**] 中，輸入此數位範圍的識別名稱。
        
        <div>
        

        > [!NOTE]  
        > 在您將軌道範圍提交至資料庫之後，您就無法變更此名稱。

        
        </div>
    
      - 若要修改現有的軌道範圍，請在 [搜尋] 欄位中輸入所有或部分的軌道範圍名稱。 在 [軌道式] 的結果清單中，按一下您想要的軌道，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  在 [第一個**數位範圍**] 欄位中，輸入此通話公園軌道的延伸範圍起始編號，然後在第二個 [**數位範圍**] 欄位中，輸入範圍的結束數位。
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>該範圍的起始號碼必須小於或等於範圍的結束號碼。</P>
    > <LI>
    > <P>該範圍的起始號碼值的長度必須等於範圍的結束號碼值長度。</P>
    > <LI>
    > <P>軌道範圍必須是唯一的。 此範圍不得與其他任何範圍重疊。</P>
    > <LI>
    > <P>如果軌道範圍是以字元 * 或 # 開頭，則範圍必須大於100。</P>
    > <LI>
    > <P>有效值：必須符合正則運算式字串（[\*| #]？ [1-9] \d{0,7}） |（[1-9] \d{0,8}）。 這表示值必須是開頭為字元 * 或 # 或數字 1 至 9 的字串 (第一個字元不得為零)。 如果第一個字元是 * 或 #，則後續字元必須是數字 1 至 9 (不得為零)。 後續字元可以是從0到9的任何數位，最多可達七個其他字元（例如，"#6000"、"*92000"、"* 95551212" 和 "915551212"）。 如果第一個字元不是 * 或 #，則第一個字元必須是數位1到9（不能是零），然後再加上最多八個字元（例如，"915551212"，"41212"，"300"）。</P>
    > <LI>
    > <P>每個池子不應超過總計50000的 [軌道式]。 每個軌道範圍通常會包含100或更少的軌道式，但只要包含超過10000的軌道式，就能更大。 例如，與其指定起始號碼 7000000 與結束號碼 8000000，請考慮指定起始號碼 7000000 與結束號碼 7000100。</P></LI></UL>

    
    </div>

6.  在 [**目的地伺服器的 FQDN**] 中，按一下主持通話駐留應用程式之應用程式服務的完整功能變數名稱（FQDN）或服務識別碼。 在軌道範圍內由 start 編號和結束編號所指定範圍內的所有來電都會路由到這個伺服器或池子。

7.  按一下 [認可]****。

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>使用 Windows PowerShell 來建立或修改停用通話的數位範圍

1.  登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組的成員的電腦，或使用[Lync server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者許可權。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  使用 [**新-CsCallParkOrbit** ] 建立新的軌道編號範圍。 使用 [**設定] CsCallParkOrbit**來修改現有的軌道編號範圍。
    
    在命令列上執行：
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    例如：
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    下列範例顯示如何修改現有的軌道範圍中的數位，
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

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

