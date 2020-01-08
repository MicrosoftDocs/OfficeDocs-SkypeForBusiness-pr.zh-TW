---
title: 將單一使用者移至 [試驗] 池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9ee58a49afaa9c1e57689b6a3a87fac1a6a4502
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>將單一使用者移至 [試驗] 池

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-26_

您可以使用 Lync Server 2013 [控制台] 或 [Lync Server 2013 管理命令介面]，將使用者從 Lync Server 2010 池中移至您的 Lync Server 2013 試驗區。 在下列範例中，在 [註冊機構池] 欄中， **pool01.contoso.net**是 [Lync Server 2010] 池，且所有六個使用者都已連線到此池。 使用下列程式將使用者移至 Lync Server 2013 池（使用 Lync Server 2013 控制台和 Lync Server 管理命令介面）。

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>使用 Lync Server 2013 [控制台] 移動使用者

**Lync Server 2013 [控制台] 中的使用者清單**

![Lync server [控制台]、[移動使用者] 對話方塊][(images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync server] 控制台、[移動使用者] 對話方塊")

1.  使用 RTCUniversalServerAdmins 群組成員的帳戶或 CsAdministrator 或 CsUserAdministrator 系統管理角色的成員登入前端伺服器。

2.  開啟 [ **Lync Server 控制台**]。

3.  按一下 [**使用者**]，按一下 [搜尋]，然後按一下 [**尋找**]。

4.  選取您要移至 Lync Server 2013 池的使用者。 在這個範例中，我們將移動 [使用者 Sara Davis]。

5.  在 [**動作**] 功能表上，選取 [**將選取的使用者移至資源庫**]。

6.  從下拉式清單中，選取 [Lync Server 2013] 池。

7.  按一下 [**動作**]，然後按一下 [**將選取的使用者移至資源庫**]。 按一下 [確定]****。
    
    [![移動使用者]、[目的地註冊機構池] 對話方塊][(images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "移動使用者]、[目的地註冊員池] 對話方塊")  

8.  確認使用者的 [**註冊機構池**] 欄現在包含 Lync Server 2013 池，這表示使用者已順利移動。

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>使用 Lync Server 2013 管理命令介面來移動使用者

1.  開啟 Lync Server 管理命令介面。

2.  在命令列中，輸入下列內容：
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  接著，在命令列中輸入下列內容：
    
        Get-CsUser -Identity "David Pelton"

4.  **RegistrarPool**身分識別現在會指向 Lync Server 2013 池。 此身分識別的狀態會確認使用者已順利移動。
    
    ![Move-csuser Cmdlet 的輸出與](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "含身分識別的 move-csuser Cmdlet")的身分識別篩選器輸出  
    
    <div>
    

    > [!NOTE]  
    > 如需<STRONG>move-csuser</STRONG> Cmdlet 的詳細資料，請執行： <STRONG>Get-help move-csuser-詳細</STRONG>資訊

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

