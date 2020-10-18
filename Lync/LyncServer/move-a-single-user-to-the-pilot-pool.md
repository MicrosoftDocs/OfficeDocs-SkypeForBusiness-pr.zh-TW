---
title: 將單一使用者移至試驗集區
description: 將單一使用者移至試驗集區。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5f7396ed2d92c7015f01ff6cd6e90fd3998219d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574729"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>將單一使用者移至試驗集區

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-26_

您可以使用 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面，將您的 Lync Server 2010 集區中的使用者移至 Lync Server 2013 試驗集區。 在下列範例中，在 [報名者集區] 欄中， **pool01.contoso.net** 是 Lync Server 2010 集區，而這六個使用者都連接至此集區。 使用下列程式，使用 Lync Server 2013 控制台和 Lync Server 管理命令介面，將使用者移至您的 Lync Server 2013 集區。

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>使用 Lync Server 2013 控制台移動使用者

**Lync Server 2013 控制台中的使用者清單**

![Lync Server 控制台，移動使用者對話方塊](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server 控制台，移動使用者對話方塊")

1.  使用 RTCUniversalServerAdmins 群組的成員帳戶、CsAdministrator 成員帳戶或 CsUserAdministrator 系統管理角色的成員帳戶，登入前端伺服器。

2.  開啟 [ **Lync Server 控制台**]。

3.  按一下 [ **使用者**]，按一下 [搜尋]，然後按一下 [ **尋找**]。

4.  選取您要移至 Lync Server 2013 集區的使用者。 在這個範例中，將移動使用者 Sara Davis。

5.  在 [執行]**** 功能表上，選取 [將選取的使用者移至集區]****。

6.  從下拉式清單中，選取 [Lync Server 2013 集區]。

7.  按一下 [動作]****，然後按一下 [將選取的使用者移至集區]****。 按一下 [確定]****。
    
    ![移動使用者、目的地註冊集區] 對話方塊](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "移動使用者、目的地註冊集區] 對話方塊")  

8.  確認使用者的 [ **報名者集** 區] 欄現在包含 Lync Server 2013 集區，這表示使用者已順利移動。

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>使用 Lync Server 2013 管理命令介面移動使用者

1.  開啟 Lync Server 管理命令介面。

2.  在命令列輸入下列命令：
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  接著，在命令列輸入下列命令：
    
        Get-CsUser -Identity "David Pelton"

4.  **RegistrarPool**身分識別現在會指向 Lync Server 2013 集區。 這個身分識別的出現表示已成功移動使用者。
    
    ![具有身分識別篩選的 Get-CsUser Cmdlet 的輸出](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "具有身分識別篩選的 Get-CsUser Cmdlet 的輸出")  
    
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

