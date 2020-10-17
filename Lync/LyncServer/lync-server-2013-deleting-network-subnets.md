---
title: Lync Server 2013：刪除網路子網
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network subnets
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49733806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 013de3ae58424473aa42aee767982fd84a9d651e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504270"
---
# <a name="deleting-network-subnets-in-lync-server-2013"></a>在 Lync Server 2013 中刪除網路子網

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

您可以使用下列程式來刪除子網。 在 [Lync Server 控制台] 中，您可以建立、修改或刪除網路子網。 如需建立或修改網路子網的詳細資訊，請參閱 [在 Lync Server 2013 中建立或修改網路子網](lync-server-2013-create-or-modify-network-subnets.md)。

在大多數安裝通話許可控制 (CAC) 的 Microsoft Lync Server 2013 中，通常會有大量子網。 因此，通常最好是從 Lync Server 管理命令介面來設定子網。 從那裡，您可以將 **New-CsNetworkSubnet** 與 Windows PowerShell Cmdlet 匯 **入-CSV**搭配呼叫。 透過這些 Cmdlet 一起使用，您可以從逗點分隔的值讀取子網設定 ( .csv) 檔案，並同時建立多個子網。 如需如何從 .csv 檔案建立子網的範例，請參閱 [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。

<div>

## <a name="to-delete-a-network-subnet"></a>若要刪除網路子網

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，依序按一下 **[網路設定]** 和 **[子網路]**。

4.  在 [ **子網** ] 頁面上，按一下您要刪除的子網。
    
    <div>
    

    > [!NOTE]  
    > 您可以一次刪除一個以上的子網。 若要執行此動作，請按住 CTRL 鍵並選取多個子網，然後按住 CTRL 鍵。 或者，若要選取所有子網，請按一下 [<STRONG>編輯</STRONG>] 功能表上的 [全<STRONG>選</STRONG>]。

    
    </div>

5.  在 **[編輯]** 功能表中，按一下 **[刪除]**。

6.  按一下 [確定]****。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中建立或修改網路子網](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

