---
title: 將單一使用者移至試驗集區
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 200e929cb7dff4006ffe776504220618e5e7b570
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>將單一使用者移至試驗集區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

您可以使用 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面，將使用者從 Office 通訊伺服器 2007 R2 集區移至 Lync Server 2013 試驗集區。 在下列範例中，[報名者集區] 欄 **\<Office Communications Server\>** 是 Office 通訊伺服器 2007 R2 集區，而這六個使用者都連接至此集區。 使用下列程式，使用 Lync Server 2013 控制台和 Lync Server 管理命令介面，將使用者移至您的 Lync Server 2013 集區。

![在 Lync Server 控制台中搜尋 OCS 使用者](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "在 Lync Server 控制台中搜尋 OCS 使用者")

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>使用 Lync Server 2013 控制台移動使用者

1.  使用 RTCUniversalServerAdmins 群組的成員帳戶、CsAdministrator 成員帳戶或 CsUserAdministrator 系統管理角色的成員帳戶，登入前端伺服器。

2.  開啟 [Lync Server 控制台]。

3.  按一下 [使用者]****。

4.  從 [使用者搜尋]**** 索引標籤，按一下 [搜尋]**** 按鈕。

5.  接著，按一下 [新增篩選]****。

6.  建立篩選，其中的 [Office Communications Server 使用者]**** 等於 [True]****。

7.  按一下 [**尋找**] 搜尋舊版 Office 通訊伺服器 2007 R2 使用者。
    
    ![在 Lync Server 控制台中搜尋 OCS 使用者](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "在 Lync Server 控制台中搜尋 OCS 使用者")  

8.  選取您要移至 Lync Server 2013 集區的使用者。 在這個範例中，將移動使用者 Sara Davis。

9.  在 [執行]**** 功能表上，選取 [將選取的使用者移至集區]****。

10. 從下拉式清單中，選取 [Lync Server 2013 集區]。

11. 按一下 [動作]****，然後按一下 [將選取的使用者移至集區]****。 按一下 [確定]****。
    
    ![在 [移動使用者] 對話方塊中設定目的地集區](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "在 [移動使用者] 對話方塊中設定目的地集區")  

12. 確認使用者的 [**報名者集**區] 欄現在包含 Lync Server 2013 集區，這表示使用者已成功移動

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>使用 Lync Server 2013 管理命令介面移動使用者

1.  開啟 Lync Server 管理命令介面。

2.  在命令列輸入下列命令：
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

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

