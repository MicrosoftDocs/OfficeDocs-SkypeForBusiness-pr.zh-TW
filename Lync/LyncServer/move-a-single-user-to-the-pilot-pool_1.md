---
title: 將單一使用者移至 [試驗] 池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 086af622644f8d8285ef5f7be8e17f75ff436000
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>將單一使用者移至 [試驗] 池

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

您可以使用 Lync Server 2013 [控制台] 或 [Lync Server 2013 管理命令介面]，將使用者從您的 Office 通訊伺服器 2007 R2 池移至您的 Lync Server 2013 試驗區。 在下列範例中，在 [註冊機構池] 欄中， ** \<[office 通訊伺服器\> ** ] 是 office 通訊伺服器 2007 R2 池，且所有六個使用者都已連線到此池。 使用下列程式將使用者移至 Lync Server 2013 池（使用 Lync Server 2013 控制台和 Lync Server 管理命令介面）。

在 Lync server [控制台]![中搜尋 ocs]使用者(images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "在 Lync server [控制台] 中搜尋 ocs 使用者")

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>使用 Lync Server 2013 [控制台] 移動使用者

1.  使用 RTCUniversalServerAdmins 群組成員的帳戶或 CsAdministrator 或 CsUserAdministrator 系統管理角色的成員登入前端伺服器。

2.  開啟 [Lync Server 控制台]。

3.  按一下 [**使用者**]。

4.  從 [**使用者搜尋] 索引**標籤上，按一下 [**搜尋**] 按鈕。

5.  接著，按一下 [**新增篩選**]。

6.  建立 [ **Office 通訊伺服器] 使用者**等於 [ **True**] 的篩選器。

7.  按一下 [**尋找**]，搜尋舊版 Office 通訊伺服器 2007 R2 使用者。
    
    在 Lync server [控制台]![中搜尋 ocs]使用者(images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "在 Lync server [控制台] 中搜尋 ocs 使用者")  

8.  選取您要移至 Lync Server 2013 池的使用者。 在這個範例中，我們將移動 [使用者 Sara Davis]。

9.  在 [**動作**] 功能表上，選取 [**將選取的使用者移至資源庫**]。

10. 從下拉式清單中，選取 [Lync Server 2013] 池。

11. 按一下 [**動作**]，然後按一下 [**將選取的使用者移至資源庫**]。 按一下 [確定]****。
    
    ![在 [移動使用者] 對話方塊中設定目的地池](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "設定 [移動使用者] 對話方塊中的 [目標] 池")  

12. 確認使用者的 [**註冊機構池**] 欄現在包含 Lync Server 2013 池，這表示使用者已順利移動

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>使用 Lync Server 2013 管理命令介面來移動使用者

1.  開啟 Lync Server 管理命令介面。

2.  在命令列中，輸入下列內容：
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

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

