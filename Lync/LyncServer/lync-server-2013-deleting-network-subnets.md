---
title: Lync Server 2013：刪除網路子網
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting network subnets
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49733806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93806d3e9d5f0cb7f004a90d6f461b363aff65f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-subnets-in-lync-server-2013"></a>刪除 Lync Server 2013 中的網路子網

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

您可以使用下列程式來刪除子網。 您可以從 Lync Server [控制台] 建立、修改或刪除網路子網。 如需建立或修改網路子網的詳細資料，請參閱[在 Lync Server 2013 中建立或修改網路子網](lync-server-2013-create-or-modify-network-subnets.md)。

在部署呼叫許可控制（CAC）的大多數 Microsoft Lync Server 2013 部署中，通常會有大量的子網。 因此，通常最好是從 Lync Server 管理命令介面設定子網。 您可以從該處呼叫**CsNetworkSubnet** ，並與 Windows PowerShell Cmdlet **Import-CSV**搭配使用。 透過搭配使用這些 Cmdlet，您就可以從逗號分隔值（.csv）檔案朗讀子網設定，並同時建立多個子網。 如需如何從 .csv 檔案建立子網的範例，請參閱[新 CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。

<div>

## <a name="to-delete-a-network-subnet"></a>刪除網路子網

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**子網**]。

4.  在 [**子網**] 頁面上，按一下您要刪除的子網。
    
    <div>
    

    > [!NOTE]  
    > 您可以一次刪除一個以上的子網。 若要這樣做，請按住 CTRL 並選取多個子網，同時按住 CTRL 鍵。 或者，若要選取所有子網，請在 [<STRONG>編輯</STRONG>] 功能表上，按一下 [全<STRONG>選</STRONG>]。

    
    </div>

5.  在 [**編輯**] 功能表上，按一下 [**刪除**]。

6.  按一下 [確定]****。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中建立或修改網路子網](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

