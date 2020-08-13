---
title: Lync Server 2013：鎖定或解除鎖定使用者 PIN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lock or unlock a user PIN
ms:assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688028(v=OCS.15)
ms:contentKeyID: 49733618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 698bbb2138978cea9ca5b2aa75b5370ea7e11c14
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lock-or-unlock-a-user-pin-in-lync-server-2013"></a>鎖定或解除鎖定 Lync Server 2013 中的使用者 PIN

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

您可以從 Lync Server 2013 控制台的 [**使用者**] 區段鎖定或解除鎖定使用者的 PIN 碼。

<div>

## <a name="to-lock-a-users-pin-in-lync-server-control-panel"></a>在 Lync Server 控制台中鎖定使用者的 PIN

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

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
    
    5.  按一下 **[尋找]**。
    
    6.  按一下使用者、**[動作]**，然後按一下 **[鎖定 PIN]**。

</div>

<div>

## <a name="to-unlock-a-users-pin-in-lync-server-control-panel"></a>在 Lync Server 控制台中解除鎖定使用者的 PIN

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

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
    
    5.  按一下 **[尋找]**。
    
    6.  按一下使用者、**[動作]**，然後按一下 **[解除鎖定 PIN]**。

</div>

<div>

## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 鎖定和解除鎖定使用者 Pin

您可以使用 Windows PowerShell 和 Lock-CsClientPin 及 Unlock-CsClientPin Cmdlet 來鎖定和解除鎖定使用者 Pin。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行這些 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-lock-a-user-pin"></a>鎖定使用者 PIN

  - 如要鎖定使用者的 PIN，請使用 Lock-CsClientPin Cmdlet。例如：
    
        Lock-CsClientPin -Identity "Ken Myer"

</div>

<div>

## <a name="to-unlock-a-user-pin"></a>解除鎖定使用者 PIN

  - 如要解除鎖定使用者的 PIN，請使用 Unlock-CsClientPin Cmdlet。例如：
    
        Unlock-CsClientPin -Identity "Ken Myer"

</div>

如需詳細資訊，請參閱[Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin)和[Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) Cmdlet 的 [說明] 主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

