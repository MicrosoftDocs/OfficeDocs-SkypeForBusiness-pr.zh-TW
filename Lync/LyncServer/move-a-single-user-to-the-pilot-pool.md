---
title: 將單一使用者移至試驗集區
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 187b0b3055710f89b8c16d8167c1b6692d5eaac2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>將單一使用者移至試驗集區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-26_

您可以將使用者從 Lync Server 2010 集區移至 Lync Server 2013 試驗集區使用 Lync Server 2013 Control Panel] 或 [Lync Server 2013 管理命令介面。 在範例中，以下登錄器集區] 欄中， **pool01.contoso.net**是 Lync Server 2010 集區，且所有第六個這些使用者會連線到此集區。 若要將使用者移至 Lync Server 2013 集區使用 Lync Server 2013 控制台] 及 [Lync Server 管理命令介面中使用下列程序。

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>若要使用 Lync Server 2013 控制台移動使用者

**Lync Server 2013 控制台] 中的使用者清單**

![Lync Server Control Panel，移動使用者] 對話方塊](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server Control Panel，移動使用者] 對話方塊")

1.  使用 RTCUniversalServerAdmins 群組的成員帳戶、CsAdministrator 成員帳戶或 CsUserAdministrator 系統管理角色的成員帳戶，登入前端伺服器。

2.  開啟**Lync Server 控制台**。

3.  按一下 [**使用者**]，按一下 [搜尋]，然後按一下 [**尋找**。

4.  選取您想要將移至 Lync Server 2013 集區的使用者。 在這個範例中，將移動使用者 Sara Davis。

5.  在 [執行]**** 功能表上，選取 [將選取的使用者移至集區]****。

6.  從下拉式清單中，選取 [Lync Server 2013 集區。

7.  按一下 [動作]****，然後按一下 [將選取的使用者移至集區]****。 按一下 [確定]****。
    
    ![移動使用者，目的地登錄器集區] 對話方塊](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "移動使用者，目的地登錄器集區] 對話方塊")  

8.  請確認使用者的 [**登錄器集區**] 欄現在包含 Lync Server 2013 集區，即表示使用者已順利移動。

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>若要使用 Lync Server 2013 管理命令介面時，移動使用者

1.  開啟 Lync Server 管理命令介面。

2.  在命令列輸入下列命令：
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  接著，在命令列輸入下列命令：
    
        Get-CsUser -Identity "David Pelton"

4.  **RegistrarPool** identity 現在指向 Lync Server 2013 集區。 這個身分識別的出現表示已成功移動使用者。
    
    ![從 Identity 篩選與 Get-csuser cmdlet 的輸出](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "從 Identity 篩選與 Get-csuser cmdlet 的輸出")  
    
    <div>
    

    > [!NOTE]  
    > 如需關於 <STRONG>Get-CsUser</STRONG> Cmdlet 的詳細資訊，請執行：<STRONG>Get-Help Get-CsUser –Detailed</STRONG>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

