---
title: Lync Server 2013：查看使用者 PIN 碼資訊
description: Lync Server 2013：查看使用者 PIN 資訊。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View user PIN information
ms:assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688067(v=OCS.15)
ms:contentKeyID: 49733661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56f0808e645a2589841ff70d4923fa2de2c020ff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580059"
---
# <a name="view-user-pin-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看使用者 PIN 資訊

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

若要將電話撥入式會議加入為已驗證的使用者，使用 Active Directory 網域服務 (AD DS) 認證的 Lync Server 2013 使用者需要個人識別碼)  (PIN 碼。 您可以從 Lync Server 2013 控制台中查看使用者的 PIN 碼資訊。

<div>


> [!NOTE]  
> 您可以檢視諸如是否已設定 PIN 或上次變更 PIN 的時間之類的 PIN 狀態資訊，但無法藉由查看 PIN 狀態來查看目前的 PIN。 如果使用者已遺失 PIN 碼，您可以遵循在<A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">Lync Server 2013 中設定使用者的電話撥入式會議 PIN</A>中的程式來重設它。



</div>

<div>

## <a name="to-view-a-users-pin-in-lync-server-control-panel"></a>在 Lync Server 控制台中查看使用者的 PIN

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[使用者]**。

4.  使用下列其中一種方法，找到使用者：
    
      - 在 **[搜尋使用者]** 方塊中，輸入該使用者帳戶的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的全部或頭幾個字，然後按一下 **[尋找]**。
    
      - 如果有儲存的查詢，請按一下 **[開啟查詢]** 圖示、使用 **[開啟]** 對話方塊擷取查詢 (.usf 檔)，然後按一下 **[尋找]**。

5.  (選用) 指定其他搜尋條件，縮減結果：
    
    1.  按一下 **[新增篩選]**。
    
    2.  輸入使用者內容，您可以自行輸入或按一下下拉式清單的箭頭以選取內容。
    
    3.  在 **[等於]** 下拉式清單中，按一下運算子 (例如 **[等於]** 或 **[不等於]**)。
    
    4.  視您選取的使用者內容而定，透過直接輸入文字或按一下下拉式清單中的箭頭，輸入您要用來篩選搜尋結果的準則。
        
        <div>
        

        > [!TIP]  
        > 若要將更多搜尋子句加入至查詢，請按一下 <STRONG>[新增篩選]</STRONG>。

        
        </div>
    
    5.  按一下 [尋找]****。
    
    <div>
    

    > [!NOTE]  
    > 如果 PIN 已鎖定，您必須解除鎖定 PIN，才能設定 PIN。若要解除鎖定 PIN，請依序按一下使用者、[執行]<STRONG></STRONG> 和 [解除鎖定 PIN]<STRONG></STRONG>。

    
    </div>

6.  依序按一下搜尋結果中的使用者、[執行]**** 和 [檢視 PIN 狀態]****。

</div>

<div>

## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看使用者 PIN 碼資訊

您可以使用 Get-CsClientPinInfo Cmdlet 來檢視使用者 PIN 資訊。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-view-user-pin-information"></a>檢視使用者 PIN 資訊

  - 若要查看使用者的 PIN 資訊，請在 Lync Server 管理命令介面中輸入類似下列的命令，然後按 ENTER：
    
        Get-CsClientPinInfo -Identity "Ken Myer"
    
    如此將傳回類似如下的資訊：
    
        Identity          : sip:kenmyer@litwareinc.com
        IsPinSet          : False
        IsLockedOut       : False
        LastPinChangeTime : 9/25/2012 1:35:03 PM
        PinExpirationTime :

</div>

如需詳細資訊，請參閱 [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/Get-CsConferenceDisclaimer) Cmdlet 的 [說明] 主題。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定使用者的電話撥入式會議 PIN](lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md)  
[鎖定或解除鎖定 Lync Server 2013 中的使用者 PIN](lync-server-2013-lock-or-unlock-a-user-pin.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

